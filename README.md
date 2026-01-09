Excelente pregunta. He revisado ambas secciones y entiendo tu preocupación: al ser estructuras isoestructurales (mismo grupo espacial I4₁/amd), es fácil caer en la repetición. Te propongo una estrategia para que la sección 3.2 sea comparativa y no descriptiva.

---

## **Estrategia: De la descripción a la comparación**

### **Enfoque actual (repetitivo):**
> "El Xenótimo tiene tetraedros PO₄... tiene dodecaedros YO₈... los poliedros se conectan..."

### **Enfoque propuesto (comparativo):**
> "El Xenótimo, isoestructural con el Zircón, presenta diferencias cuantitativas derivadas de la sustitución Zr⁴⁺/Si⁴⁺ → Y³⁺/P⁵⁺ que afectan las distancias de enlace y la distorsión poliédrica..."

---

## **Estructura sugerida para la Sección 3.2**

### **1. Párrafo introductorio: establecer la relación**

En lugar de repetir la descripción del grupo espacial, enfatiza la **sustitución isovalente** y sus consecuencias:

```latex
\section{Xenótimo (\texorpdfstring{\ce{YPO4}}{YPO4})}

El Xenótimo cristaliza en el mismo grupo espacial que el Zircón ($I4_1/amd$), 
constituyendo un ejemplo de \textbf{isoestructuralismo} derivado de la sustitución 
heterovalente acoplada \ce{Zr^{4+} + Si^{4+} -> Y^{3+} + P^{5+}}. Esta sustitución 
mantiene la neutralidad de carga pero introduce diferencias significativas en las 
distancias de enlace y la geometría poliédrica, consecuencia directa de los distintos 
radios iónicos: $r(\ce{Y^{3+}}) = \SI{1.019}{\angstrom}$ vs. 
$r(\ce{Zr^{4+}}) = \SI{0.84}{\angstrom}$ en coordinación 8.
```

---

### **2. Tabla comparativa (elemento central)**

En lugar de repetir tablas individuales, crea una **tabla comparativa** que destaque las diferencias:

```latex
\begin{table}[H]
  \centering
  \caption{Comparación de parámetros estructurales entre Zircón y Xenótimo.}
  \label{tab:comparacion_zircon_xenotimo}
  \begin{tabular}{l c c c}
    \toprule
    \textbf{Parámetro} & \textbf{Zircón} & \textbf{Xenótimo} & \textbf{$\Delta$ (\%)} \\
    \midrule
    \multicolumn{4}{l}{\textit{Parámetros de celda}} \\
    $a = b$ (\si{\angstrom}) & 6.62 & 6.89 & +4.1 \\
    $c$ (\si{\angstrom}) & 6.00 & 6.03 & +0.5 \\
    $V$ (\si{\cubic\angstrom}) & 286.98 & 286.27 & −0.2 \\
    \midrule
    \multicolumn{4}{l}{\textit{Tetraedro $TO_4$ (T = Si, P)}} \\
    Distancia T–O (\si{\angstrom}) & 1.626 & 1.533 & −5.7 \\
    Varianza angular (\si{\degree\squared}) & 97.71 & 107.96 & +10.5 \\
    Volumen (\si{\cubic\angstrom}) & 2.13 & 1.84 & −13.6 \\
    \midrule
    \multicolumn{4}{l}{\textit{Dodecaedro $MO_8$ (M = Zr, Y)}} \\
    Distancia M–O corta (\si{\angstrom}) & 2.13 & 2.31 & +8.5 \\
    Distancia M–O larga (\si{\angstrom}) & 2.27 & 2.38 & +4.8 \\
    Índice de distorsión (BLD) & 0.0318 & 0.0149 & −53.1 \\
    Volumen (\si{\cubic\angstrom}) & 22.13 & 25.56 & +15.5 \\
    \bottomrule
  \end{tabular}
\end{table}
```

---

### **3. Texto analítico (no descriptivo)**

Después de la tabla, **interpreta** los datos en lugar de repetir descripciones:

```latex
Los datos de la Tabla \ref{tab:comparacion_zircon_xenotimo} revelan tendencias 
cristaloquímicas coherentes con la sustitución catiónica:

\begin{itemize}
  \item \textbf{Expansión anisotrópica de la celda:} El mayor radio del \ce{Y^{3+}} 
        expande preferentemente el parámetro $a$ (+4.1\%), mientras que $c$ permanece 
        casi invariante (+0.5\%). Esto refleja la orientación de los dodecaedros 
        \ce{MO8} en el plano $ab$.
  
  \item \textbf{Contracción del tetraedro:} Paradójicamente, el tetraedro \ce{PO4} 
        es más pequeño que el \ce{SiO4} (−13.6\% en volumen), consecuencia de la 
        mayor carga del \ce{P^{5+}} que acorta los enlaces P–O. Sin embargo, la 
        mayor varianza angular indica una distorsión geométrica más pronunciada.
  
  \item \textbf{Regularización del dodecaedro:} El índice de distorsión del 
        \ce{YO8} es aproximadamente la mitad del \ce{ZrO8}, sugiriendo que el 
        mayor tamaño del \ce{Y^{3+}} permite una geometría más regular del 
        bisdisfenoide.
\end{itemize}
```

---

### **4. Figuras: selección estratégica**

No repitas todas las proyecciones. Incluye solo las que aporten información **comparativa**:

| **Figura** | **¿Incluir?** | **Justificación** |
|------------|---------------|-------------------|
| Proyecciones a, b, c de la celda unitaria | ✅ Sí | Necesarias para mostrar la estructura, pero con caption comparativo |
| Tetraedro PO₄ individual | ⚠️ Opcional | Solo si muestras diferencia visual vs. SiO₄ |
| Dodecaedro YO₈ individual | ⚠️ Opcional | Ídem |
| Proyecciones de poliedros (ejes a, b, c) | ❌ Reducir | Incluir solo **una** proyección representativa |
| **Figura comparativa lado a lado** | ✅ **Nueva** | Muy recomendada (ver abajo) |

#### **Figura comparativa sugerida:**

```latex
\begin{figure}[H]
  \centering
  \begin{subfigure}[b]{0.45\linewidth}
    \includegraphics[width=\linewidth]{Imagenes/1_ZIRCON/POLYHEDRA/ZIRCON_c0.png}
    \caption{Zircón: proyección [001]}
  \end{subfigure}
  \hfill
  \begin{subfigure}[b]{0.45\linewidth}
    \includegraphics[width=\linewidth]{Imagenes/2_XENOTIMO/POLYHEDRA/XENOTIMO_c.png}
    \caption{Xenótimo: proyección [001]}
  \end{subfigure}
  \caption{Comparación de la proyección a lo largo del eje $c$ entre Zircón y 
           Xenótimo. A pesar del isoestructuralismo, se aprecia la expansión 
           de los dodecaedros \ce{YO8} (verde) respecto a los \ce{ZrO8}.}
  \label{fig:comparacion_zircon_xenotimo}
\end{figure}
```

---

### **5. Conexión con aplicaciones (cierre de sección)**

Termina conectando las diferencias estructurales con las propiedades:

```latex
Estas diferencias estructurales tienen implicaciones directas en las propiedades 
físicas y aplicaciones de ambos materiales. La mayor regularidad del poliedro 
\ce{YO8} en el Xenótimo, combinada con la flexibilidad del sitio para acomodar 
otros lantánidos pesados (Tb–Lu), fundamenta su uso como matriz para la 
inmovilización de actínidos en residuos nucleares \cite{rafiuddin_review_2022}. 
La contracción lantánida permite una modulación sistemática de los parámetros 
de celda a lo largo de la serie \ce{LnPO4}.
```

---

## **Resumen de la estrategia**

| Elemento | Sección 3.1 (Zircón) | Sección 3.2 (Xenótimo) |
|----------|----------------------|------------------------|
| **Enfoque** | Descriptivo completo | Comparativo |
| **Grupo espacial** | Explicación detallada | Referencia breve ("isoestructural con...") |
| **Tabla de coordenadas** | Completa | Mantener (necesaria para Z diferente) |
| **Tabla de distorsión** | Individual | **Comparativa** con Zircón |
| **Figuras de poliedros** | Todas | Reducir + añadir figura comparativa |
| **Texto** | Descripción | Análisis de diferencias |

---

¿Te gustaría que te ayude a redactar el texto completo de la sección 3.2 siguiendo esta estructura, o prefieres que te prepare un borrador como Pull Request?
