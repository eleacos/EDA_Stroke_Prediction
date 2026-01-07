# Stroke Prediction Dataset – Exploratory Data Analysis

## 1. Descripción del proyecto:
El ictus es una enfermedad cerebrovascular y es actualmente la segunda causa de mortalidad a nivel mundial. Es también, a su vez, la primera causa de mortalidad femenina y la principal causa de discapacidad permanente cerebral. Debido a la gravedad de la enfermedad, es importante concienciar a la población acerca de la misma informando qué lo produce y los métodos para prevenirlo.

En este EDA, se ha utilizado un dataset encontrado en Kaggle llamado **Stroke Prediction Dataset**. Nuestro objetivo principal en este estudio es analizar los factores asociados a la ocurrencia de ictus e identificar variables que muestran una mayor relación con su aparición. 

## 2. Objetivos:
- Analizar las diferencias entre personas que han sufrido ictus y las que no.
- Identificar las variables que más se asocian con el ictus.
- Detectar patrones relevantes en variables demográficas y clínicas.
- Dar recomendaciones para prevenir la enfermedad.

## 3. Description del dataset:
Fuente: Kaggle (Stroke Prediction Dataset- https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset/data)
Número de observaciones: 5110
Número de variables: 12
Tipos de variables:
Demográficas: **id**, **gender** (género), **age** (edad)
Clínicas: **hypertension** (hipertensión), **heart_disease** (enfermedad cardíaca), **avg_glucose_level** (nivel de glucosa medio), **bmi** (índice de masa corporal - IMC), **stroke** (ictus)
Estilo de vida: **smoking_status** (estado de fumador), **ever_married** (casado alguna vez), **work_type** (tipo de trabajo), **residence_type** (tipo de residencia)
- Variable target: **stroke** (0 = no; 1= sí)

## 4. Limpieza de datos y preprocesado:
- Se identificó una única variable con valores faltantes, la columna ***bmi***, que presentaba 201 valores nulos. Dado que se trata de una variable numérica, se optó por imputar estos valores utilizando la media.

- Aunque no se detectaron más valores nulos, algunas variables requirieron tratamiento adicional. En la variable ***age***, el tipo de dato era decimal (*float*), por lo que se decidió convertirla a entero (*int*), interpretando el valor 0 como bebés con edades comprendidas entre 0 y 11 meses.

- En la variable ***gender*** se identificaron tres categorías (*Male*, *Female* y *Other*), siendo esta última un único caso aislado. Al tratarse de una variable categórica nominal, se decidió reemplazar el valor *Other* por la moda, quedando finalmente las categorías *Male* y *Female*.

- En cuanto a la variable ***smoking_status***, se encontraron cuatro categorías (*never smoked, formerly smoked, smokes* y *Unknown*). Dado que los valores *Unknown* representan aproximadamente un 30 % del total, se decidió mantener esta categoría y analizarla como información desconocida en lugar de imputarla o eliminarla.

- Algunas variables no se utilizaron en el análisis final tras realizar un análisis exploratorio preliminar, ya que no aportaban información relevante en relación con la variable objetivo *stroke*.

- Por último, se eliminó la columna *id*, ya que actuaba únicamente como un identificador único de cada individuo y no aportaba valor analítico al estudio de la incidencia del ictus.


## 5. Exploratory Data Analysis (EDA)

### Análisis univariante:

- Dentro de las **variables categóricas**

	- ***gender***, variable binaria: Un 58.61% de participantes son mujeres frente a un 41.39% que son hombres. Se empleó un diagrama de barras para ver las frecuencias absolutas y relativas, y un gráfico de tarta para el porcentaje absoluto.

	- ***hypertension***, variable binaria: Un 9.75% de ellos tienen hipertensión, frente al 90.25% que no tienen hipertensión. Se empleó un diagrama de barras para ver las frecuencias absolutas y relativas, y un gráfico de tarta para el porcentaje absoluto.

	- ***heart_disease***, variable binaria: De ellos, alrededor de un 5.4% presentan alguna enfermedad cardiaca, y hay un 94.6% que no presentan ninguna enfermedad cardiaca. Se utilizó un gráfico de tarta para obtener el porcentaje absoluto.

	- ***smoking_status***, variable categórica: Más del 35% de personas del estudio no fuman; hay aproximadamente un 18% de personas que fumaban antes; un 15% de ellos fumaban en el momento del estudio, y hay un 30% de personas de las que se desconoce si fuman, fumaban o no fumaban. Se empleó un diagrama de barras para ver las frecuencias absolutas y relativas.

	- ***stroke***, variable binaria: Hay un 95.13% de personas que no han sufrido ictus antes, y un 4,87% que sí (249 personas). Se empleó un diagrama de barras para ver las frecuencias absolutas y relativas, y un diagrama de tarta para el porcentaje absoluto.

- Dentro de las **variables numéricas:**

	- ***age***, variable numérica discreta: Las edades se comprenden entre los 0 y 82 años. Se empleó un histograma para ver el reparto de edades, con picos de edad entre los 45 y 60 años, así como entre los 78 y 82 años.

	- ***avg_glucose_level***, variable numérica continua: Los niveles de glucosa son en su mayoría entre 50 y 150, que son valores normales. Se empleó un diagrama de violín para su visualización.

	- ***bmi***, variable numérica discreta: Respecto a la edad, el índice de masa corporal aumenta entre los 0 y 30 años; es estable entre los 30 y 60 años y disminuye ligeramente entre los 60 y 82 años. Se empleó un gráfico de línea para visualizar el valor del “bmi” a lo largo del valor de edad.

### Análisis bivariante: 
- La variable directora es ***“stroke”***, de tipo categórica binaria, en donde el valor *stroke* = 0 corresponde a la no ocurrencia de ictus, y el valor *stroke* = 1 corresponde con la ocurrencia de ictus.

   - ***age vs stroke***: se valora si la edad es un factor de riesgo para sufrir ictus. Para la visualización, se emplea un boxplot y un diagrama de violín, y se comprueba que los casos en los que se ha sufrido ictus se concentran en personas de mayor edad, a partir de los 60 años aproximadamente. Se concluye entonces que a mayor edad, hay mayor riesgo de sufrir ictus.

   - ***hypertension vs stroke***: se valora si la hipertensión es un factor de riesgo para tener un ictus. Se realiza una tabla de contingencia normalizada para obtener el porcentaje de personas con hipertensión, y se visualiza mediante un gráfico de barras. Se concluye que la hipertensión es un factor de riesgo a la hora de sufrir un ictus. Una persona con hipertensión tiene un 13% de probabilidad de sufrir un ictus, frente al aproximado 4% de probabilidad que tiene una persona sin hipertensión.

   - **avg_glucose_level vs stroke**: Se analiza si los valores de glucemia son un factor de riesgo para la aparición de un ictus. Para su visualización, se emplea un boxplot en el que se descubre que el nivel medio de glucosa es mucho mayor en personas que han tenido ictus (sube hasta 200 aproximadamente) frente a las personas que no (que sube hasta 115 aproximadamente). Esto sugiere que niveles elevados de glucosa estan relacionados con una mayor posibilidad de ictus.

   - **bmi vs stroke**: Se estudia si un valor alto de IMC corresponde con una mayor posibilidad a sufrir un ictus. Empleando un boxplot se visualiza que los valores son similares y no parece haber una relación directa. Por tanto, no se observa una asociación clara entre el IMC y la ocurrencia de ictus en este dataset.

### Análisis multivariante:
- ***hypertension vs age vs stroke:*** Se analiza la relación entre tener hipertensión y la edad respecto a sufrir un ictus. Se emplea un boxplot en el que se observa que las personas de mayor edad, con o sin hipertensión, han sufrido un ictus. También se observa que las personas con hipertensión que han sufrido ictus son mayores que las personas que no tienen hipertensión y no han sufrido ictus. 

- ***smoking_status vs heart_disease vs stroke:*** Se analiza la relación entre fumar, tener una cardiopatia y la posibilidad de sufrir un ictus. Se emplea un diagrama de calor y se observa que:

   - hay una mayor asociación entre las personas con una enfermedad cardiaca, que fuman y que han sufrido ictus. 

   - También se observa que las personas que no fuman y que tienen una cardiopatía tienen un riesgo menor a sufrir ictus.

   - Las personas que dejaron de fumar tienen un riesgo a sufrir ictus menor que las personas que fuman, pero no es menor a las personas que nunca han fumado.

   - En cuanto a los valores *Unknown*, se observa que las personas con cardiopatía presentan una probabilidad mayor a sufrir un ictus frente a las personas que no tienen una cardiopatía. Sin embargo, debido a la ambigüedad de esta categoría, su interpretación es limitada.

## 6. Principales hallazgos:
- La edad muestra una fuerte relación con el ictus. A mayor edad, hay más riesgo de sufrir ictus.
- Las personas con hipertensión y enfermedades cardíacas presentan un mayor riesgo.
- Altos niveles de glucosa están relacionados con el ictus.
- El hábito de fumar muestra una fuerte relación con el ictus.
- Estas observaciones son consistentes con la evidencia científica. 

## 7. Limitaciones:
- El dataset está desbalanceado. La proporción de personas que han sufrido ictus es mucho menor respecto a las personas que no (4861 personas no; 249 personas sí).
- Hay valores faltantes.
- Hay variables categóricas con información incompleta, como en smoking_status con sus valores Unknown, que son 1544 valores respecto al total.
- Este análisis se basa en datos observaciones. Por ello, no se puede inferir una relación causal sino solamente asociaciones entre variables y la ocurrencia de ictus.

## 8. Trabajo futuro:
Como continuación de este análisis exploratorio, el proyecto podría ampliarse mediante la aplicación de técnicas de ingeniería de variables (feature engineering), como la transformación de variables continuas, la creación de rangos de edad o la codificación de variables categóricas para su uso en modelos predictivos.

## 9. Herramientas y tecnologías:
- Python
- Pandas
- Numpy
- Matplotlib
- Seaborn
- Jupyter Notebook

## 10. Estructura del repositorio:

```text
EDA_STROKE_PREDICTION/
│
├── src/
│   ├── data/
│   │   └── healthcare-dataset-stroke-data.csv
│   │
│   └── img/
│       ├── univariate_*.png
│       ├── bivariate_*.png
│       └── multivariate_*.png
│
├── notebooks/
│   ├── notebook-eda-principal.ipynb
│   └── notebook-eda-analisis_alternativo.ipynb
│
├── main.py
├── README.md
├── .gitignore
│
├── EDA Project Break.docx
├── Memoria.pdf
└── Presentacion.pdf
```


## 11. Autores:

Elena Acosta

Eric Calvo

Brenda Oyola



