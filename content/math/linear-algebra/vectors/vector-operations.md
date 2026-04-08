---
title: Vector Operations
topic: vector operations
tags: [math, linear-algebra, vectors]
related: [
  "[[vectors/linear-combinations]]",
  "[[spaces/basis]]"
]
status: draft
source: AGLA I
aliases: ["vector algebra basics"]
---

# Intuition

A vector represents magnitude and direction.

Vector operations describe the most basic ways to work with vectors:

- addition combines vectors into a new vector
- scalar multiplication rescales a vector
- dot product measures how strongly two vectors align
- cross product builds a vector orthogonal to two given vectors in R^3

Geometrically:

- addition means placing one vector after another
- scalar multiplication changes length and possibly direction
- dot product detects similarity of direction
- cross product gives a perpendicular direction and encodes area

# Theory

Let

$$
\mathbf{a} = (a_1, a_2, \ldots, a_n), \quad
\mathbf{b} = (b_1, b_2, \ldots, b_n), \quad
\lambda \in \mathbb{R}
$$

## Addition

Vector addition is defined coordinate-wise:

$$
\mathbf{a} + \mathbf{b} = (a_1 + b_1, a_2 + b_2, \ldots, a_n + b_n)
$$

This operation is defined only when both vectors have the same dimension.

## Scalar multiplication

Multiplication of a vector by a scalar is also defined coordinate-wise:

$$
\lambda \mathbf{a} = (\lambda a_1, \lambda a_2, \ldots, \lambda a_n)
$$

If $\lambda > 0$, the direction is preserved.
If $\lambda < 0$, the direction is reversed.
If $\lambda = 0$, the result is the zero vector.

## Dot product

The dot product of two vectors in $\mathbb{R}^n$ is

$$
\mathbf{a} \cdot \mathbf{b} = \sum_{i=1}^{n} a_i b_i
$$

Equivalent geometric form:

$$
\mathbf{a} \cdot \mathbf{b} = \|\mathbf{a}\| \|\mathbf{b}\| \cos \theta
$$

where $\theta$ is the angle between the vectors.

Important consequences:

$$
\mathbf{a} \cdot \mathbf{b} = 0
\quad \Longleftrightarrow \quad
\mathbf{a} \perp \mathbf{b}
$$

for nonzero vectors.

## Cross product

The cross product is defined only in $\mathbb{R}^3$.

For

$$
\mathbf{a} = (a_1, a_2, a_3), \quad
\mathbf{b} = (b_1, b_2, b_3)
$$

we define

$$
\mathbf{a} \times \mathbf{b} =
\left(
a_2 b_3 - a_3 b_2,\;
a_3 b_1 - a_1 b_3,\;
a_1 b_2 - a_2 b_1
\right)
$$

Geometric meaning:

- $\mathbf{a} \times \mathbf{b}$ is orthogonal to both $\mathbf{a}$ and $\mathbf{b}$
- its magnitude is

$$
\|\mathbf{a} \times \mathbf{b}\| = \|\mathbf{a}\| \|\mathbf{b}\| \sin \theta
$$

# Use Cases

## Length of a vector

The Euclidean norm is computed through the dot product:

$$
\|\mathbf{a}\| = \sqrt{\mathbf{a} \cdot \mathbf{a}}
$$

For $\mathbf{a} = (a_1, a_2, \ldots, a_n)$ this becomes

$$
\|\mathbf{a}\| = \sqrt{a_1^2 + a_2^2 + \cdots + a_n^2}
$$

## Angle between vectors

From the geometric formula for the dot product:

$$
\cos \theta = \frac{\mathbf{a} \cdot \mathbf{b}}{\|\mathbf{a}\| \|\mathbf{b}\|}
$$

This is useful for checking whether vectors are:

- parallel
- orthogonal
- close in direction

## Area of a parallelogram

If two sides of a parallelogram are $\mathbf{a}$ and $\mathbf{b}$, then its area is

$$
\|\mathbf{a} \times \mathbf{b}\|
$$

The area of the triangle built on the same two vectors is

$$
\frac{1}{2} \|\mathbf{a} \times \mathbf{b}\|
$$

# Code

```python
import numpy as np

a = np.array([1.0, 2.0, 3.0])
b = np.array([4.0, 5.0, 6.0])

a_plus_b = a + b
scaled = 2.0 * a
dot = np.dot(a, b)
cross = np.cross(a, b)
norm_a = np.linalg.norm(a)

print("a + b =", a_plus_b)
print("2a =", scaled)
print("a . b =", dot)
print("a x b =", cross)
print("||a|| =", norm_a)
````

# Problems

## Problem 1

Compute the dot product of

$$
\mathbf{a} = (1, 2, 3), \quad \mathbf{b} = (4, -1, 2)
$$

<details>
<summary>Solution</summary>

We use the coordinate formula for the dot product:

$$
\mathbf{a} \cdot \mathbf{b} = a_1 b_1 + a_2 b_2 + a_3 b_3
$$

Substitute the coordinates:

$$
\mathbf{a} \cdot \mathbf{b} = 1 \cdot 4 + 2 \cdot (-1) + 3 \cdot 2
$$

Now compute each term:

$$
1 \cdot 4 = 4
$$

$$
2 \cdot (-1) = -2
$$

$$
3 \cdot 2 = 6
$$

Add them together:

$$
4 + (-2) + 6 = 8
$$

Therefore,

$$
\mathbf{a} \cdot \mathbf{b} = 8
$$

Python check:

```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([4, -1, 2])

print(np.dot(a, b))
```

Output:

```python
8
```

</details>

## Problem 2

Find the angle between

$$
\mathbf{a} = (1, 0, 0), \quad \mathbf{b} = (1, 1, 0)
$$

<details>
<summary>Solution</summary>

We use the formula

$$
\cos \theta = \frac{\mathbf{a} \cdot \mathbf{b}}{|\mathbf{a}| |\mathbf{b}|}
$$

Step 1. Compute the dot product.

$$
\mathbf{a} \cdot \mathbf{b} = 1 \cdot 1 + 0 \cdot 1 + 0 \cdot 0 = 1
$$

Step 2. Compute the norm of $\mathbf{a}$.

$$
|\mathbf{a}| = \sqrt{1^2 + 0^2 + 0^2} = \sqrt{1} = 1
$$

Step 3. Compute the norm of $\mathbf{b}$.

$$
|\mathbf{b}| = \sqrt{1^2 + 1^2 + 0^2} = \sqrt{2}
$$

Step 4. Substitute into the cosine formula.

$$
\cos \theta = \frac{1}{1 \cdot \sqrt{2}} = \frac{1}{\sqrt{2}}
$$

Step 5. Recover the angle.

$$
\theta = \arccos \left( \frac{1}{\sqrt{2}} \right)
$$

This is the standard value

$$
\theta = 45^\circ
$$

or in radians

$$
\theta = \frac{\pi}{4}
$$

Python check:

```python
import numpy as np

a = np.array([1.0, 0.0, 0.0])
b = np.array([1.0, 1.0, 0.0])

dot = np.dot(a, b)
norm_a = np.linalg.norm(a)
norm_b = np.linalg.norm(b)

cos_theta = dot / (norm_a * norm_b)
theta_rad = np.arccos(cos_theta)
theta_deg = np.degrees(theta_rad)

print("cos(theta) =", cos_theta)
print("theta in radians =", theta_rad)
print("theta in degrees =", theta_deg)
```

Expected output:

```python
cos(theta) = 0.7071067811865475
theta in radians = 0.7853981633974484
theta in degrees = 45.0
```

</details>

## Problem 3

Compute

$$
\mathbf{a} \times \mathbf{b}
$$

for

$$
\mathbf{a} = (1, 0, 0), \quad \mathbf{b} = (0, 1, 0)
$$

<details>
<summary>Solution</summary>

We use the coordinate formula for the cross product:

$$
\mathbf{a} \times \mathbf{b} =
\left(
a_2 b_3 - a_3 b_2,;
a_3 b_1 - a_1 b_3,;
a_1 b_2 - a_2 b_1
\right)
$$

For

$$
\mathbf{a} = (1, 0, 0), \quad \mathbf{b} = (0, 1, 0)
$$

we have

$$
a_1 = 1, ; a_2 = 0, ; a_3 = 0
$$

$$
b_1 = 0, ; b_2 = 1, ; b_3 = 0
$$

Now compute each coordinate separately.

First coordinate:

$$
a_2 b_3 - a_3 b_2 = 0 \cdot 0 - 0 \cdot 1 = 0
$$

Second coordinate:

$$
a_3 b_1 - a_1 b_3 = 0 \cdot 0 - 1 \cdot 0 = 0
$$

Third coordinate:

$$
a_1 b_2 - a_2 b_1 = 1 \cdot 1 - 0 \cdot 0 = 1
$$

So,

$$
\mathbf{a} \times \mathbf{b} = (0, 0, 1)
$$

Interpretation:

* the result is orthogonal to both input vectors
* the vectors $\mathbf{a}$ and $\mathbf{b}$ span the xy-plane
* therefore the cross product points along the z-axis

Python check:

```python
import numpy as np

a = np.array([1, 0, 0])
b = np.array([0, 1, 0])

print(np.cross(a, b))
```

Output:

```python
[0 0 1]
```

</details>

# Connections

## Prerequisites

* [[vectors/linear-combinations]]

## Next

* [[vectors/dot-product]]
* [[vectors/cross-product]]

## Used in

* [[geometry/lines]]
* [[geometry/planes]]
* [[projections/orthogonal-projection]]
* [[robotics/kinematics]]
