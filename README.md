# 🛵 📲 🍔 Pipeline ETL & Inteligencia de Mercado — Food Delivery USA

Este proyecto presenta un análisis integral del mercado de una startup nueva de Food Delivery 
que busca expandirse en Estados Unidos. Se documentan todo el ciclo de vida de los datos: 
desde la **extracción, transformación y limpieza (ETL)** hasta la **visualización 
estratégica de los datos** orientada a extracción de insights y la toma de decisiones del CEO.

---

## 💻 Tecnologías Utilizadas
- **Lenguaje:** Python, SQL (SQLite)
- **Bibliotecas:** `Pandas`, `Numpy`, `Matplotlib`, `SQLAlchemy`
- **Base de Datos:** SQLite (`delivery_insights.db`)
- **Entorno:** Google Colab (`.ipynb`)
---

## 📐 Arquitectura del Pipeline

| Fase | Descripción |
|:-----|:------------|
| **Extract** | Carga de `restaurants.csv` y 10 archivos de menús con bucle automático |
| **Transform** | Limpieza de precios, mapeo de rangos, split de direcciones y filtros de calidad |
| **Load** | Carga a base de datos SQLite mediante SQLAlchemy |
| **Business Intelligence** | Queries SQL con visualizaciones estratégicas en Matplotlib, insights para toma de decisiones |

---

## 🗄️ Datasets Utilizados

| Archivo | Descripción | Registros |
|:--------|:------------|:----------|
| `restaurants.csv` | Catálogo maestro de restaurantes | ~63,000 |
| `restaurant_menus_parte_1.csv` | Detalle de ítems de menú | ~900,000 |
| `restaurant_menus_parte_2.csv` | Detalle de ítems de menú | ~900,000 |
| `restaurant_menus_parte_3.csv` | Detalle de ítems de menú | ~900,000 |
| `restaurant_menus_parte_4.csv` | Detalle de ítems de menú | ~900,000 |
| `restaurant_menus_parte_5.csv` | Detalle de ítems de menú | ~900,000 |
| `restaurant_menus_parte_6.csv` | Detalle de ítems de menú | ~900,000 |
| `restaurant_menus_parte_6.csv` | Detalle de ítems de menú | ~900,000 |
| `restaurant_menus_parte_7.csv` | Detalle de ítems de menú | ~900,000 |
| `restaurant_menus_parte_8.csv` | Detalle de ítems de menú | ~900,000 |
| `restaurant_menus_parte_9.csv` | Detalle de ítems de menú | ~900,000 |
| `restaurant_menus_parte_10.csv` | Detalle de ítems de menú | ~900,000 |

---

## 🔧 Transformaciones Aplicadas

- **Mapeo de precios:** `$` → `Económico`, `$$` → `Moderadamente caro`, etc.
- **Split de direcciones:** Separación de `full_address` en `calle`, `ciudad` y `estado`
- **Limpieza de precios:** Conversión de `"15.99 USD"` a `float`
- **Filtro de calidad:** Eliminación de restaurantes sin score o con score = 0
- **INNER JOIN:** Cruce entre restaurantes y menús por `id`

---

## 📊 Visualización de Resultados

| Pregunta de Negocio | Insight | Visualización |
|:--------------------|:--------|:--------------|
| **1. Penetración Geográfica** | Seattle lidera con 388 restaurantes | ![Ciudades](grafico_1_ciudades.png) |
| **2. Distribución de Precios** | El 75% del mercado opera en segmento Económico | ![Precios](grafico_2_precios.png) |
| **3. Precio Promedio por Ciudad** | Seattle tiene el mayor precio promedio ($12.05 USD) | ![Ciudad](grafico_3_precio_ciudad.png) |
| **4. Correlación Precio-Calidad** | Correlación de 0.79 pero no es regla absoluta | ![Correlacion](grafico_4_precio_calidad.png) |

---

## 💡 Insights Estratégicos

- **Seattle** es la ciudad prioritaria de lanzamiento — lidera en cantidad de restaurantes y precio promedio
- El **75%** del mercado opera en segmento económico — el volumen está en lo accesible
- Los restaurantes **económicos superan en score** a los moderadamente caros
- **Correlación precio-calidad de 0.79** — el precio no garantiza mejor experiencia

> **Conclusión:** Lanzar en Seattle, posicionarse en segmento económico y apostar por calidad — esa combinación captura el mayor volumen del mercado con el menor riesgo.

---

## 📁 Estructura del Repositorio

```text
apellido-proyecto-etl-delivery/
├── data/
│   ├── restaurants.csv
│   └── restaurant_menus_parte_1.csv
│   └── restaurant_menus_parte_2.csv
│   └── restaurant_menus_parte_3.csv
│   └── restaurant_menus_parte_4.csv
│   └── restaurant_menus_parte_5.csv
│   └── restaurant_menus_parte_6.csv
│   └── restaurant_menus_parte_7.csv
│   └── restaurant_menus_parte_8.csv
│   └── restaurant_menus_parte_9.csv
│   └── restaurant_menus_parte_10.csv
│       ...
├── graficos/
│   ├── grafico_1_ciudades.png
│   ├── grafico_2_precios.png
│   ├── grafico_3_precio_ciudad.png
│   └── grafico_4_precio_calidad.png
├── proyecto_etl_delivery.ipynb
└── README.md
```

---

## 👤 Autor
Juan Pablo Mendoza Granda
Módulo: Python para Análisis de Datos
Instructor: Christian Condori
