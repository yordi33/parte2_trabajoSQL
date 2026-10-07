# Justificación del Modelo y Normalización 3NF

## 1. Primera Forma Normal (1NF)
* Todos los atributos de nuestras 7 tablas (`customers`, `categories`, `products`, `orders`, `order_items`, `payments`, `reviews`) contienen **valores atómicos** (no hay listas ni valores múltiples guardados en una misma celda)[cite: 5].
* No existen grupos repetidos; cada celda de la tabla almacena un único valor escalar[cite: 5].

## 2. Segunda Forma Normal (2NF)
* El modelo cumple 1NF[cite: 5].
* Todas las tablas con clave primaria simple dependen totalmente de dicha clave[cite: 5]. 
* En la tabla intermedia `order_items`, cuya clave primaria es compuesta (`order_id`, `product_id`), los atributos no clave (`quantity`, `unit_price`, `discount`) dependen funcionalmente de **toda** la clave compuesta y no de una parte de ella (evitando dependencias parciales)[cite: 4, 5].

## 3. Tercera Forma Normal (3NF)
* El modelo cumple 2NF[cite: 5].
* **No existen dependencias transitivas** (ningún atributo no clave depende de otro atributo no clave)[cite: 5].

### Decisiones de diseño clave justificadas:
1. **¿Por qué `unit_price` está en `order_items` y no se lee directamente de `products.price`?**[cite: 5]
   * Porque el precio de un producto puede cambiar con el tiempo. Guardar el `unit_price` en el momento de la compra en la línea de pedido garantiza la integridad histórica de los ingresos de cada pedido[cite: 4, 5].
2. **¿Por qué `country` está directamente en `customers` y no en una tabla `countries` separada?**[cite: 5]
   * Para cumplir estrictamente con el volumen y alcance del enunciado sin sobre-ingeniería innecesaria, ya que los clientes pertenecen a un único país dentro de nuestro análisis geográfico en Europa[cite: 2, 3, 5].
3. **¿Por qué no almacenamos el nombre del cliente (`customer_name`) en la tabla `orders`?**[cite: 5]
   * Si lo hiciéramos, violaríamos la 3NF (dependencia transitiva, ya que `customer_name` dependería de `customer_id` que a su vez es clave ajena en `orders`). Por eso solo guardamos `customer_id` en `orders`[cite: 5].