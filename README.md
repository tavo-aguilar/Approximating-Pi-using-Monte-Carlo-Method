# Approximating-Pi-using-Monte-Carlo-Method
Pi approximation using Monte Carlo Method

- Author: Gustavo Aguilar

# Monte Carlo Approximation of π

This repository contains a Jupyter notebook that demonstrates how to estimate the value of π using a simple **Monte Carlo** method. The code generates random points in a square and determines how many fall inside a circle — giving a statistical approximation of π.

## Overview

This project uses a classic Monte Carlo integration technique to approximate π. By throwing random points into a unit square and counting how many land inside the inscribed circle, we estimate the area ratio. The notebook visualizes the points, compares vectorized vs. looped implementations, and shows how accuracy improves with more points. It’s an excellent educational example of probabilistic methods, random sampling, and performance optimization in Python.

## Physics / Math Background

Consider a square with side length 2 centered at the origin (from -1 to +1 in both x and y). Inside this square lies a quarter circle of radius 1 (the first quadrant part of the unit circle).

The area of the square is 4.  
The area of the quarter circle is π/4.

If we generate N uniformly random points inside the square and count how many fall inside the circle (i.e., x² + y² ≤ 1), then:

π ≈ 4 × (number of points inside circle) / N

This is a geometric probability method — the more points we use, the better the approximation.

## Methods

- **Numerical Method**: Monte Carlo integration via random sampling
- **Implementation styles compared**:
  - Vectorized (fast) — using NumPy array operations
  - Looped (intuitive but much slower)
- **Languages and Libraries**:
  - Python 3
  - NumPy — for fast random number generation and vectorized computations
  - Matplotlib — for visualizing points inside/outside the circle

## Results

The notebook produces:

- A scatter plot showing:
  - Green points → inside the quarter circle
  - Red points → outside the quarter circle
- Numerical approximation of π (e.g. 3.1412… with enough points)
- Comparison of execution time:
  - Vectorized version: ~20–30 µs per run (very fast)
  - Looped version: ~2 ms per run (≈100× slower)
- Error analysis: difference between approximated π and `np.pi`

Typical output with 1,000,000 points: π approximation = 3.14184, Error = 0.000248…
