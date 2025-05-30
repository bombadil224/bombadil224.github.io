---
title: How to derive the Jefimenko Equations Part 1 of 3
date: 2025-05-30 08:00 AM
catagproes: [Maxwell Equations, Jefimenko]
tags: [maxwell, jefimenko]                                  # TAG names should always be lowercase
math: true
---

# Introduction
In this three part derivation we will go step by step in deriving the Jefimenko equations, a vary general solution to the Maxwell equations.

# A few words about the Maxwell equations

These are the Maxwell equations, 

$$ \nabla \bf{\cdot E} = {\rho \over \epsilon_0} \hspace{100pt} \nabla \bf{\cdot B} = 0 $$

$$ \nabla \times E = - {\partial B \over \partial t} \hspace{50pt} \nabla \times B = - \mu_0 \left( \bf{J} + \epsilon_0 {\partial E \over \partial t} \right) $$

each one on them on its own tells us something important about the electric and or the magnetic fields that surround us, taken together they tells us even more. But have you ever wondered what there general solution looks like and what those solutions might tell us about the universe that surrounds us.

We will not go into a in-depth analysis of these equations here rather our goal will be to derive the equations

$$ E = - {1 \over 4 \pi \epsilon} \int {[\nabla' \rho + {1 \over c^2} {\partial J \over \partial t} ] \over r} dV \ \hspace{20pt} and \hspace{20pt} B(r,t) = {\mu_0 \over 4 \pi} \int{[\nabla' \times J] \over R }d^3r' \ . $$

These equation are called the Jefimenko equations and are a vary general solution to the Maxwell equations.

We will try to derive these in full although there will be one or two places where we will use well known results, at these points it should be relatively easy for someone not familiar with these steps to find the missing parts. We will try and do this as little as we can but we will of course assume an understanding of vector calculus as the Maxwell equations, as we are working with them are fundamentally vector calculus equations.

A understanding of the Helmholtz theorem while useful is by no means necessary as a full derivation of a generalization of this theorem will be included, and will actually be the majority of the work that we have to do. We will proceed to do this in the same way as "Ricardo Heras" in the paper ["The Helmholtz theorem and retarded fields"](https://www.researchgate.net/publication/308438867_The_Helmholtz_theorem_and_retarded_fields).

A word of warning, this will not be for the faint of heart! But the reward at the end will be worth it as we will have a general solution to the Maxwell equations in free space. We will also find that charges and currents can be looked at as the sources of these fields. We will also derive some valuable tools that can be used in the future.

We will then conclude our investigation with some interesting insights into the mathematics and physics of the Maxwell equations that seem to be suggested by deriving the Jefimenko equations in this way.

We will assume a few things about the Maxwell equations, in porticular we will assume that the electric permittivity $\epsilon_0$ , and the magnetic permeability $\mu_0$ are constant and we will define the speed of light to be

$$c = {1 \over \sqrt {\epsilon_0 \mu_0}}\ .$$

However we will consider the right hand side to be a derived quantity and not a definition with no meaning other then a mathematical definition. In other words the left hand side of this equation is being defined to be c however the right hand side is the propagation speed of an electromagnetic wave in free space.

The approach that we will take suggests that we assume this from the beginning  since we will not solve the homogeneous electromagnetic wave equation. Of course this is a well known result and information on it is easily found.

Anyone familiar with electrodynamics should be able to understand that this will save us a considerable amount of time although the trade of is that we are not really doing an introduction to electrodynamics here or even an introduction to electromagnetic waves.

All the same we will begin by trying to motivate this approach.

# The Inhomogeneous electromagnetic wave equation

We will begin by deriving the inhomogeneous electromagnetic wave equations, these are the general form of the electromagnetic wave equations, and the equations that we wish to solve.

If we start with the Faraday equation

$$ \nabla \times E = - {\partial B \over \partial t} $$

and take the curl of it, we get the equation

$$ \nabla \times \nabla \times E = - {\partial \over \partial t} \nabla \times B \ .$$

Applying amperes law now gives

$$ \nabla \times \nabla \times E = - {\partial \over \partial t} \mu \left( J + \epsilon {\partial E \over \partial t} \right) \ ,$$

and if we apply the identity

$$ \nabla \times \nabla \times A = \nabla (\nabla \cdot A) - \nabla^2 A \ , $$

to the left hand side, and use Gauss's law we will get the equation

$$ \nabla {\rho \over \epsilon} - \nabla^2 E = - {\partial \over \partial t} \mu \left( J + \epsilon {\partial E \over \partial t} \right) \ .$$

We can reorganize this to get the far more recognizable equation 

$$ {1 \over c^2} {\partial^2 E \over \partial t^2} - \nabla^2 E = - \left( \nabla {\rho \over \epsilon} + \mu {\partial J \over \partial t} \right) \ . $$

If we do the same thing but starting with ampere's law we will get the equation 

$$ {1 \over c^2} {\partial^2 B \over \partial t^2} - \nabla^2 B = \mu_0 \nabla \times J \ . $$

We will not do this here as the steps are almost exactly the same, also this is a well known result and all that is needed to do it is to interchange the equations used for E and B.

Notice that we started with four coupled partial differential equations, and decoupled them giving us two inhomogeneous partial differential equations. It is worth noticing that if we set the right hand side of either of these equations to zero we will get the well known homogeneous wave equation, also any solution to these equations will be a general solution to the Maxwell equations.

We should also notice that from a physics prospective the left hand side of these equations is exactly the same as in free space. The only difference between these equations and there free space counterparts is that we now have terms on the right hand side, to get the free space form just set the right hand side to zero. Further more the E and B fields do not appear on the right hand side instead we have derivatives of the current J and charge density $\rho$ . We could consider J to be some sort of current density but we will try and avoid this discussion here.

Fundamentally what might we expect from these equations, since they are wave equations we should expect that we will have some sort of travailing wave solutions just like in free space, with a fixed wave velocity. It should also be clear that the right hand side of this equation will be some sort of source term for the electromagnetic field. This will in fact be the case, however proving it will not be as simple as in free space.

Perhaps more interesting is the fact that the electrostatic case will also be a consequence of these equations.

We could try and solve these equations directly, this can be done however we will instead take a different route involving the Helmholtz theorem.

Hopefully this derivation will be at least a little bit simper then some derivations that we could do and more importantly, it will hopefully give us some intuition about what the Maxwell equations are and why they appear the way that they do that we would not necessarily get from some other ways of solving these equations.

# Retardation
Before we derive the Jefimenko equations, and that is our goal after all. We will need to better understand the idea of retardation and retarded integrals. To do this we will define some notation that will simplify how we write things out. We will also need to derive some identities that will be needed later.

We will begin by defining just what we mean when we say a retarded function and how we do it.

Whenever we wish to retard a function we will use square brackets $[ \ ]$ so that if we have a function F and we wish to retard the function we will write this new function as $[F]$ . We will begin by writing out everything in full so that we can get use to this notation, but as we move on and become more familiar with the notation and derive a few identities we will find it much easier and convenient to just use the square bracket notation. We will also avoid using square brackets for anything else!

It should also be noted that F can be a vector or a scalar function, our notation is unchanged in either case, in fact we could go further and say that it could be any function containing t but we will find little to no need to go beyond vector functions here, but we could just as easily be doing tensor calculus.

We will use $x,y,z$ to indicate a location in space and $t$ to indicate what we will call time, at least right now as this is a discussion for another time. 

Furthermore we will use $x',y',z'$ to indicate the location of a source for $F$ at time $t' = t-r/c$ , we will also tend to use $R$ in place of $(x,y,z)$ and $R'$ in place of $(x',y',z')$ whenever convenient.

Putting this all together will give us the definition

$$[F(x,y,z,t)] = F(x',y',z',t - r/c)=F(x',y',z',t')$$

where 

$$ r = |R - R'| = \sqrt{(x-x')^2 + (y-y')^2 + (z-z')^2} \ .$$

Our motivation for using this notation should not be to difficult to follow, we expect that our solution will be a traveling wave, with group velocity c and originating from the point $(x',y',z')$ . This means that the effects from it traveling a distance $r$ before arriving at the point $(x,y,z)$ will take time $r/c$ to arive. It should be pointed out that the point $(x',y',z')$ can be looked at as a function of $t$ as a function of $t'$ or as an actual point in space, we will have need for all of these ideas as we continue.

This is why we wish to look at c as a derived quantity. If we looked at $c$ as nothing more then a mathematically defined quantity we would have no reason to believe that it was the propagation speed of the waves that we are looking for and we would not be able to justify our notation. Instead we would have to substitute some constant in for c and actually solve for it latter on, or we might just disregard are notation until we actually solved the equations and then define our notation and rewrite our equations using it at the end.

We will find it to be far more convenient to just use this notation from the start.

#  A few identities involving retarded functions

As was said above instead of solving the wave equation directly we will use a generalization of the Helmholtz theorem. The version that we will use will include, retarded functions and time derivatives, when combined with the Maxwell equations this will do most if not all of the work for us.

So why did we not just do this and skip deriving the Wave equations all together, quite simply we need the wave equations to motivate our definition of retardation and gain some intuition into what we expect form a solution.

With this in mind our goal is to derive this generalized Helmholtz equation, but before we can do that we will need a few identities.

We will begin by defining the term u by the equation

$$u = t'-t + |R - R'|/c \ ,$$

for those that are familiar with the delta function it should not be hard to see that 

$$[F(R', t')] = \int ^{\infty}_{-\infty} \delta(u)F(R', t') dt'$$

for those not familiar with the delta function, you can just take the above equation as a definition and say that the integral of any function times the delta function is the value of the function at $u = 0$. We will not be proving that such a function exist hear, although we will prove a similar idea in part 2.

We will tend not to write out the bounds of the integrals unless we actually plan to integrate it or we need to specify a particular boundary. Just remember that the point $u = 0$ is inside of the region being integrated over, and if in question then just assume that the bounds are at plus and minus infinity, or that the integral is over all of the $x,y,z$ plane.

We will also need the following equations involving the delta function, we will not try to prove existence or convergence here, as a full treatment of the delta function is a project on its own and would take us to far off of topic. We will rather stick with a somewhat informal treatment.

Information on the delta function should not be to difficult to find for someone that is interested in the details. If the above equation is used as a definition then most of these equations can be easily arrived at if one is willing to over look any questions of convergence that come up.

We will use $\rho$ as a scalar, J as a vector and F as an arbitrary function although sometimes we will treat it in a way that requires it to be a vector. With that said we will begin with

$$\nabla [\rho] = \int \nabla \ \delta(u) \ \rho(R',t') \ dt' =  - {\hat r \over c} {\partial \over \partial t} \int \delta(u) \ \rho(R',t') \ dt' = - {\hat r \over c} \left[ {\partial \rho \over \partial t} \right]$$

where $\hat r$ is the unit vector pointing between $(x,y,z)$ and $(x',y',z')$ and $\rho$ is a scalar function.

It should be clear that the first equality follows from applying the integral that we just defined and observing that we can move the gradient inside of the integral. The second equality is found directly from differentiating $\delta(u)$ and noticing that we can scale a partial to $t$ to make it the same as the partials to $(x,y,z)$ . The final equality is found by reversing the steps used in the first equality and the integral of the $\delta$ function.

Notice that we can do the same thing for the curl

$$\nabla \times [J] = \int \nabla \ \delta(u) \ J(R',t') \ dt' =  - {\hat r \over c} \times {\partial \over \partial t} \int \delta(u) \ \rho(R',t') \ dt' = - {\hat r \over c} \times \left[ {\partial \rho \over \partial t} \right]$$


The question of if the partial to $t$ is being retarded or if it is a retarded function that is being differentiated, is worth bringing our attention to. And is the next thing that we will determine. In fact it makes no difference if the partial to $t$ is retarded or if it it the partial of a retarded function as both ways of doing it are equal, we will prove this now.

$$ {\partial [F] \over \partial t} = \int {\partial \delta(u) \over \partial t} F(R', t') dt' = \int {\partial \delta(u) \over \partial t'} F(R', t') dt'$$

$$ = \int \delta(u) {\partial F(R',t') \over \partial t'} dt' - \int {\partial \over \partial t'} (\delta(u) F(R', t')) dt' $$

$$=\left[{\partial F \over \partial t}\right] - \delta(u)  \left. F(R',t') \right|_{-\infty} ^\infty = \left[{\partial F \over \partial t}\right]$$

where we have used integration by parts for the third equality and assumed that $u$ is not zero at infinity so that $\delta(u) F \rightarrow 0$ . We could have assumed that F goes to zero at infinity, from a physics stand point these are more or less the same idea, just remember there is nothing at infinity.

Again we will use a similar idea, But now we will use a vector function J and calculate the Laplacian giving us

$$\nabla^2 [J] = \int \nabla^2 \ \delta(u) \ J(R',t') \ dt' $$


$$ = {1 \over c^2} {\partial^2 \over \partial t^2} \int \delta(u) \ J(R',t') \ dt' - {2 \over |R - R'| c} {\partial \over \partial t} \int \delta(u) \ J(R',t') \ dt' $$

$$ = {1 \over c^2} {\partial^2 [J] \over \partial t^2} - {2 \over |R - R'| c} {\partial [J] \over \partial t} \ . $$

How to do these calculations in a rigorous way may not be apparent for those who have not encountered the delta function before, however as can be seen above, if one simply treats $\delta(u)$ like any other function there are in many cases no real surprises that come up.

In the next part we will continue deriving the identities that we need to solve the Maxwell equations.

References

["The Electromagnetic wave equation"](https://en.wikipedia.org/wiki/Electromagnetic_wave_equation)

["The Jefimenko equations"](https://en.wikipedia.org/wiki/Jefimenko%27s_equations)

[Dirac delta function](https://en.wikipedia.org/wiki/Dirac_delta_function)

[Electromagnetic retardation and theory of relativity by Oleg D. Jefimenko ](https://www.amazon.com/Electromagnetic-Retardation-Theory-Relativity-Classical/dp/0917406257 )

["The Helmholtz theorem and retarded fields"](https://www.researchgate.net/publication/308438867_The_Helmholtz_theorem_and_retarded_fields)

