# 📊 Análisis de Ventas y Rentabilidad

## 📝 Descripción del Proyecto
Este proyecto tiene como objetivo analizar el rendimiento de ventas y rentabilidad de una empresa utilizando SQL y Power BI. Se han extraído y visualizado datos clave para identificar tendencias, productos más vendidos y regiones con mayor facturación.

## 📌 Análisis Realizados
1. **Total de facturación por categoría** 💰
2. **Cantidad facturada por mes y año** 📆
3. **Producto más vendido por categoría y año** 🛒
4. **Mapeo de los continentes con más ventas** 🌍
5. **Suma de facturación por marca** 🔖
6. **Total facturado** 💵

## 🛠️ Consultas SQL Utilizadas
### 🔹 Ventas por mes y año
```sql
SELECT strftime('%Y-%m', fecha_venta) AS mes_anio, 
       SUM(facturacion) AS total_facturado
FROM ventas
GROUP BY mes_anio
ORDER BY mes_anio;
```
📌 *Analiza cómo evolucionan las ventas mes a mes.*

### 🔹 Comparación de ventas por categoría
```sql
SELECT categoria, 
       SUM(facturacion) AS total_facturado
FROM ventas
GROUP BY categoria;
```
📌 *Útil para saber qué categorías generan más ingresos.*

### 🔹 Días con ventas anormalmente altas o bajas
```sql
SELECT fecha_venta, 
       SUM(facturacion) AS total_facturado
FROM ventas
GROUP BY fecha_venta
ORDER BY total_facturado DESC
LIMIT 10;
```
📌 *Detecta picos o caídas de ventas para investigar qué pasó.*

## 📊 Visualización en Power BI
Los datos fueron analizados y visualizados en Power BI para generar dashboards interactivos que permiten:
✅ Identificar las tendencias de ventas.
✅ Evaluar la rentabilidad de productos y marcas.
✅ Detectar anomalías en las ventas.
✅ Analizar el comportamiento de los clientes por ubicación.

## 📂 Archivos del Proyecto
- 📄 `ventas_analisis.pbix` → Archivo de Power BI con todas las visualizaciones.
- 📄 `queries.sql` → Archivo con todas las consultas SQL utilizadas.
- 📄 `README.md` → Explicación del análisis realizado (este archivo).

## 🚀 Conclusiones y Hallazgos
🔹 Se identificaron los productos más vendidos y las categorías con mayor rentabilidad.
🔹 Se detectaron períodos con anomalías en las ventas que requieren un análisis más detallado.
🔹 Los datos geográficos ayudaron a mapear las regiones con mayor impacto en las ventas.

---
📌 **Autor:** Nicolás Pereira 
📆 **Fecha:** 2025
