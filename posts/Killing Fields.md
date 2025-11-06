# Killing Fields :

I know — it sounds pretty barbaric, right? The name might conjure up images of blood and destruction, but for us, a *Killing field* is quite the opposite. It’s not a destroyer, but a preserver. Before we get into what that means, let’s first build some of the mathematical groundwork we’ll need.

## Pushforwards :

We often deal with smooth maps between two manifolds of interest, $M$ and $N$. Such maps allow us to carry vector and tensor fields from one manifold to another. For a smooth map $\phi : M \rightarrow N$, we define something called the **pushforward** of $\phi$ as the map:

$$
\phi _* : TM \to TN \implies \phi _*: X \to \phi _*(X)
$$

where $X$ is a vector defined at some point $p$ on $M$, and $\phi _*(X)$ is a vector at the corresponding point $\phi(p)$ on $N$.

The pushforward is defined such that:

$$
\phi _*(X)f = X(f \circ \phi)
$$

This expresses how a vector acts on a function after being “pushed forward” by the map $\phi$.

## Pushforwards in a chart :

To make this concrete, let’s consider a chart $(U, x)$ on $M$ and a chart $(V, y)$ on $N$. At some point $p \in U \subset M$, consider the chart-induced basis vector:

$$
\bigg(\frac{\partial}{\partial x^i}\bigg) _{p}
$$

We will now push this vector forward into $N$, where it lies under the chart $(V, y)$. The components of this pushed-forward vector can be written as:

$$
dy^\mu \bigg(\phi _* \bigg(\frac{\partial}{\partial x^\nu}\bigg) _{p} \ \bigg) = \phi _* \bigg(\frac{\partial}{\partial x^\nu}\bigg) _{p} (y^\mu)
$$

Using our definition of a pushforward, we then obtain:

$$
\frac{\partial (y \circ \phi)^\mu}{\partial x^\nu} = \frac{\partial y^\mu}{\partial x^\nu}
$$

Here $\mu$ ranges over the dimensions of $N$, and $\nu$ ranges over those of $M$. This expression closely resembles the tensor transformation law and indeed, the pushforward is a generalization of it.

## Pullbacks :

Opposite to pushforwards, we have the concept of the **pullback**. You might imagine it as the reverse process and that’s partially correct. A pullback takes a covector from the target manifold of the smooth map $\phi$ and pulls it back to the domain manifold. It is defined as:

$$
\phi ^* : T^ *N \to T^ *M \ \implies \omega \to \phi ^ *(\omega)
$$

The pullback $\phi ^ * (\omega)$ acts on a vector $X \in TM$ as follows:

$$
\phi ^* (\omega)(X) = \omega(\phi _*(X))
$$

Essentially, it lets us compare or “transport” covectors through the map $\phi$ in a way consistent with how vectors are pushed forward.

## Pullbacks in charts :

I’ll leave the explicit computation as a short exercise since it closely follows the steps for the pushforward. Interestingly, the numerical form of both pushforwards and pullbacks turns out to be the same:

$$
\frac{\partial y^\mu}{\partial x^ \nu}
$$

The distinction lies in which index is being contracted — a subtle but important difference.

## Pushing and Pulling Tensors :

In general, an object that has been pushed forward cannot be pulled back using the same map, and vice versa. For tensors, this means we cannot freely push or pull mixed tensors. These operations are well-defined only for purely covariant $(0, k)$ or contravariant $(k, 0)$ tensors.

For instance, consider a $(0, k)$ covariant tensor $T$ that maps $k$ vectors to a real number. Its pullback is defined as:

$$
\phi ^ * T(V^{(1)}, \dots, V^{(k)}) = T(\phi _ * V^{(1)}, \dots, \phi _* V^{(k)})
$$

Similarly, for a $(k, 0)$ contravariant tensor $S$ that maps $k$ covectors to a real number, the pushforward is:

$$
\phi _* S(\omega _{(1)}, \dots, \omega _{(k)}) = S(\phi ^* \omega _{(1)}, \dots, \phi ^* \omega _{(k)})
$$

In component form, both resemble the familiar tensor transformation laws:

$$
(\phi ^* T) _ {\mu _{1}, \dots, \mu _{k}} = \frac{\partial y^{\alpha _{1}}}{\partial x^{\mu _{1}}} \dots \frac{\partial y^{\alpha _{k}}}{\partial x^{\mu _{k}}} T _{\alpha _{1} \dots \alpha _{k}}
$$

$$
(\phi _*S)^{\alpha _{1} \dots \alpha _{k}} = \frac{\partial y^{\alpha _{1}}}{\partial x^{\mu _{1}}} \dots \frac{\partial y^{\alpha _{k}}}{\partial x^{\mu _{k}}} S^{\mu _{1}, \dots, \mu _{k}}
$$

## Diffeomorphisms :

Now that we understand pushforwards and pullbacks, we can move on to an important class of maps called **diffeomorphisms**.

Consider two manifolds $M$ and $N$, with a smooth map $\phi$ between them. A diffeomorphism is a map $\phi$ that has an inverse which is also smooth. 

But what does this mean intuitively?

Think of a spherical surface and the surface of a potato. Surprisingly, these two shapes can be connected by a diffeomorphism — meaning they are *diffeomorphic*. On the level of manifolds, they represent the same underlying structure, just smoothly deformed.

A key advantage of diffeomorphisms is that we can now pull back something that we had previously pushed forward. Since $\phi$ is invertible and its inverse is also smooth, the operations of pushing and pulling become reversible.

If we take the diffeomorphism $\phi : M \to N$, and push a vector on $M$ forward to $N$ using $\phi _ * $, we can then pull it back using the inverse map $(\phi^{-1}) ^* $. The same reasoning applies to covectors as well.

Most importantly, diffeomorphisms allow us to handle **mixed-rank tensors** consistently. The pushforward of a tensor $T$ of rank $(r, s)$ is now well-defined and given by:

$$
\phi _ * T(\omega_{(1)}, \ldots, \omega _{(r)}, V^{(1)}, \ldots, V^{(s)})
= T\big( \phi ^* \omega _{(1)}, \ldots, \phi ^* \omega _{(r)}, \phi _*^{-1} V^{(1)}, \ldots, \phi _*^{-1} V^{(s)} \big)
$$

## Self-Diffeomorphisms :

Finally, what happens when a diffeomorphism maps a manifold to itself — a **self-diffeomorphism**?

Such a transformation smoothly rearranges points on the manifold without changing its intrinsic structure. You can think of it as a gentle reshaping of the manifold that neither tears nor glues it, nor introduces anything new.

Consider the following illustration:

<img width="696" height="331" alt="image" src="https://github.com/user-attachments/assets/9f0b0ee4-055d-45f6-8bd0-b0ceea263c6f" />


Here, we have a flat surface representing our manifold $M$. A diffeomorphism to itself preserves the structure but shifts the points. The plane has been smoothly deformed — no tearing, gluing, or addition of new points.

Another simple example is a rotation of a 2-sphere. This is also a self-diffeomorphism, as every point moves smoothly while preserving the sphere’s overall structure.

## Comparing Tensors using Diffeomorphisms :

(Section to be expanded — here you can discuss how diffeomorphisms let us compare tensor fields defined at different points on the same manifold.)
