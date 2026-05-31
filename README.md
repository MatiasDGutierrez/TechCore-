# TechCore - Sistema de Análisis de Ventas

## Autor
**Matías Gutiérrez**

## Descripción del Proyecto
Sistema completo de análisis de datos de ventas para TechCore, implementando un modelo relacional de base de datos con análisis exploratorio de datos (EDA), cálculo de KPIs y visualizaciones para la toma de decisiones empresariales.

## Estructura del Proyecto
```
ProyectoM3_MatiasGutierrez/
├── Avances/
│   ├── Avance_1/          # Limpieza y transformación de datos
│   ├── Avance_2/          # Modelo relacional y EDA
│   └── Avance_3/          # Dashboard en Power BI
└── Documentacion/         # Conclusiones y recomendaciones
```

## Dataset
- **Período**: 2014 - 2025
- **Total de ventas**: 30,000 transacciones
- **Productos**: 40 productos únicos
- **Clientes**: 17,449 clientes únicos
- **Sucursales**: 6 sucursales (Bogotá #1, Bogotá #2, Medellín #1, Medellín #2, Cali, Pereira)
- **Vendedores**: 30 vendedores
- **Valor total de ventas**: $2,572,205,600,000

## Modelo Relacional (Esquema Estrella)

### Tablas de Dimensión
- **dim_ciudades**: Información geográfica de ciudades
- **dim_sucursales**: Ubicaciones de puntos de venta
- **dim_clientes**: Datos demográficos de clientes
- **dim_vendedores**: Información del equipo de ventas
- **dim_productos**: Catálogo de productos y precios

### Tablas de Hechos
- **fact_facturas**: Transacciones de ventas
- **fact_detalle_facturas**: Líneas de detalle por producto

## KPIs y Fórmulas

### 1. Ventas Totales
**Fórmula**: `SUM(TotalVenta)`
**Descripción**: Suma de todas las ventas en el período analizado.

### 2. Promedio de Venta por Transacción
**Fórmula**: `SUM(TotalVenta) / COUNT(FacturaID)`
**Descripción**: Valor promedio de cada transacción de venta.

### 3. Ventas por Sucursal
**Fórmula**: `SUM(TotalVenta) GROUP BY SucursalID`
**Descripción**: Distribución de ventas por cada ubicación.

### 4. Ticket Promedio por Cliente
**Fórmula**: `SUM(TotalVenta) / COUNT(DISTINCT ClienteID)`
**Descripción**: Valor promedio de compra por cliente único.

### 5. Productos Más Vendidos
**Fórmula**: `SUM(Cantidad) GROUP BY ProductoID ORDER BY DESC`
**Descripción**: Ranking de productos por unidades vendidas.

### 6. Ventas por Vendedor
**Fórmula**: `SUM(TotalVenta) GROUP BY VendedorID`
**Descripción**: Performance individual del equipo de ventas.

### 7. Tasa de Descuento Promedio
**Fórmula**: `AVG(DescuentoVenta)`
**Descripción**: Porcentaje promedio de descuentos aplicados.

### 8. Ventas por Período Temporal
**Fórmula**: `SUM(TotalVenta) GROUP BY Año, Mes`
**Descripción**: Análisis de tendencias temporales de ventas.

## Tecnologías Utilizadas
- **Python**: Pandas, NumPy
- **Base de Datos**: SQLite
- **Visualización**: Power BI
- **Procesamiento de Datos**: Jupyter Notebooks

## Avances del Proyecto

### Avance 1: Limpieza y Transformación de Datos
- Carga del dataset original (ventas.csv)
- Limpieza de datos faltantes y normalización
- Transformación a formato estructurado (ventasTransformed.csv)
- Validación de calidad de datos

### Avance 2: Modelo Relacional y EDA
- Diseño e implementación del esquema estrella
- Creación de tablas de dimensión y hechos
- Análisis exploratorio de datos
- Cálculo de KPIs y métricas de negocio
- Normalización de sucursales y ciudades

### Avance 3: Dashboard en Power BI
- Desarrollo de visualizaciones interactivas
- KPIs en tiempo real
- Análisis geográfico de ventas
- Reportes ejecutivos

## Conclusiones y Recomendaciones

### Hallazgos Principales
- Las sucursales de Medellín concentran el mayor volumen de ventas
- El rango de edad con mayor actividad comercial es 35-44 años
- Los métodos de pago más utilizados son tarjeta de crédito y efectivo
- Se identifican patrones estacionales en las ventas

### Recomendaciones
- Optimizar el inventario en sucursales de alto rendimiento
- Implementar estrategias de fidelización para el segmento 35-44 años
- Expandir la presencia en ciudades con potencial de crecimiento
- Desarrollar campañas promocionales en períodos de baja actividad

## Instrucciones de Ejecución

### Requisitos Previos
```bash
pip install pandas numpy openpyxl
```

### Ejecución del Notebook
```bash
jupyter notebook Avances/Avance_2/Avance_2_Modelo_Relacional.ipynb
```

## Notas de Mejora
- Implementar gráficos formales para el diagrama ER
- Reducir el uso de prints en el código para mejorar legibilidad
- Priorizar visualizaciones sobre texto en el EDA
- Minimizar dependencia de herramientas de IA en el análisis

## Contacto
Para consultas sobre este proyecto, contactar a: Matías Gutiérrez
