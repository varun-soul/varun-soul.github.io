
# Slicing spacetime :

We have our space-time defined as a 4D manifold with a metric $(M, g _{ab})$. We want to slice it into 3D hypersurfaces which are (locally) level surfaces of a scalar function $t$ which acts like the **global time**.
These slices will then be completely space-like.

<center>
![My Image](/images/slices.png)
</center>



## Unit normal vector :

We start out by defining the one-form :

$$
\Omega _{a} = \nabla _{a} t
$$

By definition, the above one-form is closed, i.e, $\nabla _{[a}\Omega _{b]} = 0$ . The metric allows us to compute the norm of this one-form :

$$
g^{ab} \Omega _{a} \Omega _{b} = \frac{1}{\alpha^2}
$$

Here $\alpha$ is something called the **lapse function** and it measures how much proper time elapses between neighbouring time slices. We always assume it to be positive such that our one-form is time-like.

The normalised one-form is given by $\omega_a = \alpha \Omega_a$ . Now we can define the **unit normal** to the slices as :

$$
n^a = -g^{ab}\omega _{b}
$$

The negative sign exists so that $n^a$ points in direction of increasing $t$. This can easily be checked by computing :

$$
n^a \nabla _{a} t > 0
$$

Since $\nabla _a t$ is the gradient and will always point in direction of increasing time, a positive inner product (dot product) with $n _a$ will mean that $n _a$ will also be pointing towards increasing time.

## Spatial metric :

We construct the spatial metric $\gamma_{ab}$ which is defined as :

$$
\gamma _{ab} = g _{ab} + n _{a} n _{b}
$$

The intuition behind this can be thought of as $g _{ab}$ calculating the spacetime distance while $n _{a} n _{b}$ kills off the time-like contribution.

The spatial metric as the name suggests is purely spatial. This can be seen by contracting it with the unit normal vector :

$$
n^a \gamma _{ab} = n^a g _{ab} + n^a n _{a} n _{b} = n _{b} - n _{b} = 0
$$

## Decomposing Tensors :


