COHMPA model
================================

Overview
---------
The “COmpressible Hall Magnetohydrodynamics simulations for Plasma Astrophysics” (COHMPA)[1]_ is a pseudo-spectral algorithm which solves the three-dimensional magnetohydrodynamics equations on a three-periodic Cartesian domain. It eventually includes the Hall and the electron pressure terms in the induction equation for the magnetic field. COHMPA exploits a MPI-based parallelization and employs fast Fourier transform routines (FFTW).

COHMPA can efficiently tackle scientific questions on plasma turbulence at large scales or the interplay between magnetic structures (flux tubes, coronal loops) and turbulence.

Developer team: Oreste Pezzi (National Research Council of Italy), Sergio Servidio (University of Calabria), Francesco Pucci (National Research Council of Italy), Claudio Meringolo (Institut für Theoretische Physik)

+------------------------+---------------------------------------------------------------------+
| WG Point of Contact    | Oreste Pezzi, Francesco Pucci                                       |
+------------------------+---------------------------------------------------------------------+
| Current code version   |                                                                     |
+------------------------+---------------------------------------------------------------------+
| code/repository        | Not publicly available                                              |
+------------------------+---------------------------------------------------------------------+
| Legal Code License     | N.A.                                                                |
+------------------------+---------------------------------------------------------------------+
| Software code          | Mainly Fortran.                                                     |
| languages and tools    | Fortran and Python scripts are available for post-processing.       |
+------------------------+---------------------------------------------------------------------+

Use cases
---------

COHMPA has been recently employed to study how a large-scale flux rope mediates turbulent energy transfer, particle transport and energization in space plasmas[1]_. COHMPA is also being used to study how energy is dissipated in coronal loops [2]_. Finally, fully-developed turbulent flow produced with COHMPA has been adopted to mimic the pre-existing turbulence upstream of a shock, thus investigating the interaction of shock and turbulence in space and astrophysical contexts [3]_.

Data availability
-----------------

Upon request and based on collaborations.

Simulations-on-demand
---------------------

Yes.

Numerical Methods
-----------------

COHMPA, whose development starts from previous 2D versions [4]_,[6]_, assumes periodic boundary conditions. A logarithmic regularization of the density is adopted to better describe flow discontinuities. Being a pseudo-spectral method, the right-hand side of MHD equations is computed through FFT routines. Spatial derivatives are computed in the Fourier space, while products between variables are calculated in physical space. Then, the time evolution is performed in physical space through a second-order Runge-Kutta scheme. Standard dealiasing procedures are implemented. Both physical viscosity and resistivity and (unphysical) hyper-viscous/resistive terms are implemented in the COHMPA code. Further details can be found in Ref. [1]_.


References
----------

.. [1] Pezzi, O. et al. Turbulence and particle energization in twisted flux ropes under solar-wind conditions. Astron. Astrophys. 686, A116 (2024). `<https://doi.org/10.1051/0004-6361/202348700>`_
.. [2] Meringolo, C. et al. Joint action of phase mixing and nonlinear effects in MHD waves propagating in coronal loops. Astron. Astrophys. 688, A12 (2024). `<https://doi.org/10.1051/0004-6361/202349094>`_
.. [3] Trotta, D. et al. Three-dimensional modelling of the shock–turbulence interaction. Mon. Not. R. Astron. Soc. 525, pp. 1856-1866 (2023). `<https://doi.org/10.1093/mnras/stad2384>`_
.. [4] Perri, S. et al. Numerical Study on the Validity of the Taylor Hypothesis in Space Plasmas. Astrophys. J. Suppl. Ser. 231, 4 (2017). `<https://doi.org/10.3847/1538-4365/aa755a>`_
