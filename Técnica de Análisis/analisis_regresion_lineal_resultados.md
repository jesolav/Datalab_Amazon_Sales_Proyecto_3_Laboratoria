
# Análisis de Regresión Lineal

## Ecuación de la regresión:

**Precio original = (1.5498748055884435 * Precio descontado) + (106.96868025787705 * Calificación) + (-0.0020342360092513445 * Número de reseñas) + 266.9162701576606**

---

## Resultados clave:

- **Coeficiente de Precio Descontado**: 1.55. Por cada unidad que aumenta el precio descontado, el precio original aumenta en aproximadamente 1.55 unidades.
  
- **Coeficiente de Calificación**: 106.97. Por cada incremento de una estrella en la calificación del producto, el precio original aumenta en 106.97 unidades monetarias.
  
- **Coeficiente del Número de Reseñas**: -0.002. El número de reseñas no tiene un impacto significativo en el precio original, ya que el coeficiente es cercano a cero.

---

## Conclusiones:

1. **Relación entre el precio descontado y el precio original**: Existe una fuerte correlación positiva entre el precio descontado y el precio original, lo cual es intuitivo ya que el precio original es generalmente superior al precio con descuento.

2. **Impacto de la calificación**: La calificación tiene un impacto significativo en el precio original. Los productos mejor valorados tienden a tener precios originales más altos. Cada estrella adicional en la calificación aumenta el precio original en 106.97 unidades monetarias.

3. **Número de reseñas**: El número de reseñas no parece ser un predictor importante del precio original en este modelo, ya que su coeficiente es muy bajo y negativo.

---

## Observaciones:

Este análisis sugiere que las calificaciones de los productos son un factor importante a considerar al analizar el precio original. Los vendedores podrían beneficiarse al mejorar la percepción del producto para justificar precios más altos.

El número de reseñas no es tan influyente como las calificaciones o el precio descontado, lo que sugiere que la cantidad de reseñas no necesariamente refleja un aumento en el precio.



```python
# Asegurarse de que las columnas que vamos a usar sean numéricas
df['discounted_price'] = pd.to_numeric(df['discounted_price'], errors='coerce')
df['actual_price'] = pd.to_numeric(df['actual_price'], errors='coerce')

# Si la columna rating ya es numérica, no es necesario usar el método .str
# Verificamos si la columna es numérica antes de aplicar el reemplazo
if df['rating'].dtype == 'object':  # Esto verifica si es de tipo string
    df['rating'] = df['rating'].str.replace(',', '.').astype(float)
else:
    df['rating'] = pd.to_numeric(df['rating'], errors='coerce')

df['rating_count'] = pd.to_numeric(df['rating_count'], errors='coerce')

# Eliminar filas con valores faltantes
filtered_data = df[['discounted_price', 'rating', 'rating_count', 'actual_price']].dropna()

# Dividir las variables independientes (X) y la variable dependiente (y)
X = filtered_data[['discounted_price', 'rating', 'rating_count']]
y = filtered_data['actual_price']

# Dividir el conjunto de datos en entrenamiento y prueba
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Crear y entrenar el modelo de regresión lineal
from sklearn.linear_model import LinearRegression
linear_regressor = LinearRegression()
linear_regressor.fit(X_train, y_train)

# Hacer predicciones con el conjunto de prueba
y_pred = linear_regressor.predict(X_test)

# Evaluar el modelo
from sklearn.metrics import mean_squared_error, r2_score
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)

# Mostrar los resultados
print("Coeficientes:", linear_regressor.coef_)
print("Intercepto:", linear_regressor.intercept_)
print("Error Cuadrático Medio (MSE):", mse)
print("R² (R-squared):", r2)

# Mostrar la ecuación de la regresión lineal
print("\nEcuación de la regresión:")
print(f"Precio original = ({linear_regressor.coef_[0]} * Precio descontado) + ({linear_regressor.coef_[1]} * Calificación) + ({linear_regressor.coef_[2]} * Número de reseñas) + {linear_regressor.intercept_}")


