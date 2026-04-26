---
layout: post
title: "questioning the lagrangian"
date: 2026-04-24
tags: [physics]
---

## "I don't know anything, but I do know that everything is interesting if you go into it deeply enough." - Richard Feynman

##### This post assumes some basic knowledge of Lagrangian mechanics. If you don't feel like that's you, [this Veritasium video](https://www.youtube.com/watch?v=Q10_srZ-pbs) is essentially all the context you need. Additionally, you can always skip terminology/math-heavy sections for clarity.

Why is the Lagrangian equal to $$T-V$$?

When I was a freshman in high school and first learning about the Lagrangian, I did briefly wonder why it was equal to $$T-V$$, but paid very little mind to it. Lately, however, I thought about it a little more after struggling with some basic problems and ragequitting. Doing a little digging uncovered a brief proof from Landau & Lifschitz. I was unsatisfied with it, however, and after some collaboration with friends, we devised a 'proof' of why the Lagrangian is more or less constrained to some specific boundaries. Such questions in a field commonly regarded as dead such as physics is highly important, which is why I curled a lip witnessing a teacher answer the question with a dismissive "because the laws of nature dictate it so." It is like saying Basel's Theorem appears because God willed it to be, paying no mind to mathematical beauty and induction. If ever that were true, it is but a half-truth. Sans intellectual curiosity, all that scientists have is pretty much just the revision and confirmation of old ideas, never the challenging of paradigms in Galileo, Newton, Einstein. But enough rambling.

### Assumptions

Some fairly standard axioms will be needed:

- the laws of physics are the same in every inertial reference frame

- the laws of motion are second-order in time
  
- free space is homogenous in space and time

It is not so explicitly clear why all of these must be true. For one, why must the laws of motion be second-order in time? Why not first-order, or third-order? It's simpler to use second-order dynamics, and you could argue anthropically for the environment around us to not be encouraging first-order dynamics (not much would move it all, but rather just be in equilibrium) and third-order dynamics (highly chaotic universe probably couldn't support human life), but naturally this is mostly speculatory. Beyond me is the thought that a given object with some position x and velocity y will not follow the same trajectory that another given object with some position x and velocity y due to some third-order variable. With all that in mind, we must take the same leap as Hoyle and confirm that indeed, we live in a universe where the laws of motion are second-order in time. A perfect machine throwing baseballs will throw from the same position and have the same velocity of throwing, and the baseballs do in fact follow the same trajectory. Moreover, each human throw has some variability, so objects can exist in different positions with different velocities as well.

As one might've learned in a relativity class, the laws of physics are the same according to every observer moving with constant velocity to each other. Such inertial (they are not accelerating with respect to the other) observers will always observe the same accleration of every point in space as the other. Their velocity is moot in terms of acceleration. This concept is otherwise known as *Galilean relativity* and actually ties back to the aforementioned assumption; the laws of physics will certainly, definitively give you the acceleration of a set of objects. From this we can derive that two observers moving with constant velocity respectively to one another will indeed have the same laws of physics applied on them.

Lastly, it is fairly intuitive to grasp that our universe has free space (I never enjoyed the term 'free' in this context but I digress). Free space is essentially just the definition of empty space; nothing changes through time, nor through physical movement. Moving 30 kilometers southwest will not yield a different sort of space, just a different location. While again, this isn't something that is necessarily true a priori, it would certainly be a universe we are unused to if it had some preconditioned direction of choice. Wouldn't it be weird if all objects suddenly accelerated towards the direction of Earth's magnetic north?

Regardless, without higher-order math or knowledge, I am more or less forced to also accept Hamilton's principle of least action and the Euler-Lagrange equations of motion as true. Aliens might know how to prove certain things with just the axioms provided, but there is no meaningful way human reasoning could extend the Lagrangian without the Euler-Lagrange equations. As a reminder, the Euler-Lagrange equations:

$$\frac{\partial L}{\partial q} = \frac{d}{dt}\left(\frac{\partial L}{\partial \dot{q}}\right)$$

where $\boldsymbol{L(q, \dot{q}, t)}$ is the Lagrangian, and $\boldsymbol{q}$ are coordinates that describe the system, and $\boldsymbol{\dot{q}}$ the time derivatives of those coordinates. Most often, $\boldsymbol{q}$ are just the spatial coordinate $\boldsymbol{x}$ and $\boldsymbol{\dot{q}}$, the time derivatives, the spatial velocity, $\boldsymbol{v}$.

We can generally infer, along with the two assumptions above, that the Lagrangian is the generator of the physical laws of motion, through the Euler-Lagrange equations. This set of axioms somehow must uniquely define the equations of motion for a system, and any properties of such equations will be encoded in that Lagrangian.

It is important to emphasize that going forward, we know nothing else about what the Lagrangian for a general system ought to look like. We know neither of kinetic nor potential energy. In fact, the concept of energy is foreign to us. Newton's laws? Never heard of them. There exists a function $\boldsymbol{L}$ called the Lagrangian such that it is the integrand within Hamilton's action. Besides this, all we know are the descriptions of the universe we can infer from our base assumptions. From just those things then, what can we say about the Lagrangian? About energy?

### The general Lagrangian

##### There is a lot of math here; this is already simplified by assuming there is only one spatial dimension to clean the algebra. To conclude an even more accurate result, allow $x$ and $v$ to be vectors.

As with all complex problems, let's begin with a simpler one as a stepping stone to our rather scary task of tackling a general form of the Lagrangian:

The homogeneity of free space implies that there is no real dependence of the function $\boldsymbol{L}$, when we're in free space. Otherwise, since the Lagrangian determines the equations of motion, we would get different equations of motion at different points in space and time⁴. Hence:

$$L(x, v, t) = L(v)$$

The equations of motion should be unchanged in all inertial reference frames according to our earlier axioms. For this to hold true generally, it means that the process of extremizing the action must not be changed by the Galilean into the other reference frame. This means that our state function can only change by a total time derivative (since this would at most add a constant to the action), hence:

$$x' = x - ut$$
$$v' = v - u$$
$$t' = t \qquad L'(x', v', t') = L(x, v, t) + \frac{dG(x, v, t;\, u)}{dt}$$

Plugging in the fact that $\boldsymbol{L}$ is just a function of $\boldsymbol{v}$, and expanding the total time derivative of $\boldsymbol{G}$, we get:

$$L(v - u) - L(v) = v\frac{\partial G}{\partial x} + \dot{v}\frac{\partial G}{\partial v} + \frac{\partial G}{\partial t}$$

LHS is only a function of $\boldsymbol{v}$, hence $\frac{\partial G}{\partial v}$ must be zero, and thus $\boldsymbol{G = G(x, t)}$. Then, we observe that RHS is at most linear in $\boldsymbol{v}$, due to the $v\frac{\partial G}{\partial x}$ term. Everything else is constant in $\boldsymbol{v}$, since $\boldsymbol{G}$ is not a function of $\boldsymbol{v}$. Thus, we get:

$$L(v - u) - L(v) = \alpha v + \beta$$

Where $\boldsymbol{\alpha}$ and $\boldsymbol{\beta}$ must be constants, since LHS only depends on $\boldsymbol{v}$. This is a functional equation for $\boldsymbol{L(v)}$, whose general solution is the quadratic. Thus, we conclude that the free state function is:

$$L_{\text{free}}(v) = \alpha v^2 + \beta v + \gamma$$

where the constant term $\boldsymbol{\gamma}$ is unimportant to the physics, since we only deal with derivative of the Lagrangian to determine the equations of motion.

### The general Lagrangian

By the same argument as above, we find that the general Lagrangian $\boldsymbol{L}$ must also be at most quadratic in $\boldsymbol{v}$ (since $\boldsymbol{G}$ is still at most linear in $\boldsymbol{v}$). This gives a general expression for $\boldsymbol{L}$ as:

$$L(x, v, t) = A(x, t)v^2 + B(x, t)v + C(x, t)$$

To further constrain the state function, we will apply our relativity constraint again. We boost the state function into an inertial frame of relativity velocity $\boldsymbol{u}$, and demand that the state function change by only a total time derivative:

$$L(x', v', t') - L(x, v, t) = \frac{dG(x, t)}{dt}$$

$$[A(x, t) - A(x', t')]v^2 + [B(x', t) - B(x, t)]v + C(x', t) - C(x, t) = v\frac{\partial G}{\partial x} + \frac{\partial G}{\partial t}$$

---

The $\boldsymbol{v^2}$ dependence in LHS must be zero for all $\boldsymbol{u}$, hence $\boldsymbol{A}$ can't have any spatial dependence. The same argument goes for simple time translations, and hence $\boldsymbol{A(x, t) = \text{const}}$. Thus, we arrive at our final, most general expression for our state function, having applied our constraints to the fullest extent we have:

$$L = \alpha v^2 + B(x, t)v + C(x, t)$$

In traditional physics, we identify (for a single-body Lagrangian) the constant $\boldsymbol{\alpha}$ as one half of the mass of the body, $\boldsymbol{C(x, t)}$ as the negative of the potential energy, and $\boldsymbol{B(x, t)}$ being a term that only comes up when dealing with magnetic fields, the details of which we won't linger on here.

## So what?

$$L = \alpha v^2 + B(x, t)v + C(x, t)$$

This is the most general form of a Lagrangian that we can have, given our fairly minimal symmetry constraints at the start. It's worth noting that this is quite an exceptional amount of constraint on the Lagrangian. Before applying our conditions for certain symmetries, there was no limit to what the Lagrangian could look like. Exponentials, fraction, square roots, trigonometric functions. All of these were fair game. Turns out that we are, at least in $\boldsymbol{v}$, limited to a second-order polynomial. Of course, we're hiding some structure in our $\boldsymbol{A}$ and $\boldsymbol{B}$ functions, which currently could be arbitrary functions (although we will likely demand smoothness at some point down the line). I plan to dedicate a second post to the constraints that we can place on these functions, from further symmetry arguments.

And so, in the absence of magnetic fields, the Lagrangian becomes:

$$L = \alpha v^2 + C(x, t)$$

where we usually identify $\boldsymbol{\alpha}$ and $\boldsymbol{C}$ with $\frac{1}{2}m$ and negative $\boldsymbol{V}$ respectively, such that we get:

$$L = T - V$$

where $\boldsymbol{T} = \frac{1}{2}mv^2$ is the kinetic energy and $\boldsymbol{V}$ the potential energy of the body.
___

Remark:
