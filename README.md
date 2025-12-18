Análisis de Datos del Banco Mundial (PCA y Clasificación)
Este repositorio contiene un cuaderno de Jupyter (.ipynb) diseñado para extraer indicadores económicos directamente desde la base de datos del Banco Mundial, procesarlos mediante técnicas de reducción de dimensionalidad y preparar un modelo de análisis de datos.


🚀 Descripción del Proyecto
El objetivo principal es construir una base de datos en memoria (df) que permita analizar la relación entre el PIB real y otras variables macroeconómicas como el desempleo. El flujo de trabajo incluye la descarga automatizada, estandarización de variables y un Análisis de Componentes Principales (PCA).


🛠️ Requisitos previos
Para ejecutar este código correctamente, asegúrate de cumplir con lo siguiente:


Internet: Conexión activa para realizar peticiones a la API.



Google Colab: Se recomienda el uso de esta plataforma para evitar configuraciones locales.


Librerías: El código instala y utiliza wbgapi, pandas, numpy, matplotlib y scikit-learn.



📋 Pasos del Proceso
1. Extracción de Datos
Se utiliza una función personalizada llamada descargar_en_chunks para gestionar la descarga de grandes volúmenes de datos sin saturar la conexión.


Indicadores: Se extraen variables como el PIB real (PPP constante) y el Desempleo total.


Rango: Datos históricos desde el año 2000 hasta el 2023.


2. Estandarización y PCA
Para un análisis justo, los datos numéricos se escalan (media 0 y varianza 1). Luego, se aplica el Análisis de Componentes Principales (PCA) para:

Reducir el número de variables originales.

Analizar la varianza explicada acumulada.

Seleccionar los componentes óptimos que representen entre el 70% y el 90% de la información total.

3. Discretización y Preparación Final
La variable objetivo (PIB) se transforma de un valor numérico continuo a una variable categórica (Bajo, Medio, Alto) mediante cuantiles, facilitando futuros análisis de clasificación.

🖥️ Cómo ejecutarlo
Abre Google Colab.

Crea un Nuevo Cuaderno.

Copia y pega el código consolidado en una celda.




Presiona el botón de Play a la izquierda de la celda.

Una vez finalizado, la base de datos "aparecerá" bajo el nombre de la variable df.


⚠️ Errores Comunes
ModuleNotFoundError: Falta instalar la librería wbgapi. Solución: Ejecutar !pip install wbgapi.


NameError: Se intentó usar la función de descarga antes de definirla. Solución: Ejecutar las celdas en orden secuencial.
