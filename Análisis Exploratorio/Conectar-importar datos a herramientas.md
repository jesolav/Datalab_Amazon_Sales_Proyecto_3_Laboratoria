### 1.1 Conectar/importar datos a herramientas

## NULOS: 

# **Verificar valores nulos en la tabla amazon_product**

```sql
SELECT 
  COUNT(*) AS total_filas,
  SUM(CASE WHEN product_id IS NULL THEN 1 ELSE 0 END) AS nulos_product_id,
  SUM(CASE WHEN product_name IS NULL THEN 1 ELSE 0 END) AS nulos_product_name,
  SUM(CASE WHEN category IS NULL THEN 1 ELSE 0 END) AS nulos_category,
  SUM(CASE WHEN discounted_price IS NULL THEN 1 ELSE 0 END) AS nulos_discounted_price,
  SUM(CASE WHEN actual_price IS NULL THEN 1 ELSE 0 END) AS nulos_actual_price,
  SUM(CASE WHEN discount_percentage IS NULL THEN 1 ELSE 0 END) AS nulos_discount_percentage,
  SUM(CASE WHEN about_product IS NULL THEN 1 ELSE 0 END) AS nulos_about_product
FROM `datalab-433117.dataset.amazon_product`;
```

![image](https://github.com/user-attachments/assets/9fcf4dfc-624b-4bc2-9094-e6183cc71d0a)



# **Verificar valores nulos en la tabla amazon_review**
```sql
SELECT 
  COUNT(*) AS total_filas,
  SUM(CASE WHEN user_id IS NULL THEN 1 ELSE 0 END) AS nulos_user_id,
  SUM(CASE WHEN user_name IS NULL THEN 1 ELSE 0 END) AS nulos_user_name,
  SUM(CASE WHEN review_id IS NULL THEN 1 ELSE 0 END) AS nulos_review_id,
  SUM(CASE WHEN review_title IS NULL THEN 1 ELSE 0 END) AS nulos_review_title,
  SUM(CASE WHEN review_content IS NULL THEN 1 ELSE 0 END) AS nulos_review_content,
  SUM(CASE WHEN img_link IS NULL THEN 1 ELSE 0 END) AS nulos_img_link,
  SUM(CASE WHEN product_link IS NULL THEN 1 ELSE 0 END) AS nulos_product_link,
  SUM(CASE WHEN product_id IS NULL THEN 1 ELSE 0 END) AS nulos_product_id,
  SUM(CASE WHEN rating IS NULL THEN 1 ELSE 0 END) AS nulos_rating,
  SUM(CASE WHEN rating_count IS NULL THEN 1 ELSE 0 END) AS nulos_rating_count
FROM `datalab-433117.dataset.amazon_review`;
```
![image](https://github.com/user-attachments/assets/4c5a98bf-4e99-47d1-9f8b-a7b71a249823)


# DUPLICADOS ------

-- Detectar duplicados en la tabla amazon_product
```sql
SELECT 
  product_id, 
  COUNT(*) AS conteo_duplicados 
FROM `datalab-433117.dataset.amazon_product`
GROUP BY product_id
HAVING COUNT(*) > 1;
```



-- Detectar duplicados en la tabla amazon_review
```sql
SELECT 
  review_id, 
  COUNT(*) AS conteo_duplicados 
FROM `datalab-433117.dataset.amazon_review`
GROUP BY review_id
HAVING COUNT(*) > 1;
```

```sql
```


```sql
```

