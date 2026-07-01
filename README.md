# Apuntes DSA — Data Structures & Algorithms

**Aldo Zepeda Montoya** · [@AldoZM](https://github.com/AldoZM)

Apuntes personales de DSA escritos en LaTeX: fondo oscuro, colores neon, diagramas ASCII, pseudocódigo y C++17. Orientados a prep de entrevistas técnicas Google-level.

📄 **[Descargar ApuntesDSA.pdf](ApuntesDSA.pdf)** — 207 páginas compiladas

> Los capítulos nuevos incluyen una sección **🧒 "Explicado para un niño de 12"**: la misma idea contada en lenguaje simple, sin jerga.

---

## Contenido

| # | Tema | Subtemas |
|---|------|----------|
| 1 | **Fundamentos** | Big-O Notation, Complejidad Espacial |
| 2 | **Estructuras Lineales** | Arrays, Linked Lists, **Fast & Slow Pointers**, **Patrones de Linked List**, Stacks, Queues |
| 3 | **Estructuras No Lineales** | BST, AVL Trees, **Tree Traversals**, **LCA + Serialización**, **Propiedades de Árboles**, Heaps, **Segment Tree**, **Fenwick/BIT**, Hash Tables, **Hashing/Colisiones**, **Patrones Hash Map**, **LRU Cache**, Tries, Union-Find |
| 4 | **Grafos** ⭐ | Representación, BFS/DFS, **BFS Avanzado (grid/multi-source/0-1)**, Dijkstra, **Bellman-Ford**, **Floyd-Warshall**, **Topological Sort**, **MST (Kruskal/Prim)**, **Detección de Ciclos**, **SCC (Kosaraju)**, **Grafo Bipartito**, **Puentes y Articulaciones**, **Flujo Máximo (Edmonds-Karp)** |
| 5 | **Ordenamiento** | Bubble/Insertion/Selection, Merge Sort, Quick Sort, **Heap Sort**, **Counting/Radix/Bucket** |
| 6 | **Búsqueda** | Linear Search, Binary Search |
| 7 | **Patrones de Entrevista** ⭐ | Two Pointers, Sliding Window, DP (intro/memo/tabulation), **DP Knapsack/Subset/Coin**, **DP LCS/Edit Distance**, **DP LIS**, **Greedy**, Backtracking, Bit Manipulation, Recursión |
| 8 | **Cadenas y Matemáticas** | **KMP / Rabin-Karp**, **GCD/Criba/Exponenciación Rápida** |

---

## Estructura del repo

```
ApuntesData Structures and Alg/
├── ApuntesDSA.tex          ← main file (portada, TOC, 8 partes)
├── ApuntesDSA.pdf          ← libro compilado (207 pp)
├── preamble_dsa.tex        ← dark mode, neon colors, emoji, C++ style, caja niño-de-12
├── chapters/               ← 56 fragmentos de capítulo (.tex)
├── 00_Fundamentos/         ← fuentes originales por carpeta
├── 01_Estructuras_Lineales/
├── 02_Estructuras_No_Lineales/
├── 03_Grafos/
├── 04_Algoritmos_Ordenamiento/
├── 05_Algoritmos_Busqueda/
└── 06_Patrones_Entrevista/
```

## Compilar

Requiere **XeLaTeX** (MiKTeX o TeX Live) y la fuente **Segoe UI Emoji** (incluida en Windows).

```bash
cd "ApuntesData Structures and Alg"
xelatex ApuntesDSA.tex
xelatex ApuntesDSA.tex   # segunda pasada para TOC y referencias
```

---

**Estado:** 56/56 archivos · última actualización 30 junio 2026
