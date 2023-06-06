Работа с базой данных:
1. Проверка отображения созданного заказа в базе данных:
SELECT c.login,
		 COUNT(o."courierId")
FROM "Couriers" AS c
JOIN "Orders" AS o
	ON o."courierId" = c.id
GROUP BY  c.login;э

2. Проверка корректной записи статусов в базе данных:
SELECT track,
	CASE
	WHEN finished =true THEN
	2
	WHEN cancelled = true THEN
	-1
	WHEN “inDelivery” = true THEN
	1
	ELSE 0
	END AS status
FROM "Orders"; 

Автоматизация теста к API
