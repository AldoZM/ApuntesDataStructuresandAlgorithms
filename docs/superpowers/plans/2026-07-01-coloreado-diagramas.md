# Coloreado automático de diagramas ASCII — Plan de Implementación

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Colorear automáticamente los 55 diagramas ASCII de los apuntes DSA por clase de carácter (líneas gris tenue, flechas amarillo, nodos lime), definido una vez en el preámbulo.

**Architecture:** Un estilo de listings `diagrama` con reglas `literate` colorea cada clase de carácter. El entorno `dsadiagrama` pasa de tcolorbox+verbatim anidado a `\newtcblisting` (caja + listing combinados), de modo que el ASCII vive directo en el entorno y se colorea solo, sin marcado por diagrama.

**Tech Stack:** LuaLaTeX, tcolorbox (librería `listings` ya cargada), listings, fontspec (fuente mono Consolas), latexmk.

## Global Constraints

- Motor de compilación: `latexmk -lualatex -interaction=nonstopmode -halt-on-error ApuntesDSA.tex`. Éxito = `EXIT=0` + `Output written on ApuntesDSA.pdf`.
- Commits SIN firma de IA (nada de Co-Authored-By ni menciones de IA). Mensajes en español, palabras completas, sin jergas.
- Fuente mono: Consolas (`\setmonofont{Consolas}[Scale=0.92]`). Ya renderiza los glyphs box-drawing en el PDF actual (216pp).
- Colores existentes reutilizados: `n-lime` (0,255,0), `n-yellow` (255,255,0), `verdeoscu` (6,95,70). Preámbulo: `preamble_dsa.tex`.
- Los 55 bloques `dsadiagrama` siguen el patrón uniforme verificado:
  ```
  \begin{dsadiagrama}
  \begin{verbatim}
    ...ascii...
  \end{verbatim}
  \end{dsadiagrama}
  ```

---

### Task 1: Color `diagLine` + estilo de listings `diagrama` (probado en scratch aislado)

Define el color gris y el estilo `diagrama` con todas las reglas `literate`, y lo prueba en un archivo scratch de 1 página ANTES de tocar el entorno real o los 55 archivos. De-riesga las reglas literate, alineación y el glyph backslash de forma barata.

**Files:**
- Modify: `preamble_dsa.tex` (zona de `\definecolor`, ~línea 74; y zona de `\lstdefinestyle`, después del estilo `cpp` ~línea 146)
- Create (temporal, se borra en Task 2): `scratch_diag.tex`

**Interfaces:**
- Produces: color `diagLine`; `\lstdefinestyle{diagrama}` usable vía `[style=diagrama]` en cualquier `lstlisting`.

- [ ] **Step 1: Añadir color `diagLine` al preámbulo**

En `preamble_dsa.tex`, después de la línea `\definecolor{grisclaro}{RGB}{200, 200, 200}` (~línea 74), añadir:

```latex
\definecolor{diagLine}{RGB}{140, 140, 140}   % gris tenue: esqueleto de diagramas
```

- [ ] **Step 2: Definir el estilo `diagrama`**

En `preamble_dsa.tex`, después de `\lstset{style=cpp}` (~línea 146), añadir el bloque completo:

```latex
% --- Estilo para diagramas ASCII (coloreado por clase de caracter) ---
\lstdefinestyle{diagrama}{
  basicstyle=\ttfamily\small\color{white},
  columns=fullflexible,
  keepspaces=true,
  breaklines=false,
  literate=
    % lineas / esqueleto (gris tenue) -- unicode box-drawing
    {─}{{\color{diagLine}─}}1 {│}{{\color{diagLine}│}}1
    {┌}{{\color{diagLine}┌}}1 {┐}{{\color{diagLine}┐}}1
    {└}{{\color{diagLine}└}}1 {┘}{{\color{diagLine}┘}}1
    {├}{{\color{diagLine}├}}1 {┤}{{\color{diagLine}┤}}1
    {┬}{{\color{diagLine}┬}}1 {┴}{{\color{diagLine}┴}}1 {┼}{{\color{diagLine}┼}}1
    {═}{{\color{diagLine}═}}1 {║}{{\color{diagLine}║}}1
    {╔}{{\color{diagLine}╔}}1 {╗}{{\color{diagLine}╗}}1
    {╚}{{\color{diagLine}╚}}1 {╝}{{\color{diagLine}╝}}1
    {╠}{{\color{diagLine}╠}}1 {╣}{{\color{diagLine}╣}}1
    {╦}{{\color{diagLine}╦}}1 {╩}{{\color{diagLine}╩}}1 {╬}{{\color{diagLine}╬}}1
    {╭}{{\color{diagLine}╭}}1 {╮}{{\color{diagLine}╮}}1
    {╰}{{\color{diagLine}╰}}1 {╯}{{\color{diagLine}╯}}1
    % lineas / esqueleto -- ASCII
    {|}{{\color{diagLine}|}}1 {-}{{\color{diagLine}-}}1
    {+}{{\color{diagLine}+}}1 {/}{{\color{diagLine}/}}1
    {\\}{{\color{diagLine}\char`\\}}1
    % flechas (amarillo)
    {→}{{\color{n-yellow}→}}1 {←}{{\color{n-yellow}←}}1
    {↑}{{\color{n-yellow}↑}}1 {↓}{{\color{n-yellow}↓}}1
    {↔}{{\color{n-yellow}↔}}1 {⇒}{{\color{n-yellow}⇒}}1 {⇐}{{\color{n-yellow}⇐}}1
    {▲}{{\color{n-yellow}▲}}1 {▼}{{\color{n-yellow}▼}}1
    {►}{{\color{n-yellow}►}}1 {◄}{{\color{n-yellow}◄}}1
    {<}{{\color{n-yellow}<}}1 {>}{{\color{n-yellow}>}}1
    % nodos (lime)
    {[}{{\color{n-lime}[}}1 {]}{{\color{n-lime}]}}1,
}
```

- [ ] **Step 3: Crear archivo scratch de prueba**

Crear `scratch_diag.tex` en la raíz del proyecto:

```latex
\documentclass[12pt]{article}
\input{preamble_dsa}
\begin{document}
\begin{lstlisting}[style=diagrama]
Grafo:
    [1]
   /   \
 [2]───[3]
  |     |
 [4]───[5]

BFS desde 1: 1 → 2,3 → 4,5
Tabla:
  +-------+-------+
  | clave | valor |
  +-------+-------+
BFS ← DFS ↔ nivel
\end{lstlisting}
\end{document}
```

- [ ] **Step 4: Compilar el scratch y verificar**

Run: `cd "D:/Codigo Abierto/ApuntesData Structures and Alg" && latexmk -lualatex -interaction=nonstopmode -halt-on-error scratch_diag.tex 2>&1 | tail -5`
Expected: `Output written on scratch_diag.pdf` (1 page), sin `Fatal error`.

Verificar en el log que NO haya errores por el backslash: `grep -iE "runaway|Fatal|! LaTeX|! Package|Undefined" scratch_diag.log | grep -v "Missing character"`
Expected: sin salida.

Abrir `scratch_diag.pdf` y confirmar visualmente:
- Líneas `─ │ + - / \ |` en gris tenue.
- Flechas `→ ← ↔` en amarillo.
- Nodos `[1] [2]...` con corchetes lime.
- Números y texto en blanco, alineación de la tabla y el grafo intacta.

Si el backslash (`\`) da error o matchea doble-backslash: quitar la línea `{\\}{{\color{diagLine}\char`\\}}1` del estilo (el `\` queda blanco; limitación menor documentada), recompilar y continuar.

- [ ] **Step 5: Commit (color + estilo)**

```bash
cd "D:/Codigo Abierto/ApuntesData Structures and Alg"
git add preamble_dsa.tex
git commit -m "Anadir color diagLine y estilo listings diagrama para coloreado de diagramas"
```

(El scratch NO se commitea; se borra en Task 2.)

---

### Task 2: Convertir entorno `dsadiagrama` a tcblisting + migrar los 55 diagramas

Cambia el entorno a `\newtcblisting` y elimina el `verbatim` interno de los 55 archivos. Estos dos cambios están acoplados (el nuevo entorno rompe los archivos viejos y viceversa), por eso van juntos en una tarea atómica. Compila el libro completo y verifica.

**Files:**
- Modify: `preamble_dsa.tex` (entorno `dsadiagrama`, ~líneas 175-183)
- Modify: los 55 `chapters/*.tex` que contienen `dsadiagrama` (quitar `\begin{verbatim}`/`\end{verbatim}` internos)
- Delete: `scratch_diag.tex` y sus artefactos

**Interfaces:**
- Consumes: `\lstdefinestyle{diagrama}` y color `diagLine` de Task 1.

- [ ] **Step 1: Convertir el entorno `dsadiagrama` a tcblisting**

En `preamble_dsa.tex`, reemplazar el bloque actual (líneas ~175-183):

```latex
\newtcolorbox{dsadiagrama}{
  colback=verdeoscu!25!black,
  colframe=n-lime,
  colupper=white,
  fonttitle=\bfseries\large,
  title={\emj{🎨}~Diagrama},
  breakable,
  before upper={\parskip=4pt}
}
```

por:

```latex
\newtcblisting{dsadiagrama}{
  colback=verdeoscu!25!black,
  colframe=n-lime,
  fonttitle=\bfseries\large,
  title={\emj{🎨}~Diagrama},
  breakable,
  listing only,
  listing options={style=diagrama},
}
```

- [ ] **Step 2: Verificar conteo de diagramas antes de migrar**

Run: `cd "D:/Codigo Abierto/ApuntesData Structures and Alg" && grep -rc "begin{dsadiagrama}" chapters/ | awk -F: '{s+=$2} END{print s}'`
Expected: `55`

- [ ] **Step 3: Quitar el `verbatim` interno de los 55 archivos (script mecánico)**

Ejecutar este perl por archivo; solo elimina el `verbatim` inmediatamente adyacente a `dsadiagrama` (no toca otros verbatim):

```bash
cd "D:/Codigo Abierto/ApuntesData Structures and Alg"
for f in chapters/*.tex; do
  perl -0777 -i -pe 's/(\\begin\{dsadiagrama\})\s*\n\s*\\begin\{verbatim\}[ \t]*\n/$1\n/g; s/\n[ \t]*\\end\{verbatim\}\s*\n([ \t]*\\end\{dsadiagrama\})/\n$1/g' "$f"
done
```

- [ ] **Step 4: Verificar que ya no quedan verbatim dentro de dsadiagrama**

Run:
```bash
cd "D:/Codigo Abierto/ApuntesData Structures and Alg"
for f in chapters/*.tex; do perl -0777 -ne 'while(/\\begin\{dsadiagrama\}(.*?)\\end\{dsadiagrama\}/gs){print "RESIDUAL verbatim: '"$f"'\n" if $1=~/verbatim/}' "$f"; done; echo "scan done"
```
Expected: solo `scan done` (ningún `RESIDUAL`). Y el conteo de diagramas sigue en 55:
`grep -rc "begin{dsadiagrama}" chapters/ | awk -F: '{s+=$2} END{print s}'` → `55`

- [ ] **Step 5: Borrar el scratch y compilar el libro completo**

```bash
cd "D:/Codigo Abierto/ApuntesData Structures and Alg"
rm -f scratch_diag.*
latexmk -lualatex -interaction=nonstopmode -halt-on-error ApuntesDSA.tex > /tmp/dsa_build.log 2>&1; echo "EXIT=$?"
grep -aoE "Output written on ApuntesDSA.pdf \([0-9]+ pages" /tmp/dsa_build.log | tail -1
grep -nE "^!|Fatal error|no output PDF" ApuntesDSA.log | grep -viE "Missing character" | head
```
Expected: `EXIT=0`, `Output written on ApuntesDSA.pdf (~216 pages`, sin errores fatales.

- [ ] **Step 6: Verificación visual**

Abrir `ApuntesDSA.pdf` y revisar 3 diagramas de secciones distintas:
- BFS/DFS (cap. `02_bfs_dfs`): grafo con nodos lime, flechas amarillas, líneas grises.
- Un árbol (cap. `01_trees_bst`): ramas `/  \` grises, nodos lime.
- Una tabla hash (cap. `04_hash_tables`): rejilla `+---+` / box-drawing gris, alineación intacta.

Confirmar: color correcto por clase, alineación de columnas preservada, caja verde y título `🎨 Diagrama` intactos.

- [ ] **Step 7: Commit**

```bash
cd "D:/Codigo Abierto/ApuntesData Structures and Alg"
git add preamble_dsa.tex chapters/ ApuntesDSA.pdf
git commit -m "Colorear diagramas: dsadiagrama como tcblisting + migrar 55 diagramas a estilo coloreado"
```

---

## Notas de diseño (refinamiento sobre el spec)

- El spec listaba box-drawing unicode + slashes. La inspección reveló que los diagramas mezclan ASCII (`| - + / \`) con unicode para las mismas líneas, así que el `literate` cubre ambos sets para colorear el esqueleto de forma consistente. Coherente con el objetivo visual aprobado (esqueleto gris).
- Colorear `-` y `+` puede teñir de gris algún guion dentro de una etiqueta de texto dentro del diagrama. Impacto cosmético mínimo, solo dentro de las cajas de diagrama. Se mantiene por consistencia del esqueleto.
- `<` y `>` se colorean amarillo como cabezas de flecha ASCII.
- Fuera de alcance (YAGNI): pesos de aristas, `O(n)`, resaltado semántico por-nodo.
