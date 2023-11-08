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



CREATE TABLE Carts (
    id   INT PRIMARY KEY,
    user_id INT,
    product_id INT,
    products_quantity INT,
    FOREIGN KEY (product_id) REFERENCES Products(id)
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
    FOREIGN KEY (product_id) REFERENCES Products(id)
);




```
