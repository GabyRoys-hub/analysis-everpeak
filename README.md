# Analysis everpeak — Movilidad Urbana y Productividad Económica (2024)

Análisis exploratorio e integrativo de datos sobre **movilidad urbana y productividad económica** (PIB per cápita y población) en ciudades de Latinoamérica durante **2024**, a partir de los conjuntos de datos de *TomTom Traffic Index* y *OECD Cities*. En el notebook se limpian y estandarizan los datos, se consolidan métricas anuales de congestión (como `JamsDelay`, `TrafficIndexLive`, `JamsLengthInKms`, `JamsCount` y `MinsDelay`), se cruzan con indicadores económicos (`city_gdp_capita` y `population`) y se evalúa visualmente si existe una relación clara entre congestión y PIB per cápita para orientar decisiones de inversión en infraestructura de transporte.

## 📂 Contenido del repositorio

- `notebooks/everpeak_analysis.ipynb`
  → Notebook principal con limpieza, EDA, distribuciones, outliers y conclusiones.

## ▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](URL_DEL_NOTEBOOK_EN_GITHUB)

O:

1. Abre el archivo `.ipynb` en GitHub
2. Haz clic en **Open in Colab**

## 📘 Cómo reproducir el análisis

1. Abre `notebooks/everpeak_analysis.ipynb`
2. Ejecuta las celdas en orden
3. El notebook carga automáticamente el dataset desde `/data/` o desde un enlace público (según corresponda)

## 🧠 Objetivo del análisis

- Identificar problemas de calidad de datos
- Construir un pipeline de limpieza reproducible
- Analizar comportamientos, distribuciones y outliers
- Generar insights para el equipo de Estrategia e Integración de EverPeak
