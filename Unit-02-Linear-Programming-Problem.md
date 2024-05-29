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
Max ≤ 40x+40y
```
