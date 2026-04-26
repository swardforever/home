---
layout: post
title: "questioning the lagrangian"
date: 2026-04-24
tags: [physics]
description: "A proof-based exploration of why the Lagrangian must equal T-V, derived from symmetry principles alone."
---

## "I don't know anything, but I do know that everything is interesting if you go into it deeply enough." - Richard Feynman

##### This post assumes some basic knowledge of Lagrangian mechanics. If you don't feel like that's you, [this Veritasium video](https://www.youtube.com/watch?v=Q10_srZ-pbs) is essentially all the context you need. Additionally, you can always skip terminology/math-heavy sections for clarity.

Why is the Lagrangian equal to $$T-V$$?

That is one of the most natural questions a student first encountering the Lagrangian has. Why does it appear the way it does? When I was a freshman in high school and learning about the Lagrangian, I did briefly wonder why it was equal to $$T-V$$ (the potential energy of the body subtracted by the kinetic energy of the body), but paid very little mind to it. Lately, however, I thought about it a little more after struggling with some basic problems and ragequitting. Doing a little digging uncovered a brief proof from Landau & Lifschitz. I was unsatisfied with it, however, and after some collaboration with friends, we devised a 'proof' of why the Lagrangian is more or less constrained to some specific boundaries. Such questions in a field commonly regarded as dead such as physics is highly important, which is why I curled a lip witnessing a teacher answer the question with a dismissive "because the laws of nature dictate it so." It is like saying Basel's Theorem appears because God willed it to be, paying no mind to mathematical beauty and induction. If ever that were true, it is but a half-truth. Sans intellectual curiosity, all that scientists have is pretty much just the revision and confirmation of old ideas, never the challenging of paradigms in Galileo, Newton, Einstein. But enough rambling.

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
$$t' = t \qquad L'(x', v', t')$$

___

$$L(x, v, t) + \frac{dG(x, v, t;\, u)}{dt}$$

Plugging in the fact that $\boldsymbol{L}$ is just a function of $\boldsymbol{v}$ and manipulating the total time derivative of $\boldsymbol{G}$ yields:

$$L(v - u) - L(v) = v\frac{\partial G}{\partial x} + \dot{v}\frac{\partial G}{\partial v} + \frac{\partial G}{\partial t}$$

LHS is only a function of $\boldsymbol{v}$, hence $\frac{\partial G}{\partial v}$ must be zero, and thus $\boldsymbol{G = G(x, t)}$. We may (or at least I was) stuck at first, but then we observe that RHS is at most linear in $\boldsymbol{v}$, due to the $v\frac{\partial G}{\partial x}$ term. Everything else is constant in $\boldsymbol{v}$, since $\boldsymbol{G}$ is not a function of $\boldsymbol{v}$. All that is to imply

$$L(v - u) - L(v) = \alpha v + \beta$$

where $\boldsymbol{\alpha}$ and $\boldsymbol{\beta}$ must be constants, since LHS only depends on $\boldsymbol{v}$. Yippee, wahoo, hooray; this is a functional equation for $\boldsymbol{L(v)}$, whose general solution is the quadratic. At last, we conclude that the free state function is:

$$L_{\text{free}}(v) = \alpha v^2 + \beta v + \gamma$$

where the constant term $\boldsymbol{\gamma}$ is unimportant to the physics, since we only deal with derivative of the Lagrangian to determine the equations of motion. But now, having dealt with the baby version of our problem, we can simply extrapolate the similar ideas. By the same argument as above, we find that the general Lagrangian $\boldsymbol{L}$ must also be at most quadratic in $\boldsymbol{v}$ (since $\boldsymbol{G}$ is still at most linear in $\boldsymbol{v}$). This gives a general expression for $\boldsymbol{L}$ as:

$$L(x, v, t) = A(x, t)v^2 + B(x, t)v + C(x, t)$$

Applying our relativity constraint again will constrain our state function even more. We shift the state function into an inertial frame of relative velocity $\boldsymbol{u}$, and must also therefore demand that the state function change for only a total time derivative.

$$L(x', v', t') - L(x, v, t) = \frac{dG(x, t)}{dt}$$

$$[A(x, t) - A(x', t')]v^2 + [B(x', t) - B(x, t)]v + C(x', t) - C(x, t) = v\frac{\partial G}{\partial x} + \frac{\partial G}{\partial t}$$.

The $\boldsymbol{v^2}$ dependence in LHS must be zero for all $\boldsymbol{u}$, hence $\boldsymbol{A}$ can't have any spatial dependence at all. Now it becomes more clear - the same argument goes for temporal dependence, and hence $\boldsymbol{A(x, t) = \text{const}}$. We can then conclude, with our constraints, our most general expression for our state function (one spatial dimension aside):

$$L = \alpha v^2 + B(x, t)v + C(x, t)$$.

Of course, much of this is drawn on prerequisite knowledge and would've taken much longer than that relatively concise explanation. We identify the constant $\boldsymbol{\alpha}$ as one half of the mass of the body, $\boldsymbol{C(x, t)}$ as the negative of the potential energy, and $\boldsymbol{B(x, t)}$ being a term that we seemingly have not accounted for, but allegedly (from sources beyond my ken) only comes up in discussions related to magnetic fields, meaning it's not my problem to discuss here.

$$L = \alpha v^2 + B(x, t)v + C(x, t)$$ is the most general form of a Lagrangian that we can have, given our fairly minimal symmetry constraints at the start. I should note that this is quite an exceptional amount of constraint on the Lagrangian. Before applying our conditions for certain symmetries, the Lagrangian could look like pretty much anything i.e. square roots, trigonometric functions, exponentiations. Turns out that we are however limited to a second-order polynomial in $\boldsymbol{v}$. And so, in the absence of magnetic fields, the Lagrangian becomes:

$$L = \alpha v^2 + C(x, t)$$, so

$$L = T - V$$.

Amazing, we've seemingly proven it! But some important clarifications need to be made.

### Intellectual Curiosity

By identifying $\boldsymbol{\alpha}$ with $\frac{1}{2}\boldsymbol{m}$ where we had to *show* that $\boldsymbol{\alpha}$ is in fact equal to $\frac{1}{2}\boldsymbol{m}$. I believe it is much more intuitive to think of this as the definition of mass itself. Much like motion, mass is a very difficult thing to quantify by itself. Yes, you can weigh yourself on a scale much like you can measure the velocity of a car, but many physical qualities elude definition. Try to define something like mass by itself. You'll find the dictionary definition to be relatively unsastisfactory. The fact remai that while we were all taught as middle schoolers to believe mass was a fairly easy-to-represent quality (and it is), its pure definition is much more abstract. It is the only truly *intrinsic* property that a body can have. While this is related to what we feel as "heaviness" in an object on Earth, this is merely a consequence of gravity, which is dependent but not deriving from mass itself.. Hence, mass *is* $\boldsymbol{2\alpha}$.⁵

The second part of this last step was identifying $\boldsymbol{C(x, t)}$ with $-V(x, t)$, the negative
of the potential energy. The obvious question here is, why the minus sign? Now, this one is actually just
arbitrary, but is the cause of much confusion (to myself). A most common objection to the Lagrangian
voiced by first-year university students (again, myself included) is: why the minus sign in front of the
potential energy? Most students will, by the time they enter university, have deeply internalized that
total energy $\boldsymbol{E = T + V}$, is a profound and important quantity in physics. Safe to say, the
Lagrangian would cause much less confusion if it happened to equal $\boldsymbol{T + V}$, the energy.
"I've seen that before, only makes sense that that's what it would be!", students would say. But this
would be poor judgment. The problem, rather, is one of selective skepticism.

Most people are taught the definition of energy (and the fact of its conservation) in middle school,
where it is written up on the board and stated as fact. Few people think to question this definition (I,
perhaps rather embarrassingly, certainly didn't). Why the $\boldsymbol{v^2}$? Why the $+\boldsymbol{V}$
instead of the $-\boldsymbol{V}$? And even those who do question, likely give up after a short while and
submit to internalizing the definition of energy as fact, and over time come to think of it as a deeply
physical truth. But there is nothing intuitively physical about energy! Sure, it certainly is physical,
in the sense that we use it in physics (same as mass). But can you tell me what it looks like? Can you
tell me what it feels like? When I first learned Lagrangian mechanics, I used to love asking people for
their "physical intuition for the Lagrangian", which is a fair, but difficult question. But never once
did I stop to ask anyone what the physical intuition of energy is, an equally hard, but fair, question!
Students enter their first analytical mechanics course with an unjustified acceptance of energy, and begin
harassing its close cousin, the Lagrangian, as if it all of a sudden now has to prove itself. We could
just as well have flipped signs on our definition of potential energy (which wouldn't be particularly
unintuitive, because again, the intuition for potential energy isn't quite as deep or rigid as we might
think), and thus defined energy as $\boldsymbol{T - V}$, and the Lagrangian and $\boldsymbol{T + V}$.
Would you be happier with this?

So, the real question becomes, well why is energy different from the Lagrangian by a sign change on the
potential energy, $\boldsymbol{V}$? My best answer to that is that the sign change occurs as you apply
Noether's theorem to find the energy as the conserved quantity arising from time translational symmetry,
and that there isn't any obvious physical intuition for why the signs should differ. It's "just" an
algebraic remnant, the "physical understanding" of which won't be particularly useful. But this is of
course an unsatisfying answer, and I would be happy to hear better ones! But if you do go looking for
better ones, remember to be fair, and if I may say, *symmetric*, in your scrutiny. While you may find a
physical intuition for why the Lagrangian differs from the energy by the flip of a sign, that doesn't
make either object privileged in terms of "intuition" above the other.

___

Remark: This is among the more technically complex posts I will make. For such posts, I will add disclaimers before convoluted sections that require high levels of context (in this case, math)

However, the struggle is mainly to make posts accessible and informational for readers who know very little about the subject matter while simultaneously opening new avenues of thought and posing questions to those more experienced for the topic. To this end, I will continue to refine my post quality, although I think I've done a reasonable job here. Feel free to reach out with suggestions and viewpoints on this, particularly if you identify with one of the extremes here.

To be rigorous here, you would want to show something like proving there is no dependence of the function  explicitly, but I will generally favour intuition-based arguments like these throughout, while trying my best to not sweep any important physics under the rug.

Finally, a huge thanks to my friends Farren, meduh., and the help of professor Katerina C. for their insights and helping me with a lot of the math.
