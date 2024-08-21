# Datalab_Amazon_Sales_Proyecto_3_Laboratoria.


# Resumen de las Tablas de Amazon

## amazon_product.csv

Este archivo contiene información relacionada con productos disponibles en Amazon. Las columnas presentes en este archivo son las siguientes:

- **product_id**: Un identificador único para cada producto.
- **product_name**: El nombre del producto.
- **category**: La categoría del producto, que incluye una jerarquía separada por `|`.
- **discounted_price**: El precio del producto después de aplicar descuentos.
- **actual_price**: El precio original del producto antes del descuento.
- **discount_percentage**: El porcentaje de descuento aplicado al producto.
- **about_product**: Una descripción breve o resumen de las características principales del producto.

## amazon_review.csv

Este archivo contiene información sobre las reseñas de productos en Amazon. Las columnas presentes en este archivo son las siguientes:

- **user_id**: Identificadores únicos para cada usuario que ha dejado una reseña. (Separados por comas en algunos casos).
- **user_name**: Los nombres de los usuarios que dejaron la reseña, también como una lista separada por comas.
- **review_id**: Identificadores únicos para cada reseña, separados por comas.
- **review_title**: Títulos de las reseñas, también separados por comas.
- **review_content**: Contenido o texto de las reseñas, separado por comas.
- **img_link**: Enlace a la imagen del producto asociado con la reseña.
- **product_link**: Enlace al producto en Amazon.
- **product_id**: Un identificador único para cada producto, que se puede relacionar con la tabla de productos.
- **rating**: Calificación dada por el usuario al producto.
- **rating_count**: Número total de veces que el producto ha sido calificado.
