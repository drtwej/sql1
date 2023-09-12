Запрос на выборку всех данных из таблицы "Users":
 
SELECT * FROM Users;

![image](https://github.com/drtwej/sql1/assets/144841894/d2c0ce65-e7a7-43ec-ae99-3264f6ef51eb)


Запрос к условиям к двум таблицам (например, выбрать пользователей и их заказы):

SELECT Users.FirstName, Users.LastName, Orders.OrderDate
FROM Users
JOIN Orders ON Users.UserID = Orders.UserID;

![image](https://github.com/drtwej/sql1/assets/144841894/cc64b255-5ff1-4436-8989-b9fb7a6d51f2)


Запрос с сортировкой к двум таблицам (например, отсортировать продукты по цене в убывающем порядке):

SELECT Products.ProductName, Products.Price
FROM Products
ORDER BY Products.Price DESC;

![image](https://github.com/drtwej/sql1/assets/144841894/053c0951-063e-4657-a045-937fb19a10ac)


Подзапросы к таблицам (например, выбрать пользователей, сделавших заказы с определенной суммой):

SELECT FirstName, LastName
FROM Users
WHERE UserID IN (SELECT UserID FROM Orders WHERE TotalAmount > 15);


![image](https://github.com/drtwej/sql1/assets/144841894/47b2770d-d3d0-4b81-8441-f294631e40e1)




