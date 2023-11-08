## Диаграмма базы данных
![prokh drawio](https://github.com/drtwej/sql1/assets/144841894/6b323d3d-b782-4948-8779-049d0671014c)
## Создание таблиц

```
CREATE TABLE Users (
    id INT PRIMARY KEY,
    username TEXT,
    email VARCHAR(64),
    address VARCHAR(128)
);




CREATE TABLE products (
    id INT PRIMARY KEY,
    title TEXT,
    price FLOAT,
    category_id INT,
    quantity INT
);


 
 
 CREATE TABLE Carts (
    id   INT PRIMARY KEY,
    user_id INT,
    product_id INT,
    products_quantity INT,
	FOREIGN KEY (user_id) REFERENCES users(id),
    FOREIGN KEY (product_id) REFERENCES Products(id)
);



CREATE TABLE status (
    id INT PRIMARY KEY,
    status TEXT
);


CREATE TABLE orders (
    id INT PRIMARY KEY,
    user_id INT,
    date DATE,
    price FLOAT,
    status_id INT,
    title TEXT,
    FOREIGN KEY (user_id) REFERENCES users(id),
    FOREIGN KEY (status_id) REFERENCES status(id)
);


 CREATE TABLE Reviews (
    id INT PRIMARY KEY,
    user_id INT,
    product_id INT,
    rating INT,
    FOREIGN KEY (user_id) REFERENCES users(id),
    FOREIGN KEY (product_id) REFERENCES products(id)
);



CREATE TABLE shipping (
    id INT PRIMARY KEY,
    order_id INT,
    order_date DATE,
    status_id INT,
    FOREIGN KEY (order_id) REFERENCES orders(id),
    FOREIGN KEY (status_id) REFERENCES status(id)
);


CREATE TABLE order_details (
    id INT PRIMARY KEY,
    order_id INT,
    product_id INT,
    quantity INT,
    FOREIGN KEY (order_id) REFERENCES orders(id),
    FOREIGN KEY (product_id) REFERENCES products(id)
);


CREATE TABLE discounts (
    id INT PRIMARY KEY,
    title TEXT,
    cost FLOAT,
    discount_start DATE,
    discount_finish DATE
);


CREATE TABLE promo (
    id INT PRIMARY KEY,
    title TEXT,
    discount_id INT,
    FOREIGN KEY (discount_id) REFERENCES discounts(id)
);



```
