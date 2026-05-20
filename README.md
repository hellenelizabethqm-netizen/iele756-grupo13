# iele756-region-XXXX
# Miembros
1. Hellen Quiñones
2. Gustavo Sanchez

# Comunas asignadas
Alhue, La Pintana, Huechuraba, María Pinto, El Monte

# Bases de datos
Para este código se utilizaron distintas bases de datos las cuáles puedes decargar, junto con sus diccionarios, desde sus páginas oficiales:

**Censo 2024** https://censo2024.ine.gob.cl/resultados/

**ENO CHILE (Enfermedades de Notificación Obligatoria)** https://epi.minsal.cl/bases-de-datos-eno/

**GRD** 
---

# Anomalía identificada

La anomalía principal detectada en este proyecto corresponde a la comuna de **Calera de Tango**, que presenta una estadía hospitalaria promedio observada notablemente mayor a la predicha por nuestro modelo OLS.

Esta anomalía fue identificada en la **Tarea 3- parte 3**, en el modelo continuo para predecir `grd_mean_los` (promedio de días de hospitalización), concretamente en la tabla de los mayores residuos del modelo.

Los resultados obtenidos fueron:

| Variable | Valor |
|---|---|
| `grd_mean_los` (observado) | **7.22** |
| `pred_los` (predicho) | **5.394** |
| `resid_los` (residuo) | **1.826** |

Este es el mayor residuo absoluto que aparece en la tabla, lo que convierte a Calera de Tango en el caso más llamativo del análisis.

Lo interesante es que, considerando el perfil demográfico y social de la comuna incluido en el modelo, esperábamos una estadía media bastante más cercana a la predicción —no casi 1.83 días por encima de ella. En otras palabras, incluso después de ajustar por todas las covariables comunales disponibles, Calera de Tango sigue apareciendo como un outlier relevante.

Como posibles explicaciones preliminares, planteamos tres hipótesis:

1. **Inestabilidad del estimador**: el promedio podría ser poco confiable dado un número relativamente bajo de casos GRD en la comuna.
2. **Case-mix atípico**: podría existir una concentración de hospitalizaciones particularmente largas que infla el promedio observado.
3. **Factores locales no capturados**: patrones de atención o derivación hospitalaria propios de la zona que las covariables comunales actuales no logran recoger.

---

# Estructura del repositorio

```text
.
├── README.md
├── requirements.txt
├── data/
│   ├── CENSO
│   ├── ENO
│   ├── GRD
│   └── shapefiles
│
├── notebooks/
│   ├── tarea0.ipynb
│   ├── tarea1.ipynb
│   ├── tarea2.ipynb
│   ├── tarea3.ipynb
│   └── final_anomaly.ipynb
│
├── outputs/
│   ├── figuras
│   ├── tablas
│   └── csv
│
└── video/
    └── presentacion_final.mp4
```

---

# Notebook principal

El análisis final y la detección de la anomalía se encuentran en:

```text
notebooks/final_anomaly.ipynb

---

# Instalación

Instalar las dependencias con:

```bash
pip install -r requirements.txt
```

Luego abrir los notebooks en Jupyter Notebook o VSCode y ejecutar las celdas en orden.

---

# Librerías principales

```python
pandas
numpy
matplotlib
geopandas
statsmodels
pyarrow
fastparquet
scikit-learn
```

---

# Datos utilizados

Debido al tamaño de los archivos, los datasets originales no se incluyen directamente en el repositorio. El proyecto utiliza:

- Microdatos del Censo 2024
- Datos ENO
- Registros GRD de egresos hospitalarios
- Shapefiles de comunas de Chile
- Tablas auxiliares y diccionarios entregados junto al material del curso

---

# Resumen por tarea

## Tarea 0
Carga inicial, exploración y limpieza de los datasets.

## Tarea 1
Construcción de perfiles demográficos y migratorios comunales a partir del Censo 2024.

## Tarea 2
Construcción de perfiles epidemiológicos usando notificaciones ENO y tasas normalizadas por población.

## Tarea 3
Integración de indicadores demográficos, epidemiológicos y hospitalarios para construir modelos comunales y detectar anomalías mediante regresión OLS.

---

# Disclosure de uso de IA

Durante el desarrollo del proyecto utilizamos herramientas de IA (ChatGPT y Claude) para:

- depuración de código Python,
- organización y limpieza del código,
- mejora de redacción,
- apoyo en interpretación de resultados estadísticos,
- y estructuración de este README.

Todas las decisiones metodológicas, el trabajo de limpieza de datos, el análisis estadístico, la selección de la anomalía y las interpretaciones finales fueron revisadas y validadas por el equipo.



**Imagen de pinguinos para aligerar el estrés**
![image alt](https://github.com/hellenelizabethqm-netizen/iele756-region-XXXX/blob/f244977b272a56ee0258851ad4b5323a8cec88b1/TeamImage.jpg)
