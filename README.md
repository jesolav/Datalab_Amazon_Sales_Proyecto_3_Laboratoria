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

## 💻 [Procesamiento y preparación para analisis de datos:] 

[1.1 Conectar/importar datos a herramientas](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/362ad879b7911c3002fb7e3ecb6b8ea3fb8c78c5/Procesar%20y%20preparar%20la%20base%20de%20datos/1.1%20Conectar-importar%20datos%20a%20herramientas.md)

[1.2 Análisis de nulos y duplicados](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/362ad879b7911c3002fb7e3ecb6b8ea3fb8c78c5/Procesar%20y%20preparar%20la%20base%20de%20datos/1.2%20An%C3%A1lisis%20de%20Nulos%20y%20Duplicados.md)

[1.3 Identificar Y Manejar Datos Fuera Del Alcance Del Análisis](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/362ad879b7911c3002fb7e3ecb6b8ea3fb8c78c5/Procesar%20y%20preparar%20la%20base%20de%20datos/1.3%20Identificar%20Y%20Manejar%20Datos%20Discrepantes%20En%20Variables%20Categ%C3%B3ricas.md)

[1.4 Identificar Y Manejar Datos Discrepantes En Variables Categóricas](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/362ad879b7911c3002fb7e3ecb6b8ea3fb8c78c5/Procesar%20y%20preparar%20la%20base%20de%20datos/1.4%20Comprobar%20Y%20Cambiar%20Tipo%20De%20Dato.md)

[1.5 Estandarización de tabla amazon_reviews para análisis de sentimientos](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/362ad879b7911c3002fb7e3ecb6b8ea3fb8c78c5/Procesar%20y%20preparar%20la%20base%20de%20datos/1.6%20Estandarizaci%C3%B3n%20de%20tabla%20amazon_reviews%20para%20an%C3%A1lisis%20de%20sentimientos.md)

[1.6 Sentiment_Analysis](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/3b601b2d338bdb574fcc235c2debf93c65bc3ed6/Procesar%20y%20preparar%20la%20base%20de%20datos/1.6%20sentiment_analysis.ipynb)

[1.7 Unión Tablas](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/b146729137fb451c42f4f70d2268e2d943382e66/Procesar%20y%20preparar%20la%20base%20de%20datos/1.7%20Uni%C3%B3n%20de%20Tablas.md)


## 🔎 [Análisis exploratorio:]


[2.1 Visualización de Distribuciones](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/b146729137fb451c42f4f70d2268e2d943382e66/EDA/2.1%20Visualizaci%C3%B3n%20Distribuciones.md)

[2.2 Medidas de Tendencia Central](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/b146729137fb451c42f4f70d2268e2d943382e66/EDA/2.2%20Medidas%20Tendencia%20Central.md)

[2.3 Correlación de Variables](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/aa8d3c891815b477a11a79f7bfb67b95e33b1a59/EDA/2.3%20Correlaci%C3%B3n%20Variables.md)

[2.4 Creación de Cuartiles](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/aa8d3c891815b477a11a79f7bfb67b95e33b1a59/EDA/2.4%20Creaci%C3%B3n%20de%20cuartiles.md)

[2.5 Prueba Significancia](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/dd15304ad08f8b1fa655c948ec389bd625ad7898/EDA/2.5%20Prueba%20de%20Significancia.md)

## ✅ [Validar Hipótesis:]

[3.1 Hipótesis 1](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/228ead1ee636f06acbb3a1cfe761ae9ca2f92ad2/Validar%20Hip%C3%B3tesis/Hip%C3%B3tesis%201.md)

[3.2 Hipótesis 2](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/228ead1ee636f06acbb3a1cfe761ae9ca2f92ad2/Validar%20Hip%C3%B3tesis/Hip%C3%B3tesis%202.md)

[3.3 Hipótesis 3](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/228ead1ee636f06acbb3a1cfe761ae9ca2f92ad2/Validar%20Hip%C3%B3tesis/Hip%C3%B3tesis%203.md)

[3.4 Hipótesis 4](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/228ead1ee636f06acbb3a1cfe761ae9ca2f92ad2/Validar%20Hip%C3%B3tesis/Hip%C3%B3tesis%204.md)


[3.5 Hipótesis 5](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/86968a72712da3c5de757f6b83514e6ebd0b7495/Validar%20Hip%C3%B3tesis/Hip%C3%B3tesis%205.md)

[3.6 Notebook Python Análisis Hipótesis](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/86968a72712da3c5de757f6b83514e6ebd0b7495/Validar%20Hip%C3%B3tesis/C%C3%B3digo%20Python%20Hip%C3%B3tesis.ipynb)


## 💡 [Enlaces de interés:]

[4.1 Presentación](https://drive.google.com/file/d/1KK1ZODEqtDcIk36mK1UNNfnTZskr14v5/view?usp=drive_link)

[4.2 Video Presentación]([https://drive.google.com/file/d/1KK1ZODEqtDcIk36mK1UNNfnTZskr14v5/view?usp=drive_link](https://www.loom.com/share/6dbc0b16a8764c15b3a0d3f4c5fdb277?sid=b98917bf-be56-4070-83ba-c86fc6c53051))

4.3 Dashboard:

| <!-- --> | 
|:------------: |  
| [Camila Maluenda](dot.com) | 
| [Jenifer Soto](https://public.tableau.com/views/Datalab_amazon_tableau/ResumenVentas?:language=es-ES&:sid=&:display_count=n&:origin=viz_share_link&:device=desktop) | 


[4.4 Notebook Google Colab](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/3bbf5b66b0cb81f104cbda82190df9d1be8e97d8/analisis_datalab.ipynb)


[4.5 Conclusiones y Recomendaciones](https://github.com/jesolav/Datalab_Amazon_Sales_Proyecto_3_Laboratoria/blob/9fa4144e83f42a466be6ab2a7e7828356c79fe87/Conclusiones/Conclusiones.md)

