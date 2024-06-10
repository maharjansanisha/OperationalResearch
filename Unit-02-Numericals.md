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

**Profit of each package of Meaties**

```
Selling Price of Meaties = $2.8 per package,
Packaging Price of Meaties = $0.25 per package,

Cost of Cereal = $0.2 per pound,
Quantity of Cereal in Meaties = 2 lb per package,

Cost of Meat = $0.5 per pound,
Quantity of Meat in Meaties = 3 lb per package,

Profit of each package of Meaties = Selling Price of Meaties - Packaging Price of Meaties - (Cost of Cereal x Quantity of Cereal in Meaties) - (Cost of Meat x Quantity of Meat in Meaties)
= 2.8 - 0.25 - (0.2 * 2) - (0.5 * 3)
= 2.8 - 0.25 - 0.4 - 1.5
= 2.55 - 1.9
= 0.65
```

**Profit of each package of Yummies**

```
Selling Price of Yummies = $2 per package,
Packaging Price of Yummies = $0.2 per package,

Cost of Cereal = $0.2 per pound,
Quantity of Cereal in Yummies = 3 lb per package,

Cost of Meat = $0.5 per pound,
Quantity of Meat in Yummies = 1.5 lb per package,

Profit of each package of Yummies = Selling Price of Yummies - Packaging Price of Yummies - (Cost of Cereal x Quantity of Cereal in Yummies) - (Cost of Meat x Quantity of Meat in Yummies)
= 2 - 0.2 - (0.2 * 3) - (0.5 * 1.5)
= 2 - 0.2 - 0.6 - 0.75
= 1.8 - 1.35
= 0.45
```

**Objective Function**

```
Max z ≥ 0.65x + 0.45y
```

**Constraints**

```
2x + 3y ≤ 4,00,000
3x + 1.5y ≤ 3,00,000
x ≤ 90,000
x, y ≥ 0
```
