# Análisis de ventas retail — TechCore

Pipeline completo de datos de ventas de una cadena de tiendas de computadoras: limpieza de 30,000 facturas, construcción de un modelo relacional y un **dashboard interactivo en Power BI** con KPIs de negocio.

## Resultados clave

- **Medellín** es la ciudad con más ventas de las 4 analizadas (Bogotá, Cali, Medellín, Pereira).
- **Lenovo** lidera las ventas en las 4 ciudades, seguido por HP, Dell y Apple.
- **Alerta:** la caída de ventas entre 2024 y 2025 es la más fuerte de toda la serie histórica (2015–2025).
- La **tarjeta de crédito** concentra cerca de un tercio de las ventas, y el segmento de **18 a 30 años** es el más activo.

Las conclusiones y recomendaciones estratégicas están en [`docs/Conclusiones_Recomendaciones.pdf`](docs/Conclusiones_Recomendaciones.pdf).

## Proceso

| Fase | Herramienta | Qué se hizo |
|---|---|---|
| **1. Limpieza** | Power BI · Power Query | 30,307 filas crudas. Se corrigieron marcas mal escritas ("Aple" → "Apple", "Lenvo" → "Lenovo"…), se homologaron ciudades y se convirtieron fechas y montos a su tipo correcto |
| **2. Modelo relacional** | Python · pandas | Se pasó de formato ancho a largo y se construyeron 7 tablas con PK/FK. Se resolvieron duplicados ("Razor" vs. "Razer") y homónimos de clientes, con **0 llaves huérfanas** en las 6 relaciones |
| **3. Dashboard** | Power BI · DAX | 8 medidas DAX (ventas netas y brutas, margen, ticket promedio, % de participación por ciudad), jerarquías de fecha y geografía, 5 segmentadores, mapa y drill-down temporal |

## Estructura

```
├── avance_1_limpieza/           # .pbix de Power Query + CSV crudo y limpio
├── avance_2_modelo_relacional/  # Notebook + modeloVentas.xlsx (7 tablas)
├── avance_3_dashboard/          # Dashboard interactivo (.pbix)
└── docs/                        # Documentación y conclusiones
```

## Stack

Power BI (Power Query, DAX) · Python · pandas · numpy · Excel

## Cómo reproducir

1. Abre `avance_1_limpieza/Avance_1_Limpieza_Transformacion.pbix` en Power BI Desktop para ver los pasos de limpieza.
2. Ejecuta `avance_2_modelo_relacional/Avance_2_Modelo_Relacional.ipynb`, que regenera `modeloVentas.xlsx`.
3. Abre `avance_3_dashboard/Avance_3_Dashboard_PowerBI.pbix`.

---

Proyecto integrador del Bootcamp de Data Science de [Henry](https://www.soyhenry.com/). Autor: **Alam Uriel Flores Quiroz** · [LinkedIn](https://www.linkedin.com/in/alam-uriel-flores-quiroz-b18a6126a/)
