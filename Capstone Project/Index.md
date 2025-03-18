
## Application of Local Time-Stepping for Adaptive Mesh Refinement in Simulated Binary Neutron Star Mergers.

| ID                                             | Name                                                                                                           |     |
| ---------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | --- |
| [2404.11346](https://arxiv.org/pdf/2404.11346) | Modern tools for computing neutron star properties                                                             |     |
| [2502.05513](https://arxiv.org/pdf/2502.05513) | The Equation of State of Neutron Stars: Theoretical Models, Observational Constraints, and Future Perspectives |     |


### Neutron Stars
Neutron stars (NS) are among the most interesting astrophysical objects, as their description requires both general relativity and nuclear physics. [2404.11346](https://arxiv.org/pdf/2404.11346)

NSs are distinguished individuals with different surface temperature, magnetic field strengths and topologies, rotation rates, and propensity for glitches or radiation outbursts. [2404.11346](https://arxiv.org/pdf/2404.11346)

(For MMA) Computing NS properties for a given EOS, such as mass, radius, moment of inertia, tidal deformability, and , is therefore an important task. [2404.11346](https://arxiv.org/pdf/2404.11346)

**Properties of a Neutron Star:**
 - Gravitational Mass
	 - Completely determines the metric outside the NS. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Baryonic Mass
	 - expresses the baryon number in units of mass. [2404.11346](https://arxiv.org/pdf/2404.11346)
	 - important as a conserved quantity... in neutron star mergers. [2404.11346](https://arxiv.org/pdf/2404.11346)
	 - NS mass is bounded, maximum mass depends on the EOS. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Binding Energy
	 - The difference between baryonic and gravitational mass. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Proper Circumferential Radius
	 - Expresses the NS size. [2404.11346](https://arxiv.org/pdf/2404.11346)
	 - Determines surface area. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Compactness
	 - Ratio of gravitational mass over proper circumferential radius. [2404.11346](https://arxiv.org/pdf/2404.11346)
	 - Directly determines the surface redshift. [2404.11346](https://arxiv.org/pdf/2404.11346)
	 - Strongly correlated with oscillation frequencies, moment of inertia, or tidal deformability.. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Moment of Inertia
	 - Answers questions related to spin-down or glitches. [2404.11346](https://arxiv.org/pdf/2404.11346)
	 - Determines lowest order rotational corrections to metric. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Tidal Deformation
	 - Proportionality factor between external tidal fields and induced quadrupole moment. [2404.11346](https://arxiv.org/pdf/2404.11346)
	 - Important for late in-spiral phase of BNS mergers. Determines main corrections to orbital dynamics. [2404.11346](https://arxiv.org/pdf/2404.11346)
	 - Corrections, compared to binary black hole mergers lead to gravitational wave signals [2404.11346](https://arxiv.org/pdf/2404.11346).
 - Innermost Stable Circular Orbits (ISCO)




### Historical Solutions to EOS
 - The equations governing mass and radius of nonrotating neutron stars (NS) are known since the early work by [1](http://dx.doi.org/10.1103/PhysRev.55.364), [2](http://dx.doi.org/10.1103/PhysRev.55.374). [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Not all solutions for static NS are stable against radial perturbations. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - The single parameter sequence of NS consists of one or more stable and unstable branches, which depends on the EOS [3](http://dx.doi.org/10.1086/148791). [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Moment of inertia were derived by [4](http://dx.doi.org/10.1086/149400) for slowly rotating NS.  [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Tidal deformability have been derived in [5–8]. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - The computation of (moment of inertia and tidal deformation) requires the solution of an ordinary differential equation system (ODE) with singular boundary conditions. [2404.11346](https://arxiv.org/pdf/2404.11346)


### Complications in EOS
 - Phase transitions in the EOS, which can lead to discontinuities in the energy density as function of pressure. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Continuous transitions don't cause issues (mostly). [2404.11346](https://arxiv.org/pdf/2404.11346)
 - A true discontinuity can be treated analytically for the tidal deformability ODE [9, 10].

### Multi-Messenger Astronomy
Observations of radio or gamma-ray pulsars, accreting neutron stars and x-ray bursts, magnetar giant flares, and recently, the gravitational waves (GW) from coalescing binary neutron stars. [2404.11346](https://arxiv.org/pdf/2404.11346)

Measurements of NS properties can help to constrain the equation of state (EOS) of neutron star matter. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Any measurement of a NS mass provides a lower bound for the maximum NS mass. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Measurement of mass-radius relations by electromagnetic observations (see, e.g., [11–13]). [2404.11346](https://arxiv.org/pdf/2404.11346) 
 - The moment of inertia can constrain the EOS via observation of double pulsar systems [14].  [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Measurement of mass and tidal deformability using observations of gravitational waves from BNS coalescence, such as the famous event GW170817 [15– 20]. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Further, the stability of BNS merger remnant is related to the maximum NS mass. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - If electromagnetic counterparts in a BNS multi-messenger observation carry information on the fate of the remnant, it can be used to constrain the EOS. This was already done (under additional assumptions) using the short gamma ray burst associated with GW170817 [21]. [2404.11346](https://arxiv.org/pdf/2404.11346)



### Software Stuff
 - Despite the astrophysical importance of computing NS properties, the available software infrastructure is very limited. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - This task is unnecessarily difficult because relevant formulas are scattered throughout the literature and publicly available software tools are far from being complete and easy to use. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - computing NS properties as part of the library RePrimAnd. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - RePrimAnd was developed to support general relativistic magnetohydrodynamics simulations [23]. [2404.11346](https://arxiv.org/pdf/2404.11346)



### Equations:

Stress Energy of a perfect fluid ([2404.11346](https://arxiv.org/pdf/2404.11346))
$$\begin{align}
T_{\mu\nu}&=(E+P)u_\mu u_\nu + P g_{\mu\nu}
\end{align}$$
Where $u$ is the 4-velocity of the fluid, $E$ is total energy density in rest frame of the matter, and $P$ is the pressure. Approximation of isotropic pressure, and exclude any shear-stresses. This is commonly neglected in Tidal Deformation calculations.
Parameters ([2404.11346](https://arxiv.org/pdf/2404.11346)):
$$\begin{align}
\rho&=m_Bn_B\\
\epsilon&=\dfrac{E-\rho}{\rho}\\
h&=\dfrac{E+P}{\rho}=1+\epsilon+\dfrac{P}{\rho}
\end{align}$$


### Equation of State
(nuclear physics) comes into play via the equation of state (EOS) of matter up to densities exceeding nuclear saturation density. [2404.11346](https://arxiv.org/pdf/2404.11346)
The EOS is assumed to be universal, i.e., not dependent on the star’s origin. [2404.11346](https://arxiv.org/pdf/2404.11346)

Given a thermodynamic potential and its canonical state variables, one can derive all other quantities. Such derived relations are collectively referred to as equation of state (EOS). [2404.11346](https://arxiv.org/pdf/2404.11346)
#### Equation of State (Helmholtz)
We can parametrize the EOS as functions [2404.11346](https://arxiv.org/pdf/2404.11346):
 - $F(V,T,N_i)$ is the Helmholtz Free Energy.
 - $P(\rho, T, Y_e)=\dfrac{\partial F}{\partial V}$ : Pressure
 - $S(\rho, T, Y_e)=\dfrac{\partial F}{\partial T}$ : Entropy
 - $E(\rho, T, Y_e)=F+TS$ : Internal Energy





NS matter has three degrees of freedom [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Usually parametrized in terms of baryon number density $n_B$, temperature $T$, and electron fraction $Y_e$.  [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Assumes macroscopic charge neutrality (since astrophysical objects are assumed to carry negligible net charge) [2404.11346](https://arxiv.org/pdf/2404.11346)
 - Assumes NS matter is highly conductive.  [2404.11346](https://arxiv.org/pdf/2404.11346)


The variables $n_B$ and $Y_e$ are equivalent to the thermodynamic state variables V (volume) and particle numbers $N_i$ for protons and neutrons. [2404.11346](https://arxiv.org/pdf/2404.11346)

The behavior of matter is completely described by a single thermodynamic potential, meaning a scalar function of a particular set of state variables. [2404.11346](https://arxiv.org/pdf/2404.11346)

There are different but completely equivalent thermodynamic potentials, each based on a different set of state variables. When using state variables (V, T, Ni), the corresponding potential is the Helmholtz free energy F(V, T, Ni). [2404.11346](https://arxiv.org/pdf/2404.11346)

It should be noted that one cannot chose the various EOS functions independently. The existence of a thermodynamic potential implies thermodynamic consistency constraints. For example, -∂P/∂T = ∂S/∂V = ∂ 2F/∂T ∂V . If those constraints are violated, an EOS is physically invalid. [2404.11346](https://arxiv.org/pdf/2404.11346)








#### Barotropic EOS
 - Pressure and energy density can be expressed as functions $P(\rho)$ and $E(\rho)$ of the mass density alone. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - employing a barotropic EOS means that two of the matter degrees of freedom are restricted somehow. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - where thermal effects can be neglected and one can set $T = 0$ for all practical purposes.  [2404.11346](https://arxiv.org/pdf/2404.11346)
 - model equilibrium models. For those, the electron fraction becomes a function of density because weak processes drive the matter towards β-equilibrium. [2404.11346](https://arxiv.org/pdf/2404.11346)
 - For perturbed NS, β-equilibrium is maintained if the perturbation timescale is much longer than the intrinsic timescales of weak processes. [2404.11346](https://arxiv.org/pdf/2404.11346)
**Equation of State:**
$$\begin{align}
\dfrac{\text{d}E}{\text{d}\rho}&=h & \dfrac{\text{d}\epsilon}{\text{d}\rho}&=\dfrac{P}{\rho^2} & \dfrac{\text{d}h}{\text{d}P}&=\dfrac{1}{\rho}\\
\end{align}$$
$$\begin{align}
c_s^2&=\dfrac{\text{d}P}{\text{d}E}=\dfrac{1}{h}\dfrac{\text{d}P}{\text{d}\rho}\\
0&\le c_s^2 < 1
\end{align}$$
Where $c_s$ is the adiabatic speed of sound, which for isentropic barotropic has that equiv.
























