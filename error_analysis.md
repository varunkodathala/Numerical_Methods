## Numerical Analysis

[Back](https://varunkodathala.github.io/Numerical_Methods/)

**Error Analysis of Numerical Algorithms corresponding to solution of equation**

Numerical errors arise from the use of approximations to represent exact mathematical operations and quantities. These include truncation errors, which result when approxima- tions are used to represent exact mathematical procedures, and round-off errors, which result when numbers having limited significant figures are used to represent exact numbers.

There are two types of errors:

- Absolute Error
- Relative Error

## Necessity of Error Analysis:

The solution analysis is expresses through tendency and stability of algorithm which is described by the error definitions.

This helps to break our execution when our desired latency is reached.

This helps us in choosing right algorithm availaible from literature for individual problem based on it's performance.

## Formulation:

```
Absolute Error:

1. Initialize true_value

2. Determine root_value from algorithm

3. Absolute_Error is given by abs_error = absolute(true_value - root_value)

```

```
Relative Error:

1. Run the Algorithm and Store the root value as prev = root value at 1st Iteration

2. Run the Algorithm again and store the root as present = root_value ar ith Iteration (where i is not 0)

3. Relative_Error is given by rel_error = absolute(((present - prev)/(present))*100) %

```

## Points to Note:

> Absolute Error should be used when true value is known

> Relative Error should be used when true value is not known







