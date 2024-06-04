# SQL-HW1

- A SQL join combines columns from two orem ore tables in a single result set.
- Three Main joins: Inner, Outer, Cross join.
- Inner joins returns rows when there is atlea in both tables
- Avoid ambiguity by qualifying each column name with tables
- Uses conditionals
- Inner join is like a Venn diagram with one middle section

 # INNER JOIN example:
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

------------------------------------
# Outer Joins
-Left Outer Joins returns entire table1 and overlapping part of table 2

LEFT OUTER JOIN:
select fruits.fruit_name, colors.color
    -> from fruits
    -> left join colors
    -> on fruits.fruit_id = colors.color_id;
+------------+--------+
| fruit_name | color  |
+------------+--------+
| Apple      | Red    |
| Banana     | Yellow |
+------------+--------+
- Left join is more common because we read from left to right.

# Right Outer Joins
- Returns all the rows from the right table with the matching rows from the left table,
- If there are no columns matching the left table it returns null values

mysql> select froot.fruit_name, cooler.color
    -> from fruits as froot
    -> right join colors AS cooler
    -> on froot.fruit_id = cooler.color_id;
+------------+--------+
| fruit_name | color  |
+------------+--------+
| Apple      | Red    |
| Banana     | Yellow |
| NULL       | Purple |
| NULL       | Green  |
| NULL       | Pink   |
| NULL       | Orange |
+------------+--------+
6 rows in set (0.01 sec)


#Full Outer join
- Full outer join combines leter and right join
- returns rows from either table with null values

- mysql > SELECT f.fruit_name,c.color
    -> FROM fruits AS f
    -> LEFT JOIN colors AS c
    -> ON f.fruit_id = c.color_id
    -> UNION
    -> SELECT f.fruit_name, c.color
    -> FROM fruits AS f
    -> RIGHT JOIN colors AS c
    -> ON f.fruit_id = c.color_id;
+------------+--------+
| fruit_name | color  |
+------------+--------+
| Apple      | Red    |
| Banana     | Yellow |
| NULL       | Purple |
| NULL       | Green  |
| NULL       | Pink   |
| NULL       | Orange |
+------------+--------+
6 rows in set (0.00 sec)

# Cross Join
- Cartesian join, does not necessitate any condition to join
  - result set contains records that are multiples of the record number of both tables.
 
- mysql> select t1.*, t2.*
    -> from fruits t1
    -> cross join colors t2;
+----------+------------+----------+--------+
| fruit_id | fruit_name | color_ID | color  |
+----------+------------+----------+--------+
|        1 | Apple      |        1 | Red    |
|        2 | Banana     |        1 | Red    |
|        1 | Apple      |        2 | Yellow |
|        2 | Banana     |        2 | Yellow |
|        1 | Apple      |        3 | Purple |
|        2 | Banana     |        3 | Purple |
|        1 | Apple      |        4 | Green  |
|        2 | Banana     |        4 | Green  |
|        1 | Apple      |        5 | Pink   |
|        2 | Banana     |        5 | Pink   |
|        1 | Apple      |        6 | Orange |
|        2 | Banana     |        6 | Orange |
+----------+------------+----------+--------+
12 rows in set (0.00 sec)

