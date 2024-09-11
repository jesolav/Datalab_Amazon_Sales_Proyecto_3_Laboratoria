
# Análisis de Correlación de Variables Numéricas

Este análisis de correlación evalúa la relación entre varias variables numéricas dentro del dataset proporcionado. A continuación se presentan las principales variables analizadas y las correlaciones encontradas.

## Variables Analizadas:
1. **discounted_price** (Precio con descuento)
2. **actual_price** (Precio original)
3. **discount_percentage** (Porcentaje de descuento)
4. **rating** (Calificación de usuarios)
5. **rating_count** (Número de reseñas)

## Matriz de Correlación:

| Variable              | discounted_price | actual_price | discount_percentage | rating | rating_count |
|-----------------------|------------------|--------------|---------------------|--------|--------------|
| **discounted_price**   | 1.00             | 0.96         | -0.17               | 0.13   | -0.08        |
| **actual_price**       | 0.96             | 1.00         | -0.03               | 0.13   | -0.07        |
| **discount_percentage**| -0.17            | -0.03        | 1.00                | -0.18  | 0.08         |
| **rating**             | 0.13             | 0.13         | -0.18               | 1.00   | 0.16         |
| **rating_count**       | -0.08            | -0.07        | 0.08                | 0.16   | 1.00         |

## Observaciones:

- El **precio con descuento** y el **precio original** están fuertemente correlacionados (0.96), lo cual es esperado, ya que ambos precios están relacionados.
- El **porcentaje de descuento** tiene una correlación negativa leve con el **precio** (-0.17 para el precio descontado y -0.03 para el original), lo que indica que los productos con mayores descuentos tienden a tener precios más bajos.
- Las **calificaciones** tienen una correlación positiva leve con el **precio**, lo que sugiere que los productos más caros tienden a tener mejores calificaciones.
- El **número de reseñas** no muestra una fuerte correlación con ninguna otra variable.

## Conclusión:

Este análisis muestra que, aunque algunas variables como el precio con descuento y el precio original están fuertemente correlacionadas, otras variables como el porcentaje de descuento y el número de reseñas tienen correlaciones débiles con las calificaciones y los precios. Esto sugiere que el precio no es un indicador fuerte del número de reseñas o del porcentaje de descuento.
