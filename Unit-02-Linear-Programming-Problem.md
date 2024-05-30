# Unit 02: Linear Programming Problem

## Linear Programming Problem Model

1. Decision Variables 
- Identify what variables affect the outcome of the objective function. These are the variables you will solve for.

2. Objective Function 
- Determine the goal of the problem (maximize profit, minimize cost, etc.).
- Express the objective as a linear function of the decision variables.

3. Constraints
- List all the restrictions or limitations in the problem.
- Represent these constraints as linear inequalities or equations involving the decision variables.

### Formulation of LPP 
A factory produces two products P1 and P2. Each product requires time on two machines M1 and M2. The factory wants to determine how many units of each product to maximise its profilt. 
- Each unit of P1 requires 2 hours on M1 and 1 hr on M2. 
- Each unit of P2 requires 1 hour on M1 and 3 hr on M2. 

Machine M1 is available for 100 hours and machine M2 is available for 90 hours. The profit per unit of P1 is $40 and profit per unit of P2 is $40.

**Variables**
```
Let x be the no. unirs of P1 produced and y be the no. of units of p2 produces 
```
**Constrains**
```
2x+y ≤ 100
x+3y ≤  90
x, y ≥ 0 
```

**Objective Function**

```
Max ≥ 40x+40y
```

The Healthy Pet Food Company manufactures two types of dog food: Meaties and Yum- mies. Each package of Meaties contains 2 pounds of cereal and 3 pounds of meat; each package of Yummies contains 3 pounds of cereal and 1.5 pounds of meat. Healthy believes it can sell as much of each dog food as it can make. Meaties sell for $2.80 per package and Yummies sell for $2.00 per package. Healthy's production is limited in several ways. First, Healthy can buy only up to 400,000 pounds of cereal each month at $0.20 per pound. It can buy only up to 300,000 pounds of meat per month at $0.50 per pound. In addition, a spe- cial piece of machinery is required to make Meaties, and this machine has a capacity of 90,000 packages per month. The variable cost of blending and packing the dog food is $0.25 per package for Meaties and $0.20 per package for Yummies. This information is given in Table B-1.

`lb = pound`

`Availability of Cereal = 4,00,000`

`Availability of Meat: 3,00,000`

`Buy: $0.5`

`Capacity of MAchine to make meat:  `
| Meaties | Yummies |
|:--|:--|
|2lb+3lb|3lb+1.5lb|
|Sell: $3|Sell: $2|
|Packaging: $0.25|Packaging: %0.20|

---

**Decision Variable**

Let x be the no. of package of meaties.
Let y be the no. of package of yummies.

**Profit of each package of meaties**

 = 2.8 - 0.25(packaging) - 0.20 * 2 - 3 * 0.5 

= 0.65

**Profit of each package of meaties**

 =2.0 - 0.2 - 3 * 0.2 - 1.5 * 0.5

= 0.45

**Objective Function**
```
Max Z ≥ 0.65x+0.45y
```
**Constraints** 

```
2x+3y  ≤ 4,00,000 
3x+1.5y  ≤ 3,00,000
x ≤ 90,000
x, y ≥ 0
```