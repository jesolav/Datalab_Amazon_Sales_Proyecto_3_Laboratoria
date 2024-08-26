# Datalab_Amazon_Sales_Proyecto_3_Laboratoria.


<details>
<summary> ⚙️ Herramientas y Recursos</summary>

- Google BigQuery
- Google Colab
- Google Slides
- Google Looker Studio

</details>


<details>
<summary> 📄 Resumen de las Tablas de Amazon</summary>


<details>
<summary> <strong> amazon_product.csv </strong></summary>
Este archivo contiene información relacionada con productos disponibles en Amazon. Las columnas presentes en este archivo son las siguientes:

- **product_id**: Un identificador único para cada producto.
- **product_name**: El nombre del producto.
- **category**: La categoría del producto, que incluye una jerarquía separada por `|`.
- **discounted_price**: El precio del producto después de aplicar descuentos.
- **actual_price**: El precio original del producto antes del descuento.
- **discount_percentage**: El porcentaje de descuento aplicado al producto.
- **about_product**: Una descripción breve o resumen de las características principales del producto.
</details>


<details>
<summary> <strong>  amazon_review.csv </strong></summary>
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
</details>
</details>

### 💻 [Procesamiento y preparación para analisis de datos:] 

[Conectar/importar datos a herramientas](https://github.com/jesolav/Riesgo_Relativo_Proyecto_3_Laboratoria-/blob/01d3cde026e2852c46698d89d54d617758d478b1/%5BProcesamiento%20y%20preparaci%C3%B3n%20para%20analisis%20de%20datos%3A/2.1%20Conectar%20e%20importar%20datos%20a%20herramientas.md)

[1.2 Análisis de nulos y duplicados](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/76141509eea0d896627cc1ef6f0f692f789fa9e8/An%C3%A1lisis%20Exploratorio/1.2%20An%C3%A1lisis%20de%20Nulos%20y%20Duplicados.md)

[1.3 Resumen Estadístico Inicial](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/76141509eea0d896627cc1ef6f0f692f789fa9e8/An%C3%A1lisis%20Exploratorio/1.3%20Resumen%20Estad%C3%ADstico%20Inicial.md)

[1.4 Distribución de categorías y calificaciones](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/76141509eea0d896627cc1ef6f0f692f789fa9e8/An%C3%A1lisis%20Exploratorio/1.4%20Distribuci%C3%B3n%20de%20categor%C3%ADas%20y%20calificaciones.md)


