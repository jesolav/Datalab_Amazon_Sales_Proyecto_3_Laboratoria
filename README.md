# Datalab_Amazon_Sales_Proyecto_3_Laboratoria.

**Objetivo:** 
El propósito del este análisis, es entender mejor cómo se perciben los productos en Amazon por parte de los consumidores, identificar patrones en las calificaciones y reseñas, y utilizar esta información para tomar decisiones informadas que optimicen las estrategias de ventas, como ajustar precios, mejorar descripciones de productos, y enfocar los esfuerzos de marketing en categorías más exitosas.




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

[1.1 Conectar/importar datos a herramientas](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/b7f14cd33699709b2549fd514aa340fb3ed7be12/An%C3%A1lisis%20Exploratorio/1.1%20Conectar-importar%20datos%20a%20herramientas.md)

[1.2 Análisis de nulos y duplicados](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/4aacf9902f7a362f93eb085b41be08d4dc376c90/An%C3%A1lisis%20Exploratorio/1.2%20An%C3%A1lisis%20de%20Nulos%20y%20Duplicados.md)

[1.3 Identificar Y Manejar Datos Fuera Del Alcance Del Análisis](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/76141509eea0d896627cc1ef6f0f692f789fa9e8/An%C3%A1lisis%20Exploratorio/1.3%20Resumen%20Estad%C3%ADstico%20Inicial.md)

[1.4 Identificar Y Manejar Datos Discrepantes En Variables Categóricas](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/4aacf9902f7a362f93eb085b41be08d4dc376c90/An%C3%A1lisis%20Exploratorio/1.4%20Distribuci%C3%B3n%20de%20categor%C3%ADas%20y%20calificaciones.md)

[1.5 Identificar Y Manejar Datos Discrepantes En Variables Numéricas](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/4aacf9902f7a362f93eb085b41be08d4dc376c90/An%C3%A1lisis%20Exploratorio/1.5%20Identificar%20Y%20Manejar%20Datos%20Discrepantes%20En%20Variables%20Num%C3%A9ricas.md)

[1.6 Comprobar Y Cambiar Tipo De Dato](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/4aacf9902f7a362f93eb085b41be08d4dc376c90/An%C3%A1lisis%20Exploratorio/1.6%20Comprobar%20Y%20Cambiar%20Tipo%20De%20Dato.md)

[1.7 Crear Nuevas Variables](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/639fc6e53b72b0af13014e4f64df5504d8d09a3c/An%C3%A1lisis%20Exploratorio/1.7%20Crear%20Nuevas%20Variables.md)


🔎 [Análisis exploratorio:]


[2.1 Visualización de Distribuciones](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/aa8d3c891815b477a11a79f7bfb67b95e33b1a59/EDA/2.1%20Visualizaci%C3%B3n%20Distribuciones.md)

[2.2 Medidas de Tendencia Central](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/aa8d3c891815b477a11a79f7bfb67b95e33b1a59/EDA/2.2%20Medidas%20Tendencia%20Central.md)

[2.3 Correlación de Variables](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/aa8d3c891815b477a11a79f7bfb67b95e33b1a59/EDA/2.3%20Correlaci%C3%B3n%20Variables.md)

[2.4 Creación de Cuartiles](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/aa8d3c891815b477a11a79f7bfb67b95e33b1a59/EDA/2.4%20Creaci%C3%B3n%20de%20cuartiles.md)


✅ [Validar Hipótesis:]

[3.1 Hipótesis 1](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/228ead1ee636f06acbb3a1cfe761ae9ca2f92ad2/Validar%20Hip%C3%B3tesis/Hip%C3%B3tesis%201.md)

[3.2 Hipótesis 2](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/228ead1ee636f06acbb3a1cfe761ae9ca2f92ad2/Validar%20Hip%C3%B3tesis/Hip%C3%B3tesis%202.md)

[3.3 Hipótesis 3](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/228ead1ee636f06acbb3a1cfe761ae9ca2f92ad2/Validar%20Hip%C3%B3tesis/Hip%C3%B3tesis%203.md)

[3.4 Hipótesis 4](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/228ead1ee636f06acbb3a1cfe761ae9ca2f92ad2/Validar%20Hip%C3%B3tesis/Hip%C3%B3tesis%204.md)
