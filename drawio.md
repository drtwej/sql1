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



INSERT INTO users (id, username, email, address)
VALUES 
    (1, 'ИванПетров', 'ivanpetrov@example.com', 'ул. Ленина, 1'),
    (2, 'МарияСмирнова', 'mariasmirnova@example.com', 'пр. Победы, 10'),
    (3, 'АлексейИванович', 'alexeyivanovich@example.com', 'ул. Гагарина, 5'),
    (4, 'ЕкатеринаСидорова', 'ekaterinasidorova@example.com', 'ул. Пушкина, 15'),
    (5, 'АндрейВасильев', 'andreyvasiliev@example.com', 'пр. Мира, 20'),
    (6, 'ОльгаКозлова', 'olgakozlova@example.com', 'ул. Советская, 7'),
    (7, 'ДмитрийНовиков', 'dmitrynovid@example.com', 'ул. Володарского, 9'),
    (8, 'НатальяМорозова', 'natalyamorozova@example.com', 'пр. Ленина, 25'),
    (9, 'СергейПавлов', 'sergeypavlov@example.com', 'пр. Гагарина, 30'),
    (10, 'АннаНиколаева', 'annanikolaeva@example.com', 'ул. Пушкина, 50'),
    (11, 'ПавелЕгоров', 'pavelegorov@example.com', 'пр. Мира, 12'),
    (12, 'МаринаКузнецова', 'marinakuznetsova@example.com', 'ул. Советская, 3'),
    (13, 'ИгорьСоколов', 'igorsokolov@example.com', 'ул. Володарского, 27'),
    (14, 'АллаПетрова', 'allapetrova@example.com', 'пр. Ленина, 8'),
    (15, 'СеменИванов', 'semenivanov@example.com', 'пр. Гагарина, 40'),
    (16, 'ЛарисаСмирнова', 'larisasmirnova@example.com', 'ул. Пушкина, 22'),
    (17, 'ИльяВасильев', 'ilyavasiliev@example.com', 'пр. Мира, 18'),
    (18, 'ТатьянаКозлова', 'tatyanakozlova@example.com', 'ул. Советская, 14'),
    (19, 'ВладимирНовиков', 'vladimirnovikov@example.com', 'ул. Володарского, 36'),
    (20, 'ЕленаМорозова', 'elenamorozova@example.com', 'пр. Ленина, 21');







```
