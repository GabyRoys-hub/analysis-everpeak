# Analysis everpeak — Movilidad Urbana y Productividad Económica (2024)

Análisis exploratorio e integrativo de datos sobre **movilidad urbana y productividad económica** (PIB per cápita y población) en ciudades de Latinoamérica durante **2024**, a partir de los conjuntos de datos de *TomTom Traffic Index* y *OECD Cities*. En el notebook se limpian y estandarizan los datos, se consolidan métricas anuales de congestión (como `JamsDelay`, `TrafficIndexLive`, `JamsLengthInKms`, `JamsCount` y `MinsDelay`), se cruzan con indicadores económicos (`city_gdp_capita` y `population`) y se evalúa visualmente si existe una relación clara entre congestión y PIB per cápita para orientar decisiones de inversión en infraestructura de transporte.

## Contenido del repositorio

* **Notebook principal (`.ipynb`)**: contiene todo el flujo paso a paso en Python (`pandas`, `numpy`, `seaborn`, `matplotlib`), desde la carga, limpieza de fechas/formatos numéricos y filtrado a 2024 hasta la agregación por ciudad, unión (`inner` join), visualizaciones y exportación.
* **Gráficas generadas en el notebook**:
  * **Boxplot de `JamsDelay` (2024)**: muestra distribución, media, mediana y valores atípicos en los minutos de congestión.
  * **Histograma de `city_gdp_capita` (con KDE)**: resume la distribución y el nivel del PIB per cápita.
  * **Gráfico de barras comparativo (`JamsDelay` vs. `city_gdp_capita`)**: compara ambos indicadores por ciudad (primeras 15 ciudades del dataset combinado).
* **Dataset exportado**: `ladb_mobility_economy_2024_clean.csv`, generado al final del notebook con los datos limpios y combinados (`index=False`).
* *(Nota: en el notebook adjunto no se incluyen scripts `.py` externos; todo el código vive dentro de las celdas del notebook).*

## Abrir en Google Colab y reproducir el análisis

1. **Abrir en Colab**: sube tu archivo `.ipynb` a Google Colab (*Archivo → Subir notebook*) o ábrelo directamente desde GitHub usando Colab (*Archivo → Abrir notebook → pestaña GitHub*).
2. **Carga del dataset**: el notebook **ya incluye** las celdas de carga con `pd.read_csv('/datasets/tomtom_traffic.csv')` y `pd.read_csv('/datasets/oecd_city_economy.csv')`. Si ejecutas fuera del entorno donde existen las rutas `/datasets/...`, sube ambos archivos CSV o ajusta las rutas en la celda de carga antes de correr el resto.
3. **Orden de ejecución**: ejecuta las celdas **secuencialmente de arriba hacia abajo** (`Paso 1` → `Paso 7`):
   1. Importar librerías y cargar `traffic` y `eco`.
   2. Explorar estructura/nulos, renombrar columnas a `snake_case` y convertir fechas (`datetime`) y columnas numéricas (`float`).
   3. Extraer `year` y filtrar ambos DataFrames para `2024` (`traffic_2024` y `eco_2024`).
   4. Calcular promedios anuales por ciudad y revisar el ranking por `JamsDelay`.
   5. Seleccionar columnas clave y unir con `pd.merge(..., how='inner')` en `merged`.
   6. Generar las visualizaciones y revisar observaciones.
   7. Exportar `ladb_mobility_economy_2024_clean.csv`.
