# Unit 02: Linear Programming Problems

## Question 01

The Healthy Pet Food Company manufactures two types of dog food: `Meaties` and `Yummies`. Each package of Meaties contains `2 pounds of cereal` and `3 pounds of meat`; each package of Yummies contains `3 pounds of cereal` and `1.5 pounds of meat`. Healthy believes it can sell as much of each dog food as it can make. Meaties sell for `$2.80 per package` and Yummies sell for `$2.00 per package`. Healthy's production is limited in several ways.

- Healthy can buy only up to `400,000 pounds of cereal` each month at `$0.20 per pound`.
- It can buy only up to `300,000 pounds of meat` per month at `$0.50 per pound`.
- A special piece of machinery is required to make Meaties, and this machine has a capacity of `90,000 packages per month`.
- The variable cost of blending and packing the dog food is `$0.25 per package` for Meaties and `$0.20 per package` for Yummies.

<u>Given</u>

|                                      | Meaties                   | Yummies       |
| :----------------------------------- | :------------------------ | :------------ |
| Sales price per package              | $2.80                     | $2.00         |
| Raw materials per package            |
| Cereal                               | 2.0 lb.                   | 3.0 lb.       |
| Meat                                 | 3.0 lb.                   | 1.5 lb.       |
| Variable cost - blending and packing | $0.25 package             | $0.20 package |
| Resources                            |
| Production capacity for Meaties      | 90,000 packages per month |
| Cereals available per month          | 400,000 lb.               |
| Meat available per month             | 300,000 lb.               |

<u><b>Solution</b></u>

**Decision Variable**

```
Let x be the no. of package of meaties.
Let y be the no. of package of yummies.
```

|                    |       Meaties        |       Yummies        |
| :----------------- | :------------------: | :------------------: |
| Selling price      |        $2.80         |        $2.00         |
| Minus              |
| Cereal             | (2.00 x 0.20) = 0.40 | (3.00 x 0.20) = 0.60 |
| Meat               | (3.00 x 0.50) = 1.50 | (1.50 x 0.50) = 0.75 |
| Blending           |         0.25         |         0.20         |
| Profit per package |        $0.65         |        $0.45         |

**Objective Function**

```
Max z ≥ 0.65x + 0.45y
Here,
0.65 represents the profit of Meaties
0.45 represents the profit of Yummies
```

**Constraints**

```
2x + 3y ≤ 4,00,000
3x + 1.5y ≤ 3,00,000
x ≤ 90,000
x, y ≥ 0
```

**Introduce slack variable**

```
2x + 3y = 40
3x + 1.5y = 30
x = 9
- 0.65x - 0.45y = 0
```

**Canonical form**

```
2x + 3.0y + 1 * s1 + 0 * s2 + 0 * s3 = 40
3x + 1.5y + 0 * s1 + 1 * s2 + 0 * s3 = 30
1x + 0.0y + 0 * s1 + 1 * s2 + 1 * s3 = 9
- 0.65x - 0.45y + 0 * s1 + 0 * s2 + 0 * s3 + z = 0
```

**First Tableau**

| Basic Variable |   x   |   y   | s1  | s2  | s3  |  z  | RHS | Ratio |
| :------------- | :---: | :---: | :-: | :-: | :-: | :-: | :-: | :---: |
| s1             |   2   |  3.0  |  1  |  0  |  0  |  0  | 40  |  20   |
| s2             |   3   |  1.5  |  0  |  1  |  0  |  0  | 30  |  10   |
| s3             |   1   |  0.0  |  0  |  0  |  1  |  0  |  9  |   9   |
| z              | -0.65 | -0.45 |  0  |  0  |  0  |  1  |  0  |   0   |

```
The last row has two -ve and hence doesn't give optimal solution.
Since -0.65 < -0.45, x is pivot column.

Since 9 < 10 < 20, s3 row is pivot row.
s3 is departing element and 1 is pivot element.
```

**Second Tableau**

```
R1 = R1 - 2R3
R2 = R2 - 3R3
R4 = R4 + 0.65R3
```

| Basic Variable |  x  |     y | s1  | s2  | s3  |  z  |   RHS | Ratio |
| :------------- | :-: | ----: | :-: | :-: | :-: | :-: | ----: | ----: |
| s1             |  0  |  3.00 |  1  |  0  | -2  |  0  | 22.00 |  7.33 |
| s2             |  0  |  1.50 |  0  |  1  | -3  |  0  |  3.00 |  2.00 |
| x              |  1  |  0.00 |  0  |  0  |  1  |  0  |  9.00 |       |
| z              |  0  | -0.45 |  0  |  0  |  0  |  1  |  5.85 |       |

```
The last row still consists of -ve.
So the pivot column is y.

Since 2 < 7.33, s2 row is pivot row.
s2 is departing element and 1.5 is pivot element.
```

**Third Tableau**

```
Divide R2/1.5
```

| Basic Variable |  x  |     y | s1  |  s2  | s3  |  z  |   RHS |
| :------------- | :-: | ----: | :-: | :--: | :-: | :-: | ----: |
| s1             |  0  |  3.00 |  1  | 0.00 | -2  |  0  | 22.00 |
| s2             |  0  |  1.00 |  0  | 0.66 | -2  |  0  |  2.00 |
| x              |  1  |  0.00 |  0  | 0.00 |  1  |  0  |  9.00 |
| z              |  0  | -0.45 |  0  | 0.00 |  0  |  1  |  5.85 |

**Forth Tableau**

```
R1 = R1 - 3R2
R4 = R4 + 0.45R2
```

| Basic Variable |  x  |  y  | s1  |     s2 |   s3 |  z  |   RHS |
| :------------- | :-: | :-: | :-: | -----: | ---: | :-: | ----: |
| s1             |  0  |  0  |  1  | -1.988 |  4.0 |  0  | 16.00 |
| y              |  0  |  1  |  0  |  0.666 | -2.0 |  0  |  2.00 |
| x              |  1  |  0  |  0  |  0.000 |  1.0 |  0  |  9.00 |
| z              |  0  |  0  |  0  |  0.297 | -0.9 |  1  |  6.75 |

```
Max Z = 6.75
6.75 at (9, 2)
```
