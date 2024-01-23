# BEMT Derivation 
By Vishal Gautam
February, 2023
## Actuator Disk Theory:
- **Assumptions**
	- neglect any rotational flow imparted to the fluid
	- incompressible flow at low mach numbers
	- flow outside the propeller streamtube has constant stagnation pressure (no work has been done on it)
	- steady flow (blades are smeared)
	- the velocities across the disk vary in a continious manner, but the pressure changes discontinuously
	 ![042155250968ee125fc2b57e338c5bda.png](../_resources/042155250968ee125fc2b57e338c5bda.png)
	 ![71c9645be4efaddc21a9784226d90c1a.png](../_resources/71c9645be4efaddc21a9784226d90c1a.png)
- **Power Due to Momentum**
	- The power expanded is equal to the change in kinetic energy as the fluid passes through the propeller and through the control volume
	 $$ P = \frac{1}{2}\dot{m}(V_e^2 - V_0^2) $$
	- where $P$ is the power in Watt, $\dot{m}$ is the mass flow rate in kg/s, $V_e$ is the exit velocity and $V_0$ is the upstream velocity in m/s.
	$$ \dot{m} = \rho A V $$
- **Power Due to Thrust**
	- Power expanded can also be calculated by taking into account the Thrust applied to the fluid and the velocity of the fluid:
	$$ P = TV_{disk} = A_{disk}(P_2 - P_1)V_{disk} = \dot{m}(V_e - V_0)V_{disk} $$
	$$ \frac12W(V_e^2 - V_0^2) = \dot{m}(V_e - V_0)V_{disk} $$
	$$ V_{disk} = \frac{V_e + V_0}{2} $$
	- for verificaiton of the same, dimensional analysis can be done.
- **Thrust, Power and Efficiency using Bernoulli**
	- **Applying Bernoulli Upstream and Downstream**
		- We apply Bernoulli's equation for total pressure where there is no discountinuity in pressure and velocity
		$$ p_1 - \frac12 \rho V_{disk}^2 = p_0 + \frac12 \rho V_0^2 (=) \frac12 \rho V_{disk}^2 - p_0 = \frac12 \rho V_0^2 - p_1 $$
		$$ p_2 - \frac12 \rho V_{disk}^2 = p_0 + \frac12 \rho V_e^2 (=) \frac12 \rho V_{2}^2 - p_0 = \frac12 \rho V_e^2 - p_2 $$
		$$ \frac12 \rho V_{e}^2 - p_2 = \frac12 \rho V_0^2 - p1 $$
		$$ p_2 - p_1 = \frac12 \rho (V_e^2 - V_0^2) $$
		- This means that the difference between the static pressure just before and after the disk is equal to the difference in the dynamic pressure, very far downstream and very far upstream of the disk.
		- $V_{disk}$ is not a measurable value, it is in our interest to remove it.
		- This is because the a porpeller is not a disk and measuring the velocity at the propeller is not very simple.
	- **Calculating Thrust from Continuity**
		- We know that: $T = \dot{m} (V_e - V_0)$ and $W = \rho A_{disk} V_{disk}$
		- Hence,
		$$ \dot{m} = \frac{\rho A_{disk}(V_e + V_0)}{2} $$
		$$ T = \frac12 \rho A_{disk}(V_e^2 - V_0^2) $$
	- **Minimum Power Required for Thrust**
		- we can express the exit velocity as
		$$ \left( \frac {V_e}{V_0} \right)^2 = \frac{T}{\frac12 \rho A_{disk}V_0^2}+1 $$
		- knowing that $V_{disk} = \frac12 (V_e + V_0)$ we can write
		$$ V_{disk} = \frac{V_0}{2} \sqrt{ \frac{T}{\frac12 \rho A_{disk}V_0^2}+1}+\frac{V_0}{2} $$
		- Thus, minimum powre required for specific thrust is:
		$$ P = TV_{disk} = \frac{TV_0}{2} \sqrt{ \frac{T}{\frac12 \rho A_{disk}V_0^2}+1}+\frac{TV_0}{2} $$
	- **Efficiency**
		- Propulsive efficiency, is the measure of how much of the power given to the propeller isconverted to thrust:
		$$ \eta_{propulsive} = \frac{2}{1 + \frac{V_e}{V_0}} = \frac{2}{1 + \left(\frac{T}{\frac12 \rho A_{disk}V_0^2}+1 \right)^{\frac12}} $$
		
- **Dimensionless Numbers**
	- **Advance Ratio**
		- distance advanced per revolution
		$$ J = \frac{V_0}{nD} $$
		- With $J$ is the advance ratio, $n$ is the revolutions per second and $D$ is the diameter of the propeller
	- **Thrust Coefficient**
		$$ T = k_T \rho n^2 D^4 $$
		- with $T$ the thrust in $N$ and $\rho$ is the density in $\frac{kg}{m^3}$ and $k_T$ is the thrust coefficient, a function of propeller design, Reynolds number, tim Mach number and Advance Ratio.
	- **Torque Coeffieient**
		$$ Q = k_Q \rho n^2 D^5 $$
		- with $Q$ as the torque in $Nm$ and $k_Q$ the torque coefficient, a function of propeller deisgn, Reynolds number, tip Mach number and Advance Ratio.  
	- **Propulsive Efficiency**
		- the ratio of useful power out to mechanical power supplied to the shaft:
		$$ \eta_{propulsion} = \frac{P_{out}}{P_{in}} = \frac{TV_0}{2 \pi n Q} = \frac{k_T \rho n^2 D^4 V_0}{k_Q \rho n^2 D^5 2 \pi n} = \frac{1}{2 \pi} \frac{k_T}{k_Q} J  $$
		
## Blade Element Theory:
- **Definition** 
	- unlike Actuator Disk Theory, Blade Element Theory allows to take into account the shape of the blades
	- the blade being studied is divided into a number of small sections along its length that act independently of surrounding elements
	- considers the flow as two dimensional
	- words well for lightly loaded two or three bladed propellers, except near the hub 
	![bae059484602d06cb96adcd6dfe12922.png](../_resources/bae059484602d06cb96adcd6dfe12922.png)
	 
- **Solidity & Validity**
	- Individual propeller baldes can be assumed to operate in isolation without interference from other blades when the spacing-to-chrod ratio is sufficiently high:
	$$ \frac{s}{c} >> 1 $$
	- with $s$ the spacing or the circumferential distance between the blades, and the chord $c$ the width of the blade between its leading and trailing edge.
	- **Solidity**
		$$ \sigma = \frac{B.c}{\pi.r} $$
		- with $B$ the number of blades and $r$ the radius
		- Blade Element Theory is only valid if $\sigma << 1$
- **Blade Elements**
	![5e1e18c46e32a73ed00c6d2d03b8651c.png](../_resources/5e1e18c46e32a73ed00c6d2d03b8651c.png)
	- Propeller blades are divided into smaller elements and secions
	- A force balance is applied to each section to produce Life and Drag and therfore the propeller's Thrust and Torque
	- The section local flow velocity is the vector summation of the axial flow velocity $V_{ax}$ and the angular flow velocity $V_\theta$
	- As the propeller's blade are set at a given geometric pitch angle $\theta$, the local flow velocity creates a flow angle of attack $\alpha$
	- The difference in angle between the Life and thrust vectors is $\phi = \theta - \alpha$ 
	- Using basic trigonometry, we can write that the elemental thrust and circumferential force are respectively:
	$$ \Delta T = \Delta L * \cos\phi - \Delta D * \sin\phi $$
	$$ \Delta F_\theta = \Delta D * \cos\phi + \Delta L * \sin\phi $$
	- The torque required to turn that element of the blade is:
	$$ \Delta Q = r * \Delta F_\theta $$
	- with $r$ as the distance between the element and the axis of rotation of the propeller.
	
- **Sectional Aerodynamics**
	- we apply the Lift and Drag equations to each elements of out blades as follows:
	$$ \Delta L = \frac{\rho V^2}{2} * C_l * c * dr $$
	$$ \Delta D = \frac{\rho V^2}{2} * C_d * c * dr $$
	with $\rho$ the air density at sea level in $kg/m^3$, $V$ the air flow velocity in $m/s$, $c$ the chord in $m$ and $dr$ the elemental width in $m$.

- **Total Thrust and Torque**
	- From  the previous equations we can right for B blades:
	$$ \Delta T = \frac{\rho V^2}{2} * (C_l * \cos\phi - C_d * \sin\phi) * B * c * dr $$
	$$ \Delta Q = \frac{\rho V^2}{2} * (C_l * \sin\phi + C_d * \cos\phi) * B * c * r * dr $$

- **Real Axial and Radial Velocity**
	- $V_{ax}$ is roughly equal to the forward velocity of the aircraft but is increased b the propeller's own induced axial flow.
	- $V_\theta$ is roughly equal to the blade section's angular speed ($\Omega * R$) but is reduced slightly due to the swirling nature of the flow induced by the propeller
	- In order to calculate $V_{ax}$ and $V_\theta$ we apply both axial and angular momentum balances. 
	- The induced components can be defined as factors increasing or decreasing the major flow components.
	![a54918aaa75e169736fa19314c43421c.png](../_resources/a54918aaa75e169736fa19314c43421c.png)
	
	- **Inflow Factors**
		- The factors previously described can be applied as follows:
		$$ V_{ax} = (1 + a) * V_\infty $$ 
		$$ V_\theta = (1 - a_{\Omega}) * \Omega * r $$
		- with the axial inflow factor and $a_\Omega$ the angular inflow factor or swirl factor.
		- Using basic trigonometry the local flow velocity V and the angle of attack of the blades are given by:
		$$ V = \sqrt{V_{ax}^2 + V_{\theta}^2} $$
		$$ \alpha = \theta - \tan^{-1}\frac{V_{ax}}{V_{\theta}} $$ 
	
	- **Conservation of Axial Momentum**
		- Conservation of axial momentum on the area swept by the element over one rotation:
		$$ \Delta T = 2 \pi r * dr * \rho * V_{ax} * (V_s - V_{\infty}) $$
		- Won't be proven here (exercise) but applying Bernoulli can show that: $V_s = V_\infty * (1 + 2a)$
		- Hence, 
		$$ \Delta T = 2 \pi r * dr * \rho * V_{\infty} * (1 + a) * (V_{\infty}(1 + 2a) - V_\infty) $$ 
		- Therefore,
		$$ \Delta T = 4 * \pi * r * dr * \rho * V_\infty^2 * a * (1 + a) $$
		- Conversation of angular momentum leads to:
		$$ \Delta Q = \Delta F_\theta * r $$
		$$ \Delta Q = 2 \pi r * dr * \rho * V_{ax} * (V_{\theta,s} - V_{\theta, \infty}) * r $$
		- with $V_{\theta, s}$ the angular flow velocity in the slipstream and $V_{\theta, \infty}$ the angular flow velocity in the freestream ahead of the propeller.
		- Taking into account conservation of angular momentum and the axial velocity chagne, it can be shown that the angular velocity in the slipstream will be twice the value at the propeller disk,
		- hence:
		$$ V_{\theta, s} = 2 * a_\Omega * \Omega * r $$ 
		$$ V_{\theta, \infty} = 0 $$
		- Hence,
		$$ \Delta Q = (2 \pi r * dr * \rho * V_\infty * (1 + a) * (2 * a_\Omega * r)) * r $$
		- Thus,
		$$ \Delta Q = 4 \pi r* dr^3 * \rho * V_\infty * (1 + a) * a_\Omega * \Omega $$
		- These equaitons cannot be solved indepently as they contain too many unknows.
		- However, by combining them ito a system we can iteratively solve them and come up with a solution.

- **Iterative Solution Process**
	- An outine of the iterative solution 
		- an initial guess for the inflow factors $a$ and $a_\Omega$ is made
		- the initial guesses are used to find the flow angle on the blade element
		- then the blade section properties are used to produce a first estimate of the element thrust $\Delta T$ and torque $\Delta Q$
		- with these approximate values of thrust and torque, imporved estimates for the inflow factors are made
		- these steps are repeated in a while loop until the values for $a$ and $a_\Omega$ are converged within a specified tolerance
		- and when the solution converges, accurate predictions of $\Delta T$ and $\Delta Q$ for specific flight can be made.
* * *
* * *
* * *