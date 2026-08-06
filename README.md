# Dashboard - Análisis comercial inmobiliario 2023-2024 <br>Andes Capital Real Estate

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=flat&logo=powerbi&logoColor=black)
![Power BI](https://img.shields.io/badge/Power%20BI-DAX-F2C811?style=flat&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoftexcel&logoColor=white)



---
## Contexto y problema de negocio
La empresa inmobiliaria Andes Capital Real Estate necesita comprender mejor el desempeño comercial. 
La empresa gestiona la venta de diferentes tipos de propiedades a través de distintos canales de venta y segmentos de clientes.
Actualmente, la información existe a nivel transaccional, pero no hay una visión analítica clara del negocio.

👉 La misión del dashboard interactivo en Power BI es permitir analizar ventas, clientes y propiedades para apoyar decisiones estratégicas.

**💡 Preguntas del negocio**<br>
El dashboard ayuda a responder preguntas como:<br>
> *¿Cuál es el ingreso total generado por las ventas de propiedades?*<br>
> *¿Qué tipo de propiedad genera más ingresos?*<br>
> *¿Qué segmentos de clientes compran más?*<br>
> *¿Cómo evolucionan las ventas en el tiempo?*<br>
> *¿El negocio está creciendo año contra año?*<br>
> *¿Los clientes vuelven a comprar después de su primera compra?*<br>

## 🎯 Funcionalidades implementadas
- Preparación y validación de datos para el análisis.
- Construcción de un **modelo de datos en esquema estrella.**
- Creación de **medidas analíticas** para análisis comercial.
- Aplicación de **inteligencia de tiempo** para analizar tendencias.
- Diseño de dashboards claros para análisis ejecutivo.
- Análisis de la **recurrencia de clientes utilizando cohortes**.
  
## 🛠️ Herramientas del proyecto
- Power BI
- Visualizaciones nativas (barras, líneas, tablas, KPI).
- Modelado de datos en esquema estrella.
- Cálculos analíticos (medidas y columnas calculadas).

## 📂 Dataset del proyecto
El proyecto utiliza una tabla de hechos (ventas) y tablas dimensionales (clientes y propiedades).<br>

**hecho_ventas_propiedades: Cada fila representa la transacción de venta de una propiedad.**<br>
👉 Este dataset permitirá analizar ventas, comisiones, canales comerciales y tendencias en el tiempo.<br>

<sub>

| Columna | Tipo de dato | Descripción | Ejemplo |
|--------|--------|------------------|------------------|
| id_venta | Categórica | Identificador único de la venta | SALE000001 |
| fecha_venta | Fecha | Fecha en que se realizó la venta | 2024-01-05 |
| id_cliente | Categórica | Identificador del cliente que realizó la compra | CUST02497 |
| id_propiedad | Categórica | Identificador de la propiedad vendida | PROP03591 |
| ciudad | Categórica | Ciudad donde se realizó la venta | Bogotá |
| precio_venta | Numérico (decimal) | Precio final de venta de la propiedad | 1027126 |
| tipo_propiedad | Categórica | Tipo de propiedad vendida | Casa |
| canal_venta | Categórica | Canal utilizado para la venta | Corredor |
| porcentaje_comision | Numérico (decimal) | Porcentaje de comisión aplicado en la venta | 0.0473 |
| monto_comision | Numérico (decimal) | Monto de comisión generado por la venta | 48605 |

</sub>

**dim_clientes : Cada fila representa un cliente.**<br>
👉 Este dataset permitirá analizar la segmentación de clientes y el comportamiento de compra por ubicación o tipo de comprador.<br>

<sub>

| Columna | Tipo de dato | Descripción | Ejemplo |
|--------|--------|------------------|------------------|
| id_cliente | Categórica | Identificador único del cliente | CUST00001 |
| segmento_comprador | Categórica | Tipo o perfil del comprador | Primera vez |
| pais | Categórica | País del cliente | Colombia |
| ciudad | Categórica | Ciudad del cliente | Bogotá |

</sub>

**dim_propiedades: Cada fila representa una propiedad disponible para venta.**<br>
👉 Este dataset permitirá analizar características de las propiedades y su relación con el desempeño comercial.<br>

<sub>
	
| Columna | Tipo de dato | Descripción | Ejemplo |
|--------|--------|------------------|------------------|
| id_venta | Categórica | Identificador único de la venta | SALE000001 |
| fecha_venta | Fecha	|Fecha en que se realizó la venta | 2024-01-05 |
| id_cliente | Categórica | Identificador del cliente que realizó la compra | CUST02497 |
| id_propiedad | Categórica | Identificador de la propiedad vendida | PROP03591 |
| ciudad | Categórica| Ciudad donde se realizó la venta | Bogotá |
| precio_venta | Numérico (decimal) |	Precio final de venta de la propiedad | 1027126 |
| tipo_propiedad | Categórica | Tipo de propiedad vendida | Casa |
| canal_venta	| Categórica | Canal utilizado para la venta	| Corredor 1
| porcentaje_comision	| Numérico (decimal) | Porcentaje de comisión aplicado en la venta | 0.0473 1
| monto_comision | Numérico (decimal)	| Monto de comisión generado por la venta | 48605 |

</sub>

Durante el proyecto se creó una tabla calendario llamada dim_fecha.<br>
**dim_fecha: Esta tabla permitirá realizar análisis temporal como:**<br>
👉 Tendencias de ventas; Comparaciones Year over Year (YoY); Métricas acumuladas YTD y MTD.

<sub>
	
| Columna | Tipo de dato | Descripción | Ejemplo |
|--------|--------|------------------|------------------|
| Date | Fecha | Fecha del calendario | 2024-01-05 |
| Año | Numérico (int) | Año de la fecha | 2024 |
| Mes | Categórica | Nombre del mes | Enero |
| Mes Numero | Numérico (int) | Número del mes | 1 |
| Año-Mes | Categórica | Año y mes en formato analítico | 2024-01 |

</sub>

## Estructura del proyecto
```
10_dashboard_analisis_comercial_ACRE/
│
├── Datasets/                                ← Datos fuente
│   ├── dim_propiedades.csv                  # 8,000 registros de propiedades · 8 columnas
│   ├── dim_clientes.csv                     # 3,500 registros de clientes · 4 columnas
│   └── hecho_ventas_propiedades.csv         # 8,500 transacciones de venta · 10 columnas
│
├── exports/                                ← Generado al ejecutar data wrangling
│   ├── Andes_Capital_RE_2023_2024.xlsx      # Dataset consolidado para Power BI
│
├── notebooks/
│   ├── S11_P10 Proyecto_InmobiliarioGrupoAndes.ipynb  # ETL · KPIs base · Análisis · estadística · conclusiones
│
├── dashboard/
│   └── S11_P10_Analisis_Comercial_ACRE.pbix           # Dashboard Power BI · 3 páginas · medidas DAX
│
└── README.md
```

## 🔄 Flujo general del proyecto (Guía paso a paso)
El proceso está documentado en el Jupyter Notebook del proyecto que incluye los detalles sobre:


| Paso | Acción | Resultado |
|---------|-----------|---------------------|
| 1. Limpieza de datos | Validación de tipos de datos, nulos y duplicados | Dataset listo para análisis |
| 2. Creación de tabla calendario | Construcción de tabla dim_fecha para análisis temporal | Base para inteligencia de tiempo |
| 3. Modelado de datos | Construcción de esquema estrella | Modelo analítico correcto |
| 4. Creación de medidas | Construcción de métricas comerciales e inteligencia de tiempo | Insights del negocio |
| 5. Diseño de dashboard | Creación de páginas de análisis ejecutivo, comercial y cohortes | Visualización clara |
| 6. Resumen ejecutivo | Interpretación de resultados y generación de recomendaciones | Insights estratégicos |

---

## Cómo reproducir el análisis

**1. Revisión del notebook**<br>
Jupyter notebook: **[notebooks/S11_P10 Proyecto_InmobiliarioGrupoAndes.ipynb](https://github.com/marisolmtzp/10_dashboard_analisis_comercial_ACRE/blob/27c85dfebb263785fa8db2c3e526a91af37278bc/notebooks/S11_P10%20Proyecto_InmobiliarioGrupoAndes.ipynb)**

**2. Power BI**<br>
Descargar el dashboard y abrirlo en Power BI: **[dashboards/S11_P10_Analisis_Comercial_ACRE.pbix](https://github.com/marisolmtzp/10_dashboard_analisis_comercial_ACRE/tree/578f0806d453d2d0dd9ee1a15546db6d909f000f/dashboards)**<br>
Conectar dashboard a la fuente de datos limpia: **[exports/Andes_Capital_RE_2023_2024.xlsx](https://github.com/marisolmtzp/10_dashboard_analisis_comercial_ACRE/tree/84e0940c20bae506b1d679c04503eec56d594b4f/exports)**

---

*Marisol Martínez Pulgarín · Data Analyst*  · 
*[LinkedIn](https://www.linkedin.com/in/marisolmtzp/) · [GitHub](https://github.com/marisolmtzp)*
