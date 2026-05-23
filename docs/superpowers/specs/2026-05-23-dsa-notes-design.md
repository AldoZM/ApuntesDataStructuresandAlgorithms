# DSA Notes — Design Spec
**Fecha:** 2026-05-23  
**Autor:** Aldo Zepeda Montoya (AldoZM)  
**Repo:** https://github.com/AldoZM/ApuntesDataStructuresandAlgorithms  
**Directorio local:** `D:\Codigo Abierto\ApuntesData Structures and Alg\`

---

## Objetivo

Apuntes personales de Data Structures & Algorithms en formato `.txt`, pensados para:
1. Aprender los temas desde cero con explicaciones profundas
2. Repasar rápido antes de entrevistas técnicas (Google-level)

---

## Idioma

- **Explicaciones:** español
- **Términos técnicos:** inglés sin traducir (`stack`, `node`, `pointer`, `edge`, `heap`, `traversal`, `merge`, `pivot`, `linked list`, etc.)
- **Estilo:** Spanglish natural

---

## Estructura de Archivos

```
ApuntesData Structures and Alg/
├── INDEX.txt                          ← mapa completo, punto de entrada
├── docs/superpowers/specs/            ← specs de diseño (este archivo)
├── 00_Fundamentos/
│   ├── 01_big_o_notation.txt
│   └── 02_complejidad_espacial.txt
├── 01_Estructuras_Lineales/
│   ├── 01_arrays.txt
│   ├── 02_linked_lists.txt
│   ├── 03_stacks.txt
│   └── 04_queues.txt
├── 02_Estructuras_No_Lineales/
│   ├── 01_trees_bst.txt
│   ├── 02_avl_trees.txt
│   ├── 03_heaps.txt
│   ├── 04_hash_tables.txt
│   ├── 05_tries.txt
│   └── 06_union_find.txt
├── 03_Grafos/
│   ├── 01_representacion.txt
│   ├── 02_bfs_dfs.txt
│   └── 03_dijkstra.txt
├── 04_Algoritmos_Ordenamiento/
│   ├── 01_bubble_insertion_selection.txt
│   ├── 02_merge_sort.txt
│   └── 03_quick_sort.txt
├── 05_Algoritmos_Busqueda/
│   ├── 01_linear_search.txt
│   └── 02_binary_search.txt
└── 06_Patrones_Entrevista/
    ├── 01_two_pointers.txt
    ├── 02_sliding_window.txt
    ├── 03a_dp_intro.txt
    ├── 03b_dp_memoization.txt
    ├── 03c_dp_tabulation.txt
    ├── 04_backtracking.txt
    ├── 05_bit_manipulation.txt
    └── 06_recursion_y_memoization.txt
```

**Total:** 23 archivos de contenido + 1 INDEX.txt

---

## Formato Interno de Cada `.txt`

Cada archivo sigue esta plantilla fija (Opción C: narrativo profundo + resumen rápido al final):

```
════════════════════════════════════════════════════════════════
🗂️  TEMA: [Nombre]
📁  CATEGORÍA: [Carpeta]
════════════════════════════════════════════════════════════════

🤔 ¿QUÉ ES?
──────────────────────────────────────────────────────────────
  Explicación como para un niño de 12 años.
  Analogías simples, sin asumir conocimiento previo.
  Emojis para apoyar la explicación visualmente.

💬 DICHO DE OTRA FORMA
──────────────────────────────────────────────────────────────
  Misma idea, tono más técnico/casual (dev a dev).
  Conecta el concepto del niño con el lenguaje real de industria.

🎨 DIAGRAMA
──────────────────────────────────────────────────────────────
  ASCII art mostrando la estructura o proceso.
  Para operaciones: mostrar antes/después.

⚙️ ¿CÓMO FUNCIONA? (Operaciones principales)
──────────────────────────────────────────────────────────────
  Paso a paso de cada operación importante.
  Más texto que código aquí. Se entiende sin saber programar.

📝 PSEUDOCÓDIGO
──────────────────────────────────────────────────────────────
  Pseudocódigo limpio. Comentado. En spanglish.
  Sirve como puente entre explicación y código real.

💻 CÓDIGO C++
──────────────────────────────────────────────────────────────
  Implementación real en C++.
  CADA línea no obvia tiene comentario.
  Comentarios nivel 12 años: explican el POR QUÉ, no solo el QUÉ.

⏱️ COMPLEJIDAD (Big-O)
──────────────────────────────────────────────────────────────
  Tabla con Time Complexity y Space Complexity.
  Caso promedio y peor caso donde aplique.

🎯 EN ENTREVISTAS (Tips Google-level)
──────────────────────────────────────────────────────────────
  Cuándo usar esta estructura/algoritmo.
  Patrones de problemas donde aparece.
  Errores comunes. Red flags. Optimizaciones típicas.

📋 RESUMEN RÁPIDO
──────────────────────────────────────────────────────────────
  Bullets concisos para repaso pre-entrevista.
  Leer esto en 2 minutos = refrescar el tema completo.
════════════════════════════════════════════════════════════════
```

---

## Convenciones de Emojis

| Emoji | Significado |
|-------|-------------|
| 🤔 | Explicación conceptual |
| 💬 | Complemento técnico |
| 🎨 | Diagrama visual |
| ⚙️ | Mecánica / cómo funciona |
| 📝 | Pseudocódigo |
| 💻 | Código C++ |
| ⏱️ | Complejidad Big-O |
| 🎯 | Tips de entrevista |
| 📋 | Resumen rápido |
| ✅ | Buena práctica |
| ❌ | Error común / evitar |
| ⚠️ | Advertencia importante |
| 🔑 | Concepto clave |
| 🔗 | Referencia a otro archivo |

---

## Código C++

- Estándar: C++17
- Sin librerías externas salvo STL donde sea necesario (`<vector>`, `<queue>`, `<unordered_map>`)
- Cada implementación es standalone: compila y corre sola
- Comentarios en español, identificadores en inglés

---

## INDEX.txt

Archivo maestro en la raíz. Contiene:
- Mapa de todos los temas con descripción de una línea
- Orden sugerido de estudio
- Referencias cruzadas entre temas relacionados

---

## Git / GitHub

- Repo: `AldoZM/ApuntesDataStructuresandAlgorithms`
- Un commit por archivo terminado
- `README.md` en raíz: mismo contenido que INDEX.txt pero en markdown con links
- `.gitignore` mínimo (excluye nada relevante en .txt)

---

## Orden de Implementación Sugerido

1. INDEX.txt + README.md (esqueleto)
2. 00_Fundamentos (base para todo lo demás)
3. 01_Estructuras_Lineales (más simples, refuerzan pseudocódigo/C++)
4. 02_Estructuras_No_Lineales
5. 03_Grafos
6. 04_Algoritmos_Ordenamiento
7. 05_Algoritmos_Busqueda
8. 06_Patrones_Entrevista (los más valiosos para Google, van al final con toda la base)
