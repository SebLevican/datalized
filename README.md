# Sales Analytics Dashboard

## Descripción del Proyecto
Dashboard interactivo desarrollado en Power BI para análisis de datos de ventas de una empresa retail, utilizando el dataset público Superstore. El objetivo es proporcionar insights accionables sobre performance de productos, tendencias temporales y distribución geográfica de ventas.

## Pregunta de Investigación
**¿Cuáles son los patrones de ventas, rentabilidad y comportamiento de clientes que pueden optimizar la estrategia comercial de la empresa?**

Preguntas específicas que responde el análisis:
- ¿Qué categorías de productos generan mayor revenue y profit?
- ¿Cuáles son las tendencias de ventas a lo largo del tiempo?
- ¿Qué segmentos de clientes son más rentables?
- ¿Cómo se distribuyen geográficamente las ventas?

## Fuentes de Datos
- **Dataset**: Superstore Sales Data (datos públicos)
- **Registros**: ~9,994 transacciones
- **Período**: 2014-2017
- **Dimensiones**: 21 columnas incluyendo datos de productos, clientes, fechas y métricas financieras

### Variables principales:
- Order Date, Ship Date
- Customer information (ID, Name, Segment)
- Product information (Category, Sub-Category, Product Name)
- Geographic data (Country, State, City)
- Financial metrics (Sales, Quantity, Discount, Profit)

## Proceso de Limpieza y Transformación

### 1. Preparación de Datos
```python
# Conversión de tipos de datos
df['Order_Date'] = pd.to_datetime(df['Order_Date'])
df['Ship_Date'] = pd.to_datetime(df['Ship_Date'])

# Cálculo de métricas derivadas
df['Profit_Margin'] = (df['Profit'] / df['Sales']) * 100
df['Days_to_Ship'] = (df['Ship_Date'] - df['Order_Date']).dt.days
```

### 2. Transformaciones Implementadas
- **Métricas de rentabilidad**: Cálculo de profit margin por transacción
- **Dimensiones temporales**: Extracción de año, mes, trimestre
- **Categorización**: Agrupación de productos por performance
- **Segmentación geográfica**: Análisis por región y estado

### 3. Validaciones de Calidad
- Verificación de valores nulos (0% encontrados)
- Validación de rangos de fechas
- Consistencia en categorías de productos

## Decisiones de Diseño del Panel

### KPIs Principales
- **Total Sales**: $2.3M
- **Total Profit**: $286K
- **Profit Margin**: 12.5%
- **Total Orders**: 5,009

### Visualizaciones Implementadas

1. **Sales Trend Over Time**
   - Gráfico de líneas mostrando evolución mensual
   - Permite identificar estacionalidades y tendencias

2. **Sales by Category**
   - Gráfico de barras horizontal
   - Facilita comparación rápida entre categorías

3. **Geographic Distribution**
   - Mapa de calor por estados
   - Identifica mercados de mayor oportunidad

4. **Profit vs Sales Scatter**
   - Análisis de rentabilidad por producto
   - Identifica productos de alta/baja performance

### Interactividad
- **Filtros por año**: 2014-2017
- **Segmentación por cliente**: Consumer, Corporate, Home Office
- **Filtro por región**: Central, East, South, West

### Paleta de Colores
- Azul corporativo para métricas principales
- Verde para indicadores positivos (profit)
- Rojo para alertas o métricas negativas
- Gris para elementos secundarios

## Insights Principales

1. **Seasonality Pattern**: Picos de ventas en Q4 (temporada navideña)
2. **Category Performance**: Technology lidera en revenue, Office Supplies en volumen
3. **Geographic Insights**: California y New York concentran mayor actividad
4. **Customer Segments**: Consumer segment representa 50% de las ventas

## Archivos del Repositorio
```
├── README.md                 # Este archivo
├── data/
│   └── superstore_data.csv   # Dataset utilizado
├── notebooks/
│   └── data_analysis.ipynb   # Código de análisis y transformaciones
├── images/
│   └── dashboard_preview.png # Captura del dashboard
└── docs/
    └── methodology.md        # Documentación detallada del proceso
```

## Tecnologías Utilizadas
- **Power BI**: Desarrollo del dashboard principal
- **Python**: Análisis exploratorio y transformaciones
- **Pandas**: Manipulación de datos
- **Matplotlib/Seaborn**: Visualizaciones exploratorias

## Nota Técnica
El archivo Power BI original (.pbi) no pudo ser incluido debido a limitaciones de tamaño en GitHub. El código Python adjunto en `notebooks/data_analysis.ipynb` recrea las principales transformaciones implementadas en el dashboard.

## Visualización
**Dashboard en Power BI**: [Ver Dashboard](https://app.powerbi.com/view?r=eyJrIjoiZDJhMWFkMDktODU1ZC00ZmZiLTk3NTYtZWUwMGYyM2ZjMDEwIiwidCI6ImZlNTVmYTkxLTI3NDQtNGRjMi04YWViLTNlODA3ZmY1ZjEwNiIsImMiOjR9)

---

**Desarrollado por Rolando Serrano** | [LinkedIn](https://linkedin.com/in/rolando-serrano) | [GitHub](https://github.com/SebLevican)
