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



INSERT INTO products (id, title, price, category_id, quantity)
VALUES
    (1, 'Футболка "Белый лебедь"', 1000.00, 1, 20),
    (2, 'Джинсы "Синий океан"', 2500.50, 2, 10),
    (3, 'Платье "Весенний цветок"', 3500.75, 3, 15),
    (4, 'Куртка "Черная пантера"', 5000.25, 4, 8),
    (5, 'Рубашка "Голубое небо"', 1800.80, 1, 12),
    (6, 'Шорты "Пляжный отдых"', 1200.00, 2, 30),
    (7, 'Блузка "Розовая сирень"', 1500.50, 3, 25),
    (8, 'Пиджак "Строгий бизнес"', 4500.75, 4, 5),
    (9, 'Юбка "Цветочное поле"', 2800.00, 3, 18),
    (10, 'Толстовка "Уют и комфорт"', 2000.50, 1, 20),
    (11, 'Брюки "Классический стиль"', 3200.75, 2, 10),
    (12, 'Пальто "Шик и элегантность"', 6000.25, 4, 8),
    (13, 'Жилет "Стильный акцент"', 1800.80, 1, 12),
    (14, 'Туника "Легкий бриз"', 1500.00, 3, 25),
    (15, 'Костюм "Деловая женщина"', 5500.75, 4, 5),
    (16, 'Кардиган "Тепло и уют"', 2800.00, 3, 18),
    (17, 'Кофта "Спортивный образ"', 2000.50, 1, 20),
    (18, 'Шорты "Пляжный отдых"', 1500.75, 2, 10),
    (19, 'Блузка "Розовый оттенок"', 3000.25, 3, 8),
    (20, 'Пиджак "Серьезный стиль"', 5000.80, 4, 12),
    (21, 'Брюки "Модный образ"', 1800.00, 1, 15),
    (22, 'Платье "Утонченная леди"', 3500.50, 3, 22),
    (23, 'Куртка "Ветреный день"', 4000.75, 4, 7),
    (24, 'Футболка "Яркий акцент"', 1200.25, 1, 10),
    (25, 'Джинсы "Удобство и стиль"', 2500.80, 2, 18),
    (26, 'Туника "Мягкие оттенки"', 1800.00, 3, 25),
    (27, 'Юбка "Повседневный комплект"', 2800.50, 3, 15),
    (28, 'Костюм "Строгое дело"', 5500.75, 4, 5),
    (29, 'Шорты "Яркое лето"', 1200.00, 2, 30),
    (30, 'Блузка "Легкость и нежность"', 1500.50, 3, 25),
    (31, 'Пиджак "Профессиональный взгляд"', 4500.75, 4, 5),
    (32, 'Футболка "Удобство и стиль"', 1000.80, 1, 20),
    (33, 'Джинсы "Стильные акценты"', 2500.00, 2, 15),
    (34, 'Платье "Летний бриз"', 3500.50, 3, 12),
    (35, 'Куртка "Модные тренды"', 5000.75, 4, 8),
    (36, 'Рубашка "Классический образ"', 1800.00, 1, 10),
    (37, 'Шорты "Удобство и активность"', 1200.50, 2, 20),
    (38, 'Блузка "Элегантная леди"', 1500.75, 3, 15),
    (39, 'Пиджак "Серьезный стиль"', 4500.00, 4, 5),
    (40, 'Юбка "Цветочный сад"', 2800.80, 3, 18);



INSERT INTO Carts (id, user_id, product_id, products_quantity) VALUES
(1, 1, 1, 5),
(2, 2, 2, 3),
(3, 3, 3, 2),
(4, 4, 4, 7),
(5, 5, 5, 1),
(6, 6, 6, 4),
(7, 7, 7, 6),
(8, 8, 8, 2),
(9, 9, 9, 8),
(10, 10, 10, 5),
(11, 11, 11, 3),
(12, 12, 12, 1),
(13, 13, 13, 4),
(14, 14, 14, 9),
(15, 15, 15, 6),
(16, 16, 16, 2),
(17, 17, 17, 7),
(18, 18, 18, 5),
(19, 19, 19, 1),
(20, 20, 20, 3);

INSERT INTO status (id,status) VALUES
(1, 'не получен'),
(2, 'получен');



INSERT INTO orders (id, user_id, date, price, status_id)
VALUES
    (1, 1, '2022-01-01', 2324, 1),
    (2, 2, '2022-01-02', 4535, 2),
    (3, 3, '2022-01-03', 4376, 1),
    (4, 4, '2022-01-04', 9879, 2),
    (5, 5, '2022-01-05', 2351, 1),
    (6, 6, '2022-01-06', 6346, 2),
    (7, 7, '2022-01-07', 7567, 1),
    (8, 8, '2022-01-08', 3456, 2),
    (9, 9, '2022-01-09', 2356, 1),
    (10, 10, '2022-01-10', 3476, 2),
    (11, 11, '2022-01-11', 3644, 1),
    (12, 12, '2022-01-12', 4364, 2),
    (13, 13, '2022-01-13', 4767, 1),
    (14, 14, '2022-01-14', 3465, 2),
    (15, 15, '2022-01-15', 5645, 1),
    (16, 16, '2022-01-16', 4565, 2),
    (17, 17, '2022-01-17', 9453, 1),
    (18, 18, '2022-01-18', 2367, 2),
    (19, 19, '2022-01-19', 4578, 1),
    (20, 20, '2022-01-20', 3678, 2);












```
