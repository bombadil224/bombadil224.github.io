---
title: How to derive the Jefimenko Equations Part 2 of 3
date: 2025-05-30 09:00 AM
catagproes: [Maxwell Equations, Jefimenko]
tags: [maxwell, jefimenko]                                  # TAG names should always be lowercase
math: true
---

# Introduction
This is a continuation of "How to Derive the Jefimenko Equations Part 1 of 3". if you have gotten here and not read part 1 it is recommended that you read part 1 first as we will be using the notation that we defined there, as well as several  identities.

In this part we will derive the generalization of the Helmholtz theorem given by the equation

$$F(R,t) = -\nabla \int {[\nabla' \cdot F] \over 4 \pi r}d^3r' + \nabla \times \int{[(\nabla' \times F)] \over 4 \pi r }d^3r' + {\partial \over \partial t} {1 \over c^2} \int{\left[ {\partial F \over \partial t}\right] \over 4 \pi r} d^3r' $$

More information on this equation can be found in the paper ["The Helmholtz theorem and retarded fields"](https://www.researchgate.net/publication/308438867_The_Helmholtz_theorem_and_retarded_fields)

# An important integral

We will begin by proving perhaps the most difficult part of generalizing the Helmholtz theorem, in particular we need to show that

$$F(R) = -{\nabla^2 \over 4 \pi} \int {F(R', t) \over |R-R'|} dV (R')$$

Where this integral is over $R^3$ .

For those not interested in proving this integral you can just jump ahead to the next section [[# Generalization of the Helmholtz theorem]].

We will begin by recalling that

$$\nabla^2 {1 \over |R-R'|} = \nabla \cdot \nabla {1 \over |R-R'|} \ ,$$

in the end we will need to integrate this term. To do so we will choose to work in spherical coordinates as it will greatly simplify things. Recall that in spherical coordinates

$$\nabla^2 = {\partial^2 \over \partial r_s^2} + {2 \over r_s} {\partial \over \partial r_s} + {1 \over r^2 sin(\theta_s)} \left( cos \theta_s {\partial \over \partial \theta_s} + sin (\theta_s) {\partial^2 \over \partial \theta_s^2}\right) + {1 \over r_s^2 sin^2 (\theta_s)} {\partial \over \partial \phi_s} $$

where the subscript s indicates that we are using spherical coordinates.
we will not prove this identity hear as it is well known and would take us to far off of topic to prove.

To simplify things further we will first consider the situation where $R' = 0$ ,
 this creates a situation that is symmetric about the origin, it also results in $|R - R'| = |r| = |r_s|$ , we now wish to find

$$ \nabla^2 {1 \over |r_r|} $$

since the situation that we have is now symmetric about the origin the partials to $\theta_s$ and $\phi_s$ both vanish by symmetry. To see this imagine drawing circles about the origin, these circles are paths along which r is constant, for the moment we will ignour the absolute value of $r_s$ leaving us with
 
 $$\left( {\partial^2 \over \partial r_s^2} + {2 \over r_s} {\partial \over \partial r_s} \right) {1 \over r_s} = {\partial \over \partial r_s} {(-1) \over r_s^2} - {2 \over r_s^3} = {2 \over r_s^3 } - {2 \over r_s^3} = 0 \ . $$
 
For anyone that has not encountered something like this before, it may be slightly surprising that the Laplacian can vanish like this for a function that is not constant. This is in fact correct though, the Laplacian of this function vanishes even though the function is not constant anywhere.

This means that we really can ignour the absolute value of $r_s$ as it will take on the same value if $r_s$ is positive or negative, also recall that we assumed that $R'$ was zero, we did that so that we could ignore the angular parts of the polar coordinates, however if we where to apply a coordinate transformation to our solution to move it to any location we would still get zero as it is no longer a function of $\theta_s$ or $\phi_s$ .

If this feels to much like hand waving or you think that some trick has been done the ambitious reader may go back and solve this in Cartesian coordinates, after some grinding you will find the same result. Although getting there will be a somewhat tedious process and is really nothing more then an exercise.

It should be noticed that there is one exception to the gradient being zero and that is the point where

$$|R - R'| = 0 \ .$$

At this point the Laplacian is not really well defined anymore. What this means is that when we do the integration we no longer need to do it over all of space, rather we only need to do it around this single point where the Laplacian is not, well defined.

We will continue to assume that $R' = 0$ since it will simplify the calculations, just remembor that the end result is not dependent on this being true.

Before we solve the integral let us recall that

$$\int_S \nabla \cdot F dV = \int_{\partial S} u_n \cdot F ds \ .$$

This is of course just one of the many ways to write the generalized strokes theorem, this one in particular is the divergence theorem. We will not try to prove  it hear, although we will discus this theorem later. Finding information on this theorem and it's many forms is not difficult as it is fundamental to all of vector calculus, and is in fact just a generalization of the fundamental theorem of calculus.

What is important to notice is that the left hand side is a volume integral over the region S and the right hand side is a surface integral over the boundary of the region S. Also notice that $u_n$ is a unit outward pointing vector to the surface S that we are integrating over.

Now let us go back to our integral, we have already shown that all that we need to integrate over is a sphere of radius r that includes the point $|R-R'| = 0$ ,
 since the Laplacian is zero outside of this region, the integral of everything outside of this region is zero and can be ignored.

As a result, instead of integrating over $R^3$ we can integrate over a finite region of $R^3$ and apply strokes theorem to transform the volume integral into a surface integral, this allows us to complete the integration as follows.

$$-{\nabla^2 \over 4 \pi} \int {F(R', t) \over |R-R'|} dV (R') = - {F(R, t) \over 4 \pi} \int \nabla^2 {1 \over |R-R'|} dV (R') $$

where we are assuming that F is sufficiently well behaved so that we can choose the radius that we are integrating over so that $|F(R',t) - F(R,t)| < \epsilon$ for any choice of $|R - R'| < \delta$ ,
 we will not concern ourselves further with convergence here, and just assume that this is true for F. This is really not that big of a deal as anyone that is familiar with the topology of what is going on here knows, we are just saying that F is a continues function in $R^3$.

Now notice that

$$\nabla^2 {1 \over |R-R'|} = \nabla'^2 {1 \over |R-R'|}$$

so that our integral becomes

$$ - {F(R, t) \over 4 \pi} \int \nabla' \cdot \nabla' {1 \over |R-R'|} dV (R') = - {F(R, t) \over 4 \pi} \int \nabla' {1 \over |R-R'|} \cdot dS(R') $$

where we have applied the divergence theorem to transform from a volume integral to a surface integral.

Do not over look what we did hear, up until this point we have been calculating the Laplacian over the un-primed coordinates, this allowed us to show that we only need to integrate around the point $|R-R'| = 0$
 however we are now calculating the Laplacian in the primed coordinates, this will not change the value of any function at this point but it will allow us to directly apply the divergence theorem.

It should be pointed out that $u_{R-R'}$ is part of $dS(R')$ , I have chosen to write it in this way so that we could ignore the actual coordinates for the moment. We now want to actually write this out and preform the integration. In spherical coordinates we have 

$$dS(R') = -u_{R -R'} |R-R'|^2 cos(\phi)\ d \theta\ d\phi$$

We also need to point out that 

$$ \nabla' |R - R'|^{-1} = u_{R-R'} |R - R'|^{-2} $$

we will not go through the trouble of calculating this out here, but if we just remembor that the gradient is in the direction of steepest decent, and think of the gradient as pointing away from the point $R-R'$ it should be clear that this is correct, if it is not clear this is not a difficult calculation and can be done by the reader.

We can now use spherical coordinates to write this integral out in full as

$$ - {F(R, t) \over 4 \pi} \int_0 ^{2 \pi} \int_{-\pi/2}^{\pi/2} {u_{R-R'} \cdot u_{R-R'} \over |R-R'|^2} |R-R'|^2 cos(\phi)\ d \theta \ d\phi \ ,$$

now recall that $u_{R-R'}$ is a unit vector so that we can simplify the above equation and integrate

$$ - {F(R, t) \over 4 \pi} \int_0 ^{2 \pi} \int_{-\pi/2}^{\pi/2} cos(\phi)\ d \theta \ d\phi = F(R,t) $$

completing the integral and finally putting everything together gives us

$$-{\nabla^2 \over 4 \pi} \int {F(R', t) \over |R-R'|} dV (R') = F(R,t) \ .$$

Remember this is what we originally set out to prove, we have just preformed several transformations since then.

# Generalization of the Helmholtz theorem

We are now ready to prove the generalization of the Helmholtz theorem that we plan to use. Before we do that we will simplify how we write things a little bit by setting

$$ r = |R - R'|$$

and defining the operator

$$\square^2 F = \nabla^2 F - {1\over c^2} {\partial^2 F \over \partial t^2} = \nabla(\nabla \cdot F) - \nabla \times (\nabla \times F) - {1\over c^2} {\partial^2 F \over \partial t^2}.$$

If we take the retardation of this operator and multiply by $1/ (4 \pi r)$, then integrate over all of $R^3$ we get

$$\int {[\square'^2 F] \over 4 \pi r }d^3r' = \int {[\nabla'(\nabla' \cdot F)] \over  4 \pi r }d^3r' - \int{[\nabla' \times (\nabla' \times F)] \over 4 \pi r }d^3r' - {1 \over c^2} \int{\left[ {\partial^2 F \over \partial t^2}\right] \over 4 \pi r} d^3r'$$

We have not actually done anything here since we are just integrating the retardation of our definition for the $\square$ operator.

We will assume that any conditions required for this integral to converge are satisfied. In particular we will require that F vanishes sufficiently fast at infinity and is continues, we will also consider it to converge at every point. Basically we just don't want to have to prove the conditions that it takes for this integral to converge, and rather just choose functions where convergence easily follows. 

We now want to calculate the integral on the left hand side of this equation, to do this we will begin with the equation

$$ \nabla^2 {[F_x] \over r} = {1 \over r} \nabla^2[F_x] + 2 \nabla [F_x]\cdot \nabla \left( {1 \over r} \right)  + [F_x] \nabla \left( {1 \over r} \right) $$

notice that we are only working with the $x$ component of $F$ , this is for simplicity so that we can use vector notation.

Now recall that 

$$\nabla [\rho] = - {\hat r \over c} \left[ {\partial \rho \over \partial t} \right] \ ,$$

and that 

$$\nabla^2 [J] = {1 \over c^2} {\partial^2 [J] \over \partial t^2} - {2 \over r c} {\partial [J] \over \partial t} \ . $$

Where $\rho$ is a scalar and $J$ is a vector.

Substituting these into the above equation gives

$$ \nabla^2 {[F_x] \over r} = \left( {1 \over r c^2} {\partial^2 [F_x] \over \partial t^2} - {2 \over r c} {\partial [F_x] \over \partial t} \right) - 2 {\hat r \over c} \left[ {\partial F_x \over \partial t} \right]\cdot \nabla \left( {1 \over r} \right)  + [F_x] \nabla \left( {1 \over r} \right) \ .$$

This can be rearranged into the equation

$$ \square {[F_x] \over r} = \left( - {2 \over r^2 c} {\partial [F_x] \over \partial t} \right) - 2 {\hat r \over c} \left[ {\partial F_x \over \partial t} \right]\cdot \left( - {\hat r \over r^2} \right) + [F_x] \nabla \left( {1 \over r} \right) $$

$$ =  - {2 \over r^2 c} {\partial [F_x] \over \partial t}  + {2 \over r^2c} \left[ {\partial F_x \over \partial t} \right]\cdot \left( {\hat r \cdot \hat r} \right)  + [F_x] \nabla \left( {1 \over r} \right) \ .$$

Since $\hat r$ is a unit vector, it is clear that the first two terms on the right hand side cancel out giving the equation

$$ \square {[F_x] \over r} = [F_x] \nabla \left( {1 \over r} \right) $$

notice that this was done for the $x$ component of $F$ however this must also be true for the $y$ and $z$ components, combining all of these components together, and multiplying by $1 / (4 \pi)$ and then integrating over $R^3$ will give us

$$\int {[\square'^2 F] \over 4 \pi r }d^3r' = -{\nabla^2 \over 4 \pi} \int {F(R', t) \over r} dV (R') $$

where the left hand side is now the integral that we are trying to calculate. Notice that the right hand side is the integral that we previously calculated and is $F(R,t)$ .

We will now simplify the right hand side of the equality, we actually have vary little to do hear as all that we want is to move the gradients and one of the partials to time out of the integrals

$$ \int {[\nabla'(\nabla' \cdot F)] \over 4 \pi r }d^3r' = \nabla \int {[\nabla' \cdot F] \over 4 \pi r }d^3r' \ , $$

$$ \int{[\nabla' \times (\nabla' \times F)] \over 4 \pi r }d^3r' = \nabla \times \int{[(\nabla' \times F)] \over 4 \pi r }d^3r' \ , $$

$$ {1 \over c^2} \int{\left[ {\partial^2 F \over \partial t^2}\right] \over 4 \pi r} d^3r' = {\partial \over \partial t} {1 \over c^2} \int{\left[ {\partial F \over \partial t}\right] \over 4 \pi r} d^3r' \ . $$

If we put together everything that we have just done, we get the equation

$$F(R,t) = -\nabla \int {[\nabla' \cdot F] \over 4 \pi r}d^3r' + \nabla \times \int{[(\nabla' \times F)] \over 4 \pi r }d^3r' + {\partial \over \partial t} {1 \over c^2} \int{\left[ {\partial F \over \partial t}\right] \over 4 \pi r} d^3r' $$

It is important to remember that these integrals are over all of $R^3$ and not some finite region, from a physics prospective we are integrating over all of space, it should also be noted that there is no integration over time. 

This is in fact the generalization of the Helmholtz theorem that we are looking for, notice that we have in effect  separated $F$ into three parts, the first part results only from it's divergence, the second part results from its cruel, and the final part is related to its partial to time. 

Notice that this differs form the Helmholtz theorem in two ways, firstly we are using retarded terms, from an intuitive prospective this was built into the derivation because we expected some sort of traveling wave solution and retardation is a nice way of building this into the equation. Secondly the final term is altogether new, while we may not have been able to just guess what the final equation would be, we should have expected a new term that would include some sort of partial to time, in fact we where looking for such a term, and that is just what we have got.

There are perhaps two ways that we can think about this equation, firstly we can think of this as a way of doing an integral, almost like a special case of strokes theorem. Although there does not appear to be a direct derivation, and this is perhaps to abstract of an idea for our needs.

The second way that makes since to look at this is as a means of factoring $F$ , although instead of using multiplication we are using integration. If we choose to look at it in this way, then we must realize that the right hand side of this equality contains second derivatives formed form a divergence a curl and a partial to time of $F$ , and then a gradient a curl and a second partial to time are used on these terms. The theorem shows that this is sufficient to define $F$ , and from a theoretical prospective this is perhaps the most important part.

The question of uniqueness is a rather delicate question that we will only touch on now. While we have mathematically defined $F$ for any reasonable function in a unique way, we have not answered the question of if this will define unique physics. That is, there may be equations out there that will not change the physics but that will give us different answers. For those that are familiar with the idea of a gauge transforms, that is of course the sort of thing that is being hinted at, no more will be said on this topic here.

Substituting the Maxwell equations into this equation will be the subject of the next part.

References

[Electromagnetic retardation and theory of relativity by Oleg D. Jefimenko ](https://www.amazon.com/Electromagnetic-Retardation-Theory-Relativity-Classical/dp/0917406257 )

[Dirac delta function](https://en.wikipedia.org/wiki/Dirac_delta_function)

["The Helmholtz theorem and retarded fields"](https://www.researchgate.net/publication/308438867_The_Helmholtz_theorem_and_retarded_fields)
