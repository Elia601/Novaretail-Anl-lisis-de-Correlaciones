# Novaretail-Análisis-de-Correlaciones

## Descripción
Proyecto del Sprint 8 de TripleTen - Explorar las conexiones de datos. Análisis de correlaciones entre variables de comportamiento de clientes de NovaRetail para identificar drivers de negocio y evitar multicolinealidad en modelos futuros.

## Objetivo
Identificar las relaciones más fuertes entre variables numéricas y traducirlas en hallazgos de negocio accionables.

## Hallazgos Principales

### Hallazgo 1: Alta colinealidad
Evidencia visual: Scatterplot de la sección 3.3 muestra una línea casi perfecta entre compras_mes e ingreso_anual, puntos muy alineados. Evidencia numérica: Pearson r=0.97, Spearman r=0.97, p<0.0001. Es el valor más alto de toda la matriz. Interpretación: A mayor número de compras mensuales, mayor ingreso anual. La relación es lineal, positiva y muy fuerte.No podemos afirmar: Que comprar más CAUSE más ingreso, solo que están asociadas. Podría haber una tercera variable. Tampoco podemos usar ambas juntas en regresión por colinealidad. Implicación de negocio: Usar solo UNA de las dos como predictor. Recomendación: mantener compras_mes y eliminar ingreso_anual del modelo para evitar redundancia y sobreajuste.

Hallazgo 2 —

Evidencia visual: Scatterplot visitas_mes vs gasto_publicidad_dirigida muestra tendencia ascendente moderada con dispersión. Evidencia numérica: Pearson r=0.58, Spearman r=0.56, p<0.0001. En cambio, gasto vs ingreso_anual r=0.20 (bajo) y gasto vs compras r=0.21 (bajo). Interpretación: El gasto en publicidad dirigida sí aumenta las visitas a la plataforma (relación moderada), pero no se traduce directamente en más compras ni más ingreso. Es un paso intermedio.No podemos afirmar: Que más gasto siempre traerá más ventas. Solo trae tráfico.Implicación de negocio: Optimizar la conversión de visita a compra. No aumentar presupuesto de publicidad hasta mejorar el embudo de ventas, porque el tráfico no está convirtiendo.

## Herramientas
Python, Pandas, Seaborn, Matplotlib, SciPy (Pearson, Spearman)

## Conclusión
Próximos pasos
Probar segmentación adicional y enriquecer datos:

Modelo de churn con nuevas variables: Incluir antigüedad, tickets de soporte, interacción con beneficios premium y encuestas de salida. Probar Random Forest / XGBoost para predecir abandono.
Test A/B de retención: Dado que V=0.120 entre premium y abandono es bajo pero es el más alto, lanzar experimento: ofrecer premium gratis 1 mes a grupo en riesgo y medir retención real vs grupo control.
Optimizar embudo de publicidad: Como gasto_publicidad correlaciona con visitas (r∼0.58) pero no con compras, hacer análisis de conversión y heatmaps para mejorar la tasa de visita → compra antes de escalar presupuesto.


---
**Autor:** Elia601
**Status:** ✅ Aprobado - 1ª iteración
**TripleTen - Sprint 8**
