# MediaSoft-practice
Выполнил Салин Никита ИСдо-34
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
