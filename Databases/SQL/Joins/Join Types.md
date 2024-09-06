In SQL, there are several types of joins used to combine data from two or more tables based on the relationships between them. Here are the main types of joins:

### 1. **[[INNER JOIN]]**

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
INNER JOIN customers ON orders.customer_id = customers.customer_id;
```

### 2. **[[LEFT OUTER JOIN|LEFT JOIN]] (or LEFT OUTER JOIN)**

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
LEFT JOIN customers ON orders.customer_id = customers.customer_id;
```

### 3. **[[RIGHT OUTER JOIN|RIGHT JOIN]] (or RIGHT OUTER JOIN)**

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
RIGHT JOIN customers ON orders.customer_id = customers.customer_id;
```

### 4. **FULL JOIN (or FULL OUTER JOIN)**

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
FULL OUTER JOIN customers ON orders.customer_id = customers.customer_id;
```

### 5. **[[CROSS JOIN]]**

```sql
SELECT products.product_name, categories.category_name
FROM products
CROSS JOIN categories;
```