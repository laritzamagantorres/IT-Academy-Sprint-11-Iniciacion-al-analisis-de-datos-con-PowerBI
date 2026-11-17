# Sprint 11 · Análisis de datos con Power BI

Proyecto realizado en el itinerario de Data Analytics de IT Academy. El informe permite analizar las transacciones de un negocio, evaluar el cumplimiento de objetivos y explorar el comportamiento de compra de sus usuarios.

## Objetivo

Transformar los datos en un informe interactivo que permita responder a preguntas de negocio:

- ¿Se alcanzan los objetivos de ventas y de importe medio por transacción?
- ¿Cómo evolucionan las ventas mensuales?
- ¿Qué países cuentan con mayor participación de empresas?
- ¿Qué usuarios realizan compras de mayor importe medio?
- ¿Cómo se distribuyen geográficamente los usuarios con compras aprobadas?

## Herramientas utilizadas

- **MySQL:** origen de los datos.
- **Power BI Desktop:** modelado, análisis y visualización.
- **Power Query:** preparación y transformación de datos.
- **DAX:** creación de medidas e indicadores.

## Datos y modelo

Se utiliza la base de datos `sprint2_estrella`, trabajada en sprints anteriores.

El modelo relaciona las tablas de transacciones, usuarios, empresas y productos, junto con una tabla de relación entre transacciones y productos y una tabla calendario para el análisis temporal.

## Criterios del análisis

- Los indicadores de las páginas principales utilizan **transacciones aprobadas**, identificadas mediante `declined = FALSE()`.
- Las medidas generales se conservan por separado para facilitar su reutilización.
- Los importes originales están expresados en **dólares estadounidenses (USD)**.
- La tabla del nivel 1 incluye una conversión a euros mediante la relación fija **1 EUR = 1,08 USD**, aplicada como `USD / 1.08`.
- El país de las empresas se utiliza para analizar su participación; el país de los usuarios, para su distribución geográfica.

## Contenido del informe

### Nivel 1 · Resumen ejecutivo

- Importe anual de ventas aprobadas frente al objetivo de **2.600.000 USD**.
- Importe medio por transacción aprobada en **2021 y 2022**, con un objetivo de **260 USD**.
- Empresas participantes por país, con un mínimo objetivo de **3 empresas**.
- Ventas mensuales de **2020 a 2024**, frente al objetivo de **220.000 USD mensuales**.
- Importe medio por usuario en USD y EUR, con formato condicional.

### Nivel 2 · Ventas y cumplimiento de objetivos

- Comparación de las ventas mensuales de **2018 y 2019**.
- Evaluación del cumplimiento del objetivo mensual.
- Importe medio por transacción aprobada en empresas de Alemania.
- Diferencia porcentual de la media alemana respecto al objetivo de **260 USD**.

### Nivel 3 · Usuarios, compras y distribución geográfica

- Indicadores de transacciones aprobadas: número, media, mediana, máximo y mínimo.
- Recuento de productos asociados a transacciones aprobadas.
- Detalle por usuario: productos comprados, importe medio y productos de mayor y menor precio.
- Formato condicional para distinguir las medias superiores a **260 USD**.
- Mapa de usuarios con al menos una compra aprobada, agrupados por país.

## Organización de las medidas

Las medidas DAX se agrupan en cuatro carpetas:

- **01 Generales**
- **02 Aprobadas**
- **03 Objetivos**
- **04 Cumplimiento**

## Cómo consultar el informe

1. Descargar el archivo `.pbix` del repositorio.
2. Abrirlo con Power BI Desktop.
3. Recorrer las páginas **Nivel 1**, **Nivel 2** y **Nivel 3**.
4. Utilizar los filtros y pasar el cursor sobre los gráficos para consultar sus detalles.

Para actualizar los datos desde el origen, es necesario disponer de acceso a la base de datos MySQL y configurar la conexión correspondiente.

## Consideraciones de interpretación

El importe medio representa el valor promedio de una transacción aprobada. Una media mayor no implica necesariamente mayores ventas totales ni mayor beneficio.

Del mismo modo, un mayor número de empresas participantes no implica que ese país genere un mayor volumen de ventas.

## Autora

Laritza Magan Torres  
IT Academy · Data Analytics
