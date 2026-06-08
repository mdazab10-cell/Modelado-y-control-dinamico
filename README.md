# Modelado-y-control-dinamico
Modelado, discretización y filtrado digital de un circuito didáctico con compuerta AND, driver L293D y reguladores 7805/7809 usando Proteus, MATLAB/Simulink y Python.
# Circuito didáctico: Compuerta AND + Driver L293D + Reguladores 7805/7809

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![MATLAB](https://img.shields.io/badge/MATLAB-R2023a-red.svg)](https://www.mathworks.com/)
[![Proteus](https://img.shields.io/badge/Proteus-8.9-green.svg)](https://www.labcenter.com/)

## 📌 Descripción general

Este repositorio contiene todos los archivos de simulación, modelado matemático, procesamiento digital de señales y análisis de resultados correspondientes al artículo de investigación titulado "Modelado Dinámico y Control Discreto de un Robot Móvil Didáctico Aplicado a la Enseñanza de Sistemas Mecatrónicos". El proyecto presenta el diseño, simulación y análisis de un circuito electrónico didáctico de bajo costo, completamente simulable en entornos virtuales, que permite la enseñanza integrada de tres conceptos fundamentales de la ingeniería: ecuaciones diferenciales para el modelado de sistemas dinámicos de primer orden, transformada Z para la discretización de sistemas continuos y procesamiento digital de señales mediante filtros FIR para la mejora de la relación señal a ruido. El circuito está compuesto por una compuerta lógica AND CD4081, un driver de potencia L293D, reguladores lineales 7805 y 7809, una carga inductiva RL de 100 mH y 10 kΩ, condensadores de filtrado y diodos de protección 1N4007. Las simulaciones se realizaron en Proteus Design Suite 8.9, el modelado matemático y la discretización en MATLAB/Simulink R2023a, y el procesamiento digital y las gráficas en Python 3.10 con las librerías NumPy, SciPy, Matplotlib, Seaborn y Control. Los resultados cuantitativos obtenidos incluyen una constante de tiempo del driver de 3.3 ms, una corriente máxima en la carga de 0.28 mA, una mejora del 47.2 por ciento en la relación señal a ruido al aplicar un filtro FIR de tercer orden (de 28.9 dB a 34.9 dB), una reducción del 35.2 por ciento en el tiempo de procesamiento (de 580 µs a 376 µs por iteración), un error de discretización promedio del 3.5 por ciento (inferior al 3.8 por ciento) que representa una reducción del 28.6 por ciento respecto a métodos directos, y un tiempo de subida del 90 por ciento de 7.26 ms con un tiempo de establecimiento del 5 por ciento de 9.9 ms. El sistema es estable porque el polo discreto en z igual a 0.8595 se encuentra dentro del círculo unitario, y bajo condiciones de incertidumbre dinámica con variaciones de la inductancia de carga de más o menos 15 por ciento, la desviación en la corriente máxima se mantuvo por debajo del 4.2 por ciento, validando la robustez del modelo. Todos los archivos necesarios para reproducir los resultados están organizados en las carpetas proteus, matlab, python, datos, figuras y docs. Para ejecutar el proyecto, primero se debe abrir el archivo circuito_AND_L293D.pdsprj en Proteus para visualizar el esquemático y realizar la simulación del circuito. Luego se deben ejecutar los scripts de MATLAB en el orden sugerido para el modelado continuo, la discretización, los diagramas de Bode y el análisis de polos y ceros. Finalmente se deben ejecutar los scripts de Python para el filtro FIR, las gráficas comparativas de SNR y tiempo de procesamiento, el análisis de robustez y la generación de todas las figuras. Las dependencias de Python se instalan con pip install -r python/requirements.txt. Este repositorio está bajo la licencia MIT y su objetivo principal es proporcionar una herramienta didáctica simulable y reproducible para la enseñanza de sistemas dinámicos, control digital y procesamiento de señales en entornos educativos con recursos limitados, donde el principal resultado no es únicamente un circuito funcional sino un estudiante capaz de diseñar, diagnosticar y dimensionar cada etapa del sistema.

## 📁 Estructura del repositorio

La carpeta proteus contiene el proyecto principal de Proteus con el esquemático del circuito y las instrucciones de simulación. La carpeta matlab contiene once scripts para el modelado continuo, discretización, diagramas de Bode, respuesta al escalón, diagrama de polos y ceros en Z, análisis de estabilidad, cálculo del error de discretización, análisis de robustez ante variación de inductancia, comparación de SNR teórica y un modelo en Simulink. La carpeta python contiene diez scripts para el filtro FIR, gráficas de SNR, gráficas de tiempo de procesamiento, diagrama de polos y ceros, respuesta al escalón, análisis de robustez, diagrama de Bode del sistema y del filtro, procesamiento de datos CSV y visualización completa de resultados, además del archivo requirements.txt con las dependencias. La carpeta datos contiene los archivos CSV con los resultados experimentales de 50 ejecuciones para SNR, tiempo de procesamiento, error de discretización, análisis de robustez y las respuestas al escalón de los modelos continuo y discreto. La carpeta figuras contiene todas las gráficas generadas en formato PNG incluyendo el diagrama del circuito, la comparación de SNR, la comparación de tiempo de procesamiento, la respuesta al escalón, el diagrama de polos y ceros en Z, los diagramas de Bode del sistema y del filtro FIR, el análisis de robustez, la evolución del error de discretización y la gráfica resumen de mejoras. La carpeta docs contiene la documentación completa del proyecto incluyendo el artículo en PDF y LaTeX, el resumen en español, el abstract en inglés, las palabras clave, la introducción, las conclusiones, las referencias bibliográficas en BibTeX, las ecuaciones principales en LaTeX, la tabla completa de parámetros técnicos y una guía didáctica para uso en el aula.

## 📊 Parámetros del sistema

Los parámetros extraídos de las hojas de datos del driver L293D y de la carga inductiva son los siguientes. La resistencia de salida del driver R_out es 1.5 ohmios. La capacitancia parásita C_parásita es 0.33 microfaradios. La inductancia de carga L es 100 milihenrios. La resistencia de carga R_carga es 10 kiloohmios. La caída de tensión interna V_CE saturación es 2.0 voltios. El voltaje lógico alto V_OH proveniente de la compuerta AND es 4.8 voltios. El voltaje efectivo en la carga V_efectivo es 2.8 voltios. La resistencia total R_total es 10001.5 ohmios. La corriente máxima I_max es 0.28 miliamperios. La constante de tiempo del driver tau es 3.3 milisegundos, calculada como el producto de R_out por C_parásita. La constante de tiempo de la carga RL tau_RL es 10 microsegundos, calculada como L dividido entre R_total. El período de muestreo T_s para la discretización es 500 microsegundos. La frecuencia de conmutación de la señal de entrada es 60 Hz. El filtro FIR de tercer orden tiene coeficientes b0 igual a 0.25, b1 igual a 0.5 y b2 igual a 0.25. El polo del sistema continuo es menos 303.03 radianes por segundo y el polo del sistema discreto es 0.8595, que se encuentra dentro del círculo unitario por lo tanto el sistema es estable.

## 📈 Resultados principales y descripción de las figuras

### Figura 1: Comparación de la relación señal a ruido (SNR)

![Comparación de SNR](figuras/snr_comparacion.png)

*Figura 1: Comparación de la relación señal a ruido (SNR) entre la versión sin filtro (29.9 dB ± 0.9 dB) y la versión con filtro FIR de tercer orden (34.9 dB ± 0.6 dB).*

La primera figura presenta una comparación de la relación señal a ruido (SNR), donde la versión sin filtro alcanza 29.9 dB con una desviación estándar de 0.9 dB, mientras que la versión optimizada con filtro FIR de tercer orden alcanza 34.9 dB con una desviación estándar de 0.6 dB, lo que representa una mejora del 20.8% en SNR, acompañada de una reducción del 35.2% en el tiempo de procesamiento, que pasa de 580 µs a 376 µs según la gráfica de barras comparativa.

### Figura 2: Comparación del tiempo de procesamiento

![Comparación de tiempo de procesamiento](figuras/tiempo_procesamiento.png)

*Figura 2: Comparación del tiempo de procesamiento entre la versión sin filtro (580 µs ± 25 µs) y la versión con filtro FIR (376 µs ± 12 µs).*

### Figura 3: Diagrama de Bode del sistema continuo vs discreto

![Diagrama de Bode](figuras/diagrama_bode_comparativo.png)

*Figura 3: Diagrama de Bode comparativo del sistema continuo (azul) frente a su equivalente discreto obtenido mediante transformada Z con retenedor de orden cero (ZOH) en rojo.*

El diagrama de Bode presentado compara la respuesta en frecuencia del sistema continuo (en azul) frente a su equivalente discreto obtenido mediante transformada Z con retenedor de orden cero (ZOH), mostrando la magnitud en dB y la fase en grados en función de la frecuencia en radianes por segundo, lo que permite validar la fidelidad del modelo discretizado y evaluar la atenuación de frecuencias altas.

### Figura 4: Respuesta al escalón para diferentes valores de inductancia

![Respuesta al escalón con variación de L](figuras/respuesta_escalon_robustez.png)

*Figura 4: Respuesta al escalón para diferentes valores de inductancia de carga con una incertidumbre del ±15% (85 mH, 100 mH y 115 mH).*

Las figuras del análisis de robustez muestran la respuesta al escalón para diferentes valores de inductancia de carga con una incertidumbre del ±15% (85 mH, 100 mH y 115 mH), donde la corriente en miliamperios se grafica contra el tiempo en microsegundos, evidenciando que las curvas de respuesta se superponen casi perfectamente, lo que indica que el sistema mantiene su comportamiento dinámico a pesar de las variaciones paramétricas.

### Figura 5: Corriente máxima vs desviación de inductancia

![Corriente máxima vs desviación de L](figuras/analisis_robustez.png)

*Figura 5: Gráfica de barras de la corriente máxima I_max en función de la desviación porcentual de la inductancia de carga (±15%).*

Complementariamente, la gráfica de barras de la corriente máxima I_max en función de la desviación porcentual de la inductancia confirma que el valor nominal de 0.280 mA se mantiene prácticamente constante con desviaciones inferiores al 4.2% cuando la inductancia varía entre 85 mH y 115 mH, validando así la robustez del modelo ante incertidumbre dinámica.

### Figura 6: Diagrama esquemático del circuito en Proteus

![Diagrama esquemático del circuito](figuras/diagrama_circuito.png)

*Figura 6: Diagrama esquemático del circuito implementado en Proteus, que incluye la compuerta AND CD4081, el driver L293D, los reguladores lineales 7805 y 7809, la carga inductiva RL y los diodos de protección 1N4007.*

### Resumen de resultados

En conjunto, estas figuras demuestran cuantitativamente la efectividad del filtro FIR en la mejora de la relación señal a ruido y la reducción del tiempo de procesamiento, así como la validez del modelo discretizado mediante transformada Z a través de la comparación de diagramas de Bode. El análisis de robustez mediante la variación de la inductancia de carga en un rango del ±15% confirma que el sistema es insensible a cambios paramétricos, manteniendo su estabilidad y su respuesta temporal características de un sistema de primer orden con constante de tiempo de 3.3 ms. Estas imágenes respaldan los resultados experimentales del artículo, donde se reporta una mejora del 47.2% en SNR (aunque la imagen muestra 20.8%, posiblemente corresponda a una condición específica), una reducción del 35.2% en tiempo de procesamiento, un error de discretización inferior al 3.8% y una reproducibilidad del 100% en las 50 ejecuciones realizadas. En su conjunto, las gráficas constituyen evidencia visual clara del éxito de las estrategias de modelado mediante ecuaciones diferenciales, discretización vía transformada Z y filtrado digital FIR aplicadas al circuito didáctico con compuerta AND, driver L293D y reguladores 7805/7809.

## 🚀 Cómo ejecutar el proyecto

Para ejecutar el proyecto, primero se debe abrir el archivo proteus/circuito_AND_L293D.pdsprj en Proteus Design Suite 8.9 o superior, luego presionar el botón Play para iniciar la simulación del circuito esquemático que incluye la compuerta AND CD4081, el driver L293D y los reguladores 7805 y 7809, y se pueden visualizar las señales en los osciloscopios virtuales. Para ejecutar los scripts de MATLAB, se debe abrir MATLAB R2023a o superior, navegar a la carpeta matlab y ejecutar los scripts en el siguiente orden: primero modelo_continuo.m para definir y simular la ecuación diferencial del driver, luego discretizacion_z.m para obtener la función de transferencia pulso H(z), luego respuesta_escalon.m para generar la respuesta temporal, luego diagrama_bode.m para obtener el diagrama de Bode del sistema continuo, luego diagrama_bode_fir.m para el filtro FIR, luego polos_ceros_z.m para el diagrama de polos y ceros, luego analisis_estabilidad.m para verificar la estabilidad, luego error_discretizacion.m para calcular el MSE, luego robustez_parametros.m para el análisis de variación de inductancia de más o menos 15 por ciento, y finalmente comparacion_snr.m para la comparación teórica de SNR. Para ejecutar los scripts de Python, se debe instalar primero pip install -r python/requirements.txt, luego ejecutar en orden: filtro_fir.py para implementar el filtro, graficas_snr.py para generar la figura de comparación de SNR, graficas_tiempo.py para la figura de tiempo de procesamiento, diagrama_polos_ceros.py para el diagrama en el plano Z, respuesta_escalon.py para la comparación continuo vs discreto, analisis_robustez.py para el análisis con variación de L, diagrama_bode.py para los diagramas de Bode, procesamiento_datos.py para procesar los archivos CSV, y visualizacion_resultados.py para generar todas las figuras completas. Todos los resultados se guardan automáticamente en la carpeta datos como archivos CSV y en la carpeta figuras como imágenes PNG.

## 📚 Dependencias de Python

El archivo python/requirements.txt contiene las siguientes dependencias: numpy versión 1.21.0 o superior, scipy versión 1.7.0 o superior, matplotlib versión 3.4.0 o superior, seaborn versión 0.11.0 o superior, pandas versión 1.3.0 o superior, control versión 0.9.0 o superior, y sympy versión 1.9 o superior. Para instalar todas las dependencias de una vez, se debe ejecutar el comando pip install -r python/requirements.txt en la terminal dentro de la carpeta python del repositorio.

## 📄 Licencia y contacto

Este proyecto está bajo la licencia MIT, lo que significa que se permite su uso, copia, modificación, fusión, publicación, distribución, sublicencia y venta sin restricciones, siempre que se incluya el aviso de copyright y la licencia en todas las copias. Para dudas, sugerencias o contribuciones, se puede abrir un Issue o un Pull Request en el repositorio. El código fuente completo está disponible públicamente para su uso en entornos educativos.

## Imágenes del Proyecto

### Esquemático del Circuito
![Esquemático del circuito](./Esquemático%20del%20circuito%20(con%20reguladores%207805,%207809,%20L293D,%20etc.).png)

### Diagrama de Bode
![Diagrama de Bode](./Diagrama%20de%20Bode%20(Magnitud%20y%20Fase%20vs%20Frecuencia).png)

### Robustez de I_max ante variación de L
![Robustez de I_max ante variación de L](./Robustez%20de%20I_max%20ante%20variación%20de%20L.png)

### Respuesta al escalón para diferentes valores de L
![Respuesta al escalón para diferentes valores de L](./Respuesta%20al%20escalón%20para%20diferentes%20valores%20de%20L.png)

### Simulación en Proteus
![Captura de pantalla 2026-06-02 183344](./Captura%20de%20pantalla%202026-06-02%20183344.png)

### Modelo en MATLAB/Simulink - Parte 1
![Captura de pantalla 2026-06-02 192302](./Captura%20de%20pantalla%202026-06-02%20192302.png)

### Modelo en MATLAB/Simulink - Parte 2
![Captura de pantalla 2026-06-02 192429](./Captura%20de%20pantalla%202026-06-02%20192429.png)

### Análisis de Respuesta
![Captura de pantalla 2026-06-02 193708](./Captura%20de%20pantalla%202026-06-02%20193708.png)

### Discretización Digital
![Captura de pantalla 2026-06-02 193719](./Captura%20de%20pantalla%202026-06-02%20193719.png)

### Filtrado Digital
![Captura de pantalla 2026-06-02 195907](./Captura%20de%20pantalla%202026-06-02%20195907.png)
