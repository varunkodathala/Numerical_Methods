## Numerical Analysis

[Back](https://varunkodathala.github.io/Numerical_Methods/)

**Secant Method (Theoretical and Programmatic Approach)**

## Math Behind Secant Method

**_"According to Math Dictionary: a secant of a curve is a line that intersects the curve at a minimum of two distinct points"_** 

<p align = "center">
<img src="https://i.stack.imgur.com/q5T7w.png" />
</p>

So let (a,b) be the range of given equation then the successive root is given by:

<p align = "center">
<img src="https://latex.codecogs.com/gif.latex?x_%7Bn&plus;1%7D%20%3D%20x_%7Bn%7D%20-%20f%28x_%7Bn%7D%29*%7B%5Cfrac%7B%28x_%7Bn%7D-x_%7Bn-1%7D%29%7D%7Bf%28x_%7Bn%7D%29-f%28x_%7Bn-1%7D%29%7D%7D" />
</p>

## How Bisection is useful in root optimisation?

This is important topic to discuss here. So, let's get some intution about it.

Try to Visualize few points from the graph below

<p align = "center">
<img src="https://scientificsentence.net/Scientific/images/secant.png" />
</p>

General Formula is given by:

<p align = "center">
<img src="https://latex.codecogs.com/gif.latex?x_%7Bn&plus;1%7D%20%3D%20x_%7Bn%7D%20-%20f%28x_%7Bn%7D%29*%7B%5Cfrac%7B%28x_%7Bn%7D-x_%7Bn-1%7D%29%7D%7Bf%28x_%7Bn%7D%29-f%28x_%7Bn-1%7D%29%7D%7D" />
</p>

Where (a,b) should be updated iteratively according to the algorithm given below:

The descriptive algorithm is as follows:

```
1. Start

2. Input Equation

3. Find Range and initialize (a = min_range, b = max_range)

4. repeat
  {
    compute root r according to formula
  }
```

## General Description:

1. The zero of a curve may (mostly) exist on the secant line joining the two distinct points of curve. 

2. So, the secant methods determines the point of secant line intersecting the x-axis as described above. 

3. This process is repeated likewise till the iterations we match or from the [error analysis](https://varunkodathala.github.io/Numerical_Methods/error_analysis).

## Graphical Intution:

<p align = "center">
<img src="https://hplgit.github.io/Programming-for-Computations/pub/p4c/figs/fig4_6.png" />
</p>

## Root Analysis through Iterations

Equation: 
<p align = "center">
<img src="https://latex.codecogs.com/gif.latex?x%5E5-8x%5E4&plus;39x%5E3-62x%5E2&plus;50x-10%3D0" />
</p>

Range Obtained from the [previous understanding](https://varunkodathala.github.io/Numerical_Methods/introduction):

(a,b) = (0,1)

Root Analysis:

![image](equation_bisection_table.png)

**Snippets that support MATLAB/ OCTAVE and Python3**

## MATLAB SCRIPT

```
% MATLAB Script for Bisection Method
clc;
clear all;
close all;
f = @(x) x.^2 - x -2;
min_range = 1;
max_range = 4;
n =1 ;
while(1)
root(n) = (min_range+max_range)/2;
if(f(root(n))<0)
        min_range = root(n);
end
if(f(root(n))>0)
        max_range = root(n);
end
if n>1
    p = root(n);
    q = root(n-1);
    er(n) = abs((p - q)/p)*100;
    disp('Percentage Error is ');
    disp(er(n));
if(er(n)<(1/10^(4-1)))
    disp(root(n));
break;
end
end
n=n+1;
end
iterations = n;
i = 1:iterations;
er = er';
i = i';
root = root';
t = table(i,root,er)
```

## Python3 SCRIPT

```
# Python3 Script for Bisection Method


def f(x):
    
    return x**2 - x - 2

min_range = 1
max_range = 4
root = []
er = []
n =0 
er.append(100)
while(1):
    root.append((min_range+max_range)/2)
    if(f(root[n])<0):
            min_range = root[n]
    if(f(root[n])>0):
            max_range = root[n]
    
    if n>0:
        p = root[n]
        q = root[n-1]
        er.append(abs((p - q)/p)*100)
        print('Percentage Error is ')
        print(er[n])
        if(er[n]<(1/10**(4-1))):
            print(root[n])
            print(n+1)
            break
    n=n+1;

```
