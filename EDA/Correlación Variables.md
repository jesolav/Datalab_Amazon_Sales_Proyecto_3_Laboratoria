### 1.2 Correlación de Variables

```sql
WITH correlations AS (
  SELECT 
    CORR(CAST(discounted_price AS FLOAT64), CAST(actual_price AS FLOAT64)) AS corr_discounted_actual,
    CORR(CAST(discounted_price AS FLOAT64), CAST(discount_percentage AS FLOAT64)) AS corr_discounted_discount,
    CORR(CAST(discounted_price AS FLOAT64), CAST(rating AS FLOAT64)) AS corr_discounted_rating,
    CORR(CAST(discounted_price AS FLOAT64), CAST(rating_count AS FLOAT64)) AS corr_discounted_rating_count,
    CORR(CAST(discounted_price AS FLOAT64), CAST(avg_sentiment AS FLOAT64)) AS corr_discounted_sentiment,
    CORR(CAST(actual_price AS FLOAT64), CAST(discount_percentage AS FLOAT64)) AS corr_actual_discount,
    CORR(CAST(actual_price AS FLOAT64), CAST(rating AS FLOAT64)) AS corr_actual_rating,
    CORR(CAST(actual_price AS FLOAT64), CAST(rating_count AS FLOAT64)) AS corr_actual_rating_count,
    CORR(CAST(actual_price AS FLOAT64), CAST(avg_sentiment AS FLOAT64)) AS corr_actual_sentiment,
    CORR(CAST(discount_percentage AS FLOAT64), CAST(rating AS FLOAT64)) AS corr_discount_rating,
    CORR(CAST(discount_percentage AS FLOAT64), CAST(rating_count AS FLOAT64)) AS corr_discount_rating_count,
    CORR(CAST(discount_percentage AS FLOAT64), CAST(avg_sentiment AS FLOAT64)) AS corr_discount_sentiment,
    CORR(CAST(rating AS FLOAT64), CAST(rating_count AS FLOAT64)) AS corr_rating_rating_count,
    CORR(CAST(rating AS FLOAT64), CAST(avg_sentiment AS FLOAT64)) AS corr_rating_sentiment,
    CORR(CAST(rating_count AS FLOAT64), CAST(avg_sentiment AS FLOAT64)) AS corr_rating_count_sentiment
  FROM `datalab-433117.dataset.tabla_unificada`
)

SELECT * FROM correlations;
```

![image](https://github.com/user-attachments/assets/ec58bd37-29cf-45a9-b3e0-52beaa6c27b7)


# **Matriz de correlación en python**
```python
# Seleccionar las columnas para el análisis de correlación
columns_for_correlation = ['discounted_price', 'actual_price', 'discount_percentage', 'rating', 'rating_count', 'avg_sentiment']

# Calcular la matriz de correlación
correlation_matrix = df_unificada[columns_for_correlation].corr()

# Crear un mapa de calor con una paleta personalizada basada en los colores de Amazon
amazon_cmap = LinearSegmentedColormap.from_list("amazon", ['#FF9900', '#146EB4'], N=50)

# Mostrar el mapa de calor
plt.figure(figsize=(10, 8))
sns.heatmap(correlation_matrix, annot=True, cmap=amazon_cmap, fmt=".2f", linewidths=0.5)

# Título del gráfico
plt.title('Mapa de Calor de Correlaciones', color='#000000')
plt.show()
```
![image](https://github.com/user-attachments/assets/209ab4ba-900d-4d3c-84fe-aa6e197901f2)

