
1. **Select all columns for all records in the dataset.**
   ```sql
   SELECT * FROM drinks;
   ```

2. **Show the total number of records in the dataset.**
   ```sql
   SELECT COUNT(*) FROM drinks;
   ```

3. **Display the unique continents in the dataset.**
   ```sql
   SELECT DISTINCT continent FROM drinks;
   ```

4. **List the top 5 countries with the highest beer servings.**
   ```sql
   SELECT country, beer_servings FROM drinks ORDER BY beer_servings DESC LIMIT 5;
   ```

5. **Find the average total liters of pure alcohol consumed across all countries.**
   ```sql
   SELECT AVG(total_litres_of_pure_alcohol) FROM drinks;
   ```

6. **Show the countries where wine servings are greater than spirit servings.**
   ```sql
   SELECT country FROM drinks WHERE wine_servings > spirit_servings;
   ```

7. **Retrieve the total beer servings for each continent.**
   ```sql
   SELECT continent, SUM(beer_servings) AS total_beer_servings FROM drinks GROUP BY continent;
   ```

8. **Calculate the average spirit servings for each continent.**
   ```sql
   SELECT continent, AVG(spirit_servings) AS avg_spirit_servings FROM drinks GROUP BY continent;
   ```

9. **Find the country with the highest total liters of pure alcohol.**
   ```sql
   SELECT country FROM drinks ORDER BY total_litres_of_pure_alcohol DESC LIMIT 1;
   ```

10. **Show the top 3 countries with the lowest wine servings.**
   ```sql
   SELECT country, wine_servings FROM drinks ORDER BY wine_servings LIMIT 3;
   ```

11. **Retrieve the countries with no recorded wine servings.**
   ```sql
   SELECT country FROM drinks WHERE wine_servings IS NULL;
   ```

12. **Display the average beer servings for European countries.**
   ```sql
   SELECT AVG(beer_servings) FROM drinks WHERE continent = 'Europe';
   ```

13. **List the countries where total liters of pure alcohol are above the global average.**
   ```sql
   SELECT country FROM drinks WHERE total_litres_of_pure_alcohol > (SELECT AVG(total_litres_of_pure_alcohol) FROM drinks);
   ```

14. **Show the total liters of pure alcohol consumed by each country, ordered from highest to lowest.**
   ```sql
   SELECT country, total_litres_of_pure_alcohol FROM drinks ORDER BY total_litres_of_pure_alcohol DESC;
   ```

15. **Find the continent with the highest average wine servings.**
   ```sql
   SELECT continent, AVG(wine_servings) AS avg_wine_servings FROM drinks GROUP BY continent ORDER BY avg_wine_servings DESC LIMIT 1;
   ```

16. **Retrieve the countries in Asia with the lowest spirit servings.**
   ```sql
   SELECT country FROM drinks WHERE continent = 'Asia' ORDER BY spirit_servings LIMIT 5;
   ```

17. **Calculate the total number of records for each continent.**
   ```sql
   SELECT continent, COUNT(*) AS record_count FROM drinks GROUP BY continent;
   ```

18. **Show the top 3 countries with the highest average beer servings.**
   ```sql
   SELECT country, AVG(beer_servings) AS avg_beer_servings FROM drinks GROUP BY country ORDER BY avg_beer_servings DESC LIMIT 3;
   ```

19. **Find the countries where wine servings are exactly equal to spirit servings.**
   ```sql
   SELECT country FROM drinks WHERE wine_servings = spirit_servings;
   ```

20. **Display the countries with a total of more than 300 beer servings.**
   ```sql
   SELECT country FROM drinks WHERE beer_servings > 300;
   ```

21. **Calculate the average total liters of pure alcohol consumed by each continent.**
   ```sql
   SELECT continent, AVG(total_litres_of_pure_alcohol) AS avg_alcohol FROM drinks GROUP BY continent;
   ```

22. **List the continents where the average wine servings are less than 50.**
   ```sql
   SELECT continent FROM drinks GROUP BY continent HAVING AVG(wine_servings) < 50;
   ```

23. **Show the countries with the lowest total liters of pure alcohol, excluding null values.**
   ```sql
   SELECT country, total_litres_of_pure_alcohol FROM drinks WHERE total_litres_of_pure_alcohol IS NOT NULL ORDER BY total_litres_of_pure_alcohol LIMIT 5;
   ```

24. **Retrieve the countries with more spirit servings than beer servings.**
   ```sql
   SELECT country FROM drinks WHERE spirit_servings > beer_servings;
   ```

25. **Calculate the total number of unique countries in the dataset.**
   ```sql
   SELECT COUNT(DISTINCT country) FROM drinks;
   ```

26. **Show the countries with the highest total liters of pure alcohol in Europe.**
   ```sql
   SELECT country FROM drinks WHERE continent = 'Europe' ORDER BY total_litres_of_pure_alcohol DESC LIMIT 5;
   ```

27. **Find the continent with the highest total wine servings.**
   ```sql
   SELECT continent, SUM(wine_servings) AS total_wine_servings FROM drinks GROUP BY continent ORDER BY total_wine_servings DESC LIMIT 1;
   ```

28. **Retrieve the countries with the lowest total liters of pure alcohol in each continent.**
   ```sql
   SELECT continent, country, total_litres_of_pure_alcohol FROM drinks WHERE (continent, total_litres_of_pure_alcohol) IN (SELECT continent, MIN(total_litres_of_pure_alcohol) FROM drinks GROUP BY continent);
   ```

29. **Show the average beer, spirit, and wine servings for each continent.**
   ```sql
   SELECT continent, AVG(beer_servings) AS avg_beer_servings, AVG(spirit_servings) AS avg_spirit_servings, AVG(wine_servings) AS avg_wine_servings FROM drinks GROUP BY continent;
   ```

30. **Retrieve the countries where the total liters of pure alcohol are above the average for their respective continent.**
   ```sql
   SELECT country FROM drinks WHERE (continent, total_litres_of_pure_alcohol) IN (SELECT continent, AVG(total_litres_of_pure_alcohol) FROM drinks GROUP BY continent);
   ```
