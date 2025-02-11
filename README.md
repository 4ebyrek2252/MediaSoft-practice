# MediaSoft-practice
Выполнил Салин Никита ИСдо-34

# Задание 2
Основные функции данного приложения:
1. Создание и управление списками покупок: Пользователь может создавать новые списки покупок, добавлять или удалять товары, изменять их количество и отмечать как купленные.
2. Синхронизация данных: Обеспечение актуальности списка между устройствами пользователя, что позволит ему иметь доступ к своим спискам с разных устройств.
3. Поиск и фильтрация товаров: Возможность искать товары и фильтровать их по категориям, цене и другим параметрам.
4. История покупок: Хранение информации о совершенных покупках для анализа и повторного использования.
5. Уведомления и напоминания: Уведомления о необходимости пополнить запас определенных товаров на основе пользовательских предпочтений.
6. Обратная связь и отзывы: Пользователь может оставлять отзывы на продукты или делиться списками с друзьями.

# Задание 7
SQL-запросы:
1. Общая стоимость книг для каждого автора и отсортировать результат в порядке убывания:
   SELECT a.Name AS AuthorName, SUM(b.Price) AS TotalBookValue
   FROM Authors a
   JOIN Books b ON a.AuthorId = b.AuthorId
   GROUP BY a.Name
   ORDER BY TotalBookValue DESC;
2. Стоимость книг автора превышает 1500:
   SELECT a.Name AS AuthorName
   FROM Authors a
   JOIN Books b ON a.AuthorId = b.AuthorId
   GROUP BY a.AuthorId, a.Name
   HAVING SUM(b.Price) > 1500;
3. Вывести авторов с количеством книг:
   SELECT a.Name AS AuthorName, COUNT(b.BookId) AS BookCount
   FROM Authors a
   LEFT JOIN Books b ON a.AuthorId = b.AuthorId
   GROUP BY a.AuthorId, a.Name;
4. Получить автора без книг:
   SELECT a.Name AS AuthorName
   FROM Authors a
   LEFT JOIN Books b ON a.AuthorId = b.AuthorId
   WHERE b.BookId IS NULL;
