# **3. Validar Hipótesis**

## 3.5 Hipótesis 5: Los productos con mayores descuentos tienen un sentimiento más positivo.


Regresión Lineal

```python
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score

# Seleccionar características y objetivo
features = df_unificada[['avg_sentiment', 'discount_percentage', 'user_count']]
target = df_unificada['rating']

# Separar los datos en conjuntos de entrenamiento y prueba
X_train, X_test, y_train, y_test = train_test_split(features, target, test_size=0.3, random_state=42)

# Crear el modelo de regresión lineal
model = LinearRegression()

# Entrenar el modelo
model.fit(X_train, y_train)

# Hacer predicciones en el conjunto de prueba
y_pred = model.predict(X_test)

# Evaluar el modelo
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)

print(f'Error cuadrático medio (MSE): {mse}')
print(f'R^2 Score: {r2}')

# Coeficientes del modelo
print(f'Coeficientes: {model.coef_}')
print(f'Intersección: {model.intercept_}')
```
![image](https://github.com/user-attachments/assets/f8c1c39c-17d2-4005-9c12-5a6987f63178)

### **Conclusión para la regresión lineal**
* El modelo de regresión lineal muestra que las variables 'avg_sentiment', 'discount_percentage' y 'user_count' tienen un impacto en la calificación promedio.
* El modelo explica aproximadamente el 65.76% de la variabilidad en la calificación promedio.
* El modelo puede ser utilizado para predecir la calificación promedio de un producto basado en estas variables.

## 4.2 Regresión Logistica

```python
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Convertir la calificación a una variable categórica (por ejemplo, 
#  calificación mayor o igual a 4 como positiva, y menor a 4 como negativa)
df_unificada['rating_category'] = df_unificada['rating'].apply(lambda x: 1 if x >= 4 else 0)

# Seleccionar características y objetivo
features = df_unificada[['avg_sentiment', 'discount_percentage', 'user_count']]
target = df_unificada['rating_category']

# Separar los datos en conjuntos de entrenamiento y prueba
X_train, X_test, y_train, y_test = train_test_split(features, target, test_size=0.3, random_state=42)

# Crear el modelo de regresión logística
model = LogisticRegression()

# Entrenar el modelo
model.fit(X_train, y_train)

# Hacer predicciones en el conjunto de prueba
y_pred = model.predict(X_test)

# Evaluar el modelo
accuracy = accuracy_score(y_test, y_pred)
print(f'Precisión: {accuracy}')

# Matriz de confusión
cm = confusion_matrix(y_test, y_pred)
print(f'Matriz de confusión:\n{cm}')

# Informe de clasificación
print(classification_report(y_test, y_pred))
```

![image](https://github.com/user-attachments/assets/5afad30e-3766-40ff-90b6-4fa4e07db43a)


### **Conclusión para la regresión logística**
* El modelo de regresión logística muestra que las variables 'avg_sentiment', 'discount_percentage' y 'user_count' tienen un impacto en la probabilidad de una calificación positiva.
* El modelo predice correctamente la categoría de calificación en aproximadamente el 80% de los casos.
* El modelo puede ser utilizado para predecir si un producto tendrá una calificación positiva o negativa.

### **Comparación de modelos**
*  La regresión logística parece tener un mejor rendimiento en términos de precisión (80%) en comparación con la regresión lineal (65.76% de variabilidad explicada).
* La elección del mejor modelo depende del objetivo del análisis. Si el objetivo es predecir la calificación exacta, la regresión lineal puede ser más adecuada.
* Si el objetivo es predecir la categoría de calificación (positiva o negativa), la regresión logística es la mejor opción.


