# Dashboard - Análisis comercial inmobiliario 2023-2024 - Andes Capital Real Estate

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

**hecho_ventas_propiedades: Cada fila representa la transacción de venta de una propiedad.**
👉 Este dataset permitirá analizar ventas, comisiones, canales comerciales y tendencias en el tiempo.
<small>			
| Columna | Tipo de dato | Descripción | Ejemplo |
|--------|--------|------------------|------------------|
id_venta | Categórica | Identificador único de la venta | SALE000001
fecha_venta | Fecha	|Fecha en que se realizó la venta | 2024-01-05
id_cliente | Categórica | Identificador del cliente que realizó la compra | CUST02497
id_propiedad | Categórica | Identificador de la propiedad vendida | PROP03591
ciudad | Categórica| Ciudad donde se realizó la venta | Bogotá
precio_venta | Numérico (decimal) |	Precio final de venta de la propiedad | 1027126
tipo_propiedad | Categórica | Tipo de propiedad vendida | Casa
canal_venta	| Categórica | Canal utilizado para la venta	| Corredor
porcentaje_comision	| Numérico (decimal) | Porcentaje de comisión aplicado en la venta | 0.0473
monto_comision | Numérico (decimal)	| Monto de comisión generado por la venta | 48605
</small>	






