# Fuzzy Logic Algorithm

## Overview
This repository demonstrates a fuzzy logic algorithm implemented in Python using the `scikit-fuzzy` library. Fuzzy logic, introduced by Lotfi A. Zadeh in 1965, extends classical logic by allowing partial membership in sets, enabling it to handle uncertainty and ambiguity in data effectively.

### What is Fuzzy Logic?
Fuzzy logic is based on fuzzy sets, where an element can belong to a set with a degree of membership ranging between 0 and 1. Unlike classical logic (where membership is binary: 0 or 1), fuzzy logic allows for a gradual transition, making it ideal for modeling real-world systems with imprecise boundaries.

For example, in classical logic, a temperature of 25°C might strictly fall into the "warm" category. In fuzzy logic, it can partially belong to both "warm" and "hot" categories with respective degrees of membership.

## Components of a Fuzzy Logic System

### 1. Fuzzification
Fuzzification maps crisp input values to corresponding fuzzy sets using membership functions. A membership function defines how each point in the input space is mapped to a degree of membership.

#### Membership Functions
Commonly used membership functions include:
- **Triangular**
- **Trapezoidal**
- **Gaussian**

For example, for the input variable `temperature`:
- `cold` might be represented by a trapezoidal function.
- `warm` and `hot` might use triangular functions.

### 2. Fuzzy Inference
Fuzzy inference evaluates fuzzy rules to produce fuzzy outputs. It involves two main steps:
- **Rule Evaluation**: Applies fuzzy operators (e.g., AND = min, OR = max) to the antecedents.
- **Aggregation**: Combines the outputs of all rules.

## Example Rule


#### If (temperature is cold) AND (wind is strong) THEN (heating is high)

Using the membership functions of `cold` and `strong`, the `AND` operator computes the minimum membership value, which determines the degree of membership for `heating`.

### 3. Defuzzification
Defuzzification converts the fuzzy output into a crisp value. A popular method is the **Center of Gravity (CoG)**, which calculates the weighted average of the fuzzy set:

xt = (Σ (xtk * mk)) / (Σ mk)

Where:
- `xtk`: Position of the centroid of each geometric shape.
- `mk`: Area of each shape.

### 4. Types of Fuzzy Inference Systems
- **Mamdani**: Outputs fuzzy sets. Aggregates results using the max function.
- **Sugeno**: Outputs singletons, which can be constants or linear combinations of input variables.

## Mathematical Principles
Fuzzy logic relies on key mathematical principles:
- **Membership Functions**: Define the degree of truth of an input belonging to a fuzzy set.
- **Fuzzy Operators**:
  - AND: `μ(a) ∧ μ(b) = min(μ(a), μ(b))`
  - OR: `μ(a) ∨ μ(b) = max(μ(a), μ(b))`
  - NOT: `¬μ(a) = 1 - μ(a)`
- **Inference Rules**: Evaluate conditions using fuzzy operators.
- **Defuzzification**: Applies geometric or numerical methods to extract crisp values from fuzzy outputs.

## Applications
This implementation can be applied to:
- Control systems (e.g., thermostats, washing machines).
- Decision-making systems.
- Data classification and clustering.

## How It Works
This repository demonstrates the complete workflow of a fuzzy system:
1. Definition of input variables and their membership functions.
2. Construction of fuzzy rules.
3. Evaluation of rules to infer fuzzy outputs.
4. Defuzzification to obtain crisp outputs.
