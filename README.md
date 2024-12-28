# Protección_de_datos_personales_y_predicción_con_Regresion_Lineal
# Introducción
Resolveremos varias tareas con la ayuda de machine learning para la compañía de seguros 'Sure Tomorrow':

**Tarea 1:**
- Encontrar clientes que sean similares a un cliente determinado. Esto ayudará a los agentes de la compañía con el marketing.

**Tarea 2:**
- Predecir la probabilidad de que un nuevo cliente reciba una prestación del seguro. ¿Puede un modelo predictivo funcionar mejor que un modelo dummy?

**Tarea 3:**
- Predecir el número de prestaciones de seguro que un nuevo cliente pueda recibir utilizando un modelo de regresión lineal.

**Tarea 4:** 
- Proteger los datos personales de los clientes sin afectar al modelo. Es necesario desarrollar un algoritmo de transformación de datos que dificulte la recuperación de la información personal si los datos llegaran a caer en manos equivocadas. Esto se denomina **enmascaramiento u ofuscación de datos**. Pero los datos deben protegerse de tal manera que no se vea afectada la calidad de los modelos de machine learning.
# Descripción de los datos
- **Características:** `genero`, `edad`, `salario` y `número de familiares` de la persona asegurada.
- **Objetivo:** `número de beneficios de seguro` recibidos por una persona asegurada en los últimos cinco años.
# Habilidades técnicas
- Phyton (creación de clases para modelos de machine learning)
- Numpy (realización de operaciones matriciales y vectoriales comunes) 
- Matplotlib
- Seaborn
- SciPy 
- Scikit-learn
- Análisis Exploratorio de Datos
- Preprocesamiento de Datos
- Fundamentos de Machine Learning
- Modelos de regresión (Regresión Lineal)
# Conclusión General
- Realizamos un (EDA), y un preprocesamiento de los datos:
  - Tenemos un Dataframe de  4847 filas y 5 columnas
   - No existian valores nulos y eliminamos valores duplicados
   - Observamos que la mayor catidad de ingresos esta entre 40,000 y 50,000
### Tarea 1. Clientes similares
  - Desarrollamos un procedimiento que devolviera los k vecinos más cercanos, con datos escaldos y no escalados y luego igual para diferentes métricas de distancia(euclidiana, manhatan)
  - Concluimos que los datos al no estar escalados la distancia es mucho mayor y como mejor métrica para nuestro caso obtuvimos la distancia euclidiana sin importar si estuvieron escalados o sin escalar!
### Tarea 2. ¿Es probable que el cliente reciba una prestación del seguro?
   - Creamos un modelo dummy y lo probamos con 4 valores de probabilidad:
   - Basado en las matrices de confusión y F1 scores, el umbral de probabilidad 0.50 parece ser el mejor. Proporciona un balance razonable entre verdaderos positivos y falsos negativos, y un F1 score de 0.19, que es el segundo más alto.
### Tarea 3. Regresión lineal
En nuestro modelo de Regresión lineal obtuvimos un:
- RMSE: 0.36
- R2_score:0.66
LO que quiere decir que nuestro modelo es muy preciso **(RMSE)** estan a una distancia de 0.36 unidades entre más cercano al 0 es mejor
y un R2_score de 0.66 significa que el 66% de la variabilidad en los datos de salida puede ser explicada por el modelo. Esto es un indicador de que el modelo tiene una capacidad predictiva moderada. Aqui en este últimop entre más cercano a 1 es mejor!
### Tarea 4. Ofuscar Datos
Realizamos la ofuscación de datos logrando enmascararlos sin afectar la calidad de nuestro modelo.
Usamos una **transformación lineal**(Este enfoque utiliza una matriz invertible para transformar los datos originales, logrando que los datos resultantes sean una versión ofuscada de los originales.)
- **Conclusión final**
No hay ninguna diferencia en las predicciones ni en las metricas con los datos ofuscados y sin ofuscar, los valores son los mismos. La ofuscación de los datos utilizando una matriz invertible  𝑃
  no afecta la calidad del modelo de regresión lineal en términos de los valores predichos ni en términos del error cuadrático medio (RMSE). Esto significa que podemos aplicar ofuscación a los datos para proteger la privacidad sin comprometer la precisión de las predicciones ni la evaluación de la calidad del modelo!!!

​


    
