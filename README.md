Predicción del Nivel de PIB: Comparativa de Modelos y PCA
Este repositorio contiene la etapa final de un proyecto de ciencia de datos cuyo objetivo es predecir el nivel de Producto Interno Bruto (PIB) de distintos países utilizando datos del Banco Mundial.

El núcleo de este análisis es comparar el rendimiento de modelos de clasificación (Regresión Logística y Random Forest) entrenados con datos originales frente a modelos entrenados con datos transformados mediante Análisis de Componentes Principales (PCA).

📋 Descripción del Proyecto
El flujo de trabajo automatizado en este cuaderno realiza las siguientes tareas:

Ingesta de Datos: Descarga datos actualizados (año 2023) directamente desde la API del Banco Mundial (wbgapi).

Limpieza y Preprocesamiento:

Eliminación de columnas con >15% de datos faltantes.

Imputación de valores faltantes (Mediana para numéricos, Moda para categóricos).

Discretización del Target: La variable objetivo (PIB PPP) se convierte en 5 categorías: Low, Medium-Low, Medium, Medium-High, High.

Reducción de Dimensionalidad: Aplicación de PCA sobre datos estandarizados para reducir las características originales a 7 componentes principales (explicando ~82.5% de la varianza).

Modelado Predictivo: Entrenamiento de modelos de clasificación:

Regresión Logística.

Random Forest.

Evaluación Comparativa: Análisis de métricas (Accuracy, Precision, Recall, F1-Score) y Matrices de Confusión para determinar el impacto de la reducción de dimensionalidad.

🛠️ Requisitos Previos
Para ejecutar este código, necesitas un entorno de Python 3. Se recomienda Google Colab o Jupyter Notebook. Las librerías necesarias son:

wbgapi (API del Banco Mundial)

pandas

numpy

scikit-learn

matplotlib

seaborn

Instalación de dependencias
La primera celda del cuaderno suele encargarse de la instalación, pero puedes hacerlo manualmente con:

Bash

pip install wbgapi pandas numpy scikit-learn matplotlib seaborn
🚀 Instrucciones de Ejecución
Sigue estos pasos para reproducir el análisis:

Abrir el Notebook: Carga el archivo .ipynb en Google Colab o tu entorno local.

Instalar Librerías: Ejecuta la primera celda de código para instalar wbgapi (si estás en Colab, es necesario).

Ejecutar Secuencialmente: Es crucial ejecutar las celdas en orden (de arriba a abajo), ya que el proceso construye el dataset paso a paso:

Las primeras celdas descargan y limpian los datos en bruto (df_wb_raw).

Las celdas intermedias realizan la estandarización y el cálculo de PCA.

Las celdas finales entrenan los modelos y generan los gráficos de evaluación.

Interpretar Resultados: Al final del cuaderno, se imprime un DataFrame resumen comparando la precisión de los 4 escenarios (Logística/RF con datos Originales/PCA).

📊 Resumen de Resultados
Basado en la ejecución actual del código, se observan las siguientes conclusiones:

Mejor Modelo: El algoritmo Random Forest utilizando los datos originales obtuvo el mejor desempeño (aprox. 80% de precisión).

Impacto de PCA:

Regresión Logística: Se benefició ligeramente del uso de PCA, sugiriendo que la reducción de ruido ayudó al modelo lineal.

Random Forest: Su rendimiento disminuyó drásticamente al usar PCA. Esto indica que el algoritmo de árboles aprovecha mejor la complejidad y las relaciones no lineales de las variables originales que las proyecciones lineales del PCA.

📁 Estructura de Datos
El script descarga indicadores relacionados con:

Economía (PIB, Exportaciones, Valor agregado por sector).

Demografía (Población, Crecimiento urbano).

Sociales (Desempleo, Educación).

Tecnología (Uso de internet).

Nota: La variable objetivo es NY.GDP.MKTP.PP.KD.


NameError: Se intentó usar la función de descarga antes de definirla. Solución: Ejecutar las celdas en orden secuencial.
