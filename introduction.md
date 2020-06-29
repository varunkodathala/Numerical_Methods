## Numerical Analysis

[Back](https://varunkodathala.github.io/Numerical_Methods/)

**Introduction to Solution of Algebraic and Transcedental Equations**

During the computation of Scientific and Engineering Problems, a recursive problem is to find the zero's of equations of the form

![equation1](https://latex.codecogs.com/gif.latex?f%28x%29%20%3D%200%20%5C)

If the equation is of lower order then algebraic formulae are available to determine zeros. 

Example:

Equation: 

![equation2](https://latex.codecogs.com/gif.latex?f%28x%29%20%3D%20x%5E2-x-12%20%3D%200)

Solution:

From Formula:

![equation3](https://latex.codecogs.com/gif.latex?root%20%3D%20%28%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D%29)

![equation4](https://latex.codecogs.com/gif.latex?root%20%3D%20-3%5C%20and%20%5C4)


Now, let's imagine to solve the following equations:

![equation5](https://latex.codecogs.com/gif.latex?f%28x%29%20%3D%20%5Cln%28x%5E3%29%20-%200.7)

![equation6](https://latex.codecogs.com/gif.latex?f%28x%29%20%3D%20%5Cexp%28-0.5x%29%20-%205x)

![equation7](https://latex.codecogs.com/gif.latex?f%28x%29%20%3D%20%5Csin%5E2%28x%29%20-%20x%5E2-2)

So, as of now there is no definite approach to solve these kind of equations through formulae. And in most of the times we are required to solve these kind of equations in the streams of science and engineering. 

Here comes the approximate approach called **Numerical Methods** to solve any kind of equations.

The Numerical Analysis is a wide concept dealing with basic equation's solution to integral solution.

Starting with root finding algorithms, It is divided into two categories:

1. Bracketing Method
2. Open Method

_Bracketing Method requires range of equation, range here refers to lower and upper limit of equation._

_Say **a** is the lower limit and **b** is the upper limit of the equation then it must satisfy the following equation._

![equation8](https://latex.codecogs.com/gif.latex?f%28a%29.f%28b%29%3C0)

## Let's Begin with the problem solving

_Initially the Bracketing Methods problem solving requires the range of equation let's say the range as (a,b)_

To satisfy the condition:

![equation8](https://latex.codecogs.com/gif.latex?f%28a%29.f%28b%29%3C0)

There are two approaches:

![equation9](https://latex.codecogs.com/gif.latex?1.%5C%20f%28a%29%3C0%5C%20and%5C%20f%28b%29%3E0)

![equation10](https://latex.codecogs.com/gif.latex?2.%5C%20f%28a%29%3E0%5C%20and%5C%20f%28b%29%3C0)


![range](https://lh3.googleusercontent.com/proxy/TwPF_y40SqWAV0IrJPpd2kPhHzxSH_pysDX1KM2qWZytyFYgDw0QmIomm0xL6o5LDrCPTuDdZuR-6LO7rySx60TGs45-c_ww9JweT8MWafsJdgu9a7uB6vA-)


Mathematically one can start taking values and find the range,

Example:

For the equation:

![equation2](https://latex.codecogs.com/gif.latex?f%28x%29%20%3D%20x%5E2-x-12%20%3D%200)

| ![image](https://latex.codecogs.com/gif.latex?x) | ![image](https://latex.codecogs.com/gif.latex?f%28x%29)|
| --- | --- |
| ![image](https://latex.codecogs.com/gif.latex?0) | ![equation11](https://latex.codecogs.com/gif.latex?f%280%29%20%3D%20-12) |
| ![image](https://latex.codecogs.com/gif.latex?1) | ![equation12](https://latex.codecogs.com/gif.latex?f%281%29%20%3D%20-12) |
| ![image](https://latex.codecogs.com/gif.latex?2) | ![equation13](https://latex.codecogs.com/gif.latex?f%282%29%20%3D%20-10) |
| ![image](https://latex.codecogs.com/gif.latex?3) | ![equation14](https://latex.codecogs.com/gif.latex?f%283%29%20%3D%20-6) |
| ![image](https://latex.codecogs.com/gif.latex?4) | ![equation15](https://latex.codecogs.com/gif.latex?f%284%29%20%3D%200) |
| ![image](https://latex.codecogs.com/gif.latex?5) | ![equation14](https://latex.codecogs.com/gif.latex?f%285%29%20%3D%208) |


Therefore (a,b) = (3,5) and root lies between this range. 
One can note that at x = 4 there is one zero of equation. In this example the root is real integer and hence f(x) = 0 at x = 4. But it varies with different equations, Let's infer with the programming. 

The programming snippets are provided which support MATLAB/ OCTAVE and Python3

## MATLAB SCRIPT
```
% MATLAB/ OCTAVE snippet to determine range of equation

function[min_range,max_range] = range_of_equation(eqn)
f = eqn;
k = 0;
min_range = 0;
max_range = 0;
if(f(k)~=0)
if(f(k)<0)
    while(f(k)<0)
        min_range = k;
        k = k+1;
    end
    end
    while(1)
        if(f(k)>0)
        max_range = k;
        k = k+1;
        break;
        end
    end
k = 0;
if(f(k)>0)
    while(f(k)>0)
        min_range = k;
        k = k+1;
    end
    while(1)
        if(f(k)<0)
        max_range = k;
        k = k+1;
        break;
        end
    end
end
end
end
```

## MATLAB DEMO

![image](matlab_range.gif)


## PYTHON3 SCRIPT
```
# Python3 Snippet to determine range of equation

def f(x):
    
    return 11*x**11 - 1 #update corresponding equation here

def range_of_equation():
    
    min_range = 0
    max_range = 0
    k = 0
    if(f(k)!=0):
        if(f(k)<0):
            while(f(k)<0):
                min_range = k
                k = k+1
        while(1):
            if(f(k)>0):
                max_range = k
                k = k+1
                break
        k = 0
        if(f(k)>0):
            while(f(k)>0):
                min_range = k
                k = k+1
            while(1):
                if(f(k)<0):
                    max_range = k
                    k = k+1
                    break
    return min_range,max_range

print(range_of_equation())

```
## Python Demo

![image](python_range.gif)

