# Why split spacetime?

_________________________________________________________________________________


We have often heard the term "4D space-time" in Einstein's Relativity. It describes the entire history of the universe, the past, present and future as a single, static object. 

But that is not how we experience reality. We live in a 3D world and experience time (1D) linearly. It is quite natural for us to ask the question : "If I know the state of the universe right now, can I predict how it would look like in the future?".

This is something known as the "Initial Value Problem" or the "Cauchy Problem" and this is precisely the problem that we aim to solve by performing a 3+1 decomposition of our space time.

This isn't just a mathematical exercise. Have you seen all those cool videos of two stars or two black holes merging? Thats the 3+1 formalism in action. Its the engine behind numerical relativity. So how does this engine work?

>Before going into all that, I should probably tell you that the notation being followed is that of Baumgarte's book and can be found in section 2.1.

# Slicing spacetime :

We start out with a 4D spacetime, characterised by a manifold $M$ and the metric $g_{ab}$ . Casting Einstein's equations into a 3+1 form amounts to carving this spacetime up into a stack of 3D "spatial slices".

This process is called **foliation**. We **foliate** spacetime into a family of 3D hypersurfaces, each of which must be space-like (meaning no  two points on it are causally connected). These hypersurfaces are defined as (at least locally) the level surfaces of a scalar function $t$, which then serves as our global time function.

Now that we have a stack of slices, we need a mathematical way to describe the direction between the slices. This is done by defining our unit normal vector. We start out by defining the one-form :

$$
\Omega_{a} = \nabla_{a} t
$$

By definition, the above one-form is closed, i.e, $\nabla_{[a} \Omega_{b]} = 0$ . The metric allows us to compute the norm of this one-form which we write out as $\alpha^{-2}$. Here $\alpha$ is something called the **lapse function** and it measures how much proper time elapses between neighbouring time slices. We always assume it to be positive.

The normalised one-form is given by $\omega_a = \alpha \Omega_a$ . Now we can define the unit normal to the slices as :

$$
n^a = -g^{ab}\omega _{b}
$$

The negative sign exists so that $n^a$ points in direction of increasing $t$. This can easily be checked by computing :

$$
n^a \nabla_{a} t > 0
$$

Thus we have finally defined our **unit normal vector**. Now we would also like to have a way to measure distances between points on our 3D spatial slices. To do that we would like to find the metric induced on the hypersurface by the space-time metric $g_{ab}$ .

Thus we construct the spatial metric $\gamma_{ab}$ which is defined as :

$$
\gamma_{ab} = g_{ab} + n_{a} n_{b}
$$

The intuition behind this can be thought of as $g_{ab}$ calculating the spacetime distance while $n_{a} n_{b}$ kills off the time-like contribution.

So we have essentially finished our slicing of the space-time. But by no means are we done with the 3+1 formalism. We also need to decompose the tensors defined on our space-time manifold into a time-like and space-like part.

The good thing is that we don't need to introduce anything extra. To convert some tensor $T_{ab}$ into its spatial part, we need to only contract its free indices using $\gamma_{c}^a$ as follows :

$$
\gamma^a_{c} \gamma_{d}^b \ T_{ab}
$$

So the spatial projection operator is simply :

$$
\gamma^a_{b} = \delta^a_{b} + n^a n_{b}
$$

Similarly, we can define the Normal or time-like projection operator as :

$$
N^a_{b} = -n^a n_{b} = \delta^a_{b} - \gamma^a_{b}
$$

We can now use these to project any tensor into its spatial or time-like components. 

