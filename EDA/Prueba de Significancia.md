# **Prueba de Significancia**

Para realizar una prueba de comparación de proporciones de sentimientos entre los productos con base en actual_price y discount_price


```python
import pandas as pd
from scipy.stats import chi2_contingency

# Crear una nueva columna 'has_discount' para identificar si el producto tiene descuento
df_unificada['has_discount'] = df_unificada['actual_price'] > df_unificada['discounted_price']

# Crear una tabla cruzada (cross-tabulation) para contar las etiquetas de sentimiento por 'has_discount'
contingency_table = pd.crosstab(df_unificada['title_sentiment_label'], df_unificada['has_discount'])

# Mostrar la tabla de contingencia
print("Tabla de contingencia entre sentimiento y descuento:")
print(contingency_table)

# Realizar la prueba chi-cuadrado
chi2, p, dof, expected = chi2_contingency(contingency_table)

# Mostrar los resultados
print(f"Chi-cuadrado: {chi2}")
print(f"Grados de libertad: {dof}")
print(f"Valor p: {p}")
print("Frecuencias esperadas:")
print(expected)

# Interpretación
if p < 0.05:
    print("Existe una diferencia significativa en la distribución de sentimientos entre productos con y sin descuento.")
else:
    print("No hay una diferencia significativa en la distribución de sentimientos entre productos con y sin descuento.")
```

![image](https://github.com/user-attachments/assets/a6633ee8-ef4d-4249-a225-d5a6b5a7dd02)

### **Conclusión**:
* No hay una diferencia significativa en la distribución de sentimientos entre productos con y sin descuento.

 ![image](https://github.com/user-attachments/assets/3a78af31-9ce1-40f9-9d11-5eae45dec2f3)
