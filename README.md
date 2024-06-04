# SQL-HW1

- A SQL join combines columns from two orem ore tables in a single result set.
- Three Main joins: Inner, Outer, Cross join.
- Inner joins returns rows when there is atlea in both tables
- Avoid ambiguity by qualifying each column name with tables
- Uses conditionals
- Inner join is like a Venn diagram with one middle section

INNER JOIN example:
- mysql> SELECT 
    ->     fruits.fruit_name,
    ->     colors.color
    -> FROM fruits
    -> INNER JOIN colors
    -> ON fruits.fruit_id = colors.fruit_id;
+------------+--------+
| fruit_name | color  |
+------------+--------+
| Apple      | Red    |
| Banana     | Yellow |
| Grape      | Purple |
+------------+--------+
3 rows in set (0.00 sec)


