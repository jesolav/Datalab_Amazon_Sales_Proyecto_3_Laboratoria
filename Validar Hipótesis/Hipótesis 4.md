# **3. Validar Hipótesis**

## 3.4 Hipótesis 4: Los productos con mayores descuentos tienen un sentimiento más positivo.

El objetivo de este análisis es comprobar si existe una relación directa entre el **porcentaje de descuento** aplicado a los productos y el **sentimiento promedio** de las reseñas. Para ello, se analizará la correlación entre estas dos variables.

## Análisis y Código Utilizado

### Consultas SQL

#### **Consulta SQL para calcular la correlación entre el porcentaje de descuento y el sentimiento promedio:**

```sql
SELECT
  CORR(CAST(discount_percentage AS FLOAT64), CAST(avg_sentiment AS FLOAT64)) AS correlacion_descuento_sentimiento
FROM
  `datalab-433116.dataset.tabla_unificada`;

```
### Código en Python
El siguiente script se utilizó para calcular la correlación y visualizar la relación entre el porcentaje de descuento y el sentimiento promedio.

```python

import matplotlib.pyplot as plt
import pandas as pd

# Verificar el tipo de dato de 'discount_percentage' antes de aplicar la conversión
if df['discount_percentage'].dtype == 'object':
    df['discount_percentage'] = df['discount_percentage'].astype(str).str.replace(',', '.', regex=False)

# Convertir las columnas de porcentaje de descuento y sentimiento promedio a numérico
df['discount_percentage'] = pd.to_numeric(df['discount_percentage'], errors='coerce')
df['avg_sentiment'] = pd.to_numeric(df['avg_sentiment'], errors='coerce')

# Calcular la correlación entre porcentaje de descuento y sentimiento promedio
correlation_discount_sentiment = df[['discount_percentage', 'avg_sentiment']].corr().iloc[0, 1]
print(f"Correlación entre porcentaje de descuento y sentimiento promedio: {correlation_discount_sentiment}")

# Crear el gráfico de dispersión para visualizar la relación
plt.figure(figsize=(8,6))
plt.scatter(df['discount_percentage'], df['avg_sentiment'], color='green', alpha=0.5)
plt.title('Relación entre Porcentaje de Descuento y Sentimiento Promedio')
plt.xlabel('Porcentaje de Descuento')
plt.ylabel('Sentimiento Promedio')
plt.grid(True)
plt.savefig('images/grafico_descuento_vs_sentimiento.png')
plt.show()

```

## Resultados
Correlación:
Correlación entre porcentaje de descuento y sentimiento promedio: -0.0132
Este valor indica que no existe una relación significativa entre el porcentaje de descuento aplicado y el sentimiento promedio de los clientes. La correlación extremadamente baja sugiere que los descuentos no influyen en cómo los clientes valoran el producto en términos de sentimientos.

## Gráficos
Gráfico: Relación entre Porcentaje de Descuento y Sentimiento Promedio

<img width="578" alt="image" src="https://github.com/user-attachments/assets/f4141d9a-3f51-49d8-b63e-b42771668241">


## Interpretación de los Resultados

### Correlación:

El valor de la correlación es -0.0132, lo que sugiere que el porcentaje de descuento no tiene una relación significativa con el sentimiento promedio. Esta correlación baja indica que los descuentos no parecen influir en cómo los clientes perciben los productos en sus reseñas.
Gráfico de Dispersión:

El gráfico muestra una alta dispersión de puntos sin una tendencia clara, lo que refuerza la conclusión de que no hay una relación significativa entre estas dos variables.

