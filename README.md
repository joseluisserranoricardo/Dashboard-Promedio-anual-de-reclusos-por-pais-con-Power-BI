# 📊 Dashboard – Promedio anual de reclusos por país

![dashboard final](https://github.com/user-attachments/assets/587b175e-194a-410b-b2bf-3010d59d0627)

Este repositorio contiene un dashboard interactivo en Power BI que analiza el promedio anual de personas privadas de la libertad por país, utilizando datos internacionales armonizados y un proceso explícito de limpieza y estandarización para garantizar comparabilidad.

## 🎯 Objetivo del proyecto
El objetivo principal es:

Comparar países de manera justa, aun cuando:

-tienen distintos rangos de años disponibles,

-existen diferentes desagregaciones (sexo, tipo de delito, estatus, etc.),

-los valores están reportados en magnitudes muy dispares.

Para ello, el dashboard se centra en promedios anuales y en visualizaciones que evitan sesgos por tamaño poblacional o cobertura temporal.

## 🧹 Limpieza y preparación de datos (Power Query)
Antes de construir el modelo y las visualizaciones, se realizó un proceso de limpieza y selección de datos en Power Query, con los siguientes criterios:

1️⃣ Selección de indicadores

Se filtró el dataset original para trabajar únicamente con:

-Persons held (reclusos)

Se excluyeron indicadores como:

-tasas por cada 100,000 habitantes,

-mortalidad en prisión,

-capacidad carcelaria,

dado que no son directamente comparables con los conteos absolutos que necesitamos para hacer los promedios que se querian mostrar.

2️⃣ Homogeneización de unidades

-Se trabajó exclusivamente con conteos absolutos (counts).

-Se eliminaron métricas mixtas (ratios, porcentajes), evitando combinaciones inconsistentes en visualizaciones y KPIs.

3️⃣ Manejo de desagregaciones (Sexo y Dimensión)

Se priorizó la consistencia entre países.

Dado que algunos filtros eliminaban la categoría Total, se optó por:

-conservar Male y Female,

-reconstruir el total mediante medidas DAX cuando fue necesario.

Ejemplo conceptual:

Total = Masculino + Femenino (por país y año)

Esto evita perder información cuando los totales no están disponibles explícitamente.

4️⃣ Cobertura temporal desigual

Uno de los puntos más importantes del proyecto:

No todos los países tienen datos para los mismos años.

Sumar valores a lo largo del tiempo genera comparaciones sesgadas.

✅ Solución adoptada:

Uso de promedios anuales por país,

Esto garantiza que:

-países con más años no estén sobrerrepresentados,

-la comparación sea metodológicamente correcta.

## 🌍 Visualizaciones incluidas

El dashboard se organiza en una sola página, con los siguientes elementos:

🗺️ Mapa de burbujas

-Tamaño proporcional al promedio anual

-Permite identificar concentraciones regionales

📊 Gráfico de barras (Top países)

-Comparación directa de países con mayor población penitenciaria

🔢 KPI global

-Promedio anual total (agregado mundial)

🎛️ Segmentadores

-Año

-Subregión

-Sexo

![segmentacion de datos](https://github.com/user-attachments/assets/a0d8d092-e672-4197-b435-0182e51557c1)

## Autor: Jose Serrano![Uploading segmentacion de datos.jpg…]()

## Herramientas: Power BI · Power Query · DAX



