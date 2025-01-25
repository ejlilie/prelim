
### A few math facts
#### Taylor Expansion
Taylor expansion to know, for positive and negative $n$:
$$(1+x)^{n} \approx 1+nx$$
Or, if we think of these as vectors we can taylor expand $r$ as $$\frac{1}{|\vec{a}-\vec{r}|} = \frac{1}{\sqrt{r^{2}+a^{2}-2\vec{a}\cdot\vec{r}}}=\frac{1}{a\sqrt{1-2\cos\theta r/a+r^{2}/a^{2}}}$$
Which we can approximate as
$$\approx\frac{1}{a}(1-\frac{1}{2}2\cos\theta r/a+O(r^{2}))=\frac{1}{a}-\frac{\vec{a}\cdot{\vec{r}}}{a^{3}}$$
#### Gaussian Integral
$$\int_{-\infty}^{\infty}dxe^{-ax^{2}}=\sqrt\frac{\pi}{a}$$
Note that in the case where you have $-ax^{2}+bx$ as the argument I recommend completing the square rather than memorizing that formula. 

Note: why should we expect this answer? Well, we know the only parameter that can be in the answer is $a$ and that it has dimensions $1/\left[\text{length}\right]^{2}$ so we should expect the answer to be proportional to $1/\sqrt{a}$ . This is a good process to keep in mind for the prelim. Dimensional analysis is a powerful tool, use it to check your answers or to come up with an approximate answer if you can't solve a question.
#### Laplace's Equation
Let's give some example solution to  Laplace's Equation:
$$\nabla^{2} V = 0$$
is solved by in cartesian coordinates by:
$$V(x,y) = a_{0}+\sum_{n=1}^{\infty}(A_{n}\sin(\frac{n\pi}{a}x)+B_{n}\cos(\frac{n\pi}{a}x))\sum_{m=1}^{\infty}(C_{m}\sinh(\frac{n\pi}{a}y)+D_{m}\cosh(\frac{n\pi}{a}y))$$
This has periodic boundary conditions, but you may have other boundary conditions where they become hyperbolic trig functions for example.

is solved by in spherical coordinates by:
$$ V(r,\phi,\theta) = \sum_{l=0}^{\infty}(A_{l}r^{l}+B_{l}r^{-(l+1)})P_{l}(\cos\theta)$$
Here we have $\phi$ independence.

is solved by in cylindrical coordinates by:
$$V(r,\phi,z) = a_{0} + b_{0}\ln(r)+\sum_{n=1}^{\infty}r^{n}(A_{n}\sin(n\phi)+B_{n}\cos(n\phi))+r^{-n}(C_{n}\sin(n\phi)+D_{n}\cos(n\phi))$$
This is the case where the solution is independent of $z$. 

Ultimately, if you don't recall a solution do separation of variables, check boundary conditions, and get the result. 

Note that the constants can then be set by boundary conditions, and using the orthogonality of sine/cosine. (Fourier's trick, if you read Griffiths E&M.)

# Classical Mechanics

## Lagrangian and Hamiltonian Mechanics

The definition of the Lagrangian:
$$
L = T -V
$$
The Euler-Lagrangian equation (from the stationary action principle)
$$
\frac{d}{dt}\frac{\partial L}{\partial \dot{q} } = \frac{\partial L}{\partial q }
$$
The definition of canonical momentum
$$
p = \frac{\partial L}{\partial \dot{q}}
$$
The definition of the Hamiltonian:
$$
H(q,p) = \sum p \dot q - L
$$
## Conservation Laws
Let's write our important conservation laws:

Energy is conserved when the potential is conservative (for example, a time-dependent force is not conservative.)
$$ E = E' $$
Momentum is conserved when there are no external forces $$\vec{p} = \vec{p}'$$Angular Momentum is conserved when there are no external torques $$\vec{L} = \vec{L}'$$There are important tools for problem solving. Don't forget them. If you aren't sure what to do in a problem, think about the conservation laws

Let's also note one 'trick' here:
$$x\dot{x} = \frac{1}{2} \frac{d(x^{2})}{dt}$$
Which can be used in some equations of motion to solve for time if 
$$\frac{1}{2} \frac{d(x^{2})}{dt} = C$$
leads to
$$\int_{x_0}^{x}d(x'^{2}) = 2C\int_{t_{0}}^{t}dt'$$
Note that the term $\frac{1}{2}\frac{d(x^{2})}{dt}$ looks like the derivative of kinetic energy. So, we can look at this in a different view (assuming energy is conserved):
$$T = E - V(x)$$
which leads to 
$$\frac{1}{2}mv^{2} = E - V(x)$$
and then
$$\int_{t_{0}}^{t}{dt'} = \pm\sqrt\frac{m}{2}\int_{x_{0}}^{x}\frac{dx'}{\sqrt{E-V(x')}}$$Note that taking the positive root is not always the choice that will make $t$ positive (for example consider the case of a free particle where $x < x_{0}$).
## Some Basic Kinematics
$$
\vec{v(t)} = \vec{v_{i}} + \vec{a}t 
$$
$$
\vec{x(t)} = \vec{x(0)}+\vec{v(0)t}+\frac{1}{2}\vec{a}{t}^2
$$
$$ v(t)^{2}= v(0)^{2}+2a\Delta x$$

Note this last one is usually treated as a kinematics equation when you first learn physics, but is really just conservation of energy.
## Newton's Laws
The Second Law:
$$
\vec{F} = m\vec{a} = \frac{\vec{dp}}{dt}
$$
The definition of potential:
$$
-\vec{\nabla}V=\vec{F}
$$
Gravity:
$$
\vec{F} = -\frac{GMm}{r^{2}}\hat r
$$
$$G = 6.67 \times 10^{-11} \text{N m}^2/\text{kg}^2]$$
## Normal Modes and small oscillations 
### Small oscillations 
$$\omega = \sqrt\frac{k}{m}$$
Also, note the formula for period:
$$T = \frac{2\pi}{\omega}$$
We can always write
$$U(x) \approx U(x_0)+U'(x_0)(x-x_{0})+\frac{1}{2}U''(x_0)(x-x_{0})^{2}$$
The first term we can always redefine to be 0. The second term is 0 because we are expanding about a minimum. Thus our potential will look like a harmonic oscillator with $U''(x_{0}) = k$.

There is also another way to do this, by writing $x = x_{0} + \varepsilon$ and rewriting the Lagrangian and carrying out the equation of motion. 
### Normal modes
We can write a coupled differential equation for coupled oscillators as 
$$\textbf{M}\ddot{\vec{x}}=-\textbf{K}\vec{x}$$
With some math, we can get to the condition
$$\det(\textbf{K}-\omega^{2}\mathbf{M}) = 0$$
Where we assume solutions of the type 
$$\vec{A}e^{i\omega_{1} t},\space\vec{B}e^{i\omega_{2} t}$$
where $\vec{A}$ and $\vec{B}$ are eigenvectors of $$\textbf{K}-\omega_{1}\textbf{M}$$ and $$\textbf{K}-\omega_{2}\textbf{M}$$respectively. 
## Rotations and Rigid Bodies
Definition of centripetal acceleration:
$$
a = \frac{v^{2}}{r}
$$

Definition of angular velocity:
$$
\vec{v} = \vec{\omega} \times \vec{r} 
$$
Angular momentum of a point particle:
$$\vec{l} = \vec{r} \times \vec{p}$$
Angular momentum of a rigid body: 
$$\vec{L} = I\vec{\omega}$$
Relationship between rotating frame time derivative, where $S_{0}$ is inertial and $S$ is rotating:
$$
\left( \frac{\vec{dQ}}{dt} \right) _{S_{0}} = \left( \frac{\vec{dQ}}{dt} \right) _{S} + \vec{\Omega} \times \vec{Q}
$$
Newton's Laws in non-inertial frame:
$$
m\ddot{\vec{r}} = \vec{F}+\vec{F}_{\text{Coriolis}}+\vec{F}_{\text{Centrifugal}}
$$
Where these forces are defined as:
$$
\vec{F}_{\text{Coriolis}} = 2m{\dot{\vec{r}}} \times \vec{\Omega}
$$
$$\vec{F}_{\text{Centrifugal}} = m(\vec{\Omega} \times \vec{r}) \times \vec{\Omega}
$$
Coriolis force is because of having a velocity in the rotating frame, where as the centrifugal force is inherit to being in a rotating frame. 
Euler's Equation in the rigid body frame:
$$
\vec{\tau} = \frac{d\vec{L}}{dt} + \vec{\Omega} \times {\vec{L}}
$$
## Classical Scattering
The differential cross section is defined by 
$$\frac{d\sigma}{d\Omega} = \frac{b}{\sin{\theta}}\left| \frac{db}{d\theta}\right|$$
where $b$ is the impact parameter. 
## Central potentials and effective potentials
Lagrangian:
$$ L = \frac{1}{2}m_{1}\dot{r}^{2}_{1}+\frac{1}{2}m_{2}\dot{r}^{2}_{2} - U(r)$$
Definition of center of mass:
$$\vec{R} = \frac{m_{1}\vec{r}_{2}+m_{1}\vec{r}_{2}}{m_{1}+m_{2}}$$
Defining $r$ in terms of $r_{1}$ and $r_{2}$:
$$\vec{r}_{1} = \vec{R}+\frac{m_{2}}{m_{1}+m_{2}}\vec{r}$$
$$\vec{r}_{2} = \vec{R}-\frac{m_{1}}{m_{1}+m_{2}}\vec{r}$$
$$ L = \frac{1}{2}M\dot{R}^{2} + (\frac{1}{2}\mu\dot{r}^{2}-U(r))$$
We can enter the center of mass frame and effectively ignore the movement of the center of mass. This leads to the relevant equation of motion:
$$ \mu\ddot{\vec{r}} = -\vec{\nabla}U(\vec{r})$$
We are going to make more simplifications still. We can note angular momentum is conserved, and thus our problem is reduced to a two-dimensional problem where:
$$\vec{L} = \vec{r}\times \mu \dot{\vec{r}}$$$$L = \frac{1}{2}\mu(\dot{r}^{2}+r^{2}\dot{\phi})-U(r)$$
This leads to the angular equation:
$$\mu r^{2} \dot{\phi} = \text{const} \equiv l$$
This leads to the radial equation where $$\mu r \dot\phi^{2} - \frac{dU}{dr}=\mu\ddot{r}$$
We can substitute $\dot{\phi} = \frac{l}{\mu r^{2}}$ into this equation
$$\mu\ddot{r} = -\frac{dU}{dr}+\frac{l^{2}}{\mu r^{3}}\equiv-\frac{d}{dr}U_{\text{eff}}(r)$$
Where $$U_{\text{eff}}(r) = U(r)+\frac{l^{2}}{2\mu r^{2}}$$ We can then use this formalism to solve gravitational problems and other potential problems.
## Waves and the Wave Equation
The wave equation is given by:
$$ \frac{\partial^{2}u(x,t)}{\partial t^{2}} = v^2\nabla^{2}u(x,t)$$
Where $v$ we can think of as the speed of the wave. There are many ways to solve this equation, by separation of variables, Fourier transform, or even assuming a plane wave solution. 

On a string, we tend to write
$$ v^{2} = \frac{T}{\mu}$$ Where $T$ is the tension and $\mu$ is the mass density. 
# Electricity and Magnetism

## Maxwell's Equations (Not in matter) + Lorentz Force

$$ \vec{\nabla}\cdot\vec{E} = \frac{\rho}{\epsilon_{0}}
$$
$$ \vec{\nabla}\times\vec{E} = -\frac{\partial B}{\partial t}
$$
$$ \vec{\nabla}\cdot\vec{B} = 0
$$
$$ \vec{\nabla}\times\vec{B} = \mu_{0}\vec{J}+\mu_{0} \epsilon_{0} \frac{\partial E}{\partial t}
$$
These can be converted to the integral forms using Divergence and Stokes' Theorem:
$$\iint_{S}\vec{F}\cdot d{\vec{S}}= \iiint_{V}(\vec{\nabla} \cdot \vec{F})dV
$$$$\int_{C}\vec{F} \cdot d\vec{r} = \iint_{S}(\vec{\nabla} \times \vec{F})\cdot d{\vec{S}}
$$
Note we can define the fields in terms of potentials:
$$\vec{E} = -\vec{\nabla}V - \frac{\partial \vec{A}}{\partial t}$$
$$\vec{B} = \nabla \times \vec{A}$$
We can also write formulas for the potentials:

$$
\nabla^{2}V = -\frac{\rho}{\epsilon_{0}}
$$
$$
\Box^{2}\vec{A} = -\mu_{0}\vec{J}
$$
Notice this first equation is in Coulomb gauge and the second is in Lorenz Gauge. Using the d'Alemblertian. 

Keep in mind the Lorentz force equation as well:
$$ \vec{F} = q\vec{E} + q(\vec{v}\times\vec{B})$$
Also, note the Biot-Savart law which can be used to calculate magnetic fields:
$$\vec{B} = \frac{\mu_{0}}{4\pi}\int_{C}\frac{Id\vec{l}\times\vec{r}'}{|\vec{r}'|^{3}}$$
It seems unlikely you would need this, but it is a usable formula.

## Energy and momenta in E&M

Poynting Vector:
$$ \vec{S} = \frac{1}{\mu_{0}}(\vec{E} \times \vec{B})$$
The momentum density from this:
$$\vec{g} = \mu_{0}\epsilon_{0}\vec{S} = \epsilon_{0}(\vec{E} \times \vec{B})$$
The angular momentum density from this is:
$$\vec{r} \times \vec{g} = \mu_{0}\epsilon_{0}\vec{r} \times\vec{S} = \epsilon_{0}[\vec{r}\times(\vec{E} \times \vec{B})]$$
Energy density:
$$u = \frac{1}{2} \left(\epsilon_{0}E^{2}+\frac{1}{\mu_{0}}B^{2} \right)$$
We can also calculate intensity as 
$$ I = \langle \vec{S} \rangle$$
Where the brackets represent a time-average.
## Jefimenko's equations + Multipole Expansion
Technically what I write here are not Jefimenko's equations, but they can be found by the relevant formula from these equations.

$$ V = \frac{1}{4\pi\epsilon_{0}}\int \frac{\rho(r',t_{r})}{|\vec{r}-\vec{r}'|} dV'$$
$$ \vec{A} = \frac{\mu_{0}}{4\pi}\int \frac{\vec{J}(r',t_{r})}{|\vec{r}-\vec{r}'|} dV'$$
Note that $$t_{r} = t -\frac{1}{c}|\vec{r}-\vec{r}_{s}|$$where $r_{s}$ is the position of the source. Note for an accelerating charge that $r_{s}$ is a function of $t_{r}$ itself. Note that this means you have to be careful about terms such as $\frac{dt_{r}}{dt}$ and $\nabla t_{r}$ which are now nontrivial. However, in the case of the prelim this should not be necessary to remember. 

Multipole Expansion:
$$V(\vec{r}) = \frac{1}{4\pi\epsilon_{0}} \sum_{n=0}^{\infty}\frac{1}{r^{(n+1)}}\int(r')^{n}P_{n}(\cos\alpha)\rho(\vec{r}')dV'$$
Where $\alpha$ is the angle between $\vec{r}$ and $\vec{r}'$.
## E&M in Matter and Boundary Conditions
There's a lot of formulas here to keep track of.
Dipole moment formulas:
$$ \vec{p} = \int \vec{r}'\rho(r')dV'$$
And for an atom:
$$
\vec{p} = \alpha \vec{E}
$$
Torque formula:
$$\vec{\tau} = \vec{p} \times \vec{E} $$
Force:
$$ \vec{F} = (\vec{p} \cdot \vec{\nabla})\vec{E} 
$$
Polarization definition:
$$ \vec{\mathbf{P}} = \frac{\vec{p}}{V} $$
Magnetic dipole moment definition:
$$ \vec{m} = \frac{1}{2}\int \vec{r}' \times \vec{J}(\vec{r}')dV'$$
Similarly:
$$ \vec{\mathbf{M}} = \frac{\vec{m}}{V} $$
also:
$$\vec{F} = \vec{\nabla}(\vec{m}\cdot\vec{B})$$
This leads us to defining two new fields:
$$ \vec{D} = \epsilon_{0}\vec{E} + \vec{\mathbf{P}}$$
$$ \vec{H} = \frac{1}{\mu_{0}}\vec{B}-\vec{\mathbf{M}}$$
Which obey equations
$$\nabla \cdot \vec{D} = \rho_{f}$$
$$ \vec{\nabla} \times \vec{H} = \vec{J}_{f}$$
Now, we can talk about bound charge/charge densities (distinct from the "free" densities above.)
$$ \sigma_{b} = \vec{\mathbf{P}} \cdot \hat n$$
$$ \rho_{b} = \vec{\nabla} \cdot\vec{\mathbf{P}} $$
$$\vec{K}_{b} = \vec{\mathbf{M}} \times \hat n$$
$$\vec{J}_{b} = \vec{\nabla} \times \vec{\mathbf{M}}$$
As I said, a lot of formulas. With little elaboration from me. I wouldn't personally worry about formulas like torque and forces, but they are here just so you can see them.  See Griffiths E&M for more detail.

A quick note here: if $\vec{J}_{f} = 0$ then the curl of $\vec{H}$ is 0, and we can actually define a magnetic vector potential where 
$$\vec{H} = -\vec{\nabla}\psi$$
Then we can use our knowledge of Laplace's equation and scalar potentials to solve for $\psi$.
### Boundary Conditions:
I would say these are very important to know (And they work for the cases of E&M not in matter as well!)
$$ D_{1}^{\perp} - D_{2 }^{\perp} = \sigma_{f}$$
$$ B_{1}^{\perp} - B_{2 }^{\perp} = 0$$
$$ \vec{E}_{1}^{\parallel} - \vec{E}_{2 }^{\parallel} = 0$$
$$ \vec{H}_{1}^{\parallel} - \vec{H}_{2 }^{\parallel} = \vec{K_{f}} \times \hat n$$
### Linear Media:
A lot of the time, we care about the case of linear media. This entails:
$$\vec{\mathbf{P}} = \epsilon_{0}\chi_{e} \vec{E}$$
$$ \vec{D} = \epsilon_{0}(1+\chi_{e})\vec{E} = \epsilon\vec{E}$$
For reference, we can define:
$$\epsilon_{r} = \frac{\epsilon}{\epsilon_{0}}$$
$$\vec{\mathbf{M}} = \chi_{m} \vec{H}$$
$$\vec{B} = \mu_{0}(1+\chi_{m})\vec{H}$$
Now you know all you could want to about E&M in matter.
## Waves in E&M
First, note the vector identity:
$$\vec{\nabla} \times (\vec{\nabla}\times\vec{E}) = \vec{\nabla}(\vec{\nabla}\cdot\vec{E})-\nabla^{2}\vec{E}$$
This is important, because you can use it on the Maxwell's equations in a vacuum to get a wave equation. 

This leads to the following equations:
$$\nabla^{2}\vec{E}=\mu_{0}\epsilon_{0}\frac{\partial^{2} \vec{E}}{\partial t^{2}}$$
$$\nabla^{2}\vec{B}=\mu_{0}\epsilon_{0}\frac{\partial^{2} \vec{B}}{\partial t^{2}}$$
We can solve these assuming plane wave solutions:
$$\vec{\tilde{E}} = \vec{\tilde{E}}_{0}e^{i(kz-\omega t)}$$
Note however, that Maxwell's equations in their original form give constraints of the orthogonality of $\vec{B}$ and $\vec{E}$:

$$\vec{B_{0}} = \frac{k}{\omega}\hat{z}\times\vec{E_{0}}$$

For the case of matter, we have a new speed $v$:

$$v  =\frac{c}{n{}} $$
where $$n = \sqrt\frac{\epsilon\mu}{\epsilon_{0}\mu_{0}}$$
Thus in our equations above, $\epsilon_{0}\mu_{0} \rightarrow  \epsilon\mu$.

We should also define the group velocity, given by 
$$v_{g} = \frac{d\omega}{dk}$$

Note one trick here, when you are using the machinery of complex fields:
$$\langle S \rangle = \frac{1}{2\mu_{0}}\Re{(\vec{E}\times\vec{B}^{*})}$$
When the incident field is at oblique angles, it gets more complicated:

The law of reflection:
$$ \theta_{R} = \theta_{I}$$
Snell's Law is:
$$\frac{\sin{\theta_{T}}}{\sin\theta_{I}} = \frac{n_{1}}{n{t}}$$

Now note Ohms law, noting that $\sigma$ is conductivity NOT charge density: $$\vec{J} = \sigma \vec{E}$$We can still solve the wave equation with this, there is just another term now proportional to $\frac{\partial \vec{E}}{\partial t}$. But, in the plane wave solution $\tilde{k} = k +i\kappa$ will be complex. This makes sense, as we are just saying there is now some decay (which you might expect). 

Also, recall the formula $$ d = \frac{1}{\kappa}$$ This defines the penetration depth or skin depth. 

We can also write $\tilde{k} = Ke^{i\phi}$ and the phase as $$ \phi = \arctan(\kappa/k)$$
We should also mention dispersion, and that we can use Newton's law to calculate the amplitude of an electron. Then, we can use this amplitude to calculate the dipole moment, and then the polarization. From this, we can calculate $\epsilon$ and use this to calculate $k$. See Griffiths pages 420-422.

Wave guides can be solved using separation of variables. However, note that in wave guides waves are generally not transverse. But, we can plug in 
$$ \vec{\tilde{E}} = \vec{E_{x}}\hat x+\vec{E_{y}}\hat y+\vec{E_{z}}\hat z$$ and similarly for $\vec{\tilde{B}}$  to get coupled equations for $B$ and $E$. Then you can uncouple them by using the equations involving divergence of the fields.

Also, this is a good spot to note the continuity equation:
$$\vec{\nabla}\cdot\vec{J} = - \frac{\partial \rho}{\partial t}$$
## Circuits, capacitance, and inductance
Note the definition of resistance as 
$$R = \rho \frac{L}{A}$$
Using $\rho$ as the resistivity and related to conductivity by $\rho = \frac{1}{\sigma}$

Capacitance is defined as 
$$C = \frac{Q}{\Delta V}$$
Inductance can be calculated from:
$$L = \frac{\Phi_{B}}{I}$$
For a resistor, Ohm's Law:
$$V = IR $$
For a capacitor
$$V = \frac{Q}{C}$$
For an inductor
$$V = L\frac{dI}{dt}$$
Adding resistances in series and parallel:
$$R_{s} = \sum_{i} R_{i}$$
$$\frac{1}{R_{p}} = \sum_{i} \frac{1}{R_{i}}$$
Adding conductance in series and parallel:
$$\frac{1}{C_{s}} = \sum_{i} \frac{1}{C_{i}}$$
$$C_{p} = \sum_{i} C_{i}$$
Adding inductance in series and parallel:
$$L_{s} = \sum_{i} L_{i}$$
$$\frac{1}{L_{p}} = \sum_{i} \frac{1}{L_{i}}$$
Some energy formulas:
$$ P = IV $$ $$U = \frac{1}{2}LI^{2}$$
$$ U = \frac{1}{2}CV^{2}$$
Don't forget Kirchhoff's Laws:
$$\sum_{\text{Loop}} V = 0$$
$$\sum_{\text{in vertex}} I = \sum_{\text{out vertex}}I$$
## Radiation
The power radiating from an accelerating non-relativistic formula is given by the Larmor formula:
$$ P = \frac{\mu_{0}q^{2}a^{2}}{6\pi c}$$
To derive this formula, you can start from the equations for the retarded potentials given in the section "Jefimenko's equations + Multiple Expansion", using the charge densities as delta-functions for a charge, take the large $|\vec{x}|$ and the non-relativistic limit, and then use the formula $$P = \int d\vec{A}\cdot \vec{S} = \frac{1}{\mu_{0}} \int d\vec{A}\cdot (\vec{E} \times \vec{B})$$
Radiation does not seem to be particularly relevant for the prelim, so you shouldn't worry too much about this section.
## Lorentz Transformations
Some basic lorentz transforms:
$$t' = \gamma\left(t-\frac{vx}{c^2}\right)$$
$$x' = \gamma\left(x-vt\right)$$
$$\vec{E}_{\perp} = \gamma(\vec{E}_{\perp}+\vec{v}\times \vec{B})$$
# Quantum Mechanics

## Basic Schrödinger Equation and Boundary Conditions
$$H\ket{E} = E\ket{E}$$
$$ \left(-\frac{\hbar^{2}}{2m}\frac{d^{2}}{dx^{2}} +V(x) \right)\psi(x) = E\psi(x)$$
An important boundary condition to know, use this to solve 1D scattering.
$$ \psi^{+}(a) = \psi^{-}(a) $$
An equally important boundary condition, found by integrating the Schrödinger Equation. Note the RHS usually vanishes, except in the case of examples like the delta function.
$$
\left. \frac{d\psi}{dx}\right|_{a+\epsilon^{-}}  - \left. \frac{d\psi}{dx}\right|_{a+\epsilon^{+}} = \frac{2m}{\hbar^{2}} \int^{a + \epsilon^{+}}_{a+\epsilon^{-}}{}V(x)\psi(x)dx
$$
We should also note the time dependent Schrödinger equation:
$$ \left(-\frac{\hbar^{2}}{2m}\frac{d^{2}}{dx^{2}} +V(x) \right)\psi(x,t) = i\hbar\frac{\partial}{\partial t}\psi(x,t)$$
Also, note formula for the probability current, which can be used to calculate reflection and transmission coefficients
$$\vec{J} = \frac{\hbar}{2mi}(\psi^{*}\vec{\nabla}{\psi}-\psi\vec{\nabla}{\psi}^{*}) = \frac{\hbar}{m}\Im({\psi^{*}}\vec{\nabla}\psi)
$$
Note here the Born rule:
The probability that a state $\ket{\psi}$ is found in $\ket{n}$ is found by:
$$P(n) = \left|\braket{n|\psi}\right|^{2}$$
## The Harmonic Oscillators

Maybe the most important system in quantum mechanics. 
$$ H = \frac{p^2}{2m} + \frac{1}{2}m\omega^{2}x^{2} = \hbar \omega(a^{\dagger}a+\frac{1}{2})$$
With wavefunction solutions:
$$
\psi(x) = e^{\frac{-m\omega x^{2}}{2\hbar}}H_{n}(\sqrt{\frac{m\omega}{\hbar}x})
$$
Notice that these aren't normalized (because this test usually doesn't care about that) and that these use special functions, Hermite polynomials. Here are the first three:
$$
H_{1}(y) = 1
$$
$$
H_{2}(y) = 2y
$$
$$
H_{3}(y) = 4y^2-2
$$
The energy levels are:
$$E_{n} = \hbar\omega(n+\frac{1}{2})$$
### Creation and Annihilation Operators
These are important, as they tend to make solving any problem involving the harmonic oscillator much easier. Let's look at their definitions and properties:
$$ X = \sqrt{\frac{\hbar}{2m\omega}}(a^{\dagger}+a)$$
$$ P = i\sqrt{\frac{\hbar m\omega}{2}}(a^{\dagger}-a)$$
Inverting these formulas gives:
$$ a = \sqrt{\frac{m \omega}{2\hbar}}(X+\frac{i}{m\omega}P)$$
$$ a^{\dagger} = \sqrt{\frac{m \omega}{2\hbar}}(X-\frac{i}{m\omega}P)$$

General Properties of our operators:
$$a\ket{0} = 0$$
$$a^{\dagger}\ket{0} = \ket{1}$$
$$a^{\dagger} \ket n = \sqrt{n+1}\ket{n+1}$$
$$a^{} \ket n = \sqrt{n}\ket{n-1}$$
## The Hydrogen Atom

I'm going to show the Hydrogen atom changing from the original Hamiltonian up to the center of mass coordinates. The reason to do this is because this is actually helpful for some prelim problems, where coordinates transformations can uncouple interactions (as long as commutation relations remain the same.) I'm going to try to stick to MKS units here, although a lot of texts use CGS.

So, first we have:
$$H = \frac{p_{p}^2}{2m_{p}}+\frac{p^2_{e}}{2m_{e}} -\frac{1}{4\pi\epsilon_{0}}\frac{e^2}{|\vec{r}_{p}-\vec{r}_{e}|}$$
Then, we do the following transformations:
$$ \vec{R} = \frac{m_{p}\vec{r}_{p}+m_{e}\vec{r}_{e}}{{m_{p}+m_{e}}}$$
$$ \vec{r} = \vec{r}_{p}-\vec{r}_{e}$$
$$ \vec{P} = \vec{p}_{p} + \vec{p}_{e}$$
$$ \vec{p} = \frac{\vec{p}_{p}m_{p} + \vec{p}_{e}m_{e}}{m_{e}+m_{p}}$$
$$ \mu = \frac{m_{p}m_{e}}{m_{p}+m_{e}} \approx m_{e}$$
So, $H$ becomes:
$$ H = \frac{\vec{P}^{2}}{2(m_{e}+m_{p})} +\frac{\vec{p}^{2}}{2m_{e}}-\frac{1}{4\pi\epsilon_{0}}\frac{e^{2}}{r}$$
The first term describes the free evolution of the center of mass so we can ignore it, either thinking about it in the CoM frame or that it would only contribute a phase to the wave function.
$$ H = \frac{\vec{p}^{2}}{2m_{e}}-\frac{1}{4\pi\epsilon_{0}}\frac{e^{2}}{r}$$
Much simpler now. I'm not going to write down the full differential equations, just the solutions to them.

The (non-normalized) wave functions are found to be:
$$ \psi(r,\phi,\theta) = e^{-\frac{r}{na_{0}}}\left(\frac{2r}{na_{0}}\right)^{l}L_{n-l-1}^{2l+1}\left(\frac{2r}{na_{0}}\right) Y_{lm}(\phi,\theta)$$
The spherical harmonics $Y_{lm}(\phi,\theta)$ are defined as:
$$Y_{lm}(\phi,\theta) = e^{im\phi}P_{l}^{m}(\cos\theta)$$
where $P_{l}^{m}$ are the associated Legendre polynomials. I'll list a few worth knowing below:
$$ P_{1}^{0}(x) = 1$$
$$ P_{2}^{0}(x) = x$$
$$ P_{3}^{0}(x) = \frac{1}{2}(3x^2-1)$$
A few associated Laguerre polynomials:
$$ L_{0}^{0} = 1$$
$$L_{1}^{0} = -x + 1$$
The Bohr radius is defined as:
$$a_{0} = \frac{4\pi\epsilon_{0}\hbar^{2}}{e^{2}m_{e}}$$
The energy levels are defined as:
$$ E_{n} = -\frac{m_{e}e^{4}}{2(4\pi\epsilon_{0})^{2}\hbar^{2}}\frac{1}{n^{2}} = -\frac{13.6}{n^{2}}\text{eV}$$
Or, if we have an atom with atomic number $Z$:
$$ E_{n} = -\frac{Z^2m_{e}e^{4}}{2(4\pi\epsilon_{0})^{2}\hbar^{2}}\frac{1}{n^{2}} = -Z^2\frac{13.6}{n^{2}}\text{eV}$$
## Addition of Angular Momentum
Spin matrices:
$$S_{z} = \frac{\hbar}{2}\begin{pmatrix}  
1 & 0\\  
0 & -1  
\end{pmatrix}$$
$$S_{y} = \frac{\hbar}{2}\begin{pmatrix}  
0 & -i\\  
i & 0  
\end{pmatrix}$$
$$S_{x} = \frac{\hbar}{2}\begin{pmatrix}  
0 & 1\\  
1 & 0  
\end{pmatrix}$$
An important identity to know:
$$
\vec{L} \cdot \vec{S} = \frac{1}{2} \left( \vec{J}^2 - \vec{L}^2-\vec{S}^{2}\right)
$$
This is a good identity to know because it can simplify problems and you can use total angular momentum (coupled) basis on the RHS rather than the uncoupled basis.

Consider a single particle with spin:
$$S_{z}\ket{s,m}=\hbar m\ket{s,m}$$
$$S^{2}\ket{s,m}=\hbar^{2} s(s+1)\ket{s,m}$$
We can also consider a system with two particles with spin say $S_{1}$ and $S_{2}$. in our uncoupled basis we have
$$\ket{s_{1},m_{1},s_{2},m_{2}}$$ where $S_{1}^{2}$, $S_{1z}$, $S_{2}^{2}$, and $S_{2z}$ are all diagonal with their respective eigenvalues.  But we can also consider the coupled basis of total angular momentum:
$$\ket{j,m_{j},s_{1},s_{2}}$$
Where $J^{2}$, $J_{1z}$, $S_{2}^{2}$, and $S_{1}^{2}$ are diagonal with there respective eigenvalues. Notice that $j$ is constrained by $$|s_{1}-s_{2}| \leq j \leq |s_{1}+s_{2}|$$ by one integer between these two values. For example, for $s_{1} = s_{2} = \frac{1}{2}$ we have $j$ = $0$, $1$

And from this we know:
$$ -j \leq m \leq j$$ So we have $2j+1$ states for each value of $j$. 

So, how do we get the $\ket{j,m_{j},s_{1},s_{2}}$ states in terms of $\ket{s_{1},m_{1},s_{2},m_{2}}$? The answer is using the ladder operators $J_{\pm}$. We can start with the highest state that we know must be eliminated by $J_{+}$ and is written as 
$$\ket{s_{1}+s_{2},s_{1}+s_{2},s_{1},s_{2}} = \ket{s_{1},s_{1},s_{2},s_{2}}$$
Note the notation here can be slightly confusing, but we are just saying $j = s_{1}+s_{2}$, $m_{j} = s_{1}+s_{2}$, $m_{1} = s_{1}$, and $m_{2} = s_{2}$ to get the uppermost ket in the $s_{1}+s_{2}$ multiplet. Why do we know these states must be equal? It's because no other product state can give $j = s_{1}+s_{2}$.

Then we can write
$$J_{-}\ket{s_{1}+s_{2},s_{1}+s_{2},s_{1},s_{2}} = (S_{1-}+S_{2-})\ket{s_{1},s_{1},s_{2},s_{2}}$$
$$\ket{s_{1}+s_{2},s_{1}+s_{2}-1,s_{1},s_{2}} = S_{1-}\ket{s_{1},s_{1},s_{2},s_{2}}+S_{2-}\ket{s_{1},s_{1},s_{2},s_{2}}$$
$$\ket{s_{1}+s_{2},s_{1}+s_{2}-1,s_{1},s_{2}} = \ket{s_{1},s_{1}-1,s_{2},s_{2}}+\ket{s_{1},s_{1},s_{2},s_{2}-1}$$
Which will then give the next lowest state coupled n terms of a combination of uncoupled. This process can then be done for each $j$ value. However, to do the next level $m_{j} = s_{1}+s_{2}-1$ we have to note this state must be orthogonal to the $j = s_{1}+s_{2}, m_{j} = s_{1}+s_{2}-1$ state. Then we can apply the same process using $J_{-}$. 

Note that I don't expect this process to be on the prelim, but it's important to know how the Clebsch-Gordan coefficients are generated.

## Time-Independent perturbation theory
Perturbation theory relies on a few formulas. If you forget these, what you can do is represent the energies and wave functions in a power series and inner product the Schrödinger equation with the zeroth order states. I won't show this here, see any QM book.

Onto the formulas:
$$ E^{1}_{n} = \bra{\psi^{0}_{n}}V\ket{\psi^{0}_{n}}$$
$$
\ket{\psi^{1}_{n}}= \sum_{m \neq n} \frac{\bra{\psi^{0}_{m}}V\ket{\psi^{0}_{n}}}{E^{0}_{n}-E^{0}_{m}}\ket{\psi^{0}_{m}}
$$
$$
E^{2}_{n} = \sum_{m \neq n} \frac{|\bra{\psi^{0}_{m}}V\ket{\psi^{0}_{n}}|^{2}}{E^{0}_{n}-E^{0}_{m}}
$$
These formulas are straight forward enough to apply. 
## Time-Dependent perturbation theory
These will go here.

This is a rich subject with that can confuse easily. Primarily, in my opinion, because there is some confusion between the interaction picture and the Schrödinger picture. 

Let's start out with some basics:
$$
H = H_{0}+V(t)
$$
Where $H_{0}$ is our solvable Hamiltonian, potentially harmonic oscillator or hydrogen or something we know how to solve. 
In the interaction picture, states evolve as 
$$
\ket{\psi(t)}_{I} = U(t,t_0)_{I}\ket{\psi(0)}_{I}
$$
Where we can write the time evolution operator as:
$$U(t,t_0)_{I} = T\left[ \text{exp}\left(-\frac{i}{\hbar}\int_{t_{0}}^{t}V_{I}(t)dt\right)\right] \approx 1 - \frac{i}{\hbar}\int_{t_{0}}^{t}V_{I}(t)dt$$
Here, $T$ is the time ordering operator. Additionally, note the definition of $V_{I}(t)$:
$$V_{I}(t) = e^{iH_{0}(t-t_{0})/\hbar}V(t_{0})_{S}e^{-iH_{0}(t-t_{0})/\hbar}$$Notice here $V(t)_{S}$ does in general not commute with $H_{0}$
Transition Amplitude:
$$dP(t)_{m\rightarrow n} = |\bra{n} V \ket{m}|$$
Notice this is a picture independent statement, as we expect this to be the same in all pictures.  So, it might be easiest to calculate this in the Schrödinger picture for example.
$$P(t) = \frac{1}{\hbar^{2}}\left|\int_{t_{0}}^{t}dP(t')dt'\right|^{2}$$
Or, in the case of $\ket{m}$ and $\ket{n}$ being energy eigenstates implies 
$$P(t) = \frac{1}{\hbar^{2}}\left| \int_{t_{0}}^{t}\bra{n_{t_{0}}} V(t')_{S} \ket{m_{t_{0}}}e^{-\frac{i}{\hbar}(E_{m}-E_{n})t'}dt'\right|^{2}$$
This isn't the best notation, but just to say $V$ is only evolving here from it's inherit time dependence not because of the Hamiltonian. 
## WKB Approximation
Bohr-Sommerfeld Quantization:
$$\oint pdq = nh$$
So why do we care about this? The answer is we don't really, but the WKB approximation has the restraint that can understood as the Bohr-Sommerfeld quantization condition with a correction:
$$ \int_{x_{1}}^{x_{2}}\sqrt{2m(E-V(x))}dx = (n+1/2)\pi\hbar$$
The WKB relies on the semiclassical approximation:
$$\hbar \left| \frac{dp}{dx}\right| \ll |p(x)|^{2}$$
Which is basically saying the de Broglie wavelength is much less than characteristic distance over which the potential varies. Where we are defining $p(x)$ as 
$$p(x) = \sqrt{2m(E-V(x))}$$
The solution for the wave function is given as 
$$\psi(x) = \frac{C_{+}e^{\frac{i}{\hbar}\int_{0}^{x}{p(x)}dx}+C_{-}e^{-\frac{i}{\hbar}\int_{0}^{x}{p(x)}dx}}{\sqrt{p(x)}}$$
## Born Approximation
The Born approximation is the first order solution to the Lippmann-Schwinger equation. I wouldn't worry about the solution to the Lippmann-Schwinger equation here, but just knowing the formula for the Born approximation and the cross section.

The Born approximation is that we can calculate the cross section from the Fourier transform of the potential. (Like LSZ Reduction, If you've taken QFT.)
$$ f(\phi,\theta) \approx -\frac{m}{2\pi\hbar^{2}}\int d^3{r}e^{i\vec{q} \cdot \vec{r}}V(r)$$
Note: here $\vec{q} = \vec{k}' - \vec{k}$ where $\vec{k}$ is the incoming wave and $\vec{k}'$ is the outgoing wave. We can write $|\vec{q}| = 2k\sin(\theta/2)$ from doing $|\vec{k}'-\vec{k}| = \sqrt{k'^{2}+k^{2}-2\vec{k} \cdot \vec{k}'} = \sqrt{2k^{2}(1-\cos(\theta))}=2k\sin(\theta/2)$ (Note we have the magnitude of $k'$ = $k$, which comes from an expansion in the Lippmann-Schwinger equation.)
$$\frac{d\sigma}{d\Omega} = \left| f(\phi,\theta)\right|^{2}$$
The Optical Theorem:
This is in no way necessary for the prelim. However, it is a good trick. The optical theorem is the statement:
$$\sigma = \frac{4\pi}{k}\Im({f(\vec{k},\vec{k})})$$
Notice $f$ is forward scattering! In other words, $\vec{k} = \vec{k}'$. However, keep in mind here to get a non-zero answer you need a second order approximation; as the first order will be real and thus $\Im({\text{real}}) = 0$.
## S-wave scattering
S-matrix definition:
$$S_{l} = e^{2i\delta_{l}(k)} $$$$ S_{l}(k) = 1 - 2ik \frac{2m}{\hbar}\int_{0}^{\infty}dr'j_{l}(kr')V(r')\psi_{l}(r',k)$$The Born approximation would send $\psi_{l} \rightarrow  j_{l}$.
$$f(k',k) = \frac{1}{2ki}\sum_{l}(2l+1)(e^{2i\delta_{l}(k)}-1)P_{l}(\cos \theta)$$
$$\sigma = \frac{4\pi}{k^{2}}\sum(2l+1)\sin^{2}\delta_{l}$$
S-wave implies $l = 0$.  This tells us our solution at large $r$ looks like $$\psi(r\rightarrow\infty) = \frac{e^{i\delta_0}}{kr}\sin(kr+\delta_0(k))$$However, the above equations may not be so easy to remember. Instead, what you can do is the following:

The radial wave function can be solved for using the radial equation: $$-\frac{\hbar^{2}}{2m}u''(r)+V(r)u(r) = E(r)u(r)$$where $u(r) = rR(r)$. Then you can match boundary conditions for the potential, and find the scattering length. Then, you can use the formula to calculate $\sigma$ and anything else you could want. Note this radial equation is specifically for s-wave scattering. **$l$ is $0$ here.**  
## Variational Principle
This is just the statement that the ground state energy is less than the average energy.
$$ E_{0} \leq \frac{\braket{\psi|H|\psi}}{\braket{\psi|\psi}}$$
## Particles in an EM field
Use the following Hamiltonian:
$$ H = \frac{(p-qA)^2}{2m}+q\phi$$
Where $A$ and $\phi$ follow the usual gauage transformations:
$$\vec{A} \rightarrow \vec{A} +\vec{\nabla}\Lambda$$
$$\phi \rightarrow \phi -\frac{\partial \Lambda}{\partial t}$$
Note however the wavefunction gauge transforms as
$$\psi \rightarrow e^{\frac{iq\Lambda}{\hbar}}\psi$$
# Statistical Mechanics
## Basic statistics, binomial dist., into microcanonical
### The binomial distribution 

Choose function:
$$C(n,k) = {n\choose k} = \frac{n!}{k!(n-k)!}$$
$n$ choose $k$ can be understood as the number of $k$ combinations of a set of $n$ elements.  

Binomial distribution:
$$P(p,N,n) = {N\choose n}p^n(1-p)^{N-n}$$
In the limit where p $\ll$ 1 and $n \ll N$ the binomial distribution becomes a Poisson distribution:
$$P(n) = \frac{\lambda^n}{n!}e^{-\lambda}$$
Where $\lambda \equiv Np$. This can be derived using the Stirling approximation:
$$ n! \approx \sqrt{2\pi n}e^{-n}n^n \approx e^{-n}n^n$$
As well as noting that $$(1-p)^{N-n} \approx e^{-p(N-n)}$$We can also do a continuum limit of the binomial distribution, where $n \in (-\infty,\infty)$. This leads to: $$ P(n) = Ae^{-B(n-n_{*})^{2}/2}$$Which can be seen by expanding $P(n)$ (or, the $\log P$) around the maximum. A$ is found by normalization. $n_{*}$ is simply the maximum of the distribution. $B$ is found by differentiating twice and comparing with the binomial distribution. This leads to $$P(n) = \frac{1}{\sqrt{2\pi\sigma^{2}}}e^{-(n-pN)^{2}/(2\sigma^{2})}$$
Lastly, let's note one trick:

Our poisson distribution should be normalized:
$$\sum_{n=0}^{\infty} P(n) = \sum_{n=0}^{\infty} \frac{\lambda^n}{n!}e^{-\lambda}=e^{-\lambda}\sum_{n=0}^{\infty} \frac{\lambda^n}{n!}=e^{-\lambda}e^{\lambda}=1$$

So, let's calculate the mean $\bar{n}$:
$$\sum_{n=0}^{\infty} nP(n) = \sum_{n=0}^{\infty}n \frac{\lambda^n}{n!}e^{-\lambda}=e^{-\lambda}\sum_{n=0}^{\infty} n\frac{\lambda^n}{n!}$$
This is where we use our trick. note that we can rewrite this term as 
$$e^{-\lambda}\sum_{n=0}^{\infty} \lambda \frac{\partial}{\partial \lambda}\frac{\lambda^n}{n!}$$ You can convince yourself this is true.
$$e^{-\lambda}\sum_{n=0}^{\infty} \lambda \frac{\partial}{\partial \lambda}\frac{\lambda^n}{n!}=e^{-\lambda}\lambda \frac{\partial}{\partial \lambda}\sum_{n=0}^{\infty} \frac{\lambda^n}{n!} =e^{-\lambda}\lambda \frac{\partial}{\partial \lambda}e^{\lambda}=\lambda$$ This is a good trick for calculating expectation values.

### Degeneracy / microcanonical ensemble

Suppose we have a volume of air particles, and we want to ask the question how many states have $n$ particles of a total $N$ particles contained a partition $p$ of the total volume. The degeneracy (total number of microstates with $n$ in $p$) will be given by
$$\Omega = {N\choose n} = \frac{N!}{n!(N-n)!}$$
In a microcanonical ensemble (isolated state with set $E$, $V$, and $N$) each microstate is equally likely:
$$P = \frac{1}{\Omega}$$
In a continuum distribution we must define the density of states $\Omega$(E) where degeneracy is defined to be $\Omega(E)dE$:
$$\Omega(E) = \frac{N(E)}{V} = \int\frac{d^{d}k}{(2\pi)^{d}}\delta(E-E(k))$$
However, we can clearly define this for a countable number of states with delta functions:
$$\Omega(E) = \frac{1}{V} \sum_{i}^{N}\delta(E-E(k_{i}))$$
As integrating this will give you back the degeneracy. 

There is one more equivalent definition:
$$\Omega(E)dE = \frac{\text{volume of state space in [E,E+dE]}}{\text{volume of a cell}}$$
However personally I find the first definition the easiest to think about. 

Note here a definition of entropy as $$S = k_{b}\log{\Omega}$$Why do isolated systems maximize entropy? In the thermodynamic limit we tend to obserb the most likely macrostate. So then we can think of equilibirum as maximizing entropy, as this is when the most likely macrostate will have the highest degeneracy.
## Laws of Thermodynamics, free energy, van der waals, maxwell-boltzmann
### Basic laws 
Convention here is $Q$ and $W$ done ***on*** the system
$$ \Delta E = \Delta Q + \Delta W
$$
$$ \Delta S \geq 0
$$
For a reversible process we have:
$$\Delta S = \int \frac{\delta Q}{T}$$
The ideal gas law is:
$$ pV = Nk_{b}T = nRT$$
Specific heat formulas at constant volume and at constant pressure are:
$$ C_{V} = \left( \frac{\delta Q}{dT}\right)_{V} = \left( \frac{\partial E}{\partial T} \right)_{V}$$
$$ C_{p} = \left( \frac{\delta Q}{dT}\right)_{p}= \left( \frac{\partial E}{\partial T} \right)_{p}+p\left( \frac{\partial V}{\partial T} \right)_{p}$$
The definition of Helmholtz free energy is: 
$$ F = E -TS$$
The definition of Gibbs free energy is:
$$G = E+pV-TS = H - TS$$
where $H$ is enthalpy.

Note the "fundamental thermodynamic relation"
$$dE = TdS-pdV$$
or$$dF = -SdT-pdV$$
or$$dG = -SdT+Vdp$$
or$$dH = TdS+Vdp$$Note that in the case where particle number changes the first term adds $\mu dN$ and the rest change accordingly from the definitions of $G, F, \text{and}\space H$.

You should note the following facts:

- Helmholtz free energy is useful in the canonical ensemble (where $T$, $V$ and $N$ are constant)
	- A canonical ensemble at will minimize $F$.
- Gibbs free energy is useful in the ensemble where $T$, $P$, and $N$ are constant
	- A system at constant $T$ and $P$ will minimize $G$.
	- This is beneficial for phase transitions 
- Enthalpy is useful for throttling as enthalpy per mass is constant

In general, entropy is maximized for an isolated system. However, when a system is not isolated (for example in contact with a heat bath) something else is minimized: The free energy. 

### Processes and the relevant quantities (adiabatic, isothermal, etc)

In adiabatic processes we have $Q$ = 0 and then we have the fact that
$$ (PV^{\gamma}) = \text{const}$$
And we can exchange to other parameters using the ideal gas law. note that
$$\gamma = \frac{C_{p}}{C_{V}} = \begin{cases}
\frac{5}{3} & \text{if monoatomic} \\
\frac{7}{3}  & \text{if diatomic} \\
\end{cases}$$
In isothermal processes we have $T$ is constant.
In isobaric processes we have $P$ is constant.
In isochoric processes we have $V$ is constant.

### Maxwell's Relations
The property you're using here is that:
$$ \frac{\partial }{\partial x_{i}}\frac{\partial\Phi}{\partial x_{j}} = \frac{\partial }{\partial x_{j}}\frac{\partial\Phi}{\partial x_{i}}$$
This will derive any identity you need. Here is an examples:
$$\left(\frac{\partial T}{\partial V}\right)_{S} = -\left(\frac{\partial p}{\partial S}\right)_{V} = \frac{\partial U}{\partial S \partial V}$$
### Van der Waal's Equations
$$\left(p+\frac{an^2}{V^{2}}\right)(V-nb) = nRT$$
The interpretation here is $b$ accounts for the size of molecules, and $a$ accounts for the attraction/repelling of molecules
### Critical Point
The critical point is the point where increasing pressure at a constant temperature makes no distinction between liquid and vapor. 
$$\left. \frac{\partial p}{\partial V}\right|_{p=p_c}=0$$
$$\left. \frac{\partial^{2} p}{\partial V^{2}}\right|_{p=p_c}=0$$
You can use these to solve for $T_{c}$ and $V_{c}$. Then plug back into the original equation for $p_{c}$.
### Boltzmann Distribution
The distribution of velocities in a 3D canonical distribution are 
$$ f(v) = \left( \frac{m}{2\pi k_{b}T}\right)^{3/2}4\pi v^{2}e^{-mv^{2}/(2k_{b}T)}$$
### Equipartition Theorem
Any degree of freedom that is quadratic in the energy only contributes $$\frac{1}{2}k_{b}T$$ to the average energy.
## Partition functions and quantities from partition functions
Let's define the partition function in discrete and continuous cases:
$$ Z = \sum e^{-\beta E_{i}}$$
$$ Z = \frac{1}{h^{3}}\int e^{-\beta H}dqdp$$
We can calculate variables from these, such as:
$$\langle E \rangle = - \frac{\partial \ln Z}{\partial \beta}$$
$$F = -k_{b}T\ln Z$$
$$ p = \frac{1}{\beta}\frac{\partial\ln Z}{\partial V}$$
$$S = k_{b}(\ln Z + \beta \langle E \rangle)$$
The grand canonical partition function:
$$\mathcal{Z} = \sum e^{\beta(N_{i}\mu-E_{i})}$$
$$ \langle N \rangle = \frac{1}{\beta}\frac{\partial \mathcal{\ln Z}}{\partial \mu}$$
### A quick note on chemical potentials / chemical reactions
$$\mu_{i} = \left( \frac{\partial H}{\partial N} \right)_{S,P}= \left( \frac{\partial F}{\partial N}\right)_{T,V}$$
At a constant pressure and temperature two chemical potentials can be related by
$$ d\mu_{B} = -\frac{n_{a}}{n_{b}}d\mu_{A}$$
## Spin Statistics
Bose (-1) and Fermi (+1) Statistics:
$$\langle N_{i} \rangle = \frac{1}{e^{\beta(\mathcal{E}_{i}-\mu)\pm1}}$$
Blackbody radiation in terms of frequency:
$$u_{\nu} = \frac{8\pi h \nu^{3}}{c^{3}} \frac{1}{e^{\frac{h\nu}{k_{b}T}}-1}$$
Note to convert to wavelength you must consider $u_{\nu}d\nu= u_{\lambda}d\lambda$.

## Lattice Materials + Ising Model
Consider $N$ spin-1 particles on a $d$ dimensional lattice and nearest neighbors $\langle i,j \rangle$ interact with coupling energy $-J\sigma_{i}\sigma_{j}$. The energy of a microstate $s$ can be written as 
$$ E_{s} = -\mu H\sum_{i=1}^{N}\sigma_{i}-J\sum_{\langle i, j\rangle}\sigma_{i}\sigma_{j}$$ Note that $\sigma = 1$ corresponds to spin aligned $\sigma = -1$ is anti-aligned, or $\sigma = 0$ is neutral. 

We can use the mean field approximation to calculate $E_{s}$. Write $$\sigma_{i} = m + \delta\sigma_{i}$$$$ \sigma_{i} \sigma_{j} = (m + \delta\sigma_{i})(m + \delta\sigma_{i}) \approx m^{2}+m(\delta\sigma_{i}+\delta\sigma_{j}) $$
Now plug in the definition of $\delta \sigma_{1}$:
$$m^{2}+m(\delta\sigma_{i}+\delta\sigma_{j}) = m^{2}+m(\sigma_{i}-m+\sigma_{j}-m) = -m^{2}+m(\sigma_{i}+\sigma_{j})$$
Then we can write $E_{s}$ as 
$$ E_{s} = -\mu H\sum_{i=1}^{N}\sigma_{i}-J\sum_{\langle i, j\rangle}(-m^{2}+m(\sigma_{i}+\sigma_{j}))$$
$$ E_{s} = -\mu H\sum_{i=1}^{N}\sigma_{i}-J\sum_{\langle i, j\rangle}(-m^{2}+2m\sigma_{i})$$
Now, calculate these sums:
$$\sum_{\langle i, j\rangle}1 = \sum_{i=1}^N\sum_{j=1}^d=Nd$$
What is the explanation for this sum? We can some over all spins $i$. Each spin has one neighbor in each dimension. Intuitively, it seems like it would be two, but if we do each spin having two neighbors then sum over all spins we would be double counting. So think about summing over all spins with one neighbor each. 
$$\sum_{\langle i, j\rangle}\sigma_{i} = \sum_{i=1}^N\sum_{j=1}^d\sigma_{i}=d\sum_{i=1}^N\sigma_{i}$$
Then we rewrite $E_{s}$ as:
$$ E_{s} = -(\mu H+2dmJ)\sum_{i=1}^{N}\sigma_{i}+Jm^{2}Nd$$
Then we can write the partition function as 
$$Z = \sum_{\sigma_{1}}\sum_{\sigma_{2}}\ldots e^{-\beta E_{s}}$$
Where each $\sigma$ is summing over the possible values. Inserting our definition of $E_{s}$:
$$Z = \sum_{\sigma_{1}}\sum_{\sigma_{2}}\ldots \sum_{\sigma_{N}} e^{-\beta ((-\mu H-2mJd)(\sigma_{1}+\sigma_{2}+\ldots)+Jm^{2}Nd)}$$
$$Z = \left( \sum_{\sigma_{1}={1,0,-1}} e^{-\beta (-\mu H-2mJd)\sigma_{1}} \right)^{N}e^{-\beta Jm^{2}Nd}$$
Now, explicitly doing this sum:
$$Z = \left( 1+e^{-\beta (-\mu H-2mJd)}+e^{\beta (-\mu H-2mJd)}\right)^{N}e^{-Jm^{2}Nd}$$
A little more simplification:
$$Z = \left( 1+2\cosh[{\beta(\mu H+2mJd)}]\right)^{N}e^{-Jm^{2}Nd}$$
This process can be generalized to other lattice materials, but the Ising model is the canonical case.
## Brownian Motion

A solid spherical particle of radius $b$ and mass $M$ is suspended in a fluid, and is seen, using an optical microscope, to undergo Brownian motion with trajectory $\vec{r}(t)$. Assume the densities of the solid and fluid are identical, so buoyancy can be ignored. The cause of the Brownian motion is the rapidly fluctuating random force, $\vec{F(t)}$, due to collisions with the molecules of the fluid. The force has mean zero, $\langle \vec{F(t)} \rangle$ = 0, and assume that its components $(F_{x}, F_{y}, F_{z})$ have two-time correlations of the form:
$$\langle F_{\alpha}(t)F_{\beta}(t) \rangle = C\delta_{\alpha \beta}\delta(t-t')$$
And follows the differential equation
$$M\frac{d^{2}\vec{r}}{dt^{2}}+6\pi\eta b\frac{d\vec{r}}{dt} = \vec{F}(t)$$
or 
$$M\frac{d\vec{v}}{dt}+6\pi\eta b\vec{v} = \vec{F}(t)$$
We can assume a solution of $$\vec{v}(t) = \vec{A}(t)e^{-6\pi\eta bt/M}$$to get 
$$M\dot{\vec{A}}(t)e^{-6\pi\eta bt/M} = F(t)$$
therefore
$$\dot{\vec{A}} = \frac{F(t)}{M}e^{6\pi \eta b t/M}$$
Now use our formula for $v(t)$ with this:
$$\vec{v}(t) = \frac{1}{M}\int_{0}^{t}e^{-6\pi\eta b(t-s)/M}\vec{F}(s)ds$$
Then we can calculate $$\langle v(t)v(t')\rangle$$ from both this integral and our formula for $$\langle F(t)F(t')\rangle$$and using a Boltzmann distribution/ equipartition theorem, equating these two to find $C$.

To calculate $\langle |\vec{r}(t_{1}) - \vec{r}(t_{2})|^{2}\rangle$ this can we done by dotting the differential equation with $\vec{r}$ and then taking the time average. 
## Fluids
### Navier Stokes Equation
$$\rho (\frac{\partial \vec{u}}{\partial t} + (\vec{u} \cdot \vec{\nabla})\vec{u} = -\vec{\nabla}p +\mu\nabla^{2}\vec{u}$$
Notice LHS is the total derivative of $u$. In steady state, this will be 0. Usually you will assume the pressure gradient is 0 too. Then you just get a Laplace's equation:
$$\nabla^{2} \vec{u} = 0$$
Generally you should know the solution to Laplace's equation from E&M. 
### Bernoulli's Equations
This first equation is really just conservation of energy:
$$p_{1} + \frac{1}{2}\rho v_{1}^{2} +\rho gh_{1} = p_{2} + \frac{1}{2}\rho v_{2}^{2} +\rho gh_{2}$$
This second equation says area times velocity is a constant: 
$$v_{1}A_{1} = v_{2}A_{2}$$
## Diffusion Equation/ The Heat Equation
The diffusion equation with diffusion $D$:
$$\frac{\partial u(x,t)}{\partial t} = D\nabla^{2}u(x,t) $$
Notice this is actually identical to the Schrödinger equation (with no potential) and is also known as the heat equation. This can be solved with separation of variables giving a solution like $\sin$ in time and $e^{-t}$ in time. This can also be solved using Fourier transforms. 