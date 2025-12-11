# SQL-analisis-datos-ventas
Este proyecto tiene como objetivo diseñar, construir y analizar una base de datos relacional utilizando SQL. Para ello se utilizó un dataset de ventas minoristas (supermercado) y se desarrolló un proceso completo que incluye:

* Modelado de datos y creación de tablas

* Proceso ETL para carga, limpieza y transformación de datos

* Análisis exploratorio mediante consultas SQL

* Generación de métricas clave para el negocio

Buscando demostrar habilidades técnicas en SQL, buenas prácticas de modelado y capacidad analítica para extraer informacion relevante del negocio.

## Herramientas utilizadas
- MySQL 8
- VS Code + SQLTools
- Git & GitHub
- Archivos CSV como fuente de datos

## Origen y modelado de datos
Los datos utilizados en este proyecto provienen de "Datasets para Proyecto BI - Análisis de Ventas", disponible en Kaggle en formato CSV y públicamente en el siguiente enlace:

https://www.kaggle.com/datasets/dataregina/datasets-para-proyecto-bi

El dataset incluye información de:
- Clientes
- Productos
- Categorías
- Ventas
- Métodos de pago

A partir de estos datos se construyó un modelo relacional que incluye las siguientes tablas y relaciones:
- Clientes
- Producto
- Categorias
- Metodo_pago
- Ventas

Con relaciones que garantizan integridad y trazabilidad:
```
- Ventas.ID_Cliente → Clientes.ID_Cliente
- Ventas.ID_Producto → Producto.ID_Producto
- Producto.ID_Categoria → Categorias.ID_Categoria
- Ventas.Metodo_Pago → Metodo_pago.ID_Metodo
```

## Desarrollo y análisis del proyecto

Se realizó un flujo completo de trabajo en SQL, desde el modelado inicial hasta la generación de insights finales para el negocio. Las principales etapas fueron:

1. Modelado y construcción de la base de datos

    - Diseño del modelo relacional a partir de archivos CSV.

    - Creación de tablas normalizadas (Clientes, Producto, Categorías, Método de pago, Ventas).

    - Implementación de claves primarias y foráneas para asegurar integridad referencial.

    - Incorporación de la columna ID_Categoria en Producto y posterior asignación mediante JOIN con Categorías.

2. Proceso ETL (carga, limpieza y validación)

    - Carga de datos con LOAD DATA INFILE desde archivos CSV.

    - Conversión y validación de fechas.

    - Eliminación automática de registros duplicados mediante IGNORE.

    - Normalización de categorías, productos y métodos de pago.

    - Verificación de consistencia entre claves foráneas y datos importados.

3. Análisis exploratorio de los datos

    Se desarrollaron consultas de exploración para comprender el comportamiento del dataset:

    - Clientes por región.

    - Stock total y cantidad de productos por categoría.

    - Distribución de ventas por método de pago.

    - Evolución mensual de ventas.

4. Métricas clave del negocio

    Se calcularon indicadores fundamentales para retail:

    - Top categorías más vendidas.

    - Top productos por cantidad y revenue.

    - Clientes con mayor volumen de compras.

    - Meses con mayor facturación.

    - Relación stock vs ventas para anticipar quiebres de inventario.

5. Controles de calidad y detección de incidencias

    Con el objetivo de simular escenarios reales del negocio, se agregaron consultas para detectar problemas frecuentes en bases de datos operativas:

    - Productos con bajo stock.

    - Ventas duplicadas.

    - Precios incorrectos o valores nulos.

    - Métodos de pago no válidos.

    - Productos sin categoría asignada.

    - Ventas realizadas con stock insuficiente.

## Información relevante obtenida 
1. Categorías más vendidas:
Las categorías con mayor volumen de ventas fueron Carnicería, Lácteos y Congelados.

    *Acción sugerida*: utilizar estas categorías como impulso para aumentar la rotación de categorías con menor demanda mediante promociones cruzadas o descuentos combinados.

2. Productos con mayor demanda:
Los productos más vendidos fueron Hamburguesas congeladas, Agua mineral y Cervezas.

    *Acción sugerida: establecer controles más estrictos de stock para estos productos, asegurando niveles mínimos para evitar quiebres durante picos de demanda.

3. Clientes de alto valor:
Los clientes con mayor volumen de compras fueron Stollsteiner Pinchas, Dan Judah y Hellens Eben.

    *Acción sugerida*: implementar estrategias de retención y fidelización, como beneficios exclusivos, descuentos personalizados o campañas de marketing directo.

4. Estacionalidad de ventas:
Los meses con mayor facturación fueron junio, marzo y diciembre, lo que revela patrones estacionales en el comportamiento del consumidor.

    *Acción sugerida*: reforzar personal y stock temporal en estos periodos para atender eficientemente la mayor demanda.

5. Gestión de stock y alertas:
El análisis de inventario permitió identificar productos con bajo stock o riesgo de ruptura.

    *Acción sugerida*: implementar alertas automáticas de reposición y revisar la rotación por categoría para optimizar la planificación de compras.

## Conclusiones Finales
Este proyecto permitió obtener información significativa para el negocio mediante la creación de una base de datos solida a partir del modelado, limpieza y análisis de datos en SQL. En síntesis, el proyecto demuestra la capacidad de transformar datos crudos en conocimiento útil para la toma de decisiones.