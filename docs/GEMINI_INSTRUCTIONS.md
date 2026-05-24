# Instrucciones para Gemini CLI — DSA Notes

## Tu misión
Crear 30 archivos de apuntes de Data Structures & Algorithms siguiendo un plan detallado.
Eres el implementador. No diseñes nada — el diseño ya está decidido.
Solo ejecuta task por task, exactamente como se especifica.

---

## PASO 1 — Lee estos archivos antes de hacer CUALQUIER cosa

```
D:\Codigo Abierto\ApuntesData Structures and Alg\docs\superpowers\specs\2026-05-23-dsa-notes-design.md
D:\Codigo Abierto\ApuntesData Structures and Alg\docs\superpowers\plans\2026-05-23-dsa-notes-implementation.md
```

El spec tiene el diseño completo.
El plan tiene las 30 tasks con instrucciones exactas.

NO empieces a escribir archivos sin leer ambos documentos primero.

---

## PASO 2 — Reglas que NUNCA puedes romper

### Formato de cada .txt
Cada archivo debe tener EXACTAMENTE estas 9 secciones en este orden:

```
════════════════════════════════════════════════════════════════
🗂️  TEMA: [nombre]
📁  CATEGORÍA: [carpeta]
════════════════════════════════════════════════════════════════

🤔 ¿QUÉ ES?
──────────────────────────────────────────────────────────────
[explicación]

💬 DICHO DE OTRA FORMA
──────────────────────────────────────────────────────────────
[complemento técnico]

🎨 DIAGRAMA
──────────────────────────────────────────────────────────────
[ASCII art]

⚙️ ¿CÓMO FUNCIONA? (Operaciones principales)
──────────────────────────────────────────────────────────────
[paso a paso]

📝 PSEUDOCÓDIGO
──────────────────────────────────────────────────────────────
[pseudocódigo comentado]

💻 CÓDIGO C++
──────────────────────────────────────────────────────────────
[C++17 con comentarios]

⏱️ COMPLEJIDAD (Big-O)
──────────────────────────────────────────────────────────────
[tabla]

🎯 EN ENTREVISTAS (Tips Google-level)
──────────────────────────────────────────────────────────────
[tips]

📋 RESUMEN RÁPIDO
──────────────────────────────────────────────────────────────
[bullets]
════════════════════════════════════════════════════════════════
```

### Idioma
- Explicaciones: ESPAÑOL
- Términos técnicos: INGLÉS sin traducir (stack, node, pointer, heap, edge, traversal, merge, pivot, linked list, etc.)
- Estilo: Spanglish natural
- Emojis: abundantes, como señales visuales

### Sección ¿QUÉ ES?
SIEMPRE como si le explicaras a un niño de 12 años.
Analogías simples. Sin asumir conocimiento previo.
Mínimo 3 párrafos. Emojis dentro del texto.

### Sección DICHO DE OTRA FORMA
Misma idea pero en tono de dev a dev.
Conecta la analogía del niño con el lenguaje real de industria.

### Código C++
- C++17 standard
- Standalone: debe poder compilar solo con `g++ -std=c++17 archivo.cpp`
- CADA línea no obvia tiene comentario en español
- Comentarios explican el POR QUÉ, no solo el QUÉ
- Identificadores en inglés, comentarios en español

---

## PASO 3 — Cómo ejecutar el plan

El plan tiene Tasks del 0 al 30. Sigue este proceso para CADA task:

1. Lee el task completo en el plan
2. Crea el archivo en la ruta exacta especificada
3. Escribe el contenido completo (NO dejes secciones vacías o con "TODO")
4. Ejecuta el comando git del Step de Commit en el task
5. Pasa al siguiente task

### Rutas de archivos
Todos los archivos van dentro de:
```
D:\Codigo Abierto\ApuntesData Structures and Alg\
```

### Comandos git
Después de crear cada archivo, haz commit con el mensaje exacto que dice el plan.
Ejemplo:
```bash
git -C "D:\Codigo Abierto\ApuntesData Structures and Alg" add 00_Fundamentos/01_big_o_notation.txt
git -C "D:\Codigo Abierto\ApuntesData Structures and Alg" commit -m "docs: add big_o_notation notes"
```

---

## PASO 4 — Contenido específico por archivo

El plan ya especifica el contenido de cada archivo. Úsalo como guía base.
Para cada archivo, el plan indica:
- Qué analogía usar en ¿QUÉ ES?
- Qué operaciones cubrir en ¿CÓMO FUNCIONA?
- Los valores exactos de Big-O para la tabla
- Los tips específicos para entrevistas Google

Si el plan dice "usar analogía de pila de platos" → úsala exactamente.
Si el plan dice "O(log n) promedio, O(n) peor caso" → esos son los valores.

Para el CÓDIGO C++: el plan describe qué implementar.
Tú escribes el código completo funcional con todos los comentarios.

---

## PASO 5 — Verificación antes de terminar

Antes de declarar que terminaste, verifica:

```bash
# Contar archivos .txt creados (debe ser 23 + INDEX.txt = 24)
Get-ChildItem "D:\Codigo Abierto\ApuntesData Structures and Alg" -Recurse -Filter "*.txt" | Measure-Object

# Ver commits hechos
git -C "D:\Codigo Abierto\ApuntesData Structures and Alg" log --oneline

# Verificar que cada archivo tiene las 9 secciones
# Buscar la sección RESUMEN RÁPIDO en todos los archivos
Select-String -Path "D:\Codigo Abierto\ApuntesData Structures and Alg\**\*.txt" -Pattern "RESUMEN RÁPIDO" -Recurse
```

Si falta algún archivo o sección → créalo antes de terminar.

---

## PASO 6 — Al terminar

Haz push al repo remoto:
```bash
git -C "D:\Codigo Abierto\ApuntesData Structures and Alg" push origin master
```

Luego reporta:
- Cuántos archivos creaste
- Si hubo algún problema
- Qué tasks completaste

---

## Errores comunes a EVITAR

❌ NO dejes secciones con texto de placeholder ("TODO", "aquí va...", "[completar]")
❌ NO traduzques términos técnicos (NO "montón" en vez de "heap")
❌ NO hagas commits de múltiples archivos juntos — uno por uno
❌ NO omitas la sección DIAGRAMA aunque sea difícil — haz ASCII art
❌ NO escribas código que no compile
❌ NO ignores el orden de las secciones

✅ SÍ usa emojis dentro del texto explicativo
✅ SÍ escribe analogías largas y detalladas en ¿QUÉ ES?
✅ SÍ verifica que el código C++ incluye el `#include` necesario
✅ SÍ menciona referencias cruzadas cuando aplique (🔗 Ver: archivo_relacionado.txt)
