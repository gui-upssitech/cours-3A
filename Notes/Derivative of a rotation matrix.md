Tags: #humanoid-robotics 

Calculating the derivative of a rotation matrix with respect to time or some other parameter involves some advanced mathematics, particularly the use of calculus and differential geometry. Let's assume we have a 3x3 rotation matrix, typically denoted as $R$, that represents a rotation in three-dimensional space. To find its derivative, we need to compute the time derivative of each element in the matrix.

To do this, we'll use the angular velocity vector, $\omega$, which describes the rate of change of the orientation of the coordinate system. The derivative of the rotation matrix $R$ with respect to time ($t$) is given by the following equation:
$$
\dot{R}(t) = R(t) \times S(\omega(t))
$$
In this equation:

- $R$ is the 3x3 rotation matrix.
- $\omega$ is the 3x1 angular velocity vector (can be noted $\omega = a \times \dot{q}$ ).
- $S(\omega)$ is the skew-symmetric matrix derived from ω.

![[Pasted image 20231023172349.png]]

So, to calculate the derivative of the rotation matrix $R$ with respect to time, you need to:

1. Determine the angular velocity vector $\omega$, which describes how the rotation is changing.
2. Construct the skew-symmetric matrix $S(\omega)$.
3. Multiply the rotation matrix $R$ by $S(\omega)$ to get the derivative $\dot{R}$.
