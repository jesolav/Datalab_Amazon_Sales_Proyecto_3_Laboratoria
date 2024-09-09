# **3. Validar Hipótesis**

## 3.1 Hipótesis 1: A mayor descuento, mejor será la puntuación.

Esta hipótesis sugiere que los productos con mayores descuentos tienden a recibir mejores calificaciones por parte de los usuarios. Se asume que, al pagar un precio más bajo, los consumidores estarán más satisfechos con la relación calidad-precio del producto y, por lo tanto, otorgarán puntuaciones más altas.

Para comprobar esta hipótesis, realizaremos un análisis de correlación entre el porcentaje de descuento de los productos y sus calificaciones.

## Resolución de la Hipótesis

### Código SQL para BigQuery

El siguiente código SQL se utiliza para calcular la correlación entre el porcentaje de descuento y la puntuación de los productos. Utilizamos la función `CORR()` de BigQuery para obtener esta relación:

```sql
SELECT 
  CORR(discount_percentage, rating) AS correlacion_descuento_puntuacion
FROM 
  `datalab-433116.dataset.tabla_unificada`
```


### Resultado de la Consulta SQL
El resultado de la consulta dio un valor de -0.17, lo cual indica una correlación negativa débil entre el descuento y la puntuación. Esto sugiere que, en general, un mayor descuento no se asocia con una mayor puntuación de los productos, sino que hay una leve tendencia contraria.
Visualización de la Relación: Gráfico de Dispersión
A continuación, se presenta un gráfico de dispersión que visualiza la relación entre el descuento y la puntuación de los productos.

# Visualización de la Relación: Gráfico de Dispersión
A continuación, se presenta un gráfico de dispersión que visualiza la relación entre el descuento y la puntuación de los productos.

### Gráfico de Dispersión en python 

<img width="541" alt="image" src="https://github.com/user-attachments/assets/80492b74-239b-4efb-869d-cf34b7abab1c"> 

``` python 
import matplotlib.pyplot as plt

# Crear el gráfico de dispersión con color naranja usando el DataFrame df
plt.figure(figsize=(8,6))
plt.scatter(df['discount_percentage'], df['rating'], color='orange', alpha=0.5)
plt.title('Relación entre Descuento y Puntuación del Producto')
plt.xlabel('Porcentaje de Descuento')
plt.ylabel('Puntuación del Producto')
plt.grid(True)
plt.show()
```


### Gráfico de Dispersión en tableu
<img width="814" alt="image" src="https://github.com/user-attachments/assets/905a565b-99dc-487c-8189-61612df13f82">

### Explicación del Gráfico
El gráfico de dispersión muestra la relación entre el porcentaje de descuento (eje X) y la puntuación del producto (eje Y). Cada punto representa un producto.
Eje X (Porcentaje de Descuento): Representa el descuento aplicado al producto.
Eje Y (Puntuación del Producto): Representa la calificación promedio que los usuarios le dieron al producto.
En este gráfico, podemos observar que no hay una clara relación directa entre los dos parámetros, lo cual coincide con el análisis de correlación que arrojó una correlación negativa débil.

# Conclusión
El análisis de correlación y el gráfico de dispersión refutan la hipótesis inicial. Aunque se esperaba que un mayor descuento condujera a mejores calificaciones de los productos, el valor de correlación de -0.17 sugiere que, en realidad, a medida que aumenta el descuento, la puntuación tiende a ser ligeramente más baja. Sin embargo, la relación es débil, lo que significa que otros factores no relacionados con el descuento probablemente tienen un mayor impacto en las calificaciones que los usuarios dan a los productos.
Este resultado podría deberse a varios factores, como las expectativas que los consumidores tienen sobre productos con grandes descuentos, lo que podría influir negativamente en la calificación si el producto no cumple con dichas expectativas.








