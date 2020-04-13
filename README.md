# AAE_Notebook_031_3dDrone
As a further continuation of the 3d Drone exercise, we're now going to place the final piece by integrating pqr into the world frame.

## Integrating PQR Into World Frame

In the last notebook, we used the equation M = I(omega_dot) + omega x (I(omega)). From there, we could perform an integration of omega_dot to figure out the new p_dot, q_dot, and r_dot. This is analogous to using the linear accelerations to update the linear velocity and means that nine of our twelve variables have been updated. All that remains is to update our Euler angles phi, theta, and psi.

![PQR To World Frame](/images/pqr_to_world_frame.png)

Since p, q, and r are not the same as phi_dot, theta_dot, and psi_dot, this is not a straight-forward integration. The equation we care about, equation 79 from the [article](https://www.astro.rug.nl/software/kapteyn-beta/_downloads/attitude.pdf), is ...

![Equation](/images/pqr_world.png)

Conceptually, what this equation does is relates and instantaneous turn-rate in the body frame to an instantaneous change to the Euler angles. (Note that we're using Euler angles because they have a more intuitive interpretation than quaternions.) 

***   ***   ***   ***   ***   ***   ***   ***   ***

Feel free to skim through sections I - III of [Feasibility of Motion Primatives for Choreography](http://flyingmachinearena.org/wp-content/publications/2011/schoellig_feasibility_of_motion_primitives.pdf); as, it provides a good summary of some of the concepts we've been discussing.

Note that this paper uses slightly different notation than what we've been using in some parts. Most notably, where we've represented the Euler Angles with ϕ,θ,ψ this paper uses α,β,γ.
