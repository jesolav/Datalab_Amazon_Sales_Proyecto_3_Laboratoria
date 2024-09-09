# **3. Validar Hipótesis**

## 3.2 Hipótesis 2: A mayor número de personas que evaluaron el producto, mejor será la calificación.

- El objetivo es comprobar si existe una relación directa entre el número de personas que evaluaron un producto y la calificación promedio que recibe. Para ello, se analizará la correlación entre el número de evaluaciones (rating_count) y la calificación promedio (rating).}

# Cómo se realizó el análisis
El análisis se realizó en dos fases:

Cálculo de la correlación con todos los datos para observar la relación general entre el número de evaluaciones y la calificación.
Cálculo de la correlación eliminando outliers utilizando el método del rango intercuartílico (IQR) para analizar si los datos atípicos estaban afectando la relación.

```python

 import matplotlib.pyplot as plt
import pandas as pd

# Función para eliminar outliers usando el método IQR
def remove_outliers_iqr(df, column):
    Q1 = df[column].quantile(0.25)
    Q3 = df[column].quantile(0.75)
    IQR = Q3 - Q1
    lower_bound = Q1 - 1.5 * IQR
    upper_bound = Q3 + 1.5 * IQR
    return df[(df[column] >= lower_bound) & (df[column] <= upper_bound)]

# Calcular correlación con outliers
correlation_with_outliers = df[['rating_count', 'rating']].corr().iloc[0, 1]
print(f"Correlación con outliers: {correlation_with_outliers}")

# Eliminar outliers de la columna 'rating_count'
df_no_outliers = remove_outliers_iqr(df, 'rating_count')

# Calcular correlación sin outliers
correlation_without_outliers = df_no_outliers[['rating_count', 'rating']].corr().iloc[0, 1]
print(f"Correlación sin outliers: {correlation_without_outliers}")

# Gráfico con outliers
plt.figure(figsize=(8,6))
plt.scatter(df['rating_count'], df['rating'], color='orange', alpha=0.5)
plt.title('Relación entre Número de Evaluaciones y Puntuación del Producto (Con Outliers)')
plt.xlabel('Número de Evaluaciones')
plt.ylabel('Puntuación del Producto')
plt.grid(True)
plt.show()

# Gráfico sin outliers
plt.figure(figsize=(8,6))
plt.scatter(df_no_outliers['rating_count'], df_no_outliers['rating'], color='orange', alpha=0.5)
plt.title('Relación entre Número de Evaluaciones y Puntuación del Producto (Sin Outliers)')
plt.xlabel('Número de Evaluaciones')
plt.ylabel('Puntuación del Producto')
plt.grid(True)
plt.show()

``` 

# Resultados
Correlaciones:
Correlación con outliers: 0.0983
Correlación sin outliers: 0.1695

### Gráficos

Gráfico con outliers: 

 <img width="585" alt="image" src="https://github.com/user-attachments/assets/10b811e7-136d-4ad1-9775-a1849a1dcd73">


Gráfico sin outliers:

<img width="585" alt="image" src="https://github.com/user-attachments/assets/3fa7db69-28e9-497e-8f1a-e955cf64cdbb">


### Interpretación de los Gráficos
Gráfico con outliers:

En este gráfico, se puede observar que los puntos están dispersos sin un patrón claro, lo que sugiere una correlación muy baja entre el número de evaluaciones y la calificación promedio.
La correlación calculada es de 0.0983, lo cual indica una relación débil.
Gráfico sin outliers:

Al eliminar los valores atípicos, los datos parecen estar menos dispersos, pero el patrón sigue sin ser claro.
La correlación mejora ligeramente a 0.1695, pero aún así sigue siendo débil.

# Conclusiones
El análisis realizado no respalda la hipótesis de que "A mayor número de personas que evaluaron el producto, mejor será la calificación". Aunque al eliminar los outliers la correlación aumenta, sigue siendo muy baja, lo que indica que no hay una relación significativa entre el número de evaluaciones y la puntuación del producto.

