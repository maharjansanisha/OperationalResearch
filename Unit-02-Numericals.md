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

## Question 2

```
Max Z = 3x1 + 2x2 + 5x3

subject to: x1 + 2x2 + x3 &le; 430
            3x1 + 2x3 &le; 460
            x1 + 4x2 &le; 420
            x1, x2, x3 &ge; 0
```

**Introduce slack variable**

```
x1 + 2x2 + x3 = 430
3x1 + 2x3 = 460
x1 + 4x2 = 420
-3x1 - 2x2 - x3 = 0
```

**Canonical form**

```
1x1 + 2x2 + 1x3 + 1 * s1 + 0 * s2 + 0 * s3 = 430
3x1 + 0x2 + 2x3 + 0 * s1 + 1 * s2 + 0 * s3 = 460
1x1 + 4x2 + 0x3 + 0 * s1 + 0 * s2 + 1 * s3 = 420
- 3x1 - 2x2 - 5x3 + 0 * s1 + 0 * s2 + 0 * s3 + z = 0
```

**First Tableau**

| Basic Variable | x1  | x2  | x3  | s1  | s2  | s3  |  z  | RHS | Ratio |
| :------------- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :---: |
| s1             |  1  |  2  |  1  |  1  |  0  |  0  |  0  | 430 |  430  |
| s2             |  3  |  0  |  2  |  0  |  1  |  0  |  0  | 460 |  230  |
| s3             |  1  |  4  |  0  |  0  |  0  |  1  |  0  | 420 |       |
| z              | -3  | -2  | -5  |  0  |  0  |  0  |  1  |  0  |   0   |

```
The last row has three -ve and hence doesn't give optimal solution.
Since -5 < -3 < -2, x3 is pivot column.

Since 230 < 430, s2 row is pivot row.
s2 is departing element and 2 is pivot element.
```

**Second Tableau**

```
Divide s2 / 2
```

| Basic Variable | x1  | x2  | x3  | s1  | s2  | s3  |  z  | RHS |
| :------------- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| s1             |  1  |  2  |  1  |  1  |  0  |  0  |  0  | 430 |
| x3             | 1.5 |  0  |  1  |  0  | 0.5 |  0  |  0  | 230 |
| s3             |  1  |  4  |  0  |  0  |  0  |  1  |  0  | 420 |
| z              | -3  | -2  | -5  |  0  |  0  |  0  |  1  |  0  |

**Third Tableau**

```
R1 = R1 - R2
R4 = R4 + 5R2
```

| Basic Variable |  x1  | x2  | x3  | s1  |  s2  | s3  |  z  | RHS  | Ratio |
| :------------- | :--: | :-: | :-: | :-: | :--: | :-: | :-: | :--: | :---: |
| s1             | -0.5 |  2  |  0  |  1  | -0.5 |  0  |  0  | 200  |  100  |
| x3             | 1.5  |  0  |  1  |  0  | 0.5  |  0  |  0  | 230  |       |
| s3             |  1   |  4  |  0  |  0  |  0   |  1  |  0  | 420  |  105  |
| z              | 4.5  | -2  |  0  |  0  |  0   |  0  |  1  | 1150 |   0   |

```
The last row still consists of -ve.
So the pivot column is x2.

Since 100 < 105, s1 row is pivot row.
s1 is departing element and 2 is pivot element.
```

**Forth Tableau**

```
Divide R1 / 2
```

| Basic Variable |  x1   | x2  | x3  | s1  |  s2   | s3  |  z  | RHS  |
| :------------- | :---: | :-: | :-: | :-: | :---: | :-: | :-: | :--: |
| x2             | -0.25 |  1  |  0  | 0.5 | -0.25 |  0  |  0  | 100  |
| x3             |  1.5  |  0  |  1  |  0  |  0.5  |  0  |  0  | 230  |
| s3             |   1   |  4  |  0  |  0  |   0   |  1  |  0  | 420  |
| z              |  4.5  | -2  |  0  |  0  |   0   |  0  |  1  | 1150 |

**Fifth Tableau**

```
R3 = R3 - 4R1
R4 = R4 + 2R1
```

| Basic Variable |  x1   | x2  | x3  | s1  |  s2   | s3  |  z  |  RHS |
| :------------- | :---: | :-: | :-: | :-: | :---: | :-: | :-: | ---: |
| x2             | -0.25 |  1  |  0  | 0.5 | -0.25 |  0  |  0  |  100 |
| x3             |  1.5  |  0  |  1  |  0  |  0.5  |  0  |  0  |  230 |
| s3             |   2   |  0  |  0  | -2  |   1   |  1  |  0  |   20 |
| z              |   4   |  0  |  0  |  1  | -0.5  |  0  |  1  | 1350 |

```
This function maximizes to the value 1350 at the points (x1,x2,x3) = (0, 100, 230)
```

## Question 3

```
Min Z = - 4x1 - x2 - 3x3 - 5x4

subject to: 4x1 - 6x2 - 5x3 - 4x4 ≥ -20
            -3x1 - 2x2 + 4x3 + x4 ≤ 10
            -8x1 - 3x2 + 3x3 + 2x4 ≤ 20
            x1, x2, x3, x4 ≥ 0
```

```
The first condition to solve simplex method should be of maximize and
The constaints must be ≤.

Since there exist minimize in objective function and ≥ in constraints
we now multiply it with -ve to satisfy the condition.
```

```
Max Z* = -Z = 4x1 + x2 + 3x3 + 5x4
Subject to: -4x1 + 6x2 + 5x3 + 4x4 ≤ 20
            -3x1 - 2x2 + 4x3 + x4 ≤ 10
            -8x1 - 3x2 + 3x3 + 2x4 ≤ 20
            x1, x2, x3, x4 ≥ 0
```

**Introduce slack variable**

```
-4x1 + 6x2 + 5x3 + 4x4 = 20
-3x1 - 2x2 + 4x3 + 1x4 = 10
-8x1 - 3x2 + 3x3 + 2x4 = 20
4x1 + 1x2 + 3x3 + 5x4 = 0
```

**Canonical form**

```
-4x1 + 6x2 + 5x3 + 4x4 + 1 * s1 + 0 * s2 + 0 * s3 = 20
-3x1 - 2x2 + 4x3 + 1x4 + 0 * s1 + 1 * s2 + 0 * s3 = 10
-8x1 - 3x2 + 3x3 + 2x4 + 0 * s1 + 0 * s2 + 1 * s3 = 20
-4x1 - 1x2 - 3x3 - 5x4 + 0 * s1 + 0 * s2 + 0 * s3 + z* = 0
```

**First Tableau**

| Basic Variable | x1  | x2  | x3  | x4  | s1  | s2  | s3  | z\* | RHS | Ratio |
| :------------- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :---: |
| s1             | -4  |  6  |  5  |  4  |  1  |  0  |  0  |  0  | 20  |   5   |
| s2             | -3  | -2  |  4  |  1  |  0  |  1  |  0  |  0  | 10  |  10   |
| s3             | -8  | -3  |  3  |  2  |  0  |  0  |  1  |  0  | 20  |  10   |
| z\*            | -4  | -1  | -3  | -5  |  0  |  0  |  0  |  1  |  0  |   0   |

```
The last row has four -ve and hence doesn't give optimal solution.
Since -5 < -4 < -3 < -1, x4 is pivot column.

Since 5 < 10, s1 row is pivot row.
s1 is departing element and 4 is pivot element.
```

**Second Tableau**

```
Divide s1 / 4
```

| Basic Variable | x1  | x2  |  x3  | x4  |  s1  | s2  | s3  | z\* | RHS |
| :------------- | :-: | :-: | :--: | :-: | :--: | :-: | :-: | :-: | :-: |
| x4             | -1  | 1.5 | 1.25 |  1  | 0.25 |  0  |  0  |  0  |  5  |
| s2             | -3  | -2  |  4   |  1  |  0   |  1  |  0  |  0  | 10  |
| s3             | -8  | -3  |  3   |  2  |  0   |  0  |  1  |  0  | 20  |
| z\*            | -4  | -1  |  -3  | -5  |  0   |  0  |  0  |  1  |  0  |

**Third Tableau**

```
R2 = R2 - R1
R3 = R3 - 2R1
R4 = R4 + 5R1
```

| Basic Variable | x1  |  x2  |  x3  | x4  |  s1  | s2  | s3  | z\* | RHS | Ratio |
| :------------- | :-: | :--: | :--: | :-: | :--: | :-: | :-: | :-: | :-: | :---: |
| x4             | -1  | 1.5  | 1.25 |  1  | 0.25 |  0  |  0  |  0  |  5  |  -5   |
| s2             | -2  | -3.5 | 2.75 |  0  |  0   |  1  |  0  |  0  |  5  | -2.5  |
| s3             | -6  |  -6  | 0.5  |  0  |  0   |  0  |  1  |  0  | 10  | -1.66 |
| z\*            | -9  | 6.5  | 3.25 |  0  | 1.25 |  0  |  0  |  1  | 25  | -2.77 |

```
The last row still consists of -ve.
So the pivot column is x1.

Since -1.66 < -2.5 < -2.77 < -5, s3 row is pivot row.
s3 is departing element and -6 is pivot element.
```

**Forth Tableau**

```
R3 / -6
```

| Basic Variable | x1  |  x2  |  x3   | x4  |  s1  | s2  |  s3  | z\* | RHS  |
| :------------- | :-: | :--: | :---: | :-: | :--: | :-: | :--: | :-: | :--: |
| x4             | -1  | 1.5  | 1.25  |  1  | 0.25 |  0  |  0   |  0  |  5   |
| s2             | -2  | -3.5 | 2.75  |  0  |  0   |  1  |  0   |  0  |  5   |
| x1             |  1  |  1   | 0.083 |  0  |  0   |  0  | 0.16 |  0  | 1.66 |
| z\*            | -9  | 6.5  | 3.25  |  0  | 1.25 |  0  |  0   |  1  |  25  |

**Third Tableau**

```
R1 = R1 + R3
R2 = R2 + 2R3
R4 = R4 + 9R3
```

| Basic Variable | x1  |  x2  |  x3   | x4  |  s1  | s2  |  s3  | z\* | RHS  |
| :------------- | :-: | :--: | :---: | :-: | :--: | :-: | :--: | :-: | :--: |
| x4             |  0  | 2.5  | 2.25  |  2  | 1.25 |  1  | 0.16 |  0  | 6.66 |
| s2             |  0  | -1.5 | 2.916 |  0  |  0   |  1  | 0.32 |  0  |  15  |
| x1             |  1  |  1   | 0.083 |  0  |  0   |  0  | 0.16 |  0  | 1.66 |
| z\*            |  0  | 15.5 | 3.997 |  0  | 1.25 |  0  | 1.44 |  1  | 39.4 |

```
No Solution
```