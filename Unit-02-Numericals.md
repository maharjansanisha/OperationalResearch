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

Solving using simplex method,

```
Z = 0.65x + 0.45y
Z - 0.65x - 0.45y + 0 * s1 + 0 * s2 + 0 * s3 = 0
```

```
2x + 3.0y + 1 * s1 + 0 * s2 + 0 * s3 = 400,000
3x + 1.5y + 0 * s1 + 1 * s2 + 0 * s3 = 300,000
1x + 0.0y + 0 * s1 + 1 * s2 + 1 * s3 = 90,000
x, y, s1, s2 ≥ 0
```

| Basic Variable |   x   |   y   | s1  | s2  | s3  |   RHS   |  Ratio  |
| :------------- | :---: | :---: | :-: | :-: | :-: | :-----: | :-----: |
| z              | -0.65 | -0.45 |  0  |  0  |  0  |    0    |    0    |
| s1             |   2   |  3.0  |  1  |  0  |  0  | 400,000 | 200,000 |
| s2             |   3   |  1.5  |  0  |  1  |  0  | 300,000 | 100,000 |
| s3             |   1   |  0.0  |  0  |  0  |  1  | 90,000  | 90,000  |

```
Here, the pivot column is x.
the pivot row is s3

Performing s3 -= 1
```

