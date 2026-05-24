# DSA Notes Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Crear 23 archivos .txt de apuntes DSA + INDEX.txt + README.md en spanglish con emojis, diagramas ASCII, pseudocódigo y C++ comentado para estudio y prep de entrevistas Google-level.

**Architecture:** Archivos .txt independientes organizados en carpetas por categoría. Cada archivo sigue plantilla fija: explicación nivel niño 12 años → complemento técnico → diagrama ASCII → pseudocódigo → C++ comentado → Big-O → tips entrevista → resumen rápido.

**Tech Stack:** Archivos .txt planos, C++17 (STL), git para commits por archivo.

---

## Plantilla Interna (referencia para TODOS los archivos)

Cada archivo .txt debe seguir EXACTAMENTE esta estructura:

```
════════════════════════════════════════════════════════════════
🗂️  TEMA: [Nombre del tema]
📁  CATEGORÍA: [Nombre de la carpeta]
════════════════════════════════════════════════════════════════

🤔 ¿QUÉ ES?
──────────────────────────────────────────────────────────────
[Explicación nivel niño de 12 años. Analogía simple. Emojis.
Sin asumir conocimiento previo. 3-6 párrafos.]

💬 DICHO DE OTRA FORMA
──────────────────────────────────────────────────────────────
[Misma idea en tono dev. Conecta analogía con lenguaje técnico real.
Usa términos del industria en inglés. 1-3 párrafos.]

🎨 DIAGRAMA
──────────────────────────────────────────────────────────────
[ASCII art. Para estructuras: visualiza la estructura.
Para algoritmos: muestra paso a paso con antes/después.]

⚙️ ¿CÓMO FUNCIONA? (Operaciones principales)
──────────────────────────────────────────────────────────────
[Paso a paso de cada operación. Más texto que código.
Se debe entender sin saber programar.]

📝 PSEUDOCÓDIGO
──────────────────────────────────────────────────────────────
[Pseudocódigo en spanglish. Comentado. Claro.]

💻 CÓDIGO C++
──────────────────────────────────────────────────────────────
[C++17. Standalone (compila solo). Comentarios en español.
Identificadores en inglés. CADA línea no obvia comentada.]

⏱️ COMPLEJIDAD (Big-O)
──────────────────────────────────────────────────────────────
[Tabla de operaciones con Time y Space complexity.]

🎯 EN ENTREVISTAS (Tips Google-level)
──────────────────────────────────────────────────────────────
[Cuándo usar. Patrones. Errores comunes. Tips específicos.]

📋 RESUMEN RÁPIDO
──────────────────────────────────────────────────────────────
[Bullets concisos. 2 minutos de lectura = tema refrescado.]
════════════════════════════════════════════════════════════════
```

---

## Task 0: Setup — Estructura de carpetas + .gitignore

**Files:**
- Create: `D:\Codigo Abierto\ApuntesData Structures and Alg\.gitignore`
- Create dirs: `00_Fundamentos`, `01_Estructuras_Lineales`, `02_Estructuras_No_Lineales`, `03_Grafos`, `04_Algoritmos_Ordenamiento`, `05_Algoritmos_Busqueda`, `06_Patrones_Entrevista`

- [ ] **Step 1: Crear carpetas**

```powershell
cd "D:\Codigo Abierto\ApuntesData Structures and Alg"
New-Item -ItemType Directory -Force "00_Fundamentos"
New-Item -ItemType Directory -Force "01_Estructuras_Lineales"
New-Item -ItemType Directory -Force "02_Estructuras_No_Lineales"
New-Item -ItemType Directory -Force "03_Grafos"
New-Item -ItemType Directory -Force "04_Algoritmos_Ordenamiento"
New-Item -ItemType Directory -Force "05_Algoritmos_Busqueda"
New-Item -ItemType Directory -Force "06_Patrones_Entrevista"
```

- [ ] **Step 2: Crear .gitignore**

Contenido de `.gitignore`:
```
.DS_Store
Thumbs.db
desktop.ini
*.bak
```

- [ ] **Step 3: Commit setup**

```bash
git add .gitignore
git commit -m "chore: initial project structure and gitignore"
```

---

## Task 1: INDEX.txt + README.md

**Files:**
- Create: `INDEX.txt`
- Create: `README.md`

- [ ] **Step 1: Crear INDEX.txt**

Contenido completo:
```
════════════════════════════════════════════════════════════════════════════════
📚 APUNTES DE DATA STRUCTURES & ALGORITHMS
   Por: Aldo Zepeda Montoya | GitHub: AldoZM
   Objetivo: Entender DSA desde cero + prep entrevistas Google-level
════════════════════════════════════════════════════════════════════════════════

🗺️  MAPA DE CONTENIDO
──────────────────────────────────────────────────────────────────────────────

📂 00_Fundamentos/
   ├── 01_big_o_notation.txt      ← Mide qué tan rápido/lento es tu código
   └── 02_complejidad_espacial.txt ← Mide cuánta memoria usa tu código

📂 01_Estructuras_Lineales/
   ├── 01_arrays.txt              ← Lista de cajitas numeradas en fila
   ├── 02_linked_lists.txt        ← Cadena de nodos que se apuntan entre sí
   ├── 03_stacks.txt              ← Pila de platos (LIFO)
   └── 04_queues.txt              ← Fila del banco (FIFO)

📂 02_Estructuras_No_Lineales/
   ├── 01_trees_bst.txt           ← Árbol con regla: izq < raíz < der
   ├── 02_avl_trees.txt           ← BST que se autobalancea
   ├── 03_heaps.txt               ← Árbol donde el mayor/menor siempre está arriba
   ├── 04_hash_tables.txt         ← Cajones con llave mágica de acceso instantáneo
   ├── 05_tries.txt               ← Árbol de letras para buscar palabras
   └── 06_union_find.txt          ← Agrupa elementos en conjuntos conectados

📂 03_Grafos/
   ├── 01_representacion.txt      ← Cómo guardar un grafo en memoria
   ├── 02_bfs_dfs.txt             ← Dos formas de explorar un grafo
   └── 03_dijkstra.txt            ← Camino más corto con pesos

📂 04_Algoritmos_Ordenamiento/
   ├── 01_bubble_insertion_selection.txt ← Los 3 básicos O(n²)
   ├── 02_merge_sort.txt          ← Divide y vencerás, O(n log n) siempre
   └── 03_quick_sort.txt          ← Rápido en práctica, O(n log n) promedio

📂 05_Algoritmos_Busqueda/
   ├── 01_linear_search.txt       ← Busca uno por uno, O(n)
   └── 02_binary_search.txt       ← Adivina partiendo a la mitad, O(log n)

📂 06_Patrones_Entrevista/        ← ⭐ LOS MÁS IMPORTANTES PARA GOOGLE
   ├── 01_two_pointers.txt        ← Dos índices que se mueven en el array
   ├── 02_sliding_window.txt      ← Ventana que se desliza por el array
   ├── 03a_dp_intro.txt           ← DP: guardar resultados para no repetir trabajo
   ├── 03b_dp_memoization.txt     ← DP top-down con caché
   ├── 03c_dp_tabulation.txt      ← DP bottom-up con tabla
   ├── 04_backtracking.txt        ← Prueba todo, deshaz si no funciona
   ├── 05_bit_manipulation.txt    ← Operaciones a nivel de bits
   └── 06_recursion_y_memoization.txt ← Función que se llama a sí misma

──────────────────────────────────────────────────────────────────────────────
📖 ORDEN SUGERIDO DE ESTUDIO
──────────────────────────────────────────────────────────────────────────────

  1️⃣  Empieza aquí → 00_Fundamentos (sin esto, nada tiene sentido)
  2️⃣  Luego        → 01_Estructuras_Lineales (las más sencillas)
  3️⃣  Después      → 02_Estructuras_No_Lineales
  4️⃣  Siguiente    → 03_Grafos
  5️⃣  Continúa     → 04_Algoritmos_Ordenamiento
  6️⃣  Luego        → 05_Algoritmos_Busqueda
  7️⃣  Final boss   → 06_Patrones_Entrevista ⭐ (aquí vive el Google prep)

──────────────────────────────────────────────────────────────────────────────
🔗 REFERENCIAS CRUZADAS IMPORTANTES
──────────────────────────────────────────────────────────────────────────────

  big_o_notation     → se usa en TODOS los demás archivos
  arrays             → base para sliding_window y two_pointers
  stacks             → necesario para entender DFS en bfs_dfs.txt
  queues             → necesario para entender BFS en bfs_dfs.txt
  trees_bst          → prerequisito para avl_trees, heaps, tries
  bfs_dfs            → prerequisito para dijkstra
  dp_intro           → prerequisito para dp_memoization y dp_tabulation
  recursion          → prerequisito para backtracking y dp_intro

════════════════════════════════════════════════════════════════════════════════
```

- [ ] **Step 2: Crear README.md** (mismo contenido estructurado en Markdown)

```markdown
# 📚 Apuntes de Data Structures & Algorithms

Por **Aldo Zepeda Montoya** | [@AldoZM](https://github.com/AldoZM)

> Apuntes personales para entender DSA desde cero y prepararse para entrevistas técnicas Google-level. Escritos en spanglish con emojis, diagramas ASCII, pseudocódigo y C++17.

## 🗺️ Contenido

### 📂 [00_Fundamentos](00_Fundamentos/)
| Archivo | Tema |
|---------|------|
| [01_big_o_notation.txt](00_Fundamentos/01_big_o_notation.txt) | Mide qué tan rápido/lento es tu código |
| [02_complejidad_espacial.txt](00_Fundamentos/02_complejidad_espacial.txt) | Mide cuánta memoria usa tu código |

### 📂 [01_Estructuras_Lineales](01_Estructuras_Lineales/)
| Archivo | Tema |
|---------|------|
| [01_arrays.txt](01_Estructuras_Lineales/01_arrays.txt) | Lista de cajitas numeradas en fila |
| [02_linked_lists.txt](01_Estructuras_Lineales/02_linked_lists.txt) | Cadena de nodos que se apuntan entre sí |
| [03_stacks.txt](01_Estructuras_Lineales/03_stacks.txt) | Pila de platos (LIFO) |
| [04_queues.txt](01_Estructuras_Lineales/04_queues.txt) | Fila del banco (FIFO) |

### 📂 [02_Estructuras_No_Lineales](02_Estructuras_No_Lineales/)
| Archivo | Tema |
|---------|------|
| [01_trees_bst.txt](02_Estructuras_No_Lineales/01_trees_bst.txt) | Árbol con regla: izq < raíz < der |
| [02_avl_trees.txt](02_Estructuras_No_Lineales/02_avl_trees.txt) | BST que se autobalancea |
| [03_heaps.txt](02_Estructuras_No_Lineales/03_heaps.txt) | Árbol donde el mayor/menor siempre está arriba |
| [04_hash_tables.txt](02_Estructuras_No_Lineales/04_hash_tables.txt) | Cajones con llave mágica de acceso instantáneo |
| [05_tries.txt](02_Estructuras_No_Lineales/05_tries.txt) | Árbol de letras para buscar palabras |
| [06_union_find.txt](02_Estructuras_No_Lineales/06_union_find.txt) | Agrupa elementos en conjuntos conectados |

### 📂 [03_Grafos](03_Grafos/)
| Archivo | Tema |
|---------|------|
| [01_representacion.txt](03_Grafos/01_representacion.txt) | Cómo guardar un grafo en memoria |
| [02_bfs_dfs.txt](03_Grafos/02_bfs_dfs.txt) | Dos formas de explorar un grafo |
| [03_dijkstra.txt](03_Grafos/03_dijkstra.txt) | Camino más corto con pesos |

### 📂 [04_Algoritmos_Ordenamiento](04_Algoritmos_Ordenamiento/)
| Archivo | Tema |
|---------|------|
| [01_bubble_insertion_selection.txt](04_Algoritmos_Ordenamiento/01_bubble_insertion_selection.txt) | Los 3 básicos O(n²) |
| [02_merge_sort.txt](04_Algoritmos_Ordenamiento/02_merge_sort.txt) | Divide y vencerás, O(n log n) siempre |
| [03_quick_sort.txt](04_Algoritmos_Ordenamiento/03_quick_sort.txt) | Rápido en práctica, O(n log n) promedio |

### 📂 [05_Algoritmos_Busqueda](05_Algoritmos_Busqueda/)
| Archivo | Tema |
|---------|------|
| [01_linear_search.txt](05_Algoritmos_Busqueda/01_linear_search.txt) | Busca uno por uno, O(n) |
| [02_binary_search.txt](05_Algoritmos_Busqueda/02_binary_search.txt) | Adivina partiendo a la mitad, O(log n) |

### 📂 [06_Patrones_Entrevista](06_Patrones_Entrevista/) ⭐
| Archivo | Tema |
|---------|------|
| [01_two_pointers.txt](06_Patrones_Entrevista/01_two_pointers.txt) | Dos índices que se mueven en el array |
| [02_sliding_window.txt](06_Patrones_Entrevista/02_sliding_window.txt) | Ventana que se desliza por el array |
| [03a_dp_intro.txt](06_Patrones_Entrevista/03a_dp_intro.txt) | DP: guardar resultados para no repetir trabajo |
| [03b_dp_memoization.txt](06_Patrones_Entrevista/03b_dp_memoization.txt) | DP top-down con caché |
| [03c_dp_tabulation.txt](06_Patrones_Entrevista/03c_dp_tabulation.txt) | DP bottom-up con tabla |
| [04_backtracking.txt](06_Patrones_Entrevista/04_backtracking.txt) | Prueba todo, deshaz si no funciona |
| [05_bit_manipulation.txt](06_Patrones_Entrevista/05_bit_manipulation.txt) | Operaciones a nivel de bits |
| [06_recursion_y_memoization.txt](06_Patrones_Entrevista/06_recursion_y_memoization.txt) | Función que se llama a sí misma |

## 📖 Orden de Estudio
1. `00_Fundamentos` → base de todo
2. `01_Estructuras_Lineales` → las más simples
3. `02_Estructuras_No_Lineales`
4. `03_Grafos`
5. `04_Algoritmos_Ordenamiento`
6. `05_Algoritmos_Busqueda`
7. `06_Patrones_Entrevista` ⭐ Google prep aquí
```

- [ ] **Step 3: Commit**

```bash
git add INDEX.txt README.md
git commit -m "docs: add INDEX.txt and README.md with full content map"
```

---

## Task 2: 00_Fundamentos/01_big_o_notation.txt

**Files:**
- Create: `00_Fundamentos/01_big_o_notation.txt`

- [ ] **Step 1: Crear el archivo con contenido completo**

```
════════════════════════════════════════════════════════════════
🗂️  TEMA: Big-O Notation
📁  CATEGORÍA: 00_Fundamentos
════════════════════════════════════════════════════════════════

🤔 ¿QUÉ ES?
──────────────────────────────────────────────────────────────
Imagínate que tienes una caja de chocolates 🍫 y quieres
encontrar uno de sabor fresa. ¿Cuánto tiempo tardarías?

  Caso 1: Si sabes que el de fresa SIEMPRE está en la posición 1
          → Lo agarras directo. No importa si hay 10 o 1,000,000 chocolates.
          → Siempre es 1 paso. ¡Rápidísimo! ⚡

  Caso 2: Si los chocolates están desordenados y tienes que revisar
          uno por uno hasta encontrar el de fresa
          → Si hay 10 chocolates, revisas hasta 10.
          → Si hay 1,000,000 chocolates, revisas hasta 1,000,000.
          → El tiempo crece igual que la cantidad de chocolates. 📈

  Caso 3: Si por cada chocolate que revisas, tienes que revisar
          TODOS los demás para compararlos
          → Si hay 10 chocolates → 10 × 10 = 100 comparaciones
          → Si hay 100 chocolates → 100 × 100 = 10,000 comparaciones
          → ¡Crece muy rápido y se pone muy lento muy pronto! 🐌

Big-O Notation es la forma que tienen los programadores para
describir qué tan rápido o lento crece el tiempo que tarda
un algoritmo cuando le das más y más datos.

La "n" siempre representa la cantidad de datos de entrada.
Big-O siempre describe el PEOR caso posible (lo más lento que puede ser).

💬 DICHO DE OTRA FORMA
──────────────────────────────────────────────────────────────
Big-O es la métrica estándar para comparar la eficiencia de
algoritmos independientemente del hardware. Describe cómo
escala el tiempo de ejecución (o uso de memoria) en función
del tamaño del input "n", siempre en el worst case.

En interviews, SIEMPRE tienes que dar el Big-O de tu solución.
Es tan esperado como que el código funcione.

🎨 DIAGRAMA — Curvas de complejidad
──────────────────────────────────────────────────────────────
Tiempo
  |                                              O(2^n) 💀
  |                                         ,,''
  |                                    ,,'''        O(n²) 🐌
  |                               ,,'''        ,,,''
  |                          ,,'''       ,,,'''
  |                     ,,'''      ,,,'''          O(n log n) 🐢
  |                ,,'''      ,,'''
  |           ,,'''      ,,'''                    O(n) 🚶
  |      ,,'''       ,,''
  |  ,,''        ,,''                           O(log n) 🏃
  |''        ,,''
  |      ,,''                                  O(1) ⚡ (línea plana)
  +-------------------------------------------------> n (tamaño del input)
        pequeño      mediano        grande

  ⚡ O(1)       → Constante    → IDEAL
  🏃 O(log n)   → Logarítmico → MUY BUENO
  🚶 O(n)       → Lineal       → ACEPTABLE
  🐢 O(n log n) → Linealítmico → BUENO para sorting
  🐌 O(n²)      → Cuadrático   → MALO (evitar si puedes)
  💀 O(2^n)     → Exponencial  → FATAL (solo para n muy pequeño)

🎨 DIAGRAMA — Ejemplos concretos
──────────────────────────────────────────────────────────────

  O(1) — Array access:
  arr = [5, 2, 8, 1, 9]
         0  1  2  3  4
  arr[2] → directo al índice 2 → siempre 1 paso ✅

  O(n) — Linear search:
  Buscar el 8 en [5, 2, 8, 1, 9]
  ¿5 == 8? No → ¿2 == 8? No → ¿8 == 8? SÍ ✅
  En el peor caso revisas todos los n elementos.

  O(n²) — Comparar cada par:
  Para n=4: [A, B, C, D]
  A vs B, A vs C, A vs D  (3 comparaciones)
  B vs C, B vs D          (2 comparaciones)
  C vs D                  (1 comparación)
  Total: n*(n-1)/2 ≈ n² comparaciones

⚙️ ¿CÓMO FUNCIONA? — Las notaciones principales
──────────────────────────────────────────────────────────────

🔑 O(1) — Tiempo Constante
  Sin importar cuántos datos tengas, siempre tarda lo mismo.
  Ejemplo: acceder a arr[5] directamente por índice.

🔑 O(log n) — Tiempo Logarítmico
  Cada paso DIVIDE el problema a la mitad.
  Si tienes 1,024 elementos → necesitas máximo 10 pasos (2^10 = 1024)
  Si tienes 1,048,576 elementos → necesitas máximo 20 pasos (2^20)
  Ejemplo: Binary search.

🔑 O(n) — Tiempo Lineal
  Si duplicas el input, el tiempo se duplica.
  Ejemplo: recorrer todos los elementos de una lista una vez.

🔑 O(n log n) — Tiempo Linealítmico
  Un poco peor que lineal. La mayoría de buenos algoritmos de sorting.
  Ejemplo: Merge Sort, Quick Sort (promedio).

🔑 O(n²) — Tiempo Cuadrático
  Dos loops anidados sobre el mismo input.
  Si duplicas el input, el tiempo se CUADRUPLICA.
  Ejemplo: Bubble Sort, comparar todos contra todos.

🔑 O(2^n) — Tiempo Exponencial
  Cada elemento nuevo DUPLICA el trabajo.
  n=30 → más de 1,000,000,000 operaciones. Imposible en práctica.
  Ejemplo: fuerza bruta para subsets, Fibonacci sin memoization.

📝 PSEUDOCÓDIGO
──────────────────────────────────────────────────────────────

// O(1) — siempre el mismo número de pasos
función obtenerPrimero(array):
    return array[0]   // directo, sin loops

// O(n) — un loop que recorre todos los elementos
función buscarLineal(array, objetivo):
    PARA cada elemento EN array:
        SI elemento == objetivo:
            return VERDADERO
    return FALSO

// O(n²) — dos loops anidados sobre el mismo array
función tienesDuplicados(array):
    PARA i desde 0 hasta n:
        PARA j desde i+1 hasta n:
            SI array[i] == array[j]:
                return VERDADERO
    return FALSO

// O(log n) — cada iteración parte el problema a la mitad
función busquedaBinaria(array, objetivo):
    izq = 0
    der = tamaño(array) - 1
    MIENTRAS izq <= der:
        medio = (izq + der) / 2
        SI array[medio] == objetivo: return medio
        SI array[medio] < objetivo:  izq = medio + 1
        SINO:                        der = medio - 1
    return -1

💻 CÓDIGO C++
──────────────────────────────────────────────────────────────

#include <iostream>
#include <vector>
using namespace std;

// ─────────────────────────────────────────────
// O(1) — Constante
// No importa si el vector tiene 10 o 10 millones
// de elementos, SIEMPRE hacemos exactamente 1 operación
// ─────────────────────────────────────────────
int obtenerPrimero(vector<int>& arr) {
    return arr[0];  // acceso directo por índice → O(1)
}

// ─────────────────────────────────────────────
// O(n) — Lineal
// Si arr tiene n elementos, en el PEOR caso
// (el objetivo no existe) revisamos los n elementos
// ─────────────────────────────────────────────
bool buscarLineal(vector<int>& arr, int objetivo) {
    for (int i = 0; i < arr.size(); i++) {  // recorremos TODO el array
        if (arr[i] == objetivo) return true; // encontrado → salimos
    }
    return false;  // no lo encontramos en ningún lado
}

// ─────────────────────────────────────────────
// O(n²) — Cuadrático
// El loop exterior corre n veces.
// Por CADA vuelta del exterior, el interior también corre ~n veces.
// Total: n × n = n² comparaciones
// ─────────────────────────────────────────────
bool tieneDuplicados(vector<int>& arr) {
    int n = arr.size();
    for (int i = 0; i < n; i++) {          // primer loop: cada elemento
        for (int j = i + 1; j < n; j++) {  // segundo loop: compara con el resto
            if (arr[i] == arr[j]) return true;  // duplicado encontrado
        }
    }
    return false;
}

// ─────────────────────────────────────────────
// O(log n) — Logarítmico
// El array DEBE estar ordenado para que funcione.
// Cada iteración descarta LA MITAD de los elementos restantes.
// Si n=1024 → máximo 10 iteraciones (porque 2^10 = 1024)
// ─────────────────────────────────────────────
int busquedaBinaria(vector<int>& arr, int objetivo) {
    int izq = 0;               // puntero al inicio del rango de búsqueda
    int der = arr.size() - 1;  // puntero al final del rango de búsqueda

    while (izq <= der) {
        int medio = izq + (der - izq) / 2;  // calculamos el punto medio
        // Nota: usamos izq + (der-izq)/2 en lugar de (izq+der)/2
        // para evitar overflow cuando izq y der son números muy grandes

        if (arr[medio] == objetivo) return medio;  // ¡encontrado!
        if (arr[medio] < objetivo)  izq = medio + 1; // buscar en la mitad derecha
        else                        der = medio - 1; // buscar en la mitad izquierda
    }
    return -1;  // -1 significa "no encontrado" (convención estándar)
}

int main() {
    vector<int> arr = {1, 3, 5, 7, 9, 11, 13, 15};

    cout << "Primero: " << obtenerPrimero(arr) << endl;           // 1
    cout << "¿Tiene 7? " << buscarLineal(arr, 7) << endl;         // 1 (true)
    cout << "¿Duplicados? " << tieneDuplicados(arr) << endl;      // 0 (false)
    cout << "Binary search 7: " << busquedaBinaria(arr, 7) << endl; // índice 3

    return 0;
}

⏱️ COMPLEJIDAD (Big-O)
──────────────────────────────────────────────────────────────

  Notación    │ Nombre         │ Ejemplo real              │ ¿Usable?
  ────────────┼────────────────┼───────────────────────────┼──────────
  O(1)        │ Constante      │ Array access, hash lookup  │ ✅ Ideal
  O(log n)    │ Logarítmico    │ Binary search, BST ops     │ ✅ Muy bueno
  O(n)        │ Lineal         │ Loop simple, linear search │ ✅ Aceptable
  O(n log n)  │ Linealítmico   │ Merge sort, Heap sort      │ ✅ Bueno
  O(n²)       │ Cuadrático     │ Bubble sort, nested loops  │ ⚠️ Malo
  O(n³)       │ Cúbico         │ 3 loops anidados           │ ❌ Muy malo
  O(2^n)      │ Exponencial    │ Subsets, Fibonacci bruto   │ 💀 Fatal
  O(n!)       │ Factorial      │ Permutaciones por fuerza   │ 💀 Fatal

  Tip: n=1,000,000
  O(1)       →             1 operación
  O(log n)   →            20 operaciones
  O(n)       →     1,000,000 operaciones
  O(n log n) →    20,000,000 operaciones
  O(n²)      → 1,000,000,000,000 operaciones ← imposible en tiempo real

🎯 EN ENTREVISTAS (Tips Google-level)
──────────────────────────────────────────────────────────────

✅ SIEMPRE da el Big-O de tu solución ANTES de que te lo pregunten.
   Di: "Esta solución es O(n) en tiempo y O(1) en espacio."
   Es señal de que sabes lo que estás haciendo.

✅ Analiza TIEMPO y ESPACIO por separado. Son dos cosas distintas.
   Una solución puede ser O(n) en tiempo pero O(n²) en espacio.

✅ Cuando hay dos loops anidados sobre el MISMO input → O(n²)
   Cuando hay dos loops SEGUIDOS (no anidados) → O(n) + O(n) = O(n)

⚠️ Big-O ignora constantes y términos menores:
   O(3n + 5) → se simplifica a O(n)
   O(n² + n) → se simplifica a O(n²) (el n² domina)

⚠️ En entrevistas, cuando dices la complejidad, el entrevistador
   a veces pregunta "¿puedes hacerlo mejor?". Siempre piensa si
   hay una solución más eficiente antes de empezar a codear.

🔑 Regla de oro: si ves que tu solución tiene O(n²) y el problema
   involucra búsqueda, piensa si un hash map te da O(n) en su lugar.

📋 RESUMEN RÁPIDO
──────────────────────────────────────────────────────────────
• Big-O = qué tan rápido crece el tiempo al crecer el input
• Siempre describe el PEOR caso
• "n" = tamaño del input
• O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2^n)
• Loops anidados sobre mismo input → multiplica las complejidades
• Loops seguidos → te quedas con el mayor
• Ignora constantes: O(3n) → O(n)
• En entrevistas: siempre menciona tiempo Y espacio
• Hash maps convierten muchos O(n²) en O(n) ← tip de oro 🏅
════════════════════════════════════════════════════════════════
```

- [ ] **Step 2: Verificar formato**

Abre el archivo y confirma que tiene las 9 secciones: ¿QUÉ ES?, DICHO DE OTRA FORMA, DIAGRAMA, ¿CÓMO FUNCIONA?, PSEUDOCÓDIGO, CÓDIGO C++, COMPLEJIDAD, EN ENTREVISTAS, RESUMEN RÁPIDO.

- [ ] **Step 3: Commit**

```bash
git add 00_Fundamentos/01_big_o_notation.txt
git commit -m "docs: add big_o_notation notes"
```

---

## Task 3: 00_Fundamentos/02_complejidad_espacial.txt

**Files:**
- Create: `00_Fundamentos/02_complejidad_espacial.txt`

- [ ] **Step 1: Crear archivo**

Contenido requerido (seguir plantilla de Task 2):

**🤔 ¿QUÉ ES? — Analogía:**
Imagina que tu programa es una receta de cocina 🍳. Big-O en tiempo mide cuánto TARDAS. Complejidad espacial mide cuántas OLLAS Y SARTENES necesitas mientras cocinas. Si necesitas una olla gigante para 10 ingredientes, y otra olla gigante para 100, eso es O(n) en espacio.

**Conceptos a cubrir:**
- Auxiliary space vs input space (explica: auxiliary = memoria EXTRA que TÚ creas, no cuenta el input original)
- Stack space en recursión: cada llamada recursiva ocupa espacio en el call stack
- Ejemplo concreto: crear un array de n elementos → O(n) espacio; crear una variable → O(1) espacio

**🎨 DIAGRAMA — Visualizar call stack:**
```
factorial(4)              ← tope del stack (último en ejecutarse)
  factorial(3)
    factorial(2)
      factorial(1)        ← base case, primero en resolverse
        return 1

Cada llamada = 1 frame en el stack
4 llamadas = O(n) espacio en el stack
```

**⚙️ Operaciones/casos a explicar:**
- O(1) espacio: swap de dos variables con variable temporal
- O(n) espacio: crear array de tamaño n, recursión de profundidad n
- O(n²) espacio: crear matriz n×n
- Iterativo vs recursivo: misma lógica, pero iterativo puede ser O(1) espacio vs O(n) recursivo

**⏱️ Tabla Big-O espacio:**
```
Algoritmo              │ Space
───────────────────────┼────────
Array access           │ O(1)
Linear search          │ O(1)
Binary search iter     │ O(1)
Binary search recur    │ O(log n) ← stack frames
Merge sort             │ O(n)     ← array auxiliar
Quick sort             │ O(log n) ← stack frames promedio
Crear array de n       │ O(n)
Crear matriz n×n       │ O(n²)
```

**🎯 Tips entrevista:**
- En Google preguntan SIEMPRE espacio Y tiempo
- "In-place algorithm" = O(1) espacio auxiliar (modifica el input directamente)
- Recursión profunda puede causar stack overflow — mencionar en entrevista
- Trade-off clásico: puedes mejorar tiempo usando más espacio (memoization)

**📋 Resumen bullets:**
- Complejidad espacial = cuánta RAM EXTRA usa el algoritmo
- No cuenta el espacio del input, solo el auxiliar
- Recursión de profundidad n → O(n) espacio en call stack
- Iterativo generalmente usa menos espacio que recursivo
- O(1) espacio = "in-place", sin estructuras extras

- [ ] **Step 2: Commit**

```bash
git add 00_Fundamentos/02_complejidad_espacial.txt
git commit -m "docs: add complejidad_espacial notes"
```

---

## Task 4: 01_Estructuras_Lineales/01_arrays.txt

**Files:**
- Create: `01_Estructuras_Lineales/01_arrays.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Los vagones de un tren 🚂 numerados en orden. El vagón 0, el vagón 1, el vagón 2... Cada vagón tiene exactamente UN pasajero (dato). Para subir a cualquier vagón, solo dices el número y ¡listo! No tienes que pasar por todos los anteriores.

**⚙️ Operaciones y su complejidad:**
- Access arr[i]: O(1) — directo por índice
- Search (unsorted): O(n) — revisar uno por uno
- Search (sorted + binary search): O(log n)
- Insert al final (dynamic array con espacio): O(1) amortizado
- Insert al principio o medio: O(n) — hay que desplazar elementos
- Delete al final: O(1)
- Delete al principio o medio: O(n) — hay que desplazar elementos

**🎨 Diagrama:**
```
Índice:  [0] [1] [2] [3] [4]
Valor:   [ 5][ 2][ 8][ 1][ 9]
          ↑
    Dirección de memoria contigua →→→→→→→→→→

Insert 99 en índice 2:
ANTES:  [5][2][8][1][9]
         ↓  ↓  ← desplazar →
DESPUÉS:[5][2][99][8][1][9]   ← O(n) porque movimos 8, 1, 9
```

**📝 Pseudocódigo:** insert, delete, search lineal, search binario (array ordenado)

**💻 C++:** usar `vector<int>` de STL. Mostrar: declaración, push_back, acceso por índice, insert, erase, size. Comentar cada línea.

**⏱️ Big-O:**
```
Operación        │ Tiempo    │ Espacio
─────────────────┼───────────┼─────────
Access           │ O(1)      │ O(1)
Search unsorted  │ O(n)      │ O(1)
Search sorted    │ O(log n)  │ O(1)
Insert end       │ O(1)*     │ O(1)
Insert middle    │ O(n)      │ O(1)
Delete end       │ O(1)      │ O(1)
Delete middle    │ O(n)      │ O(1)
*amortizado en dynamic array
```

**🎯 Tips entrevista Google:**
- Arrays son la estructura más común en entrevistas
- "Two pointers" pattern vive aquí (ver 06_Patrones_Entrevista/01_two_pointers.txt)
- "Sliding window" también (ver 06_Patrones_Entrevista/02_sliding_window.txt)
- Pregunta típica: "¿El array está sorted?" — cambia la estrategia
- Off-by-one errors son el error #1 en arrays (cuidado con `< n` vs `<= n`)
- Suma acumulada (prefix sum) convierte O(n) queries a O(1)

- [ ] **Step 2: Commit**

```bash
git add 01_Estructuras_Lineales/01_arrays.txt
git commit -m "docs: add arrays notes"
```

---

## Task 5: 01_Estructuras_Lineales/02_linked_lists.txt

**Files:**
- Create: `01_Estructuras_Lineales/02_linked_lists.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Una cacería del tesoro 🗺️. Cada pista (node) te dice dónde está la SIGUIENTE pista. No sabes dónde está la pista #5 sin seguir la cadena desde el inicio: pista 1 → pista 2 → pista 3 → ... → pista 5.

**Tipos a cubrir:**
- Singly linked list: cada node tiene `value` y `next`
- Doubly linked list: cada node tiene `value`, `next` y `prev`

**🎨 Diagrama:**
```
Singly Linked List:
HEAD
 ↓
[3|•]→[7|•]→[1|•]→[9|NULL]
 node0  node1  node2  node3

Doubly Linked List:
HEAD                      TAIL
 ↓                         ↓
[NULL|3|•]⇄[•|7|•]⇄[•|1|•]⇄[•|9|NULL]

Insert 5 después del node1 (valor 7):
ANTES:  [3]→[7]→[1]→[9]
DESPUÉS:[3]→[7]→[5]→[1]→[9]   ← O(1) si ya tienes el pointer al node1
```

**⚙️ Operaciones:**
- Insert al head: O(1)
- Insert al tail: O(1) si tienes tail pointer, O(n) si no
- Insert en medio: O(n) para encontrar la posición, O(1) para insertar
- Delete head: O(1)
- Search: O(n)
- Access por índice: O(n) — debes recorrer desde el head

**💻 C++:** Implementar Node struct y LinkedList class con: insertHead, insertTail, deleteHead, search, print. Comentar punteros detalladamente.

**⏱️ Big-O:**
```
Operación        │ Tiempo  │ vs Array
─────────────────┼─────────┼──────────────
Access por índice│ O(n)    │ Array: O(1) ← array gana
Search           │ O(n)    │ Igual
Insert head      │ O(1)    │ Array: O(n) ← linked list gana
Insert tail      │ O(1)*   │ Array: O(1) amort. → Igual
Insert medio     │ O(n)    │ Igual (pero linked list evita desplazar)
Delete head      │ O(1)    │ Array: O(n) ← linked list gana
*con tail pointer
```

**🎯 Tips entrevista:**
- Floyd's cycle detection (fast/slow pointers) es el patrón más preguntado
- Siempre preguntar: "¿Es singly o doubly?" y "¿Hay tail pointer?"
- Problema clásico: invertir linked list (O(n) tiempo, O(1) espacio)
- Cuidado con NullPointerException — siempre verificar `if (node != nullptr)`
- Para encontrar el medio: fast pointer avanza 2, slow avanza 1

- [ ] **Step 2: Commit**

```bash
git add 01_Estructuras_Lineales/02_linked_lists.txt
git commit -m "docs: add linked_lists notes"
```

---

## Task 6: 01_Estructuras_Lineales/03_stacks.txt

**Files:**
- Create: `01_Estructuras_Lineales/03_stacks.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Una pila de platos 🍽️ en el fregadero. Solo puedes poner platos encima (push) y solo puedes agarrar el de hasta arriba (pop). Si quieres el plato de abajo, debes quitar todos los de encima primero.

**Principio:** LIFO — Last In, First Out. El último que entra es el primero en salir.

**🎨 Diagrama:**
```
push(A) → push(B) → push(C)

     [C]  ← TOP (solo puedes tocar este)
     [B]
     [A]
  ───────

pop() → devuelve C, queda:
     [B]  ← nuevo TOP
     [A]
  ───────

peek() → devuelve B sin quitar nada
```

**⚙️ Operaciones:**
- push(x): O(1) — agrega al tope
- pop(): O(1) — quita y devuelve el tope
- peek()/top(): O(1) — mira el tope sin quitar
- isEmpty(): O(1)
- size(): O(1)

**💻 C++:** Usar `stack<int>` de STL. También mostrar implementación propia con `vector<int>`.

**⏱️ Big-O:** Todas las operaciones O(1) tiempo, O(n) espacio total.

**🎯 Tips entrevista:**
- Usos clásicos: validar paréntesis balanceados, DFS iterativo, historial de navegador (undo/redo), evaluar expresiones matemáticas
- Problema más preguntado con stacks: "Valid Parentheses" — abres '(' lo pusheas, encuentras ')' popeas y verificas
- Monotonic stack: patrón avanzado para "Next Greater Element"
- Convertir recursión a iteración = usar un stack explícito

- [ ] **Step 2: Commit**

```bash
git add 01_Estructuras_Lineales/03_stacks.txt
git commit -m "docs: add stacks notes"
```

---

## Task 7: 01_Estructuras_Lineales/04_queues.txt

**Files:**
- Create: `01_Estructuras_Lineales/04_queues.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** La fila para entrar al cine 🎬. El primero que llega es el primero en entrar. No puedes colarte al frente. Llegas al final y esperas tu turno.

**Principio:** FIFO — First In, First Out.

**Tipos a cubrir:**
- Queue simple: enqueue al final, dequeue al frente
- Deque (Double-ended queue): insertar/eliminar en AMBOS extremos
- Priority Queue: el elemento con mayor prioridad sale primero (implementado con heap)

**🎨 Diagrama:**
```
enqueue(A) → enqueue(B) → enqueue(C)

FRONT                    BACK
  ↓                       ↓
 [A] → [B] → [C]

dequeue() → devuelve A, queda:
FRONT         BACK
  ↓             ↓
 [B] → [C]
```

**⚙️ Operaciones:**
- enqueue(x): O(1) — agrega al final
- dequeue(): O(1) — quita del frente
- peek()/front(): O(1) — mira el frente sin quitar
- isEmpty(): O(1)

**💻 C++:** `queue<int>` y `deque<int>` y `priority_queue<int>` de STL.

**🎯 Tips entrevista:**
- BFS siempre usa una queue — sin queue no hay BFS
- Priority queue (max-heap por defecto en C++) aparece en Dijkstra, "K largest elements"
- Deque aparece en "Sliding Window Maximum" (problema clásico de Google)
- Circular queue: implementación eficiente que evita shift de elementos

- [ ] **Step 2: Commit**

```bash
git add 01_Estructuras_Lineales/04_queues.txt
git commit -m "docs: add queues notes"
```

---

## Task 8: 02_Estructuras_No_Lineales/01_trees_bst.txt

**Files:**
- Create: `02_Estructuras_No_Lineales/01_trees_bst.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Un árbol genealógico 🌳 de cabeza. La raíz (root) está arriba. Cada persona (node) puede tener hijos (child nodes). Los que no tienen hijos se llaman hojas (leaves). En un BST específicamente: en cada node, TODOS los del lado izquierdo son menores y TODOS del lado derecho son mayores.

**Términos a definir:** root, node, leaf, parent, child, height, depth, subtree.

**🎨 Diagrama BST:**
```
         [8]          ← root
        /   \
      [3]   [10]      ← children de root
      / \      \
    [1] [6]   [14]    ← siguientes niveles
        / \   /
       [4][7][13]     ← leaves (no tienen hijos)

Propiedad BST: izquierda < nodo < derecha
¿Está 6 en el árbol?
  8 > 6 → ir izquierda → 3 < 6 → ir derecha → ¡6 encontrado! ✅
  Solo 3 comparaciones para n=7 nodos ≈ O(log n)
```

**⚙️ Operaciones:**
- Search: O(log n) promedio, O(n) peor caso (árbol degenerado)
- Insert: O(log n) promedio
- Delete: O(log n) promedio — 3 casos: leaf, 1 hijo, 2 hijos
- Inorder traversal: O(n) — da los elementos en orden ascendente ← IMPORTANTE
- Preorder, Postorder: O(n)

**💻 C++:** Struct TreeNode, BST class con insert, search, inorder. Explicar los 3 casos de delete.

**⏱️ Big-O:**
```
Operación   │ Promedio   │ Peor caso
────────────┼────────────┼─────────────
Search      │ O(log n)   │ O(n)
Insert      │ O(log n)   │ O(n)
Delete      │ O(log n)   │ O(n)
Traversal   │ O(n)       │ O(n)
Espacio     │ O(n)       │ O(n)

Peor caso = árbol degenerado (como linked list):
[1]→[2]→[3]→[4]→[5]  ← todos van hacia la derecha
```

**🎯 Tips entrevista:**
- Inorder de BST = sorted array ← dato que aparece en muchos problemas
- Árbol balanceado vs degenerado: la diferencia entre O(log n) y O(n)
- Lowest Common Ancestor (LCA) es el problema más pedido en árboles
- Height de árbol: O(log n) si balanceado, O(n) si degenerado
- Siempre verificar: ¿es BST o árbol binario genérico?

- [ ] **Step 2: Commit**

```bash
git add 02_Estructuras_No_Lineales/01_trees_bst.txt
git commit -m "docs: add trees_bst notes"
```

---

## Task 9: 02_Estructuras_No_Lineales/02_avl_trees.txt

**Files:**
- Create: `02_Estructuras_No_Lineales/02_avl_trees.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Un móvil de bebé 🎐 (esos que cuelgan sobre la cuna). Cuando agregas un objeto de un lado, el móvil se desequilibra. Entonces ajustas el otro lado para que vuelva a estar balanceado. Un AVL tree hace exactamente eso: cada vez que insertas o borras, se "autoajusta" para mantenerse balanceado.

**Conceptos clave:**
- Balance factor = height(izquierda) - height(derecha). Debe ser -1, 0, o 1.
- Si balance factor es 2 o -2 → se necesita rotación
- 4 tipos de rotaciones: LL (right rotation), RR (left rotation), LR (left-right), RL (right-left)

**🎨 Diagrama de rotaciones:**
```
Caso LL (right rotation):
     [C]              [B]
    /                /   \
   [B]      →       [A] [C]
  /
 [A]

Caso LR (left-right rotation):
   [C]           [C]          [B]
  /             /            /   \
 [A]    →      [B]   →      [A] [C]
   \           /
   [B]        [A]
```

**⏱️ Big-O:** TODAS las operaciones garantizadas O(log n) — eso es el punto del AVL.

**🎯 Tips entrevista:**
- AVL garantiza O(log n) siempre, BST normal puede degradar a O(n)
- En la práctica, Red-Black Trees se usan más (C++ `std::map` usa Red-Black)
- Pregunta típica: "¿Por qué preferiría AVL sobre BST?" → respuesta: balance garantizado
- No te pedirán implementar AVL completo en entrevista, pero sí entender CUÁNDO usarlo

- [ ] **Step 2: Commit**

```bash
git add 02_Estructuras_No_Lineales/02_avl_trees.txt
git commit -m "docs: add avl_trees notes"
```

---

## Task 10: 02_Estructuras_No_Lineales/03_heaps.txt

**Files:**
- Create: `02_Estructuras_No_Lineales/03_heaps.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Un torneo de fútbol ⚽ donde el mejor equipo SIEMPRE llega a la final (está en la cima). Si el mejor equipo pierde (lo sacas), el siguiente mejor sube automáticamente a la cima. No sabes quién es el tercero mejor sin hacer más comparaciones, pero SIEMPRE sabes quién es el #1.

**Tipos:**
- Max-heap: el mayor siempre está arriba
- Min-heap: el menor siempre está arriba

**Propiedad heap:** Todo parent es mayor (max-heap) o menor (min-heap) que sus children. NO es un BST — no tiene la propiedad izquierda < raíz < derecha.

**🎨 Diagrama:**
```
Max-Heap:
          [90]
         /    \
       [80]  [75]
       / \   / \
     [60][70][50][55]

Implementado como array:
idx:  [0] [1] [2] [3] [4] [5] [6]
val:  [90][80][75][60][70][50][55]

Para idx i:
  parent  = (i-1) / 2
  hijo izq = 2*i + 1
  hijo der = 2*i + 2
```

**⚙️ Operaciones:**
- insert: O(log n) — agrega al final, luego "bubble up"
- extract max/min: O(log n) — quita raíz, pone el último arriba, "bubble down"
- peek max/min: O(1) — solo mira arr[0]
- heapify (construir heap desde array): O(n) — no O(n log n), es O(n)

**💻 C++:** `priority_queue<int>` (max-heap por default), `priority_queue<int, vector<int>, greater<int>>` (min-heap).

**🎯 Tips entrevista:**
- "Top K elements" → min-heap de tamaño K
- "K closest points to origin" → max-heap de tamaño K
- Merge K sorted lists → min-heap
- Median of data stream → two heaps (max-heap + min-heap)
- Priority queue = heap en la práctica

- [ ] **Step 2: Commit**

```bash
git add 02_Estructuras_No_Lineales/03_heaps.txt
git commit -m "docs: add heaps notes"
```

---

## Task 11: 02_Estructuras_No_Lineales/04_hash_tables.txt

**Files:**
- Create: `02_Estructuras_No_Lineales/04_hash_tables.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Un casillero de escuela 🎒. Cada estudiante tiene un número de casillero asignado por una fórmula mágica (la hash function). Para guardar la mochila de "Carlos" → calculamos hash("Carlos") = 42 → guardamos en casillero 42. Para buscarla → calculamos hash("Carlos") = 42 → vamos directo al casillero 42. ¡Sin buscar en todos los casilleros!

**Conceptos:**
- Hash function: transforma una key en un índice del array
- Collision: dos keys producen el mismo índice
- Chaining: en cada slot, una linked list de todos los elementos con ese hash
- Open addressing: si hay colisión, buscar el siguiente slot libre
- Load factor: (elementos) / (tamaño del array). Cuando > 0.75, se hace rehashing

**🎨 Diagrama:**
```
hash("Carlos") = 2
hash("Maria")  = 5
hash("Juan")   = 2  ← COLISIÓN con Carlos

Chaining:
idx 0: []
idx 1: []
idx 2: [Carlos] → [Juan]  ← linked list por colisión
idx 3: []
idx 4: []
idx 5: [Maria]
```

**⏱️ Big-O:**
```
Operación   │ Promedio │ Peor caso
────────────┼──────────┼──────────
get(key)    │ O(1)     │ O(n)
set(key,v)  │ O(1)     │ O(n)
delete(key) │ O(1)     │ O(n)
Espacio     │ O(n)     │ O(n)
Peor caso = todas las keys colisionan (hash function mala)
```

**💻 C++:** `unordered_map<string, int>` para hash map, `unordered_set<int>` para hash set.

**🎯 Tips entrevista:**
- Regla de oro: si necesitas O(1) lookup → hash map
- "Two Sum" → hash map: guardar complemento mientras recorres
- Detectar duplicados → hash set
- Frecuencia de elementos → hash map: `{elemento: count}`
- En C++: `unordered_map` = O(1) promedio; `map` = O(log n) pero ordenado

- [ ] **Step 2: Commit**

```bash
git add 02_Estructuras_No_Lineales/04_hash_tables.txt
git commit -m "docs: add hash_tables notes"
```

---

## Task 12: 02_Estructuras_No_Lineales/05_tries.txt

**Files:**
- Create: `02_Estructuras_No_Lineales/05_tries.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Un diccionario físico 📖 donde navegas letra por letra. Para buscar "GATO": vas a la sección G → dentro de G buscas A → dentro de GA buscas T → dentro de GAT buscas O → encontrado. Cada nivel del árbol representa una letra más de la palabra.

**Usos:** Autocomplete, spell checker, búsqueda de palabras con prefijo.

**🎨 Diagrama:**
```
Insertando: "CAT", "CAR", "DO", "DOG"

root
├── C
│   └── A
│       ├── T (isEnd=true)  ← "CAT"
│       └── R (isEnd=true)  ← "CAR"
└── D
    └── O (isEnd=true)      ← "DO"
        └── G (isEnd=true)  ← "DOG"
```

**⚙️ Operaciones:**
- insert(word): O(m) donde m = longitud de la palabra
- search(word): O(m) — ¿existe exactamente esta palabra?
- startsWith(prefix): O(m) — ¿existe alguna palabra con este prefijo?

**💻 C++:** Struct TrieNode con `unordered_map<char, TrieNode*> children` y `bool isEnd`. Clase Trie con insert, search, startsWith.

**🎯 Tips entrevista:**
- Cuando el problema menciona "prefijos" o "autocomplete" → Trie
- "Word Search II" (encontrar múltiples palabras en grid) → Trie + DFS
- Complejidad O(m) independiente del número de palabras guardadas ← ventaja
- Espacio puede ser grande: hasta O(26^m) en el peor caso con alfabeto inglés

- [ ] **Step 2: Commit**

```bash
git add 02_Estructuras_No_Lineales/05_tries.txt
git commit -m "docs: add tries notes"
```

---

## Task 13: 02_Estructuras_No_Lineales/06_union_find.txt

**Files:**
- Create: `02_Estructuras_No_Lineales/06_union_find.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Los clubes de la escuela 🏫. Al inicio cada estudiante es su propio club. Cuando dos estudiantes se hacen amigos, sus clubes se unen. Para saber si dos personas están en el mismo club, sigues la cadena de amistades hasta el "líder" del grupo. Si ambos tienen el mismo líder → mismo grupo.

**Optimizaciones:**
- Path compression: al buscar el root, hacer que todos apunten directo al root
- Union by rank: siempre unir el árbol más pequeño bajo el más grande

**🎨 Diagrama:**
```
Inicio: {0} {1} {2} {3} {4}
parent: [0, 1, 2, 3, 4]

union(0,1): {0,1} {2} {3} {4}
parent: [0, 0, 2, 3, 4]  ← 1 apunta a 0

union(2,3): {0,1} {2,3} {4}
parent: [0, 0, 2, 2, 4]  ← 3 apunta a 2

union(0,2): {0,1,2,3} {4}
parent: [0, 0, 0, 2, 4]  ← 2 apunta a 0

find(3): 3→2→0 (path compression: 3 apunta directo a 0)
```

**⏱️ Big-O:**
```
Con path compression + union by rank:
find:  O(α(n)) ≈ O(1) prácticamente constante
union: O(α(n)) ≈ O(1)
α = función inversa de Ackermann, crece tan lento que es ≤4 para n≤10^80
```

**🎯 Tips entrevista:**
- "Number of Connected Components" → Union-Find
- "Redundant Connection" (detectar ciclos en grafo) → Union-Find
- "Accounts Merge" → Union-Find
- Alternativa a BFS/DFS para problemas de conectividad — a veces más simple

- [ ] **Step 2: Commit**

```bash
git add 02_Estructuras_No_Lineales/06_union_find.txt
git commit -m "docs: add union_find notes"
```

---

## Task 14: 03_Grafos/01_representacion.txt

**Files:**
- Create: `03_Grafos/01_representacion.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Un mapa de ciudades 🗺️ con carreteras entre ellas. Las ciudades son los nodes (vertices) y las carreteras son los edges. Puedes ir de ciudad A a ciudad B si hay carretera directa (edge).

**Tipos de grafos:** directed/undirected, weighted/unweighted, cyclic/acyclic.

**🎨 Diagrama — Adjacency Matrix vs List:**
```
Grafo: A→B, A→C, B→C, C→D

Adjacency Matrix (4×4):
     A  B  C  D
  A [0, 1, 1, 0]
  B [0, 0, 1, 0]
  C [0, 0, 0, 1]
  D [0, 0, 0, 0]

Adjacency List:
  A: [B, C]
  B: [C]
  C: [D]
  D: []
```

**Cuándo usar cada uno:**
- Matrix: grafo denso (muchos edges), O(1) para verificar si edge existe, O(V²) espacio
- List: grafo disperso (pocos edges), O(V+E) espacio, más común en entrevistas

**💻 C++:** `vector<vector<int>> adjList(V)` para lista. `vector<vector<int>> matrix(V, vector<int>(V, 0))` para matriz.

**🎯 Tips:** En entrevistas, 90% de las veces usa adjacency list. Es más eficiente para grafos dispersos (que son la mayoría).

- [ ] **Step 2: Commit**

```bash
git add 03_Grafos/01_representacion.txt
git commit -m "docs: add grafos representacion notes"
```

---

## Task 15: 03_Grafos/02_bfs_dfs.txt

**Files:**
- Create: `03_Grafos/02_bfs_dfs.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogías:**
- BFS: como lanzar una piedra al agua 💧 y ver las ondas expandirse nivel por nivel. Primero todos los vecinos directos, luego los vecinos de los vecinos.
- DFS: como explorar un laberinto 🌀 — sigues un camino hasta el fondo. Si no funciona, regresas y pruebas otro camino.

**🎨 Diagrama:**
```
Grafo:
    1
   / \
  2   3
 / \   \
4   5   6

BFS desde 1: 1 → 2,3 → 4,5,6    (nivel por nivel)
Orden visita: [1, 2, 3, 4, 5, 6]

DFS desde 1: 1→2→4 (fondo), regresa→5 (fondo), regresa→3→6
Orden visita: [1, 2, 4, 5, 3, 6]
```

**⚙️ BFS usa QUEUE, DFS usa STACK (o recursión).**

**Aplicaciones:**
- BFS: camino más corto en grafo NO ponderado, nivel de cada nodo, bipartite check
- DFS: detectar ciclos, topological sort, connected components, path existence

**⏱️ Ambos: O(V + E) tiempo, O(V) espacio**

**💻 C++:** BFS iterativo con queue, DFS iterativo con stack y recursivo. Array `visited[]` para evitar ciclos.

**🎯 Tips entrevista:**
- "Shortest path unweighted" → BFS (garantiza camino más corto)
- "Does path exist?" → DFS (más simple)
- Ciclos en directed graph → DFS con estados: WHITE/GRAY/BLACK
- Topological sort → DFS postorder o BFS (Kahn's algorithm)

- [ ] **Step 2: Commit**

```bash
git add 03_Grafos/02_bfs_dfs.txt
git commit -m "docs: add bfs_dfs notes"
```

---

## Task 16: 03_Grafos/03_dijkstra.txt

**Files:**
- Create: `03_Grafos/03_dijkstra.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** El GPS de tu teléfono 📱. Cuando pides la ruta más rápida de casa al trabajo, no intenta TODOS los caminos posibles. Siempre expande primero el camino más prometedor (el más corto hasta ahora), y así va construyendo la ruta óptima paso a paso.

**Restricción importante:** ⚠️ Solo funciona con pesos NON-NEGATIVOS (sin edges con peso negativo).

**🎨 Diagrama:**
```
        2       3
  A ────────B────────E
  |         |        |
  4       1 |        2
  |         |        |
  C─────────D────────F
       5          1

dist desde A: {A:0, B:2, C:4, D:3, E:5, F:4}
Camino a E: A→B→D→F... espera, A→B→E = 2+3=5, A→B→D→F→E=2+1+1+2=6
El más corto: A→B→E con costo 5
```

**⚙️ Algoritmo:**
1. dist[source] = 0, todos los demás = infinito
2. Min-heap con (distancia, nodo)
3. Sacar el nodo con menor distancia
4. Para cada vecino: si dist[actual] + peso_edge < dist[vecino] → actualizar y agregar al heap
5. Repetir hasta vaciar el heap

**⏱️ O((V + E) log V) con min-heap (priority_queue)**

**💻 C++:** `priority_queue<pair<int,int>, vector<pair<int,int>>, greater<>>` como min-heap.

**🎯 Tips entrevista:**
- "Shortest path weighted graph" → Dijkstra
- Si hay pesos negativos → Bellman-Ford en su lugar
- "Cheapest flights within K stops" → Dijkstra modificado
- Network delay time → Dijkstra clásico

- [ ] **Step 2: Commit**

```bash
git add 03_Grafos/03_dijkstra.txt
git commit -m "docs: add dijkstra notes"
```

---

## Task 17: 04_Algoritmos_Ordenamiento/01_bubble_insertion_selection.txt

**Files:**
- Create: `04_Algoritmos_Ordenamiento/01_bubble_insertion_selection.txt`

- [ ] **Step 1: Crear archivo**

Cubrir los 3 algoritmos en UN archivo ya que son los básicos O(n²).

**🤔 Analogías:**
- Bubble Sort 🫧: burbujas subiendo. Los números más grandes "burbujean" hacia el final comparando pares adyacentes.
- Insertion Sort 🃏: ordenar cartas en la mano. Cada nueva carta la insertas en su lugar correcto entre las ya ordenadas.
- Selection Sort 🔍: buscar el más pequeño y ponerlo primero, luego el siguiente más pequeño, etc.

**🎨 Diagrama para cada uno con array [64, 34, 25, 12, 22]:**
- Bubble: mostrar primeros 2 passes
- Insertion: mostrar inserción de los primeros 3 elementos
- Selection: mostrar primeras 2 selecciones del mínimo

**⏱️ Big-O:**
```
Algoritmo   │ Best   │ Average │ Worst  │ Space │ Stable?
────────────┼────────┼─────────┼────────┼───────┼────────
Bubble      │ O(n)   │ O(n²)   │ O(n²)  │ O(1)  │ Sí ✅
Insertion   │ O(n)   │ O(n²)   │ O(n²)  │ O(1)  │ Sí ✅
Selection   │ O(n²)  │ O(n²)   │ O(n²)  │ O(1)  │ No ❌
```

**🎯 Tips entrevista:**
- Insertion sort tiene O(n) en best case (array casi ordenado) → útil en práctica para arrays pequeños
- Selection sort hace el mínimo de swaps: O(n) swaps aunque sea O(n²) comparaciones
- "Stable" = elementos iguales mantienen su orden relativo original
- En la práctica nadie usa estos 3 para n grande — existen para enseñar conceptos

- [ ] **Step 2: Commit**

```bash
git add 04_Algoritmos_Ordenamiento/01_bubble_insertion_selection.txt
git commit -m "docs: add bubble/insertion/selection sort notes"
```

---

## Task 18: 04_Algoritmos_Ordenamiento/02_merge_sort.txt

**Files:**
- Create: `04_Algoritmos_Ordenamiento/02_merge_sort.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Ordenar una baraja de cartas 🃏 con un amigo. Le das la mitad, tú te quedas la otra mitad. Cada quien ordena su mitad (y si son muchas, vuelven a dividir con otro amigo). Al final, fusionan las dos mitades ya ordenadas comparando carta por carta.

**Estrategia:** Divide y vencerás (Divide and Conquer).

**🎨 Diagrama:**
```
[38, 27, 43, 3, 9, 82, 10]

Divide:
[38,27,43,3]    [9,82,10]
[38,27][43,3]  [9,82][10]
[38][27][43][3] [9][82][10]

Merge (combinar ordenando):
[27,38][3,43]  [9,82][10]
[3,27,38,43]   [9,10,82]
[3,9,10,27,38,43,82]  ✅
```

**⚙️ Dos fases:** divide (recursivo hasta arrays de 1) + merge (combinar ordenando).

**⏱️ O(n log n) SIEMPRE — no tiene peor caso como Quick Sort. O(n) espacio auxiliar.**

**💻 C++:** Función mergeSort recursiva + función merge. Comentar cómo el stack de recursión crea los O(log n) niveles.

**🎯 Tips entrevista:**
- Merge sort = stable sort garantizado O(n log n)
- Usado cuando necesitas stable sort o garantía de O(n log n)
- "Sort Linked List" → Merge sort es ideal (no necesita acceso aleatorio)
- Merge step es la base de "Merge K Sorted Arrays/Lists"

- [ ] **Step 2: Commit**

```bash
git add 04_Algoritmos_Ordenamiento/02_merge_sort.txt
git commit -m "docs: add merge_sort notes"
```

---

## Task 19: 04_Algoritmos_Ordenamiento/03_quick_sort.txt

**Files:**
- Create: `04_Algoritmos_Ordenamiento/03_quick_sort.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Elegir a un jugador de referencia en el equipo ⚽. Todos los que son "peores" (número menor) van a la izquierda. Todos los "mejores" (número mayor) van a la derecha. El jugador de referencia quedó en su lugar correcto. Ahora haz lo mismo con los grupos de izquierda y derecha.

**El pivot:** El elemento de referencia. Su elección afecta el rendimiento.

**🎨 Diagrama:**
```
[3, 6, 8, 10, 1, 2, 1]  pivot = último elemento (1)

Partition:
elementos < 1: []
elementos > 1: [3,6,8,10,2]
pivot en su lugar: [] [1] [3,6,8,10,2,1]

(continúa recursivamente en cada subarray)
```

**⏱️ Big-O:**
```
Caso        │ Tiempo    │ Cuándo ocurre
────────────┼───────────┼──────────────────────────────
Best        │ O(n log n)│ Pivot siempre parte a la mitad
Average     │ O(n log n)│ Pivot aleatorio
Worst       │ O(n²)     │ Array ya ordenado + pivot=último
Espacio     │ O(log n)  │ Stack de recursión (promedio)
```

**Por qué es más rápido que Merge Sort en práctica:** mejor cache locality (opera in-place), menor overhead de memoria.

**🎯 Tips entrevista:**
- Quick Sort NO es stable
- Peor caso O(n²) con array sorted + mal pivot → usar random pivot o median-of-3
- `std::sort` en C++ usa IntroSort (Quick Sort + Heap Sort como fallback)
- Partition es la operación clave — entenderla bien es suficiente

- [ ] **Step 2: Commit**

```bash
git add 04_Algoritmos_Ordenamiento/03_quick_sort.txt
git commit -m "docs: add quick_sort notes"
```

---

## Task 20: 05_Algoritmos_Busqueda/01_linear_search.txt

**Files:**
- Create: `05_Algoritmos_Busqueda/01_linear_search.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Buscar tus llaves en casa 🔑 revisando cuarto por cuarto, cajón por cajón, sin ningún orden especial. Empiezas en un lugar y revisas todo hasta encontrarlas o verificar que no están.

**Cuándo usar:** Array desordenado, dataset pequeño, búsqueda única (no vale la pena ordenar para una sola búsqueda).

**⏱️ O(n) tiempo, O(1) espacio**

**🎯 Tips:** Rara vez aparece solo en entrevistas, pero es la base para entender por qué Binary Search es mejor. También aparece en strings (buscar substring naïve).

- [ ] **Step 2: Commit**

```bash
git add 05_Algoritmos_Busqueda/01_linear_search.txt
git commit -m "docs: add linear_search notes"
```

---

## Task 21: 05_Algoritmos_Busqueda/02_binary_search.txt

**Files:**
- Create: `05_Algoritmos_Busqueda/02_binary_search.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** El juego de adivina el número 🔢 entre 1 y 100. Dices 50 → "más alto" → dices 75 → "más bajo" → dices 62... Cada intento elimina la MITAD de las posibilidades. En 7 intentos puedes adivinar entre 128 opciones.

**Requisito:** El array DEBE estar ordenado.

**🎨 Diagrama paso a paso:**
```
Buscar 23 en [1,3,5,7,9,11,13,15,17,19,21,23,25]
idx:          0 1 2 3 4  5  6  7  8  9 10 11 12

Paso 1: izq=0, der=12, mid=6, arr[6]=13 < 23 → izq=7
Paso 2: izq=7, der=12, mid=9, arr[9]=19 < 23 → izq=10
Paso 3: izq=10, der=12, mid=11, arr[11]=23 == 23 → ¡ENCONTRADO! idx=11
Solo 3 pasos para 13 elementos ✅
```

**Variantes importantes para entrevistas:**
- Buscar primer occurrence de un valor duplicado
- Buscar último occurrence
- Buscar en rotated sorted array (clásico de Google)
- Binary search on answer (buscar en el espacio de respuestas, no en array)

**⏱️ O(log n) tiempo, O(1) espacio iterativo**

**💻 C++:** Versión iterativa (preferida) y recursiva. Comentar el bug clásico de overflow en `mid = (izq+der)/2`.

**🎯 Tips entrevista:**
- Off-by-one error es el bug más común (`<=` vs `<`, `mid+1` vs `mid`)
- "Rotated Sorted Array" → Binary search modificado, pregunta muy frecuente en Google
- Binary search on answer: cuando preguntan "¿cuál es el mínimo X que satisface condición?" → binary search en el rango de respuestas posibles
- Template de 3 punteros (izq, mid, der) cubre el 95% de variantes

- [ ] **Step 2: Commit**

```bash
git add 05_Algoritmos_Busqueda/02_binary_search.txt
git commit -m "docs: add binary_search notes"
```

---

## Task 22: 06_Patrones_Entrevista/01_two_pointers.txt

**Files:**
- Create: `06_Patrones_Entrevista/01_two_pointers.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Dos personas en extremos opuestos de un pasillo 🚶🚶 caminando hacia el centro. O un corredor lento y uno rápido en la misma pista 🏃.

**Dos variantes:**
1. Opposite ends: izq empieza en 0, der empieza en n-1, se mueven hacia el centro
2. Fast/slow (Floyd's): slow avanza 1, fast avanza 2

**Problemas clásicos con solución:**
- Two Sum (sorted array): O(n) con two pointers vs O(n²) fuerza bruta
- Container With Most Water: two pointers opuestos
- Remove Duplicates from Sorted Array: slow/fast pointers
- Detect cycle in linked list: fast/slow (Floyd's)

**💻 C++:** Mostrar implementación completa de Two Sum con two pointers y explicar por qué funciona.

**⏱️ Típicamente O(n) tiempo, O(1) espacio**

**🎯 Tips:** Cuando el array está sorted y el problema pide encontrar un par → pensar en two pointers primero.

- [ ] **Step 2: Commit**

```bash
git add 06_Patrones_Entrevista/01_two_pointers.txt
git commit -m "docs: add two_pointers pattern notes"
```

---

## Task 23: 06_Patrones_Entrevista/02_sliding_window.txt

**Files:**
- Create: `06_Patrones_Entrevista/02_sliding_window.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Una ventana de tren 🚂 que ves paisajes mientras el tren avanza. La ventana siempre muestra k metros de paisaje. Al avanzar, entra nuevo paisaje por un lado y sale por el otro.

**Dos tipos:**
- Fixed size window: siempre k elementos
- Variable size window: crece y encoge según condición

**Problemas clásicos con solución:**
- Max sum subarray of size k: fixed window
- Longest substring without repeating chars: variable window con hash set
- Minimum window substring: variable window con hash map

**💻 C++:** Implementar "max sum subarray of size k" completo con comentarios.

**⏱️ O(n) tiempo, O(1) o O(k) espacio**

**🎯 Tips:** Cuando el problema menciona "subarray/substring de tamaño k" o "contiguous sequence" → pensar sliding window.

- [ ] **Step 2: Commit**

```bash
git add 06_Patrones_Entrevista/02_sliding_window.txt
git commit -m "docs: add sliding_window pattern notes"
```

---

## Task 24: 06_Patrones_Entrevista/03a_dp_intro.txt

**Files:**
- Create: `06_Patrones_Entrevista/03a_dp_intro.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Un estudiante que guarda sus apuntes 📓. En vez de recalcular la misma fórmula 50 veces en el examen, la escribe en su cuaderno la primera vez y después la consulta. DP = guardar resultados ya calculados para no repetir trabajo.

**Dos condiciones para usar DP:**
1. Overlapping subproblems: el mismo subproblema se resuelve múltiples veces
2. Optimal substructure: la solución óptima del problema = combinación de soluciones óptimas de subproblemas

**Fibonacci como ejemplo introductorio:**
- Sin DP: O(2^n) — calcula fib(3) millones de veces
- Con DP: O(n) — calcula fib(3) una sola vez, lo guarda

**🎨 Diagrama árbol de recursión Fibonacci(5) sin y con memoization**

**🎯 Tips:** DP aparece en ~30% de entrevistas Google. Es el tema más importante de la sección de patrones.

- [ ] **Step 2: Commit**

```bash
git add 06_Patrones_Entrevista/03a_dp_intro.txt
git commit -m "docs: add dp_intro notes"
```

---

## Task 25: 06_Patrones_Entrevista/03b_dp_memoization.txt

**Files:**
- Create: `06_Patrones_Entrevista/03b_dp_memoization.txt`

- [ ] **Step 1: Crear archivo**

**Enfoque:** Top-down. Empiezas con el problema completo, lo divides recursivamente, guardas resultados en un map/array (memo).

**Problemas a cubrir con solución completa:**
1. Fibonacci memoizado: `memo[n] = fib(n-1) + fib(n-2)` con cache
2. Coin Change: mínimo de monedas para llegar a amount
   - `dp[amount] = min(dp[amount - coin] + 1)` para cada coin

**💻 C++:** Ambos problemas completos con `unordered_map<int,int> memo`.

**🎯 Tips:** Memoization = recursión + caché. Si ya sabes recursión, solo agrega el `memo` map.

- [ ] **Step 2: Commit**

```bash
git add 06_Patrones_Entrevista/03b_dp_memoization.txt
git commit -m "docs: add dp_memoization notes"
```

---

## Task 26: 06_Patrones_Entrevista/03c_dp_tabulation.txt

**Files:**
- Create: `06_Patrones_Entrevista/03c_dp_tabulation.txt`

- [ ] **Step 1: Crear archivo**

**Enfoque:** Bottom-up. Empiezas con los casos base y construyes hacia arriba llenando una tabla.

**Problemas a cubrir con solución completa:**
1. Fibonacci tabulation: `dp[i] = dp[i-1] + dp[i-2]`
2. Coin Change tabulation: misma lógica pero sin recursión
3. Optimización de espacio: Fibonacci O(n) → O(1) espacio usando solo 2 variables

**🎨 Diagrama:** tabla dp[] para Coin Change con coins=[1,2,5], amount=11.

**🎯 Tips:**
- Tabulation generalmente más eficiente que memoization (no overhead de recursión)
- Buscar si se puede reducir O(n) → O(1) espacio (solo necesitas los últimos 1-2 valores)
- "House Robber", "Climbing Stairs", "Longest Common Subsequence" → tabulation clásica

- [ ] **Step 2: Commit**

```bash
git add 06_Patrones_Entrevista/03c_dp_tabulation.txt
git commit -m "docs: add dp_tabulation notes"
```

---

## Task 27: 06_Patrones_Entrevista/04_backtracking.txt

**Files:**
- Create: `06_Patrones_Entrevista/04_backtracking.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Resolver un laberinto ✏️ a lápiz. Sigues un camino hasta que llegas a un callejón sin salida, borras (backtrack) hasta la última bifurcación, y pruebas otro camino.

**Template universal de backtracking:**
```
función backtrack(estado_actual, decisiones):
    SI llegamos al caso base:
        guardar/imprimir solución
        return
    PARA cada opción disponible:
        hacer elección (modificar estado)
        backtrack(nuevo estado, opciones restantes)
        deshacer elección (restaurar estado) ← ESTO es el "backtrack"
```

**Problemas clásicos con solución:**
1. Permutations: generar todas las permutaciones de [1,2,3]
2. Subsets: generar todos los subconjuntos
3. N-Queens simplificado: colocar N reinas en tablero N×N

**Pruning:** Agregar condiciones para no explorar ramas que ya sabemos no llevan a solución válida.

**⏱️ Varía por problema. Permutations: O(n!). Subsets: O(2^n).**

- [ ] **Step 2: Commit**

```bash
git add 06_Patrones_Entrevista/04_backtracking.txt
git commit -m "docs: add backtracking pattern notes"
```

---

## Task 28: 06_Patrones_Entrevista/05_bit_manipulation.txt

**Files:**
- Create: `06_Patrones_Entrevista/05_bit_manipulation.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Los interruptores de luz 💡 de tu casa. Cada bit es un interruptor: 1 = encendido, 0 = apagado. AND es "ambos deben estar encendidos". OR es "al menos uno encendido". XOR es "exactamente uno encendido".

**Operaciones a cubrir con ejemplos en binario:**
```
AND  (&):  5 & 3 = 101 & 011 = 001 = 1
OR   (|):  5 | 3 = 101 | 011 = 111 = 7
XOR  (^):  5 ^ 3 = 101 ^ 011 = 110 = 6
NOT  (~):  ~5    = ~101       = ...11111010 = -6 (two's complement)
Shift izq (<<): 1 << 3 = 1000 = 8   (multiplicar por 2^n)
Shift der (>>): 8 >> 2 = 10   = 2   (dividir por 2^n)
```

**Tricks clásicos con explicación:**
- `n & (n-1)`: elimina el bit más bajo. Si resultado == 0 → n es potencia de 2
- `n ^ n = 0`: XOR de un número consigo mismo = 0 (base del "Single Number")
- `n ^ 0 = n`: XOR con 0 no cambia nada
- `i & 1`: verifica si i es par (0) o impar (1)
- `n >> 1`: divide entre 2

**Problemas clásicos con solución:**
1. Single Number: encontrar el único número no duplicado en array → XOR de todos
2. Power of Two: `n > 0 && (n & (n-1)) == 0`
3. Count Set Bits (Hamming weight): Brian Kernighan's algorithm

**⏱️ Todas las operaciones O(1)**

**🎯 Tips:** Google ama bit manipulation porque demuestra que entiendes el hardware. Siempre piensa si el problema involucra duplicados, pares, o potencias de 2.

- [ ] **Step 2: Commit**

```bash
git add 06_Patrones_Entrevista/05_bit_manipulation.txt
git commit -m "docs: add bit_manipulation notes"
```

---

## Task 29: 06_Patrones_Entrevista/06_recursion_y_memoization.txt

**Files:**
- Create: `06_Patrones_Entrevista/06_recursion_y_memoization.txt`

- [ ] **Step 1: Crear archivo**

**🤔 Analogía:** Las muñecas rusas matryoshka 🪆. Abres una y adentro hay otra igual pero más pequeña. Sigues abriendo hasta llegar a la más pequeña (caso base). Cada función recursiva es una muñeca que contiene a otra más pequeña.

**Dos partes SIEMPRE presentes:**
1. Base case: condición que detiene la recursión (sin esto → stack overflow infinito)
2. Recursive case: llamada a sí misma con input más pequeño

**🎨 Diagrama call stack:**
```
factorial(4)
  → factorial(3)
    → factorial(2)
      → factorial(1)
        → return 1        ← base case
      return 1 * 1 = 1
    return 2 * 1 = 2
  return 3 * 2 = 6
return 4 * 6 = 24
```

**Cuándo recursión → iteración:**
- Si la profundidad puede ser O(n) con n grande → riesgo de stack overflow
- Si puedes mantener el estado en una variable simple → iterativo es mejor
- Tail recursion puede ser optimizada por el compilador a iteración

**Problemas recursivos clásicos:** factorial, fibonacci, tree traversal, merge sort.

**🎯 Tips:**
- Siempre define el base case PRIMERO antes de la llamada recursiva
- Escribe la "leap of faith": asume que recursive call ya funciona, úsala
- Stack overflow típico en LeetCode: recursión muy profunda en arrays grandes → pasar a DP iterativo

- [ ] **Step 2: Commit**

```bash
git add 06_Patrones_Entrevista/06_recursion_y_memoization.txt
git commit -m "docs: add recursion_y_memoization notes"
```

---

## Task 30: Actualizar INDEX.txt y README.md — estado final

**Files:**
- Modify: `INDEX.txt` (agregar fecha de última actualización y estado de completitud)
- Modify: `README.md` (misma info)

- [ ] **Step 1: Agregar sección de progreso al final de INDEX.txt**

```
──────────────────────────────────────────────────────────────────────────────
✅ ESTADO DE APUNTES
──────────────────────────────────────────────────────────────────────────────
  Última actualización: [fecha]
  Archivos completos: 23/23
  Listo para: Prep entrevistas Google-level
──────────────────────────────────────────────────────────────────────────────
```

- [ ] **Step 2: Commit final**

```bash
git add INDEX.txt README.md
git commit -m "docs: mark all notes as complete"
git push origin master
```

---

## Self-Review del Plan

**Cobertura del spec:**
- ✅ 23 archivos de contenido especificados
- ✅ INDEX.txt + README.md
- ✅ Formato 9-secciones en todos los archivos
- ✅ Spanglish definido con ejemplos
- ✅ Emojis como señales visuales
- ✅ Big-O en cada archivo
- ✅ Tips Google-level en cada archivo
- ✅ Pseudocódigo + C++17 en cada archivo
- ✅ Diagramas ASCII especificados
- ✅ Commits por archivo
- ✅ Push final al repo

**Sin placeholders:** Cada archivo tiene analogía específica, Big-O exacto, problemas concretos de entrevista.

**Orden de implementación:** Sigue el orden del spec (Fundamentos → Lineales → No Lineales → Grafos → Ordenamiento → Búsqueda → Patrones).
