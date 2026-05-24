# Instrucciones para Gemini CLI — DSA Notes (Versión LaTeX)

## Tu misión
Crear/Convertir 30 archivos de apuntes de Data Structures & Algorithms siguiendo un plan detallado.
Eres el implementador. No diseñes nada — el diseño ya está decidido.
Solo ejecuta task por task, exactamente como se especifica.

---

## PASO 1 — Lee estos archivos antes de hacer CUALQUIER cosa

```
D:\Codigo Abierto\ApuntesData Structures and Alg\docs\superpowers\specs\2026-05-23-dsa-notes-design.md
D:\Codigo Abierto\ApuntesData Structures and Alg\docs\superpowers\plans\2026-05-23-latex-conversion.md  
```

El spec tiene el diseño completo.
El plan de conversión tiene las tasks para pasar a .tex.

---

## PASO 2 — Reglas que NUNCA puedes romper

### Formato de cada .tex
Cada archivo debe ser un documento LaTeX (.tex) que use los comandos definidos en `template.tex`. 
Debe tener estas 9 secciones (usando macros LaTeX):

```latex
\section{TEMA: [nombre]}
\subsection{CATEGORÍA: [carpeta]}

\quees{[explicación nivel niño]}

\dichodeotraforma{[complemento técnico]}

\diagrama{
\begin{verbatim}
[ASCII art]
\end{verbatim}
}

\comofunciona{[paso a paso]}

\complejidad{
\begin{tabular}{|l|l|l|}
\hline
Operación & Tiempo & Espacio \\
\hline
... & ... & ... \\
\hline
\end{tabular}
}

\entrevistas{[tips]}

\resumen{[bullets]}

\begin{lstlisting}[language=C++]
[Código C++17]
\end{lstlisting}
```

---

## PASO 5 — Verificación RÁPIDA en todos los archivos
```powershell
Select-String -Path "D:\Codigo Abierto\ApuntesData Structures and Alg\**\*.tex" -Pattern "resumen" -Recurse
```

Si falta algún archivo o sección -> créalo antes de terminar.

---

## PASO 6 — Al terminar

Haz push al repo remoto:
```bash
git -C "D:\Codigo Abierto\ApuntesData Structures and Alg" push origin master
```
