# **3. Validar Hipótesis**

## 3.3 Hipótesis 3: A medida que el sentimiento promedio de las reseñas de un producto aumenta (más positivo), también lo hace la calificación general del producto.

## Objetivo
El objetivo de este análisis es comprobar si existe una relación directa entre el **sentimiento promedio** de las reseñas de un producto y la **calificación promedio** que recibe el producto. Para ello, se analizará la correlación entre estas dos variables.

---

## Análisis y Código Utilizado

### Consultas SQL

#### **Consulta SQL para calcular la correlación entre el sentimiento promedio y la calificación:**

```sql
SELECT
  CORR(CAST(avg_sentiment AS FLOAT64), CAST(rating AS FLOAT64)) AS correlacion_sentimiento_calificacion
FROM
  `datalab-433116.dataset.tabla_unificada`;
```

### Código en Python
El siguiente script se utilizó para calcular la correlación y visualizar la relación entre el sentimiento promedio y la calificación promedio.

```python 
 
import matplotlib.pyplot as plt
import pandas as pd

# Verificar los tipos de datos de las columnas
print(df.dtypes)

# Asegurarse de que las columnas 'avg_sentiment' y 'rating' son strings antes de hacer replace
df['avg_sentiment'] = df['avg_sentiment'].astype(str).str.replace(',', '.', regex=False)
df['rating'] = df['rating'].astype(str).str.replace(',', '.', regex=False)

# Convertir las columnas de sentimiento promedio y calificación a numérico
df['avg_sentiment'] = pd.to_numeric(df['avg_sentiment'], errors='coerce')
df['rating'] = pd.to_numeric(df['rating'], errors='coerce')

# Calcular la correlación entre sentimiento promedio y calificación
correlation_sentiment_rating = df[['avg_sentiment', 'rating']].corr().iloc[0, 1]
print(f"Correlación entre sentimiento promedio y calificación: {correlation_sentiment_rating}")

# Crear el gráfico de dispersión para visualizar la relación
plt.figure(figsize=(8,6))
plt.scatter(df['avg_sentiment'], df['rating'], color='blue', alpha=0.5)
plt.title('Relación entre Sentimiento Promedio y Calificación del Producto')
plt.xlabel('Sentimiento Promedio')
plt.ylabel('Calificación del Producto')
plt.grid(True)
plt.savefig('images/grafico_sentimiento_vs_calificacion.png')
plt.show()
```
## Resultados
Correlación:
Correlación entre sentimiento promedio y calificación: 0.3921
Esta correlación indica una relación positiva moderada entre el sentimiento promedio de las reseñas y la calificación del producto.

## Gráfico: Relación entre Sentimiento Promedio y Calificación del Producto
<img width="570" alt="image" src="https://github.com/user-attachments/assets/a363b4c3-83ad-45ab-892c-19e9c9286c92">

<img width="1056" alt="image" src="https://github.com/user-attachments/assets/821fffe9-d048-46dc-b10c-fcaccf1a45df">


## Interpretación de los Resultados
- Correlación:

La correlación obtenida es de 0.3921, lo que indica que existe una relación positiva moderada entre el sentimiento promedio y la calificación promedio del producto. Es decir, a medida que el sentimiento de las reseñas es más positivo, la calificación promedio del producto también tiende a ser mayor.
Aunque la correlación no es extremadamente alta, sí muestra una tendencia clara.
Gráfico de Dispersión:

El gráfico confirma la relación positiva moderada entre las dos variables. La mayoría de los productos con calificaciones superiores a 4.0 tienden a tener un sentimiento promedio más alto (positivo).

# Conclusiones
Conclusión principal: Existe una correlación positiva moderada entre el sentimiento promedio de las reseñas y la calificación general del producto. Esto sugiere que, en términos generales, las reseñas con mejor sentimiento tienden a estar asociadas con productos mejor calificados.
Implicaciones: Aunque la relación no es extremadamente fuerte, sí hay una tendencia significativa que indica que productos con reseñas más positivas suelen recibir mejores calificaciones.



