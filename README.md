Запрос на выборку всех данных из таблицы "Users":
SELECT * FROM Users;
![image](https://github.com/drtwej/sql1/assets/144841894/e0cf5989-09b1-492c-899c-67011b8327e7)
Запрос к условиям к двум таблицам (например, выбрать пользователей и их заказы):
SELECT Users.FirstName, Users.LastName, Orders.OrderDate
FROM Users
JOIN Orders ON Users.UserID = Orders.UserID;
![image](https://github.com/drtwej/sql1/assets/144841894/1b11db15-0431-488a-9219-f9c2d37bb5bb)
Запрос с сортировкой к двум таблицам (например, отсортировать продукты по цене в убывающем порядке):
SELECT Products.ProductName, Products.Price
FROM Products
ORDER BY Products.Price DESC;
![image](https://github.com/drtwej/sql1/assets/144841894/c537c3bc-e608-4a7a-bbc7-090ee7d72bc8)
Подзапросы к таблицам (например, выбрать пользователей, сделавших заказы с определенной суммой):
SELECT FirstName, LastName
FROM Users
WHERE UserID IN (SELECT UserID FROM Orders WHERE TotalAmount > 1000);
![image](https://github.com/drtwej/sql1/assets/144841894/dba780bd-3162-482a-978b-5923f3ee08b1)
