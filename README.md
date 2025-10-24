# Exp No: 8 — Solve Cryptarithmetic Problem (Constraint Satisfaction Problem) using Python  

### Name: Shanthosh G
### Register Number: 2305003008

## AIM:  
To solve a Cryptarithmetic Problem, a type of Constraint Satisfaction Problem (CSP), using Python.  

## Problem Description:  

A cryptarithmetic puzzle assigns unique digits (0–9) to letters so that a given arithmetic equation holds true.  
Example:  

```
B A S E
B A L L
---------
G A M E S
```

The goal is to find the digit substitution that satisfies this equation.  

## ALGORITHM:  

### Function: `isValid(nodeList, count, word1, word2, word3)`

**Input:**  
A list of nodes containing letters and their possible numeric values, number of elements in the node list, and three words.  

**Output:**  
True if the sum of the numeric values of `word1` and `word2` equals that of `word3`, else False.  

### Step-by-Step Logic
1. Initialize multipliers for each word (unit, tens, hundreds, etc.).
2. Convert each letter to its assigned number.
3. Compute numeric values of all three words.
4. If the equation `word1 + word2 = word3` holds, return True; else return False.  

## Sample Program:

```python
from itertools import permutations

def solve_cryptarithmetic():
    for perm in permutations(range(10), 8):
        S, E, N, D, M, O, R, Y = perm

        # Avoid leading zeros
        if S == 0 or M == 0:
            continue

        # Compute numeric values
        SEND = 1000 * S + 100 * E + 10 * N + D
        MORE = 1000 * M + 100 * O + 10 * R + E
        MONEY = 10000 * M + 1000 * O + 100 * N + 10 * E + Y

        # Check if equation satisfies
        if SEND + MORE == MONEY:
            return SEND, MORE, MONEY

    return None


# Execute the solver
solution = solve_cryptarithmetic()

if solution:
    SEND, MORE, MONEY = solution
    print(f"SEND = {SEND}")
    print(f"MORE = {MORE}")
    print(f"MONEY = {MONEY}")
else:
    print("No solution found.")
```

## Sample Input and Output:

### Input:
```
SEND
MORE
```

### Output:

```
SEND = 9567  
MORE = 1085  
MONEY = 10652
```
<img width="443" height="204" alt="image" src="https://github.com/user-attachments/assets/44872348-0c22-45bb-a718-7c318b976c98" />

## PROGRAM:
```python
from itertools import permutations

def solve_cross_roads():
    letters = ('C','R','O','S','A','D','N','G','E')
    for perm in permutations(range(10), len(letters)):
        C, R, O, S, A, D, N, G, E = perm

        # Leading letters cannot be zero
        if C == 0 or R == 0 or D == 0:
            continue

        CROSS  = 10000*C + 1000*R + 100*O + 10*S + S
        ROADS  = 10000*R + 1000*O + 100*A + 10*D + S
        DANGER = 100000*D + 10000*A + 1000*N + 100*G + 10*E + R

        if CROSS + ROADS == DANGER:
            return CROSS, ROADS, DANGER, {'C':C,'R':R,'O':O,'S':S,'A':A,'D':D,'N':N,'G':G,'E':E}

    return None

solution = solve_cross_roads()

if solution:
    CROSS, ROADS, DANGER, mapping = solution
    print("Mapping:", mapping)
    print(f"CROSS  = {CROSS}")
    print(f"ROADS  = {ROADS}")
    print(f"DANGER = {DANGER}")
else:
    print("No solution found.")

```
## OUTPUT:
<img width="840" height="97" alt="image" src="https://github.com/user-attachments/assets/71869433-2b7a-4474-91b7-457b032dc8f9" />

## RESULT:
Thus, a Cryptarithmetic Problem was successfully solved using Python.
