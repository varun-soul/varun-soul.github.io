
## Slicing spacetime :

We assume that our spacetime $(M, g _{ab})$ can be foliated into a family of non-intersecting spacelike three-surfaces $\Sigma$, which locally arise as the **level surfaces of a scalar function t**, that can be interpreted as the global time function.

<center>
![My Image](/images/slices.png)
</center>

## Unit normal vector :

### Defining the one-form :
 We start out by defining the one-form :
 
$$
\Omega _{a} = \nabla _{a} t
$$

This is basically the gradient of the global time function and we know that the gradient is always perpendicular to the level surfaces of the function.

This **one-form is closed by construction**. This can be readily seen below :

$$
\nabla _{[a}\Omega _{b]} = \nabla _{a} \Omega _{b} - \nabla _{b} \Omega _{a}
$$

Computing $\nabla _{a} \Omega _{b}$ gives us the following :

$$
\nabla _{a} \Omega _{b} = \partial _{a} \Omega _{b} - \Gamma^m _{ab} \Omega _{m}
$$

where $\Omega _b = \partial _b t$. 

$$
\nabla _{a} \Omega _{b} = \partial _{a} \partial _{b}t - \Gamma^m _{ab} \partial _{m} t
$$

Switching $a$ and $b$ will give you the same result back since partial derivatives commute and the Christoffel symbol is symmetric due to us using the levi-civita connection. This the result will be zero. Hence proved.

### The norm / lapse function :
The **norm of the one form** is defined as follows :

$$
g^{ab} \Omega _{a} \Omega _{b} = -\frac{1}{\alpha^2}
$$

Here $\alpha$ is something called the **lapse function** and it measures how much proper time elapses between neighbouring time slices along the normal vector $\Omega ^a$. We always assume $\alpha$ > 0.

### The unit normal :
The normalised one-form is given by $\omega _a = \alpha \Omega _a$ . Now we can define the **unit normal** to the slices as :

$$
n^a = -g^{ab}\omega _{b}
$$

The negative sign exists so that $n^a$ points in direction of increasing $t$. From what I've been able to understand, raising the indices using a signature $(- +++)$ means that we flip the sign of the time-like component. Hence we had an extra negative sign to flip it back (?)

**Doubt** : What decides future pointing and past pointing?

By construction, $n^a$ is as follows :

$$
n^a n_{a} = -1
$$

So you can consider it to be the 4-velocity of an observer whose worldline is always normal to the spacelike hypersurfaces. 

## Spatial metric :

We construct the spatial metric $\gamma _{ab}$ which is defined as :

$$
\gamma _{ab} = g _{ab} + n _{a} n _{b}
$$

The intuition behind this can be thought of as $g _{ab}$ calculating the spacetime distance while $n _{a} n _{b}$ kills off the time-like contribution. 

Consider a vector $V^a$ which we write as:

$$
V^a = S^a + Cn^a
$$ 

Here we have divided it into a spatial part and a purely time-like part. Lets see what the action of the induced metric will be on this vector.

$$
\gamma _{ab}(S^a + Cn^a)(S^b + Cn^b) = (g _{ab} + n _{a} n _{b})(S^a + Cn^a)(S^b + Cn^b)
$$

Considering that $S^a$ and $n^a$ are orthogonal to each other, we can easily see that the above reduces to :

$$
\gamma _{ab}V^aV^b = \gamma _{ab}S^a S^b = g _{ab}S^aS^b
$$

So in essence, the induced metric acts as a sort of (not really) **projection operator** which kills off the time component of any vector entered into it. Also, it is a 4-tensor which is purely spatial (it is orthogonal to $n^a$).

## Decomposing Tensors :

We have decomposed spacetime into spatial slices, but we also need to do the same with the tensors defined on it.

### Spatial Projector :
Remember when I just said induced metric acts like sort of a projection operator but not really? That is because its a spatial dot product operator. It takes in two vectors and gives a number 

But if we need a proper projection operator, we need to raise one index of induced metric. Now it takes in a vector and gives out a vector which is spatial.

$$
\gamma^a _{b}  = g^{ac}\gamma _{c b} = \delta^a _{b} + n^a n _{b}
$$
To project tensors into the spatial surface, each free index needs to be contracted with the projection operator. 

### Normal Projector :
The normal projection operator is defined as follows:
$$
N^a _{b} = -n^a n _{b} = \delta^a _{b} - \gamma^a _{b}
$$
This too works in ways similar to the spatial projector we defined above.

### 3D Covariant Derivative :
We require a 3D covariant derivative that maps spatial tensors into spatial tensors and we require it to be compatible with the 3 dimensional metric $\gamma _{ab}$. We construct such a derivative by projecting all the indices in a 4D covariant derivative into $\Sigma$.  

Consider the example of a tensor $T^a _b$ :
$$
D _{c} T^a _{b} = \gamma^e _{c}\gamma^f _{b} \gamma^a _{d} \nabla _{e} T^d _{f}
$$
Extension to other types of tensors is quite obvious.

### 3D connection :
We can create a 3D Levi-Civita connection the same way we do normally, except this time we replace the metric with our spatial metric.

$$
\Gamma^a _{bc} = \frac{1}{2}\gamma^{ad}(\partial _c\gamma _{db} + \partial _b\gamma _{dc} - \partial _d\gamma _{bc})
$$

### 3D Riemann Tensor
We can define the 3D Riemann Tensor in the same as we did for 4 dimensions, except this time we use the 3D covariant derivative in its definition :
$$2D _{[a} D _{b]} w _c = R^d{} _{cba} w _d \qquad R^d{} _{cba} n _d = 0$$
In terms of coordinate components, it can be computed as :

$$
R^d{} _{abc} = \partial _b \Gamma^d _{ac} - \partial _c \Gamma^d _{bc} + \Gamma^e _{ac} \Gamma^d _{eb} - \Gamma^e _{bc} \Gamma^d _{ea}
$$

where the $\Gamma$ are the 3D connections. You can contract this tensor to obtain the 3D Ricci tensor and the 3D Ricci scalar as well.
