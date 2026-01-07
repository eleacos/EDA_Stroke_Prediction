Stroke Prediction Dataset – Exploratory Data Analysis

1. Description del proyecto:
El ictus es una enfermedad cerebrovascular y es actualmente la segunda causa de mortalidad a nivel mundial. Es también, a su vez, la primera causa de mortalidad femenina y la principal causa de discapacidad permanente cerebral. Debido a la gravedad de la enfermedad, es importante concienciar a la población acerca de la misma informando qué lo produce y los métodos para prevenirlo.
En este EDA, se ha utilizado un dataset encontrado en Kaggle llamado Stroke Prediction Dataset. Nuestro objetivo principal en este estudio es determinar los factores que aumentan la probabilidad de sufrir un ictus.

2. Objetivos:
Analizar las diferencias entre personas que han sufrido ictus y las que no.
Identificar las variables que más se asocian con el ictus.
Detectar patrones relevantes en variables demográficas y clínicas.
Dar recomendaciones para prevenir la enfermedad.

3. Description del dataset:
Fuente: Kaggle (Stroke Prediction Dataset- https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset/data)
Número de observaciones: 5110
Número de variables: 12
Tipos de variables:
Demográficas: id, gender (género), age (edad)
Clínicas: hypertension (hipertensión), heart_disease (enfermedad cardíaca), avg_glucose_level (nivel de glucosa medio), bmi (índice de masa corporal - IMC), stroke (ictus)
Estilo de vida: smoking_status (estado de fumador), ever_married (casado alguna vez), work_type (tipo de trabajo), residence_type (tipo de residencia)
- Variable target: stroke (0 = no; 1= sí)

4. Limpieza de datos y preprocesado:
- Se encontró 1 variable con 201 valores nulos, la columna “bmi”. Por el tipo de variable que es (numérica discreta), se decidió utilizar la media para rellenar los valores faltantes. 
- Aunque no se encontraron más valores faltantes, se encontraron otras variables con valores a tratar:
   - En la variable “age”, el tipo de dato es decimal (float), por lo que se eligió tratar como un entero (int), resultando en que la edad 0 correspondería entonces a los bebés entre 0 y 11 meses.
   - En la variable “gender”, se vieron 3 tipos de valores, “Male”, “Female” y “Other”, habiendo 1 solo elemento que pertenecía al tipo “Other”. Para tratar esta variable, se decidió sustituir el valor de “Other” por la moda al ser una variable categórica nominal. Así, se termina tratando esta variable con los valores de “Male” y “Female”.
   - En la variable “smoking_status”, se encontraron 4 tipos de valores, “never smoked”, "formerly smoked”, “smokes” y “Unknown”. Los valores de “Unknown” representan aproximadamente un 30% sobre el total de personas, por lo que se decidió que sería tratado como sí mismo, y se analiza con otras variables teniendo en cuenta su valor como dato desconocido.
   - Hay variables que posteriormente no se utilizan en el análisis final. Se realizó un breve análisis paralelo con las columnas de importancia tipo 3 respecto a la variable “stroke” que no generó información que pudiera ser relevante en el estudio.
   - Se eliminó la columna “id”, ya que actuaba únicamente como un identificador de cada individuo y no aportaba información relevante para explicar o analizar la incidencia del ictus.


5. Exploratory Data Analysis (EDA)
Análisis univariante:
	- Dentro de las variables categóricas:
		- gender, variable binaria: Un 58.61% de participantes son mujeres frente a un 41.39% que son hombres. Se empleó un diagrama de barras para ver las frecuencias absolutas y relativas, y un gráfico de tarta para el porcentaje absoluto.
		- hypertension, variable binaria: Un 9.75% de ellos tienen hipertensión, frente al 90.25% que no tienen hipertensión. Se empleó un diagrama de barras para ver las frecuencias absolutas y relativas, y un gráfico de tarta para el porcentaje absoluto.
		- heart_disease, variable binaria: De ellos, alrededor de un 5.4% presentan alguna enfermedad cardiaca, y hay un 94.6% que no presentan ninguna enfermedad cardiaca. Se utilizó un gráfico de tarta para obtener el porcentaje absoluto.
		- smoking_status, variable categórica: Más del 35% de personas del estudio no fuman; hay aproximadamente un 18% de personas que fumaban antes; un 15% de ellos fumaban en el momento del estudio, y hay un 30% de personas de las que se desconoce si fuman, fumaban o no fumaban. Se empleó un diagrama de barras para ver las frecuencias absolutas y relativas.
		- stroke, variable binaria: Hay un 95.13% de personas que no han sufrido ictus antes, y un 4,87% que sí (249 personas). Se empleó un diagrama de barras para ver las frecuencias absolutas y relativas, y un diagrama de tarta para el porcentaje absoluto.
	- Dentro de las variables numéricas:
		- age, variable numérica discreta: Las edades se comprenden entre los 0 y 82 años. Se empleó un histograma para ver el reparto de edades, con picos de edad entre los 45 y 60 años, así como entre los 78 y 82 años.
		- avg_glucose_level, variable numérica continua: Los niveles de glucosa son en su mayoría entre 50 y 150, que son valores normales. Se empleó un diagrama de violín para su visualización.
		- bmi, variable numérica discreta: Respecto a la edad, el índice de masa corporal aumenta entre los 0 y 30 años; es estable entre los 30 y 60 años y disminuye ligeramente entre los 60 y 82 años. Se empleó un gráfico de línea para visualizar el valor del “bmi” a lo largo del valor de edad.

Análisis bivariante: 
- La variable directora es “stroke”, de tipo categórica binaria, en donde el valor stroke = 0 corresponde a la no ocurrencia de ictus, y el valor stroke = 1 corresponde con la ocurrencia de ictus.
   - age respecto a stroke: se valora si la edad es un factor de riesgo para sufrir ictus. Para la visualización, se emplea un boxplot y un diagrama de violín, y se comprueba que los casos en los que se ha sufrido ictus se concentran en personas de mayor edad, a partir de los 60 años aproximadamente. Se concluye entonces que a mayor edad, hay mayor riesgo de sufrir ictus.
   - hypertension frente a stroke: se valora si la hipertensión es un factor de riesgo para tener un ictus. Se realiza una tabla de contingencia normalizada para obtener el porcentaje de personas con hipertensión, y se visualiza mediante un gráfico de barras. Se concluye que la hipertensión es un factor de riesgo a la hora de sufrir un ictus. Una persona con hipertensión tiene un 13% de probabilidad de sufrir un ictus, frente al aproximado 4% de probabilidad que tiene una persona sin hipertensión.
   - avg_glucose_level respecto a stroke: Se valora si los valores de glucemia son un factor de riesgo para la aparición de un ictus. Para su visualización, se emplea un boxplot en el que se descubre que el nivel medio de glucosa es mucho mayor en personas que han tenido ictus (sube hasta 200 aproximadamente) frente a las personas que no (que sube hasta 115 aproximadamente). El nivel de glucosa medio es entonces un factor de riesgo para la aparición de un ictus.
   - **bmi frente a stroke**: Se estudia si un valor alto de IMC corresponde con una mayor posibilidad a sufrir un ictus. Empleando un boxplot se visualiza que los valores son similares y no parece haber una relación directa. Por tanto, el IMC no es un factor que predisponga a sufrir un ictus.

Análisis multivariante:
- hypertension vs age vs stroke: Se analiza la relación entre tener hipertensión y la edad respecto a sufrir un ictus. Se emplea un boxplot en el que se observa que las personas de mayor edad, con o sin hipertensión, han sufrido un ictus. También se observa que las personas con hipertensión que han sufrido ictus son mayores que las personas que no tienen hipertensión y no han sufrido ictus. 
- smoking_status vs heart_disease vs stroke: Se analiza la relación entre fumar, tener una cardiopatia y la posibilidad de sufrir un ictus. Se emplea un diagrama de calor y se observa que:
   - hay una mayor asociación entre las personas con una enfermedad cardiaca, que fuman y que han sufrido ictus. 
   - También se observa que las personas que no fuman y que tienen una cardiopatía tienen un riesgo menor a sufrir ictus.
   - Las personas que dejaron de fumar tienen un riesgo a sufrir ictus menor que las personas que fuman, pero no es menor a las personas que nunca han fumado.
   - En cuanto a los valores Unknown, se observa que las personas con cardiopatía presentan una probabilidad mayor a sufrir un ictus frente a las personas que no tienen una cardiopatía. Sin embargo, debido a la ambigüedad de esta categoría, su interpretación es limitada.


## 6. Key Findings
## 7. Limitations
## 8. Future Work
## 9. Tools & Technologies
## 10. Repository Structure
## 11. Author