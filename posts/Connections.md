# An Intuitive Intro to Connections :3

During my General Relativity classes this semester, one of the topics that I noticed people were confused by was the idea of a "connection" or "christoffel symbols". So I decided to write this short post hoping to clear up any confusion that might occur in to those who come behind us :3

## A thought experiment :

We live on a giant curved ball hurtling through space at thousands of miles per hour. An absurd notion — yet true. Still, in our everyday lives, none of this really matters. When we walk from one street to another, we treat the Earth as flat, and for such small journeys, that’s perfectly fine. But as we zoom out and look at the bigger picture, the truth of our curved world becomes impossible to ignore.

Imagine yourself as an explorer standing at the **North Pole**, arm stretched out and pointing straight in some direction of your choice. Having grown weary of the endless snow, you decide to head toward the **equator** — all the while keeping your arm fixed in that same direction.

Once at the equator, you enjoy the warmth and begin walking **along** it, still keeping your arm pointed the same way (you must have incredibly strong arms). Eventually, you decide to return to the **North Pole**. After a long and tiring journey, you arrive — only to be stunned. Even though you never deliberately changed the direction of your arm, it’s now pointing somewhere completely different from where you started.

<center>
![My Image](/images/conn_draw.png)
</center>

Somehow, the **intrinsic curvature of the Earth** itself has altered your arm’s orientation. Your arm, which was a stand-in for a vector has changed its directions as it was transported parallel to itself across a curved space. 

This is exactly what a **connection** encodes. The **connection** is defined as a set of rules for defining how a vector changes as you move it from one point to another. It defines how two tangent spaces are "connected" to each other. In fact, defining a connection on a manifold is akin to giving shape to it.

## Covariant Derivative :

Now it is time to look at the mathematical machinery behind a connection and we thus arrive at something known as the covariant derivative. The **connection** and **covariant derivative** are essentially two sides of the same coin. The connection is the set of rules and the covariant derivative is what you do with those set of rules.

It essentially tells us how some vector / tensor field  would change if we transport it an infinitesimal distance along some other vector field. It is a generalised directional derivative operator for vector and tensor fields.  

Why fields? Well vectors  and tensors are objects defined at  a point and if you are trying to take a directional derivative of some quantity, it is required for it to be defined at more than one point :3

Formally, we define a covariant derivative as follows :

The covariant derivative $\nabla$ on a smooth manifold $M$ is a map that takes a pair consisting of a vector field $X$ and a $(r,s)$ tensor field $T$ and sends them to another $(r,s)$ tensor field $\nabla _{X} T$. It satisfies the following properties, where $f$ is a scalar field, $X$ is a vector field and $T$ and $S$ are $(r,s)$ tensor fields :
  
- **Action on Scalar** : $\nabla _{X} f =  X(f)$
- $\nabla _X(T+S) = \nabla _{X} T + \nabla _{X}S$
- **Leibniz Rule** :  $\nabla _X (T  \otimes S) = \nabla _X T \otimes S + T \otimes \nabla _X S$
- **f-linearity in vector field** : $\nabla _{f \cdot X + Y} T = f \cdot \nabla _X T + \nabla _Y T$

<br>
Do note that it is not necessary that $X$ be a vector field. It can just be a vector and in that case your result will only be defined at that point.
