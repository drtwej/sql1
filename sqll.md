
## 1 
![](1.png)
```
insert into menu values (19,4,'cheese pizza', 700);
insert into menu values (20,4,'mushroom pizza', 950);
insert into menu values (21,4,'pepperoni pizza', 1000);
insert into menu values (22,4,'sausage pizza', 950);
insert into menu values (23,5,'cheese pizza', 700);
insert into menu values (24,5,'pormela pizza', 840);
insert into menu values (25,5,'bogata pizza', 1000);
insert into menu values (26,5,'soreta pizza', 400);
insert into menu values (27,5,'pajero pizza', 890);
insert into menu values (28,5,'muchachos pizza', 850);
```

```
insert into pizzeria values (7,'Pizza Sony','4.2');
insert into pizzeria values (8,'Pizza jony','4.7');
insert into pizzeria values (9,'Sinour','4.4');
insert into pizzeria values (10,'Potato pizza','4.8');
insert into pizzeria values (11,'Pizza Pablo','4.9');
insert into pizzeria values (12,'Pizza Soprano','4.0');
insert into pizzeria values (13,'Pizza Italia','3.5');
insert into pizzeria values (14,'Pizza Pepperoni','3.1');
insert into pizzeria values (15,'Pizza Porodala','4.9');
insert into pizzeria values (16,'Pizza Gavai','5.0')
```

```
insert into person_visits values (20, 4, 1, '2022-01-01');
insert into person_visits values (21, 2, 2, '2022-01-01');
insert into person_visits values (22, 5, 1, '2022-01-02');
insert into person_visits values (23, 3, 5, '2022-01-03');
insert into person_visits values (24, 3, 6, '2022-02-04');
insert into person_visits values (25, 4, 5, '2022-02-07');
insert into person_visits values (26, 4, 6, '2022-02-08');
insert into person_visits values (27, 5, 2, '2022-02-08');
insert into person_visits values (28, 5, 6, '2022-02-09');
insert into person_visits values (29, 6, 2, '2022-02-09');
```

```
insert into person_order values (21,4, 7, '2022-01-10');
insert into person_order values (22,5, 6, '2022-01-11');
insert into person_order values (23,5, 7, '2022-01-12');
insert into person_order values (24,6, 13, '2022-01-13');
insert into person_order values (25,7, 3, '2022-01-14');
insert into person_order values (26,7, 9, '2022-01-15');
insert into person_order values (27,7, 4, '2022-01-16');
insert into person_order values (28,8, 8, '2022-01-17');
insert into person_order values (29,8, 14, '2022-01-18');
insert into person_order values (30,9, 18, '2022-01-19');
```

```
insert into person values (16, 'Anna', 15, 'female', 'Voronej');
insert into person values (17, 'Andrey', 26, 'male', 'Novgorod');
insert into person values (18, 'Kate', 37, 'female', 'Kazan');
insert into person values (19, 'Denis', 17, 'male', 'Kazan');
insert into person values (20, 'Elvira', 45, 'female', 'Kazan');
insert into person values (21, 'Irina', 21, 'female', 'Saint-Petersburg');
insert into person values (22, 'Evgeniy', 24, 'male', 'Saint-Petersburg');
insert into person values (23, 'Nataly', 30, 'female', 'Novosibirsk');
insert into person values (24, 'Dmitriy', 18, 'male', 'Samara');
insert into person values (25, 'Grigoriy', 18, 'male', 'Samara');
```

## 2 

![image](https://github.com/drtwej/sql1/assets/144841894/9e87eff3-1679-4726-b4e0-7e9d6e81f5c1)

```
SELECT 
  ("name", "age", "address") 
FROM 
  "person" 
WHERE 
  "address" = 'Moscow'
```

## 3 

![image](https://github.com/drtwej/sql1/assets/144841894/ea8f5a3f-ec7e-41bf-a777-56f4eb87a54c)


```
SELECT 
  ("name", "age", "address") 
FROM 
  "person" 
WHERE 
  "gender" = 'female' 
  and "address" = 'Moscow' 
ORDER BY 
  "name"```
```


## 4

![image](https://github.com/drtwej/sql1/assets/144841894/3e18960b-273b-491d-883c-ed7a4c8ecc94)


```
SELECT 
  "name", 
  "rating" 
FROM 
  "pizzeria" 
WHERE 
  "rating" > 3.5 
ORDER BY 
  "rating" ASC;

```

```
SELECT 
  "name", 
  "rating" 
FROM 
  "pizzeria" 
WHERE 
  "rating" BETWEEN 4 AND 5
ORDER BY 
  "rating" ASC;
```

## 5

![image](https://github.com/drtwej/sql1/assets/144841894/b983fcee-1a7d-42a3-ae90-942feaec0222)

```
SELECT 
  "id" 
FROM 
  "person_visits" 
WHERE 
  "visit_date" BETWEEN '2022-01-01' 
  and '2022-01-06' 
  OR "pizzeria_id" = 2 
ORDER BY 
  "id"

```

## 6

![image](https://github.com/drtwej/sql1/assets/144841894/9ebac4bb-6772-44e4-ac63-dfa1a8a2e0c1)

 
```
	SELECT name FROM person WHERE id IN (
		SELECT id FROM person_order WHERE menu_id = 2 OR "menu_id"= 3 OR "menu_id"=5
	)

```

## 7

![image](https://github.com/drtwej/sql1/assets/144841894/472fd45f-9cbd-4d38-a1bd-1a70f3691f37)


```
SELECT 
  EXISTS (
    SELECT 
      "id" 
    FROM 
      "person" 
    WHERE 
      "name" = 'Kate'
  )

```



## 13.09.23 задание
## 1 

![image](https://github.com/drtwej/sql1/assets/144841894/9b72c16c-aba8-4a89-a282-2ea6490d8960)

```
SELECT id, pizza_name FROM menu
UNION
SELECT id, name FROM person
ORDER BY id, pizza_name

```

## 2

![image](https://github.com/drtwej/sql1/assets/144841894/0312825b-7f5a-4fe2-aa8b-bb532f96c86b)



```


SELECT   name, 'person' AS source FROM person
UNION ALL
SELECT  pizza_name, 'pizza' FROM menu ORDER BY source, name



```

## 19.09.23


## 1

```
SELECT person.id, person.name, "age", "gender", "address", pizzeria.id, pizzeria.name, "rating" FROM "person", "pizzeria"
ORDER BY pizzeria.id ASC;

```

![image](https://github.com/drtwej/sql1/assets/144841894/ce2d7979-419d-431a-9f93-82db492dd641)


## 2

```

SELECT order_date AS action_date, name FROM person_order, person
WHERE order_date IN (SELECT visit_date FROM person_visits) AND person_order.person_id = person.id
ORDER BY order_date ASC;

```

![image](https://github.com/drtwej/sql1/assets/144841894/82c1c465-c45b-460f-bd96-2177927b123d)


## 3

```
SELECT order_date, (name || ' (age:' || age || ')') AS person_information FROM person_order
JOIN person ON person_id = person.id
ORDER BY order_date ASC, person_information ASC;


```


![image](https://github.com/drtwej/sql1/assets/144841894/bc1b771e-0a90-437c-9ece-d485dca7fbff)

## 4

```

SELECT order_date, (name || ' (age:' || "age" || ')') AS person_information FROM person_order NATURAL JOIN person
ORDER BY order_date ASC, person_information ASC;

```


![image](https://github.com/drtwej/sql1/assets/144841894/e39627c2-6918-4891-9dd0-649b0b5e55ee)


## 5

## IN

```

SELECT pizzeria.name FROM pizzeria 
WHERE pizzeria.id  IN 
(SELECT pizzeria_id FROM person_visits);

```
![image](https://github.com/drtwej/sql1/assets/144841894/8b2d3ca6-98ea-4ac4-9979-5532dfe92098)


## EXISTS

```
SELECT name FROM pizzeria 
WHERE NOT EXISTS 
(SELECT * FROM person_visits WHERE pizzeria.id = pizzeria_id);

```


## 6

```

SELECT person.name,menu.pizza_name,pizzeria.name FROM person_order JOIN person ON person_order.person_id=person.id
LEFT JOIN menu ON menu.id = person_order.menu_id
LEFT JOIN pizzeria ON pizzeria.id=menu.pizzeria_id


```

![image](https://github.com/drtwej/sql1/assets/144841894/afe12bf2-b67a-4505-b073-7c5f4ab79271)



## 20.09.23

## 00

```

SELECT name, rating FROM pizzeria
LEFT JOIN person_visits ON pizzeria_id = pizzeria.id
WHERE pizzeria_id IS NULL;

```

![image](https://github.com/drtwej/sql1/assets/144841894/213f49c3-f374-4553-a97f-101f7d0039b2)


## 1

```

SELECT missing_date::date
FROM generate_series ('2022-01-01'::timestamp, '2022-01-10', '1 day') AS missing_date
LEFT JOIN person_visits ON visit_date = missing_date
WHERE "visit_date" IS NULL

```

![image](https://github.com/drtwej/sql1/assets/144841894/4cffc869-0cd1-433c-8f66-119af5ac13de)


## 2

```
SELECT COALESCE (person.name, '-') AS person_name, COALESCE (person_visits.visit_date, NULL) AS visit_date, COALESCE (pizzeria.name, '-') AS pizzeria_name 
FROM person_visits
RIGHT JOIN person ON person.id = person_visits.person_id
FULL JOIN pizzeria ON pizzeria.id = person_visits.pizzeria_id
ORDER BY person_name, visit_date, pizzeria_name;

```


![image](https://github.com/drtwej/sql1/assets/144841894/936d57d5-f3bd-47d1-95e8-c7f7cd9c1327)


## 3

```
WITH m AS (
	SELECT missing_date::date FROM generate_series ('2022-01-01'::timestamp, '2022-01-10', '1 day') AS missing_date
)
SELECT missing_date FROM m
LEFT JOIN person_visits ON visit_date = missing_date
WHERE visit_date IS NULL;

```

![image](https://github.com/drtwej/sql1/assets/144841894/68656cdc-db41-41ba-8a48-08e2855eaf4c)


## 4

```
SELECT menu.pizza_name, pizzeria.name AS pizzeria_name, menu.price FROM menu
JOIN pizzeria ON pizzeria.id = menu.pizzeria_id
WHERE pizza_name = 'pepperoni pizza' OR pizza_name = 'mushroom pizza'
ORDER BY pizza_name, pizzeria_name;
```

![image](https://github.com/drtwej/sql1/assets/144841894/c015fccd-b2fd-4313-997c-13bbe26fa710)



## 04.10.23


## 01


```

SELECT "id" FROM menu
EXCEPT
SELECT menu_id FROM person_order ORDER BY "id"

```
![image](https://github.com/drtwej/sql1/assets/144841894/e2f80156-dc37-4cd5-bc70-15fd51a0f774)


## 10.10.2023

## 00

```

CREATE VIEW v_person_male
AS
SELECT name, gender FROM person 
WHERE gender = 'male'

```

```

CREATE VIEW v_person_female
AS
SELECT name, gender FROM person 
WHERE gender = 'female'

```




## 01



```
SELECT * FROM v_person_male
UNION ALL
SELECT * FROM v_person_female
ORDER BY name

```

![image](https://github.com/drtwej/sql1/assets/144841894/27ac636d-d26e-46da-a0a6-0c72b1a0ec9a)


## 02

```
DROP VIEW IF EXISTS v_generated_dates;
CREATE VIEW v_generated_dates AS
	SELECT generate_series('01.01.2022', '31.01.2022', interval '1 day')::date AS generated_date
	ORDER BY generated_date;
SELECT * FROM v_generated_dates;


```

![image](https://github.com/drtwej/sql1/assets/144841894/4cb1424c-dc82-421f-9e17-66a3a830e74e)


## 04

```

CREATE VIEW v_symetric_union AS (

(SELECT person_id FROM view_r EXCEPT ALL (SELECT person_id FROM view_s))	
UNION ALL
(SELECT person_id FROM view_s EXCEPT ALL (SELECT person_id FROM view_r))
	);
	SELECT * FROM v_symetric_union



```


![image](https://github.com/drtwej/sql1/assets/144841894/a204e887-8947-41b4-83e4-8f719977b5c3)



## 05

```

CREATE VIEW v_price_with_discount AS (
SELECT pizza_name,  p.name, m.price, (m.price  * 0.9) AS
discount_price FROM  person_order po
JOIN person p ON p.id = po.person_id
JOIN menu m ON m.id = po.menu_id )
ORDER BY p.name , m.pizza_name

```
![image](https://github.com/drtwej/sql1/assets/144841894/70340734-6b7c-41d3-8570-b142f52cc7d7)


## 06 
CREATE materialized view mv_dmirty_visit
SELECT p.name  FROM pizzeria p
JOIN person_visits pv ON p.id = pv.pizzeria_id
JOIN person pr ON pv.person_id = pr.id
JOIN menu m ON m.id = p.id
WHERE pr.name = 'dmitriy' AND pr.visit_date = '2022-01-08'
AND price < OR = '800'



## 18.10

## 01

```
SELECT c.first_name, c.last_name, c.email FROM customers c
JOIN orders o ON o.customer_id = c.customer_id
GROUP BY c.customer_id , o.order_date
HAVING COUNT (c.customer_id) >= 2 AND o.order_date 
BETWEEN '2023-07-17' AND '2023-10-17'

```
![image](https://github.com/drtwej/sql1/assets/144841894/d023ae77-eafb-4784-a6e8-3cf2fca96209)


## 02

```

SELECT p.category, FLOOR (avg(o.quantity)) AS "averege order size" FROM orders o
JOIN products p ON p.product_id = o.product_id
WHERE p.price >= 50
GROUP BY p.category

```

![image](https://github.com/drtwej/sql1/assets/144841894/41bd6710-90cb-407e-8e54-fcfbc55d2e72)





## 03

```
WITH tmp_shit AS (
	SELECT p.product_id, SUM(p.price) AS "price_sum" FROM products p
	GROUP BY p.product_id, p.price
),
global_avg_price AS (
	SELECT AVG(p.price) FROM products p
)

SELECT c.first_name, c.last_name, c.email FROM customers c
JOIN orders o ON o.customer_id = c.customer_id
JOIN tmp_shit t ON t.product_id = o.product_id
WHERE t.price_sum > (SELECT * FROM global_avg_price);

```


![image](https://github.com/drtwej/sql1/assets/144841894/c1285183-7dbb-4356-a7ac-fc4add607331)


## 04

```

SELECT c.first_name, c.last_name, c.email FROM customers c
JOIN orders o ON o.customer_id = c.customer_id
JOIN products p ON p.product_id = o.product_id
WHERE p.price > 1000 AND p.category != 'Electronics';

```

![image](https://github.com/drtwej/sql1/assets/144841894/20f889b5-f424-402f-9cfd-ad8c1ecf66ce)


## 06

```
WITH customer_max_min AS (
	SELECT o.customer_id, MAX(o.order_date) AS max_date, MIN(o.order_date) AS min_date FROM orders o
	GROUP BY o.customer_id
), 
range_max_min AS(
	SELECT cusxn.customer_id, (cusxn.max_date - cusxn.min_date) AS range FROM customer_max_min cusxn
),

min_p  AS (
	SELECT cus.first_name, cus.last_name, MAX(o.order_date), MIN(o.order_date), MAX(rgxn.range) AS max_diff FROM orders o
	JOIN range_max_min rgxn ON rgxn.customer_id = o.customer_id
	JOIN customers cus ON cus.customer_id = o.customer_id
	GROUP BY cus.first_name, cus.last_name
)

SELECT first_name, last_name FROM min_p WHERE max_diff = (SELECT MAX(max_diff) FROM min_p);

```

![image](https://github.com/drtwej/sql1/assets/144841894/3989147a-b69b-4579-81b8-2b4db3145106)




## 09

```

SELECT category, AVG(price) AS avg_price FROM products
GROUP BY category
ORDER BY avg_price


```
![image](https://github.com/drtwej/sql1/assets/144841894/69c28c06-23cc-4910-b1a4-e907e0c0a6b0)




## 24.10.23


## 00

```

SELECT p.id, (SELECT COUNT(pv.id) FROM person_visits pv 
			  WHERE pv.person_id = p.id) AS "count_of_visits" FROM person p
ORDER BY count_of_visits DESC, p.id ASC


```


![image](https://github.com/drtwej/sql1/assets/144841894/b4de9139-ae33-4c5c-9465-54d8ff635302)




## 01

```

WITH tmp AS (
	SELECT p.name, (SELECT COUNT(pv.id) FROM person_visits pv WHERE pv.person_id = p.id) AS "count_of_visits" FROM person p
	ORDER BY count_of_visits DESC LIMIT 4
)

SELECT name FROM tmp ORDER BY name


```

![image](https://github.com/drtwej/sql1/assets/144841894/4cb44340-31f9-4c67-b58f-94240d598545)



## 5 
```
SELECT DISTINCT person.name FROM person
LEFT JOIN person_visits ON person_visits.person_id = person.id
ORDER BY person.name
```
![image](https://github.com/drtwej/sql1/assets/144841894/56de27f7-a775-4077-bcec-921b9bbd083e)




## 7
```
SELECT ROUND(AVG(pizzeria.rating), 4) AS "global_rating" FROM pizzeria
```
![image](https://github.com/drtwej/sql1/assets/144841894/e25850f1-9be6-4a2c-8947-2e7bfb279808)




## 17.10.23


## 0
```
CREATE TABLE person_discounts (
	id INT PRIMARY KEY,
	pizzeria_id INT,
	person_id INT,
	discount NUMERIC,
	CONSTRAINT fk_person_discounts_person_id FOREIGN KEY (person_id) REFERENCES person(id),
	CONSTRAINT fk_person_discounts_pizzeria_id FOREIGN KEY (pizzeria_id) REFERENCES pizzeria(id)
);
```

## 4
```
CREATE TABLE person_discounts (
	id INT PRIMARY KEY,
	pizzeria_id INT,
	person_id INT,
	discount NUMERIC,
	discount NUMERIC NOT NULL DEFAULT 0 CHECK (discount >=0 AND discount <= 100),
	CONSTRAINT fk_person_discounts_person_id FOREIGN KEY (person_id) REFERENCES person(id),
	CONSTRAINT fk_person_discounts_pizzeria_id FOREIGN KEY (pizzeria_id) REFERENCES pizzeria(id)
);
```

## 5
```
COMMENT ON TABLE person_discounts IS 'This table stores information about the discounts applied to individuals.';
```

## 6
```
CREATE SEQUENCE seq_person_discounts
MINVALUE 1 START WITH 1 INCREMENT BY 1;
ALTER TABLE person_discounts ALTER COLUMN id SET DEFAULT NEXTVAL('seq_person_discounts');
```



## trigg 
```
DROP function if exists fnc_before_update_orders() CASCADE;

create or replace function fnc_before_update_orders() returns trigger as $Before_Update_price$
begin
	UPDATE orders
	SET price = price + NEW.quantity * (SELECT price FROM products WHERE products.id = NEW.product_id)
	WHERE orders.id = NEW.order_id;
	return NULL;
end;
$Before_Update_price$ language plpgsql;

CREATE TRIGGER Before_Update_price
AFTER INSERT ON order_details
FOR EACH ROW EXECUTE FUNCTION fnc_before_update_orders();

select * from orders

INSERT INTO order_details VALUES (22, 1, 5, 2);
INSERT INTO order_details VALUES (23, 1, 1, 1);
```


## trigg 2
```
CREATE OR REPLACE FUNCTION tr_cart_insert_function()
RETURNS TRIGGER AS $$
BEGIN
    -- Проверяем, что значения не равны NULL
    IF NEW.user_id IS NULL OR NEW.product_id IS NULL OR NEW.products_quantity IS NULL THEN
        -- Вызываем ошибку, если одно из значений равно NULL
        RAISE EXCEPTION 'Нельзя вставлять записи с нулевыми значениями';
    END IF;

    -- Возвращаем NEW, чтобы триггер продолжил выполнение
    RETURN NEW;
END;
$$ LANGUAGE plpgsql;

-- Создаем триггер
CREATE TRIGGER tr_cart_insert
BEFORE INSERT ON carts
FOR EACH ROW
EXECUTE FUNCTION tr_cart_insert_function();



Этот триггер будет срабатывать перед вставкой новой строки в таблицу carts. Если хотя бы одно из значений user_id, product_id или products_quantity равно NULL, то триггер вызовет ошибку и не позволит вставить запись.
```


## trigg 3

```
-- Создаем таблицу для хранения истории изменений цен
CREATE TABLE IF NOT EXISTS price_history (
    product_id INT,
    old_price DECIMAL(10, 2),
    new_price DECIMAL(10, 2),
    change_date TIMESTAMP
);

-- Создаем функцию для триггера
CREATE OR REPLACE FUNCTION tr_products_price_update_function()
RETURNS TRIGGER AS $$
BEGIN
    -- Проверяем, что цена изменилась
    IF NEW.price <> OLD.price THEN
        -- Записываем историю изменений цены
        INSERT INTO price_history (product_id, old_price, new_price, change_date)
        VALUES (NEW.id, OLD.price, NEW.price, NOW());
    END IF;

    -- Возвращаем NEW, чтобы триггер продолжил выполнение
    RETURN NEW;
END;
$$ LANGUAGE plpgsql;

-- Создаем триггер
CREATE TRIGGER tr_products_price_update
BEFORE UPDATE ON products
FOR EACH ROW
EXECUTE FUNCTION tr_products_price_update_function();

Этот триггер отслеживает изменения в цене (price) в таблице products и записывает историю изменений в таблицу price_history. Пожалуйста, учтите, что вам, возможно, нужно адаптировать этот код в зависимости от конкретных требований вашего приложения.
````
