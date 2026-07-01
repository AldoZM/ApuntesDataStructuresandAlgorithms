# Coloreado automático de diagramas ASCII — Diseño

Fecha: 2026-07-01
Proyecto: Apuntes DSA (LaTeX, LuaLaTeX)

## Objetivo

Los 55 diagramas ASCII/trace de los apuntes son todo blanco. Darles color por
clase de carácter para hacerlos más atractivos y legibles, sin trabajo manual
por diagrama.

## Estado actual

- Diagramas: entorno `dsadiagrama` (tcolorbox verde, marco lime, título `🎨 Diagrama`,
  `colupper=white`) que envuelve un `\begin{verbatim}...\end{verbatim}` con el ASCII.
- Contenido: box-drawing (`─│┌┐└┘├┤┬┴┼ ═║`), slashes `/ \`, flechas (`→ ← ↑ ↓`),
  nodos `[n]`, texto.
- 55 archivos en `chapters/` contienen `dsadiagrama`.
- Motor: LuaLaTeX (fontspec + HarfBuzz). Fuente mono con glyphs box-drawing ya
  arreglada en commit `f97f856`.

## Enfoque

Coloreado automático por clase de carácter, definido una vez en el preámbulo,
aplicado a los 55 diagramas sin marcado por archivo.

1. **Estilo `diagrama`** (`\lstdefinestyle`): `basicstyle` ttfamily small blanco,
   con reglas `literate` que mapean cada clase de carácter a su color. Estilo
   separado del de código (`cpp`); no se pisan.
2. **Entorno `dsadiagrama`**: pasar de "tcolorbox + verbatim anidado" a un
   `\newtcblisting` (librería `listings` de tcolorbox) que combina la caja verde
   + título `🎨 Diagrama` con el listing de estilo `diagrama`. El ASCII vive
   directo en el entorno; se colorea solo.

## Paleta

Sobre el fondo verde oscuro actual (`verdeoscu!25!black`). Caja y título se conservan.

| Elemento           | Caracteres                                  | Color            |
|--------------------|---------------------------------------------|------------------|
| Líneas / esqueleto | `─ │ ┌ ┐ └ ┘ ├ ┤ ┬ ┴ ┼ ═ ║ ╔ ╗ ╚ ╝ ╠ ╣ / \` | Gris tenue (nuevo color `diagLine` ~RGB 140,140,140) |
| Flechas            | `→ ← ↑ ↓ ↔ ⇒`                                | Amarillo (`n-yellow`) |
| Nodos              | `[ ]`                                        | Lime (`n-lime`)  |
| Texto y dígitos    | resto                                        | Blanco           |

Objetivo visual: el esqueleto recede (gris), los datos resaltan (nodos lime,
flechas amarillas).

## Migración

Conversión mecánica de los 55 bloques: quitar el `verbatim` interno, dejando el
ASCII directo dentro de `dsadiagrama` (ahora tcblisting). Script perl con
verificación de conteo antes/después (55 = 55) para no romper ningún bloque.

Patrón esperado uniforme:
```
\begin{dsadiagrama}
\begin{verbatim}
  ...ascii...
\end{verbatim}
\end{dsadiagrama}
```
Verificar que todos los diagramas siguen este patrón antes de la conversión
automática; los que no, se ajustan a mano.

## Alcance excluido (YAGNI)

- No colorear pesos de aristas ni `O(n)` (riesgo de teñir paréntesis en prosa).
- No resaltado semántico por-nodo (nodo actual rojo, visitados verde). Se puede
  agregar después si al ver el resultado se quiere más.

## Verificación

- Recompilar el libro con `latexmk -lualatex`. EXIT=0, PDF producido.
- Riesgo: listings + glyphs box-drawing bajo LuaLaTeX. El `literate` emite cada
  glyph explícito con la fuente mono; deberían renderizar. Confirmar visualmente
  en 3-4 diagramas: BFS/DFS (`02_bfs_dfs`), un árbol, una tabla hash.
- Comparar conteo de páginas (referencia previa: 216pp).
