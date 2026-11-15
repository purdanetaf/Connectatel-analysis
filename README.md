# ConnectaTel Analysis – Segmentación de Clientes

Este repositorio contiene el análisis de datos de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica. El objetivo es limpiar los datos, segmentar a los clientes por edad y nivel de uso, y generar recomendaciones para mejorar la oferta de planes.

## Objetivo del proyecto

- Identificar y corregir problemas de calidad de datos (nulos, sentinels y fechas imposibles)
- Resumir el comportamiento de uso de cada usuario
- Segmentar a los clientes por edad y nivel de uso
- Detectar patrones de uso extremo (outliers)
- Generar recomendaciones accionables sobre los planes para el equipo de negocio

## Contenido del repositorio

- `connectatel-analysis.ipynb`
  → Notebook principal con la limpieza, el análisis, las visualizaciones y el análisis ejecutivo.
- `README.md`
  → Documentación del proyecto.

## Datasets utilizados

`plans.csv`: Catálogo de planes (Basico y Premium): mensajes, minutos y GB incluidos, y precio mensual 
`users_latam.csv`: 4,000 usuarios: edad, ciudad, fecha de registro, plan y fecha de baja 
`usage.csv`: 40,000 registros de uso (llamadas y mensajes) con fecha, duración y longitud 

Los datos de uso cubren de enero a junio de 2024.

## Etapas del análisis

1. Exploración inicial: estructura de los datasets y análisis de valores nulos (missingness).
2. Limpieza:
   - Detección y reemplazo de sentinels (`-999` en `age`, `"?"` en `city`).
   - Conversión de columnas a tipo fecha y corrección de fechas imposibles (año 2026 en `reg_date`).
   - Verificación de que los nulos de `duration` y `length` dependen del tipo de uso, por lo que se conservan.
3. Agrupación por usuario: cantidad de mensajes, de llamadas y total de minutos de llamada, combinada con los datos de usuarios.
4. Análisis estadístico y distribuciones resumen numérico, distribución de planes e histogramas por plan.
5. Outliers: boxplots y método IQR para variables de uso.
6. Segmentación: grupos de uso (Bajo uso, Uso medio, Alto uso) y de edad (Joven, Adulto, Adulto Mayor), con visualizaciones.
7. Análisis ejecutivo: hallazgos y recomendaciones para los planes.

## Cómo abrir el notebook en Google Colab

1. Abre el archivo `Connectatel-analysis.ipynb` en GitHub
2. Haz clic en 'Open in Colab'

## 📘 Guía de reproducción

1. Abre el notebook en Google Colab.
2. Sube los archivos `plans.csv`, `users_latam.csv` y `usage.csv` al entorno de Colab.
3. Ejecuta las celdas en orden, de arriba hacia abajo.
4. Revisa el Análisis ejecutivo al final del notebook.
