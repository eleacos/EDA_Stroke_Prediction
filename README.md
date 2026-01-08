
## Stroke Prediction Dataset – Exploratory Data Analysis (EDA)
### 1. Descripción breve

Este proyecto consiste en un análisis exploratorio de datos (EDA) aplicado al Stroke Prediction Dataset obtenido de [Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset/data/ "Stroke Prediction Dataset").

El ictus es una enfermedad cerebrovascular de gran impacto sanitario, siendo una de las principales causas de mortalidad y discapacidad a nivel mundial.

El objetivo del proyecto es analizar los factores demográficos, clínicos y de estilo de vida asociados a la ocurrencia de ictus, con el fin de identificar patrones relevantes y variables que muestran una mayor relación con su aparición.

### 2. Hipótesis planteadas

A lo largo del análisis se plantean las siguientes preguntas de investigación:

- ¿Aumenta la hipertensión arterial la probabilidad de ictus?

- ¿Hay relación entre niveles de glucemia y la probabilidad de sufrir ictus?

- ¿Hay relación entre el IMC y la probabilidad de ictus?

- ¿Hay subgrupos que tengan mayor riesgo de ictus?

### 3. Tecnologías utilizadas

**Lenguaje:** Python

**Librerías:**

- Pandas

- NumPy

- Matplotlib

- Seaborn

**Herramientas:**

- Jupyter Notebook

- Git / GitHub


## 4. Estructura del repositorio:

```
EDA_STROKE_PREDICTION/
│
├── src/
│   ├── data/
│   │   └── healthcare-dataset-stroke-data.csv
│   │
│   ├── img/
│   │   ├── univariante_*.png
│   │   ├── bivariante_*.png
│   │   └── multivariante_*.png
│   │
│   └── notebooks/
│       └── notebook-eda-analisis_alternativo.ipynb
│   
│
├── .gitignore
├── EDA Project Break.docx
├── Memoria.pdf
├── notebook-main.ipynb
└── Presentacion.pdf
└── README.md
```
### 5. Instrucciones de reproducción

Desde una terminal (en bash), ejecutar los siguientes comandos:

**1. Clonar el repositorio:**

**git clone** https://github.com/usuario/EDA_STROKE_PREDICTION.git

**2. Instalar las dependencias necesarias:**

**pip install** pandas numpy matplotlib seaborn

**3. Ejecutar el análisis:**

Abrir los notebooks ubicados en la carpeta notebooks/ con Jupyter Notebook

Alternativamente, ejecutar el archivo principal:
***notebook-main.ipynb***

### 6. Principales conclusiones

- La edad muestra una fuerte relación con la ocurrencia de ictus; el riesgo aumenta notablemente a partir de los 55 años.

- Las personas con hipertensión y enfermedades cardíacas presentan una mayor probabilidad de sufrir un ictus.

- Niveles elevados de glucosa están asociados a una mayor incidencia de ictus.

- El hábito de fumar se relaciona con un mayor riesgo, siendo menor en personas que nunca han fumado o que dejaron de hacerlo.

- Los resultados obtenidos son consistentes con la evidencia científica existente.

### 7. Autores

- **Elena Acosta** – [GitHub](https://github.com/eleacos)  
- **Eric Calvo** – [GitHub](https://github.com/ecalvo2411)  
- **Brenda Oyola** – [GitHub](https://github.com/brendaluoyola) 






