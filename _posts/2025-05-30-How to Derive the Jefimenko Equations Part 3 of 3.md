---
title: How to derive the Jefimenko Equations Part 3 of 3
date: 2025-05-30 10:00 AM
catagproes: [Maxwell Equations, Jefimenko]
tags: [maxwell, jefimenko]                                  # TAG names should always be lowercase
math: true
---

# Introduction
This is the third and final part on "How to derive the Jefimenko equations", in this part we will actually solve the Maxwell equations in a vary general setting and then discus possible meanings of how we got there and where there is.

If you have not read part's 1 and 2 it is recommended that you start there.

# Solving the Maxwell equations
Now that we have the generalization of the Helmholtz theorem we can solve for the E and B fields directly, this is actually a rather easy thing to do at this point as all of the hard work has been done, all we have to do is substitute E or B in place of F and then simplify the resulting equation.

Recalling the generalization of the Helmholtz theorem derived in part 2

$$F(R,t) = -\nabla \int {[\nabla' \cdot F] \over 4 \pi r }d^3r' + \nabla \times \int{[(\nabla' \times F)] \over 4 \pi r }d^3r' + {\partial \over \partial t} {1 \over c^2} \int{\left[ {\partial F \over \partial t}\right] \over 4 \pi r} d^3r' \ , $$

we will first do the electric field, recalling that the Maxwell equation state for the electric field that

$$ \nabla \bf{\cdot E} = {\rho \over \epsilon_0} \hspace{50pt} \nabla \times E = - {\partial B \over \partial t} \hspace{50pt} {\partial E \over \partial t} = c^2 \nabla \times B - \mu_0 c^2 J $$

we can substituting these in giving us

$$E(r,t) = -\nabla \int {[\nabla' \cdot E] \over 4 \pi r }d^3r' + \nabla \times \int{[(\nabla' \times E)] \over 4 \pi r }d^3r' + {\partial \over \partial t} {1 \over c^2} \int{\left[ {\partial E \over \partial t}\right] \over 4 \pi r} d^3r'$$

$$ = -\nabla \int {[\rho] \over 4 \pi \epsilon_0 r }d^3r' - \nabla \times \int{[{\partial B \over \partial t}] \over 4 \pi r }d^3r' + {\partial \over \partial t} {1 \over c^2} \int{\left[ c^2 \nabla' \times B - \mu_0 c^2 J\right] \over 4 \pi r} d^3r' \ . $$

This is actually how we want to write the first term so we will ignour it for the moment. Next we will look at the curl of B in the last integral, and observe that we can change the order of the curl and the partial to time as follows

$$ {1 \over c^2} \int{ {\partial \over \partial t} \left[ c^2 \nabla' \times B \right] \over 4 \pi r}d^3r' = {1 \over c^2} c^2 \int{ \left[ \nabla' \times {\partial \over \partial t} B \right] \over 4 \pi r}d^3r' = \nabla \times \int{ \left[ {\partial \over \partial t} B \right] \over 4 \pi r}d^3r' \ . $$

for the last step on the right it is perhaps not apparent what we did, so we will do it in full.

If we start with the equation

$$ \nabla \times {[{\partial B \over \partial t}] \over r } = {1 \over r} \nabla \times \left[ {\partial B \over \partial t} \right]  + \left( \nabla {1 \over r} \right) \times \left[ {\partial B \over \partial t} \right] $$

reorganize and integrate both sides, and notice that we can apply strokes theorem directly to the first term on the right hand side we get the equation
$$ \int {1 \over r} \nabla \times \left[ {\partial B \over \partial t} \right] dA = \int \nabla \times {[{\partial B \over \partial t}] \over r } - {\left[ \nabla' \times B \right] \over r} dA $$ 
$$  = \int {[{\partial B \over \partial t}] \over r } \times ds - \int {\left[ \nabla' \times B \right] \over r} dA \ . $$

Notice that this is this is nothing more then integration by parts.
and that the surface integral is zero since the term being integrated vanishes at infinity.

If we now compare this to the second term on the right hand side of our equation we will notice that the second integral on the right and the first part of the last integral cancel each other out.

If there are any concerns about convergence of the remaining terms converging to zero, just remember we are only concerned with the case of a finite charge and in the case that we are interested in the B field is actually zero at infinity. Not just vary small but actually zero, we just have to move out far enough that the magnetic field has not reached us yet, as we are not looking at the magneto static case.

There are other options for instance we could point out that since the magneto static cases are finite then this integral must converge as well. In any case we will not go through the trouble of rigorously proving convergence. 

Moving on, this leaves us with the term

$$ {\partial \over \partial t} {1 \over c^2} \int{\left[ - \mu_0 c^2 J \right] \over 4 \pi r} d^3r' \ .$$

To arrive at the Jefimenko equations we will write this term as

$$-{ 1 \over 4 \pi } \int{\left[ \mu_0 {\partial \over \partial t} J \right] \over r} d^3r' \ .$$

Notice that we have been assuming that $r$ is not a function of t so that we can just move the partial derivative to time around as we wish, this is not to big of a deal considering what we are trying to do although it is something to remember when using the final equations.

Combining everything that we have just done together leaves us with the rather satisfying equation

$$ E = - {1 \over 4 \pi \epsilon} \int {[\nabla' \rho + {1 \over c^2} {\partial J \over \partial t} ] \over r} dV \ .$$

This is the equation for the E field that we wanted to derive, it is a retarded integral for the E field that is dependent only on the charge density and current. 

Notice that this is in fact exactly the retarded integral of $1 / (4 \pi \epsilon r)$ times the right hand side of the Inhomogeneous wave equation that we derived for the E field. This should not be at all surprising as we did expect that this would act as some sort of a source term for a traveling wave, and that is just what we have.

If we use the right hand side of the inhomogenous wave equation for B in this way we get the equation

$$ B(R,t) = {\mu_0 \over 4 \pi} \int{[\nabla' \times J] \over r }d^3r' $$

this is in fact the Jefimenko equation for the B field. We could substituted the Maxwell equations for B into the generalized Helmholtz equation just as we did for E to arrive at this equation, but there is really no reason to do this hear, so we will leave it for the interested reader as it is exactly the same process as we just did for the E  field.

# A few insights and a new prospective on the Electromagnetic field

We will now suggest a slightly different perspective for the E and B fields.

Firstly we would like to ask the question why is the divergence of B zero, and while our derivation has not given us any definitive reason for this some considerations are worth noting that may give us some insight into this.

If we look at the equation for E we will notice that the first source is a scalar, in particular it is the charge density $\rho$ this has no direction associated with it only a magnitude, as a result we can only expect a field originating from it to have a direction defined by the direction to the source. How would we find such a direction, we might expect that this would be measured by finding the divergence of the E field itself. This is exactly what $\rho$ is and we can in fact write the equation for E as

$$ E = - {1 \over 4 \pi \epsilon} \int {[\nabla' (\nabla' \cdot E) + {1 \over c^2} {\partial J \over \partial t} ] \over r} dV \ , $$

although this is somewhat of a strange way to write the equation for E as we do not know what E is, but we expect to know what the charge density is if we are trying to calculate E. As a result we don't expects this way of writing the equation to be of much use for real world calculations.

If we go further and ask why do we have a gradient, then we might answer because we are trying to integrate over the hole region and turn the charge density into a total charge. This suggests that the gradient of $\rho$ is used not for physical reasons but is rather a direct consequence of the Divergence theorem and the gradient theorem from vector calculus.

One may expect that the second terms will have a similar reason for existing, if we think of $\rho$ as the source of E then we would expect that any non-zero time derivative of $\rho$ will create some sort of traveling disturbance in the E field. This is in fact what J is.

It should be observed that while $\rho$ is a scalar and as a result the total charge is a scalar. If we wish to conserve the total charge Q, then the only way that we can do that is by moving the charges along vectors in $R^3$. This is just what currents are doing, they are moving charge from location to location.

We will just except that charge is conserved and not prove that the Maxwell equations result in conservation of charge here, as this is a topic for another day.

If we look at E in this way we can think of E as the vector field that results from the scalar field $\rho$, and the resulting conservation of Q by use of J. If we are going to conserve the total charge Q then there appears to be no other logical way to from a vector field from the scalar field $\rho$, and it feels vary tempting to emphasize this point by writing J as a function of $\rho$ in the equation for E, doing this would give us.

$$ E = {1 \over 4 \pi \epsilon} \int {[\nabla' \rho + {1 \over c^2} {\partial \over \partial t} (\rho v)] \over r} dV $$

It may be tempting to try and argue that J will create some sort of term, if it did then this term would have to be either a vector with the same direction as J or a  vector with the same direction as $\nabla \rho$ in both cases we would expect to be able to write it as a function of B.

But in ore derivation there was just such a term, it was the term

$$  -\nabla \times \int{ \left[ {\partial \over \partial t} B \right] \over 4 \pi r}d^3r' + {\partial \over \partial t} \int{ \left[ \nabla' \times B \right] \over 4 \pi r}d^3r' $$

that vanished do to an interaction between Faraday's law and Ampere's law.

Let us consider this term further, notice that it vanished from interchanging the partial to t and the gradient of B. This is a purely mathematical idea and the only place that we might change anything is if we considered $r$ to be a function of t.

We will not consider this possibility here and so we don't expect this term to do anything except vanish. As a result we wont find any changes in the behavior of charges or fields here as the term vanishes.

It is quite interesting though that this term appears to be the B dependence of E but instead of creating some sort of E field it cancels out and the effect from Faraday's law, and Ampere's Law cancel out and instead of a changing magnetic field creating an electric field the electric field becomes a function of only the charge density and the currents. 

This is interesting because in this case we have a canceling effect of B and E that results from the interplay of Faraday's law of induction and Ampere's equation, that is the influence form

$$\nabla \times E = - {\partial B \over \partial t}$$

is canceled out by the term in ampere's law

$$\nabla \times B = - \mu_0 \epsilon_0 {\partial E \over \partial t}$$

in ampere's law.

This is actually a vary interesting prospective as we always think of a changing E field creating a changing B field, and a changing B field creating a changing E field, but with this perspective any such terms just cancel out.

If we had derived the B field directly form our generalization of the Helmholtz theorem we would have got a similar set of terms that once again whould cancel out, and we could say the same thing about B field and the E field.

If we continue to take the stance that the E field is a vector field created by a scalar field then the only remaining term that might be worth considering is the divergence of the B field, but by Gauss's law such a term would be zero from the start and does not even appear in the generalized Helmholtz theorem.

Of course we could just look at all of this as a mathematical oddity resulting from generalizing the Helmholtz theorem and ignour it outright however it does present an interesting way of looking at the equations.

There are no more terms that we might use to form E at this point that would not result in adding new physics to the Maxwell equations. While such a thing is an interesting endeavor it is not our goal at this time to hypothesize about adding new physics to the Maxwell equations, so we will put this off for future considerations.

Now let us examine the B field

$$ B(R,t) = {\mu_0 \over 4 \pi} \int{[\nabla' \times J] \over r }d^3r' $$

Motivated by the above idea that the E field is a vector field that results form a scalar field, we might ask is the B field a vector field that results form a vector field.

This appears to be what is going on, although there is a new layer of complexity added to the situation, do to needing to use strokes theorem in place of the divergence theorem, this gives us the equation 

$$\iint _{\Sigma }(\nabla \times \mathbf {F} )\cdot \mathrm {d} \mathbf {\Sigma } = \oint _{\partial \Sigma }\mathbf {F} \cdot \mathrm {d} \mathbf {\Gamma }$$

in place of the divergence theorem.

Fundamentally this is exactly the same idea as both of these theorems come from the same theorem namely the generalized Strokes theorem, it's just that we tend to refer to the above equation as strokes theorem, when it is actually a special case of the equation

$$ \int_{\partial \Omega} \omega = \int_{\Omega} dw $$

where $\Omega$ is some manifold being integrated over and $\omega$ is a differential form that we are integrating. The divergence theorem is also a special case of this theorem, again we just have to fill in the details for all of the terms.

This seems to be suggesting that there is a way to write the E and B fields using a single equation and just separating them out as resulting from scalar and vector sources.

Tensors and Quaternions both seem to be close to what I have in mind, and moving in the right direction, or moving away from it as the case may be, since Quaternions were the original way to write the Maxwell equations out. If we ever get there we will consider these and other possibilities, and see where they lead us.

We have covered a lot of ground unfortunately we seem to have left ourselves with as many questions as answers, and we have far more directions that we can go then we can possibly talk about here.

For the interested reader please refer to the following references, 

list of references 

[Jefimenko's equations](https://en.wikipedia.org/wiki/Jefimenko's_equations)

[The Generalized Strokes Theorem](https://en.wikipedia.org/wiki/Generalized_Stokes_theorem)

[The Helmholtz theorem and retarded fields](https://www.researchgate.net/publication/308438867_The_Helmholtz_theorem_and_retarded_fields)

[Can Maxwell's equations be obtained from the continuity equation?](https://arxiv.org/abs/0812.4785)

[Quaternions in electrodynamics](https://www.researchgate.net/publication/228356615_Quaternions_in_electrodynamics)