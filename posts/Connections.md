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

<div class="nice-list">
  <ol>
    <li><strong>Action on Scalar</strong> : $\nabla _{X} f =  X(f)$</li>
    <li>$\nabla _X(T+S) = \nabla _{X} T + \nabla _{X}S$</li>
    <li><strong>Leibniz Rule</strong> : $\nabla _X (T  \otimes S) = \nabla _X T \otimes S + T \otimes \nabla _X S$</li>
    <li><strong>f-linearity in vector field</strong> : $\nabla _{f \cdot X + Y} T = f \cdot \nabla _X T + \nabla _Y T$</li>
  </ol>
</div>

Do note that it is not necessary that $X$ be a vector field. It can just be a vector and in that case your result will only be defined at that point.

## Christoffel Symbols :
I may have defined a covariant derivative, but till now its just fancy symbols. I haven't really talked about how a covariant derivative looks like in action and that is exactly what we'll look at now.

Consider the vector fields $X = X^j \partial _{j}$ and $Y = Y^i \partial _i$ where $X^j$ and $Y^i$ are the components and $\partial _j$ and $\partial _i$ are the basis vectors. Now we will begin by computing $\nabla _X Y$ :

$$
\nabla _{X} Y = \nabla _{(X^j \partial_{j})} \ (Y^i \partial _{i}) = X^j \nabla _{\partial _{j}} (Y^i \partial_{i})
$$

Applying the chain rule, we end up with:

$$
X^j \bigg[(\nabla _{\partial _{j}} Y^i) \partial _{i} + Y^i (\nabla _{\partial _{j}} \partial _{i} )\bigg]
$$

As is evident, the last term is quite problematic because we have no idea how to solve for it. But what we do know is that the result will always be a vector field. This motivates us to express this covariant derivative in terms of the basis vectors themselves, where we introduce a new set of functions $\Gamma^m _{ij}$ :

$$
\nabla _{\partial _{j}} \partial _{i} = \Gamma^m _{ij} \ \partial _{m}
$$

Substituting the above into our previous equations gives us :

$$
X^j \bigg[(\partial _{j} Y^i) \partial _{i} + (Y^i \Gamma^m _{ij}) \partial _{m}\bigg]
$$

We can write this in a simpler fashion by renaming some of the summed-over indices :

$$
\bigg[X(Y^i) + X^kY^j \Gamma^i _{jk} \bigg] \partial _{i}
$$

Those confused by the first term in the above expression, since $Y^i$ is a scalar field, you can expand the term and get back our old expression :3

So in the end we have :

$$
(\nabla _{X} Y)^i = X(Y^i) + X^kY^j \Gamma^i _{jk} 
$$

Now its time to address the elephant in the room... $\Gamma ^i _{jk}$ . 

These components are called the **connection coefficient functions** of the connection and they capture how a basis vector $j$ changes along $k$ in the $i^{th}$ direction. 

And if they look familiar, then yes these are intimately related with the **christoffel symbols** we use in General Relativity. In fact, the christoffel symbols are the connection coefficient functions of a particular type of connection, known as the **Levi-Civita Connection**.  What we're discussing here, however, is a much more general notion of a connection that isn't necessarily tied to any particular metric.

It’s crucial to remember that these connection coefficients are **coordinate-dependent** quantities. Their values depend on the coordinate system we choose, and their presence doesn’t necessarily mean that the manifold itself is curved. For example, we can describe flat Euclidean space using spherical coordinates, a coordinate system where the basis vectors change from point to point. In that case, the connection coefficients will be nonzero even though the underlying space is perfectly flat. 

