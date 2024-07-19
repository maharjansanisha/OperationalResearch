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
Let 𝑥 be the no. of package of meaties.
Let 𝑦 be the no. of package of yummies.
```

|                    |       Meaties        |       Yummies        |
| :----------------- | :------------------: | :------------------: |
| Selling price      |        $2.80         |        $2.00         |
| Minus              |
| Cereal             | (2.00 × 0.20) = 0.40 | (3.00 × 0.20) = 0.60 |
| Meat               | (3.00 × 0.50) = 1.50 | (1.50 × 0.50) = 0.75 |
| Blending           |         0.25         |         0.20         |
| Profit per package |        $0.65         |        $0.45         |

**Objective Function**

```
Max 𝐙 ≥ 0.65𝑥 + 0.45𝑦
Here,
0.65 represents the profit of Meaties
0.45 represents the profit of Yummies
```

**Constraints**

```
2𝑥 + 3𝑦 ≤ 4,00,000
3𝑥 + 1.5𝑦 ≤ 3,00,000
𝑥 ≤ 90,000
𝑥, 𝑦 ≥ 0
```

**Introduce slack variable**

```
2𝑥 + 3𝑦 = 40
3𝑥 + 1.5𝑦 = 30
𝑥 = 9
- 0.65𝑥 - 0.45𝑦 = 0
```

**Canonical form**

```
2𝑥  + 3.0𝑦 + 1 × 𝑠₁ + 0 × 𝑠₂ + 0 × 𝑠₃ = 40
3𝑥  + 1.5𝑦 + 0 × 𝑠₁ + 1 × 𝑠₂ + 0 × 𝑠₃ = 30
1𝑥  + 0.0𝑦 + 0 × 𝑠₁ + 1 × 𝑠₂ + 1 × 𝑠₃ = 9
- 0.65𝑥 - 0.45𝑦 + 0 × 𝑠₁ + 0 × 𝑠₂ + 0 × 𝑠₃ + 𝑧 = 0
```

**First Tableau**

| Basic Variable |     𝑥 |     𝑦 |  𝑠₁ |  𝑠₂ |  𝑠₃ |   𝑧 | RHS | Ratio |
| :------------- | ----: | ----: | --: | --: | --: | --: | --: | ----: |
| 𝑠₁             |  2.00 |  3.00 |   1 |   0 |   0 |   0 |  40 |    20 |
| 𝑠₂             |  3.00 |  1.50 |   0 |   1 |   0 |   0 |  30 |    10 |
| 𝑠₃             |  1.00 |  0.00 |   0 |   0 |   1 |   0 |   9 |     9 |
| 𝑧              | -0.65 | -0.45 |   0 |   0 |   0 |   1 |   0 |     0 |

```
The last row has two -ve and hence doesn't give optimal solution.
Since -0.65 < -0.45, 𝑥 is pivot column.

Since 9 < 10 < 20, 𝑠₃ row is pivot row.
𝑠₃ is departing element and 1 is pivot element.
```

**Second Tableau**

```
R₁ = R₁ - 2R₃
R₂ = R₂ - 3R₃
R₄ = R₄ + 0.65R₃
```

| Basic Variable |   𝑥 |     𝑦 |  𝑠₁ |  𝑠₂ |  𝑠₃ |   𝑧 |  RHS | Ratio |
| :------------- | --: | ----: | --: | --: | --: | --: | ---: | ----: |
| 𝑠₁             |   0 |  3.00 |   1 |   0 |  -2 |   0 | 2.00 |  7.33 |
| 𝑠₂             |   0 |  1.50 |   0 |   1 |  -3 |   0 | 3.00 |  2.00 |
| 𝑥              |   1 |  0.00 |   0 |   0 |   1 |   0 | 9.00 |     ∞ |
| 𝑧              |   0 | -0.45 |   0 |   0 |   0 |   1 | 5.85 |     ∞ |

```
The last row still consists of -ve.
So the pivot column is 𝑦.

Since 2 < 7.33, 𝑠₂ row is pivot row.
𝑠₂ is departing element and 1.5 is pivot element.
```

**Third Tableau**

> Divide
> $$\frac{R_2}{1.5}$$

| Basic Variable |   𝑥 |     𝑦 |  𝑠₁ |   𝑠₂ |  𝑠₃ |   𝑧 |   RHS |
| :------------- | --: | ----: | --: | ---: | --: | --: | ----: |
| 𝑠₁             |   0 |  3.00 |   1 | 0.00 |  -2 |   0 | 22.00 |
| 𝑠₂             |   0 |  1.00 |   0 | 0.66 |  -2 |   0 |  2.00 |
| 𝑥              |   1 |  0.00 |   0 | 0.00 |   1 |   0 |  9.00 |
| 𝑧              |   0 | -0.45 |   0 | 0.00 |   0 |   1 |  5.85 |

**Forth Tableau**

```
R₁ = R₁ - 3R₂
R₄ = R₄ + 0.45R₂
```

| Basic Variable |   𝑥 |   𝑦 |  𝑠₁ |     𝑠₂ |   𝑠₃ |   𝑧 |   RHS |
| :------------- | --: | --: | --: | -----: | ---: | --: | ----: |
| 𝑠₁             |   0 |   0 |   1 | -1.988 |  4.0 |   0 | 16.00 |
| 𝑦              |   0 |   1 |   0 |  0.666 | -2.0 |   0 |  2.00 |
| 𝑥              |   1 |   0 |   0 |  0.000 |  1.0 |   0 |  9.00 |
| 𝑧              |   0 |   0 |   0 |  0.297 | -0.9 |   1 |  6.75 |

```
Max 𝐙 = 6.75
6.75 at (9, 2)
```

## Question 2

```
Max 𝐙 = 3𝑥₁ + 2𝑥₂ + 5𝑥₃

subject to: 𝑥₁ + 2𝑥₂ + 𝑥₃ ≤ 430
            3𝑥₁ + 2𝑥₃ ≤ 460
            𝑥₁ + 4𝑥₂ ≤ 420
            𝑥₁, 𝑥₂, 𝑥₃ ≥ 0
```

**Introduce slack variable**

```
𝑥₁ + 2𝑥₂ + 𝑥₃ = 430
3𝑥₁ + 2𝑥₃ = 460
𝑥₁ + 4𝑥₂ = 420
-3𝑥₁ - 2𝑥₂ - 𝑥₃ = 0
```

**Canonical form**

```
1𝑥₁ + 2𝑥₂ + 1𝑥₃ + 1 × 𝑠₁ + 0 × 𝑠₂ + 0 × 𝑠₃ = 430
3𝑥₁ + 0𝑥₂ + 2𝑥₃ + 0 × 𝑠₁ + 1 × 𝑠₂ + 0 × 𝑠₃ = 460
1𝑥₁ + 4𝑥₂ + 0𝑥₃ + 0 × 𝑠₁ + 0 × 𝑠₂ + 1 × 𝑠₃ = 420
- 3𝑥₁ - 2𝑥₂ - 5𝑥₃ + 0 × 𝑠₁ + 0 × 𝑠₂ + 0 × 𝑠₃ + 𝑧 = 0
```

**First Tableau**

| Basic Variable |  𝑥₁ |  𝑥₂ |  𝑥₃ |  𝑠₁ |  𝑠₂ |  𝑠₃ |   𝑧 | RHS | Ratio |
| :------------- | --: | --: | --: | --: | --: | --: | --: | --: | ----: |
| 𝑠₁             |   1 |   2 |   1 |   1 |   0 |   0 |   0 | 430 |   430 |
| 𝑠₂             |   3 |   0 |   2 |   0 |   1 |   0 |   0 | 460 |   230 |
| 𝑠₃             |   1 |   4 |   0 |   0 |   0 |   1 |   0 | 420 |     ∞ |
| 𝑧              |  -3 |  -2 |  -5 |   0 |   0 |   0 |   1 |   0 |     0 |

```
The last row has three -ve and hence doesn't give optimal solution.
Since -5 < -3 < -2, 𝑥₃ is pivot column.

Since 230 < 430, 𝑠₂ row is pivot row.
𝑠₂ is departing element and 2 is pivot element.
```

**Second Tableau**

> Divide
> $$ \frac{S_2}{2} $$

| Basic Variable |  𝑥₁ |  𝑥₂ |  𝑥₃ |  𝑠₁ |  𝑠₂ |  𝑠₃ |   𝑧 | RHS |
| :------------- | --: | --: | --: | --: | --: | --: | --: | --: |
| 𝑠₁             |   1 |   2 |   1 |   1 |   0 |   0 |   0 | 430 |
| 𝑥₃             | 1.5 |   0 |   1 |   0 | 0.5 |   0 |   0 | 230 |
| 𝑠₃             |   1 |   4 |   0 |   0 |   0 |   1 |   0 | 420 |
| 𝑧              |  -3 |  -2 |  -5 |   0 |   0 |   0 |   1 |   0 |

**Third Tableau**

```
R₁ = R₁ - R₂
R₄ = R₄ + 5R₂
```

| Basic Variable |   𝑥₁ |  𝑥₂ |  𝑥₃ |  𝑠₁ |   𝑠₂ |  𝑠₃ |   𝑧 |  RHS | Ratio |
| :------------- | ---: | --: | --: | --: | ---: | --: | --: | ---: | ----: |
| 𝑠₁             | -0.5 |   2 |   0 |   1 | -0.5 |   0 |   0 |  200 |   100 |
| 𝑥₃             |  1.5 |   0 |   1 |   0 |  0.5 |   0 |   0 |  230 |     ∞ |
| 𝑠₃             |    1 |   4 |   0 |   0 |    0 |   1 |   0 |  420 |   105 |
| 𝑧              |  4.5 |  -2 |   0 |   0 |    0 |   0 |   1 | 1150 |     0 |

```
The last row still consists of -ve.
So the pivot column is 𝑥₂.

Since 100 < 105, 𝑠₁ row is pivot row.
𝑠₁ is departing element and 2 is pivot element.
```

**Forth Tableau**

> Divide
> $$ \frac{R_1}{2} $$

| Basic Variable |    𝑥₁ |  𝑥₂ |  𝑥₃ |  𝑠₁ |    𝑠₂ |  𝑠₃ |   𝑧 |  RHS |
| :------------- | ----: | --: | --: | --: | ----: | --: | --: | ---: |
| 𝑥₂             | -0.25 |   1 |   0 | 0.5 | -0.25 |   0 |   0 |  100 |
| 𝑥₃             |   1.5 |   0 |   1 |   0 |   0.5 |   0 |   0 |  230 |
| 𝑠₃             |     1 |   4 |   0 |   0 |     0 |   1 |   0 |  420 |
| 𝑧              |   4.5 |  -2 |   0 |   0 |     0 |   0 |   1 | 1150 |

**Fifth Tableau**

```
R₃ = R₃ - 4R₁
R₄ = R₄ + 2R₁
```

| Basic Variable |    𝑥₁ |  𝑥₂ |  𝑥₃ |  𝑠₁ |    𝑠₂ |  𝑠₃ |   𝑧 |  RHS |
| :------------- | ----: | --: | --: | --: | ----: | --: | --: | ---: |
| 𝑥₂             | -0.25 |   1 |   0 | 0.5 | -0.25 |   0 |   0 |  100 |
| 𝑥₃             |   1.5 |   0 |   1 |   0 |   0.5 |   0 |   0 |  230 |
| 𝑠₃             |     2 |   0 |   0 |  -2 |     1 |   1 |   0 |   20 |
| 𝑧              |     4 |   0 |   0 |   1 |  -0.5 |   0 |   1 | 1350 |

```
This function maximizes to the value 1350 at the points (𝑥₁,𝑥₂,𝑥₃) = (0, 100, 230)
```

## Question 3

```
Min 𝐙 = - 4𝑥₁ - 𝑥₂ - 3𝑥₃ - 5𝑥₄

subject to: 4𝑥₁ - 6𝑥₂ - 5𝑥₃ - 4𝑥₄ ≥ -20
            -3𝑥₁ - 2𝑥₂ + 4𝑥₃ + 𝑥₄ ≤ 10
            -8𝑥₁ - 3𝑥₂ + 3𝑥₃ + 2𝑥₄ ≤ 20
            𝑥₁, 𝑥₂, 𝑥₃, 𝑥₄ ≥ 0
```

```
The first condition to solve simple𝑥  method should be of max imize and
The constaints must be ≤.

Since there e𝑥 ist minimize in objective function and ≥ in constraints
we now multiply it with -ve to satisfy the condition.
```

```
Max 𝐙* = -𝐙 = 4𝑥₁ + 𝑥₂ + 3𝑥₃ + 5𝑥₄
Subject to: -4𝑥₁ + 6𝑥₂ + 5𝑥₃ + 4𝑥₄ ≤ 20
            -3𝑥₁ - 2𝑥₂ + 4𝑥₃ + 𝑥₄ ≤ 10
            -8𝑥₁ - 3𝑥₂ + 3𝑥₃ + 2𝑥₄ ≤ 20
            𝑥₁, 𝑥₂, 𝑥₃, 𝑥₄ ≥ 0
```

**Introduce slack variable**

```
-4𝑥₁ + 6𝑥₂ + 5𝑥₃ + 4𝑥₄ = 20
-3𝑥₁ - 2𝑥₂ + 4𝑥₃ + 1𝑥₄ = 10
-8𝑥₁ - 3𝑥₂ + 3𝑥₃ + 2𝑥₄ = 20
4𝑥₁ + 1𝑥₂ + 3𝑥₃ + 5𝑥₄ = 0
```

**Canonical form**

```
-4𝑥₁ + 6𝑥₂ + 5𝑥₃ + 4𝑥₄ + 1 × 𝑠₁ + 0 × 𝑠₂ + 0 × 𝑠₃ = 20
-3𝑥₁ - 2𝑥₂ + 4𝑥₃ + 1𝑥₄ + 0 × 𝑠₁ + 1 × 𝑠₂ + 0 × 𝑠₃ = 10
-8𝑥₁ - 3𝑥₂ + 3𝑥₃ + 2𝑥₄ + 0 × 𝑠₁ + 0 × 𝑠₂ + 1 × 𝑠₃ = 20
-4𝑥₁ - 1𝑥₂ - 3𝑥₃ - 5𝑥₄ + 0 × 𝑠₁ + 0 × 𝑠₂ + 0 × 𝑠₃ + 𝑧* = 0
```

**First Tableau**

| Basic Variable |  𝑥₁ |  𝑥₂ |  𝑥₃ |  𝑥₄ |  𝑠₁ |  𝑠₂ |  𝑠₃ | 𝑧\* | RHS | Ratio |
| :------------- | --: | --: | --: | --: | --: | --: | --: | --: | --: | ----: |
| 𝑠₁             |  -4 |   6 |   5 |   4 |   1 |   0 |   0 |   0 |  20 |     5 |
| 𝑠₂             |  -3 |  -2 |   4 |   1 |   0 |   1 |   0 |   0 |  10 |    10 |
| 𝑠₃             |  -8 |  -3 |   3 |   2 |   0 |   0 |   1 |   0 |  20 |    10 |
| 𝑧\*            |  -4 |  -1 |  -3 |  -5 |   0 |   0 |   0 |   1 |   0 |     0 |

```
The last row has four -ve and hence doesn't give optimal solution.
Since -5 < -4 < -3 < -1, 𝑥₄ is pivot column.

Since 5 < 10, 𝑠₁ row is pivot row.
𝑠₁ is departing element and 4 is pivot element.
```

**Second Tableau**

```
Divide 𝑠₁ / 4
```

| Basic Variable |  𝑥₁ |  𝑥₂ |   𝑥₃ |  𝑥₄ |   𝑠₁ |  𝑠₂ |  𝑠₃ | 𝑧\* | RHS |
| :------------- | --: | --: | ---: | --: | ---: | --: | --: | --: | --: |
| 𝑥₄             |  -1 | 1.5 | 1.25 |   1 | 0.25 |   0 |   0 |   0 |   5 |
| 𝑠₂             |  -3 |  -2 |    4 |   1 |    0 |   1 |   0 |   0 |  10 |
| 𝑠₃             |  -8 |  -3 |    3 |   2 |    0 |   0 |   1 |   0 |  20 |
| 𝑧\*            |  -4 |  -1 |   -3 |  -5 |    0 |   0 |   0 |   1 |   0 |

**Third Tableau**

```
R₂ = R₂ - R₁
R₃ = R₃ - 2R₁
R₄ = R₄ + 5R₁
```

| Basic Variable |  𝑥₁ |   𝑥₂ |   𝑥₃ |  𝑥₄ |   𝑠₁ |  𝑠₂ |  𝑠₃ | 𝑧\* | RHS | Ratio |
| :------------- | --: | ---: | ---: | --: | ---: | --: | --: | --: | --: | ----: |
| 𝑥₄             |  -1 |  1.5 | 1.25 |   1 | 0.25 |   0 |   0 |   0 |   5 |    -5 |
| 𝑠₂             |  -2 | -3.5 | 2.75 |   0 |    0 |   1 |   0 |   0 |   5 |  -2.5 |
| 𝑠₃             |  -6 |   -6 |  0.5 |   0 |    0 |   0 |   1 |   0 |  10 | -1.66 |
| 𝑧\*            |  -9 |  6.5 | 3.25 |   0 | 1.25 |   0 |   0 |   1 |  25 | -2.77 |

```
The last row still consists of -ve.
So the pivot column is 𝑥₁.

Since -1.66 < -2.5 < -2.77 < -5, 𝑠₃ row is pivot row.
𝑠₃ is departing element and -6 is pivot element.
```

**Forth Tableau**

> Divide
> $$ \frac{R_3}{-6}$$

| Basic Variable |  𝑥₁ |   𝑥₂ |    𝑥₃ |  𝑥₄ |   𝑠₁ |  𝑠₂ |   𝑠₃ | 𝑧\* |  RHS |
| :------------- | --: | ---: | ----: | --: | ---: | --: | ---: | --: | ---: |
| 𝑥₄             |  -1 |  1.5 |  1.25 |   1 | 0.25 |   0 |    0 |   0 |    5 |
| 𝑠₂             |  -2 | -3.5 |  2.75 |   0 |    0 |   1 |    0 |   0 |    5 |
| 𝑥₁             |   1 |    1 | 0.083 |   0 |    0 |   0 | 0.16 |   0 | 1.66 |
| 𝑧\*            |  -9 |  6.5 |  3.25 |   0 | 1.25 |   0 |    0 |   1 |   25 |

**Third Tableau**

```
R₁ = R₁ + R₃
R₂ = R₂ + 2R₃
R₄ = R₄ + 9R₃
```

| Basic Variable |  𝑥₁ |   𝑥₂ |    𝑥₃ |  𝑥₄ |   𝑠₁ |  𝑠₂ |   𝑠₃ | 𝑧\* |  RHS |
| :------------- | --: | ---: | ----: | --: | ---: | --: | ---: | --: | ---: |
| 𝑥₄             |   0 |  2.5 |  2.25 |   2 | 1.25 |   1 | 0.16 |   0 | 6.66 |
| 𝑠₂             |   0 | -1.5 | 2.916 |   0 |    0 |   1 | 0.32 |   0 |   15 |
| 𝑥₁             |   1 |    1 | 0.083 |   0 |    0 |   0 | 0.16 |   0 | 1.66 |
| 𝑧\*            |   0 | 15.5 | 3.997 |   0 | 1.25 |   0 | 1.44 |   1 | 39.4 |

```
No Solution
```

## Question 4

```
Max 𝐙 = 20𝑥 + 30𝑦

subject to: 3𝑥 + 3𝑦 ≤ 36
            5𝑥 + 2y ≤ 50
            2𝑥 + 6y ≤ 60
            𝑥 , 𝑦 ≥ 0
```

**Introduce slack variable**

```
3𝑥 + 3𝑦 = 36
5𝑥 + 2𝑦 = 50
2𝑥 + 6𝑦 = 60
- 20𝑥 - 30𝑦 = 0
```

**Canonical form**

```
3𝑥 + 3𝑦 + 1 × 𝑠₁ + 0 × 𝑠₂ + 0 × 𝑠₃ = 36
5𝑥 + 2𝑦 + 0 × 𝑠₁ + 1 × 𝑠₂ + 0 × 𝑠₃ = 50
2𝑥 + 6𝑦 + 0 × 𝑠₁ + 0 × 𝑠₂ + 1 × 𝑠₃ = 60
- 20𝑥 - 30𝑦 + 0 × 𝑠₁ + 0 × 𝑠₂ + 0 × 𝑠₃ + 𝑧 = 0
```

**First Tableau**

| Basic Variable |   𝑥 |   𝑦 |  𝑠₁ |  𝑠₂ |  𝑠₃ |   𝑧 | RHS | Ratio |
| :------------- | --: | --: | --: | --: | --: | --: | --: | ----: |
| 𝑠₁             |   3 |   3 |   1 |   0 |   0 |   0 |  36 |    12 |
| 𝑠₂             |   5 |   2 |   0 |   1 |   0 |   0 |  50 |    25 |
| 𝑠₃             |   2 |   6 |   0 |   0 |   1 |   0 |  60 |    10 |
| 𝑧              | -20 | -30 |   0 |   0 |   0 |   1 |   0 |     0 |

```
The last row has three -ve and hence doesn't give optimal solution.
Since -30 < -20, 𝑦 is pivot column.

Since 10 < 12 < 25, 𝑠₃ row is pivot row.
𝑠₃ is departing element and 6 is pivot element.
```

**Second Tableau**

> Divide
> $$ \frac{S_3}{6} $$

| Basic Variable |   𝑥 |   𝑦 |  𝑠₁ |  𝑠₂ |  𝑠₃ |   𝑧 | RHS |
| :------------- | --: | --: | --: | --: | --: | --: | --: |
| 𝑠₁             |   3 |   3 |   1 |   0 |   0 |   0 |  36 |
| 𝑠₂             |   5 |   2 |   0 |   1 |   0 |   0 |  50 |
| 𝑦              |   ⅓ |   1 |   0 |   0 |   ⅙ |   0 |  10 |
| 𝑧              | -20 | -30 |   0 |   0 |   0 |   1 |   0 |

**Third Tableau**

```
R₁ = R₁ - 3R₃
R₂ = R₂ - 2R₃
R₄ = R₄ + 30R₃
```

| Basic Variable |    𝑥 |   𝑦 |  𝑠₁ |  𝑠₂ |   𝑠₃ |   𝑧 | RHS | Ratio |
| :------------- | ---: | --: | --: | --: | ---: | --: | --: | ----: |
| 𝑠₁             |    2 |   0 |   1 |   0 | -0.5 |   0 |   6 |     3 |
| 𝑠₂             | 13/3 |   0 |   0 |   1 |   -⅓ |   0 |  30 | 90/13 |
| 𝑦              |    ⅓ |   1 |   0 |   0 |    ⅙ |   0 |  10 |    30 |
| 𝑧              |  -10 |   0 |   0 |   0 |    5 |   1 | 300 |   -30 |

```
The last row still consists of -ve.
So the pivot column is 𝑥.

Since 3 < 6.92 < 30, 𝑠₁ row is pivot row.
𝑠₁ is departing element and 2 is pivot element.
```

**Forth Tableau**

> Divide
> $$ \frac{R_1}{2} $$

| Basic Variable |    𝑥 |   𝑦 |  𝑠₁ |  𝑠₂ |    𝑠₃ |   𝑧 | RHS |
| :------------- | ---: | --: | --: | --: | ----: | --: | --: |
| x              |    1 |   0 | 0.5 |   0 | -0.25 |   0 |   3 |
| 𝑠₂             | 13/3 |   0 |   0 |   1 |    -⅓ |   0 |  30 |
| 𝑦              |    ⅓ |   1 |   0 |   0 |     ⅙ |   0 |  10 |
| 𝑧              |  -10 |   0 |   0 |   0 |     5 |   1 | 300 |

**Fifth Tableau**

```
R₃ = R₃ - 4R₁
R₄ = R₄ + 2R₁
```

> $$ R_2 = R_2 - \frac{13}{3}R_1 $$
> $$ R_3 = R_3 - \frac{1}{3}R_1 $$
> $$ R_4 = R_4 + 10R_1$$

| Basic Variable |   𝑥 |   𝑦 |    𝑠₁ |  𝑠₂ |    𝑠₃ |   𝑧 | RHS |
| :------------- | --: | --: | ----: | --: | ----: | --: | --: |
| x              |   1 |   0 |   0.5 |   0 | -0.25 |   0 |   3 |
| 𝑠₂             |   0 |   0 | -13/6 |   1 |  0.75 |   0 |  17 |
| 𝑦              |   0 |   1 |    -⅙ |   0 |  0.25 |   0 |   9 |
| 𝑧              |   0 |   0 |     5 |   0 |   2.5 |   1 | 330 |

```
This function maximizes to the value 330 at the points (𝑥, 𝑦) = (3, 9)
```

## Find the dual from primal conversion

```
Maz 𝐙 = 𝑥₁ - 𝑥₂ + 3𝑥₃
Subject to
            𝑥₁ + 𝑥₂ + 𝑥₃ ≤ 10
            2𝑥₁ - 𝑥₂ - 𝑥₃ ≤ 2
            2𝑥₁ - 2𝑥₂ - 3𝑥₃ ≤ 6
            𝑥₁, 𝑥₂, 𝑥₃ ≥ 0
```

```
Steps
    1. First we convert the problem in canonical form.
        Min → Min ≥
        Max → Max ≤
    2. Change the objective function of maximization in the primal into minimization in the dual.
    3. The no. of varibale in the primal will be the no of constraints in dual and vice versa.
    4. Cost efficient in objective function of the primal will be RHS constant of the constraints in dual and vice versa.
```

**Canonical form**

```
Maz 𝐙 = 𝑥₁ - 𝑥₂ + 3𝑥₃
𝑥₁ + 𝑥₂ + 𝑥₃ ≤ 10
2𝑥₁ - 𝑥₂ - 𝑥₃ ≤ 2
2𝑥₁ - 2𝑥₂ - 3𝑥₃ ≤ 6
𝑥₁, 𝑥₂, 𝑥₃ ≥ 0
```

Dual form, let w₁, w₂, w₃ be dual variables.

```
∴ Min 𝐙 = 10w₁ - 2w₂ + 6w₃

Subject to
            w₁ + 2w₂ + 2w₃ ≥ 1
            w₁ - w₂ - 2w₃ ≥ -1
            w₁ - w₂ - 3w₃ ≥ 3
            w₁, w₂, w₃ ≥ 0
```

**First Tableau**

| Basic Variable |    𝑤₁ |  𝑤₂ |  𝑤₃ |  𝑠₁ |  𝑠₂ |  𝑠₃ |   𝑧 | RHS | Ratio |
| :------------- | ----: | --: | --: | --: | --: | --: | --: | --: | ----: |
| 𝑠₁             |   `1` | `2` | `2` | `1` | `0` | `0` | `0` | `1` |     1 |
| 𝑠₂             |   `1` |  -1 |  -2 |   0 |   1 |   0 |   0 |  -1 |    -1 |
| 𝑠₃             |   `1` |  -1 |  -3 |   0 |   0 |   1 |   0 |   3 |     3 |
| 𝑧              | `-10` |   2 |  -6 |   0 |   0 |   0 |   1 |   0 |     0 |

```
The last row has three -ve and hence doesn't give optimal solution.
Since -10 < -6 < 2, 𝑤₁ is pivot column.

Since 1 < 3, 𝑠₁ row is pivot row.
𝑠₁ is departing element and 1 is pivot element.
```

**Second Tableau**

```
𝐑₂ = 𝐑₂ - 𝐑₁
𝐑₃ = 𝐑₃ - 𝐑₁
𝐑₄ = 𝐑₄ + 10𝐑₁
```

| Basic Variable |  𝑤₁ |  𝑤₂ |  𝑤₃ |  𝑠₁ |  𝑠₂ |  𝑠₃ |   𝑧 | RHS |
| :------------- | --: | --: | --: | --: | --: | --: | --: | --: |
| 𝑤₁             |   1 |   2 |   2 |   1 |   0 |   0 |   0 |   1 |
| 𝑠₂             |   0 |  -3 |  -4 |  -1 |   1 |   0 |   0 |  -2 |
| 𝑠₃             |   0 |  -3 |  -5 |  -1 |   0 |   1 |   0 |   2 |
| 𝑧              |   0 |  22 |  14 |  10 |   0 |   0 |   1 |  10 |

## Question 6

```
Max 𝐙 = 𝐱₁ + 2𝐱₂ + 3𝐱₃

Subject to
            𝐱₁ + 2𝐱₂ - 3𝐱₃ ≤ 9
            𝐱₁ - 𝐱₂ + 4𝐱₃ ≥ -5
            3𝐱₁ + 2𝐱₂ + 𝐱₃ ≤ 10
            𝐱₁, 𝐱₂, 𝐱₃ ≥ 0
```

## Question 7

```
Min 𝐙 = 𝐱₁ - 2𝐱₂ = 3𝐱₃
Subject to
            𝐱₁ + 2𝐱₂ + 𝐱₃ ≥ 10
            𝐱₁ + 𝐱₂ - 𝐱₃ ≤ 9
            2𝐱₁ + 3𝐱₂ + 2𝐱₃ ≤ 5
            𝐱₁, 𝐱₂, 𝐱₃ ≥ 0
```
