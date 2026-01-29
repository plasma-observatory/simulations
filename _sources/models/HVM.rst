HVM - Hybrid Vlasov-Maxwell
================================

Overview
---------
HVM [1]_ is a massively-parallelized fully-kinetic Eulerian hybrid Vlasov-Maxwell code. It solves the Vlasov equation for protons in the full six-dimensional (3D-3V, three physical space dimensions and three velocity space dimensions) phase-space. Electrons are treated as a background charge-neutralizing fluid. The proton Vlasov equation is coupled to the Maxwell system, simplified by assuming charge neutrality and neglecting the displacement current. HVM exploits a hybrid parallelization based on MPI, OpenMP, and CUDA.

HVM has provided important insights on ion-scale phenomena, including kinetic-scale plasma turbulence [2]_ and reconnection [3]_, energy conversion and dissipation in space plasmas [4]_. Several code developments have been included in the last years to take into account (i) the dynamics of heavy ions (alpha particles) [5]_, (ii) anisotropic electron closures [6]_, and (iii) proton-proton interparticle collisions [7]_.

Developer team: Francesco Califano (University of Pisa), Silvio Cerri (Observatoire de la Côte d'Azur), Oreste Pezzi (National Research Council of Italy), Francesco Valentini (University of Calabria).

+------------------------+---------------------------------------------------------------------+
| WG Point of Contact    | Silvio Cerri, Oreste Pezzi                                          |
+------------------------+---------------------------------------------------------------------+
| Current code version   |                                                                     |
+------------------------+---------------------------------------------------------------------+
| code/repository        | Not publicly available                                              |
+------------------------+---------------------------------------------------------------------+
| Legal Code License     | N.A.                                                                |
+------------------------+---------------------------------------------------------------------+
| Software code          | Mainly Fortran.                                                     |
| languages and tools    | Fortran, IDL, and Python scripts are available for post-processing. |
+------------------------+---------------------------------------------------------------------+

Use cases
---------

HVM has been massively used to study ion-scale plasma turbulence and energy dissipation in turbulent plasmas, magnetic reconnection, magnetic dynamo, instabilities onset and wave propagation at ion scales.

Data availability
-----------------

Upon request and based on collaborations.

Simulations-on-demand
---------------------

No.

Numerical Methods
-----------------

HVM assumes periodic boundary conditions in physical space while the velocity distribution function is set to zero at the velocity-space boundaries. Hence, velocity-space boundaries are usually a large multiple of the particle thermal speed (5-6). The proton Vlasov equation is solved through the splitting algorithm [8]_ which splits the multi-advection Vlasov equation in phase space into six one-dimensional advection equations in each phase-space direction ($x$, $y$, $z$, $v_x$, $v_y$, and $v_z$). Each one-dimensional equation is then integrated the through third-order van Leer scheme. The current advance method with cyclic leapfrog (CAM-CL), improved for the hybrid approximation, is implemented for the calculation of electromagnetic ﬁelds. The Maxwell system of equations is simplified by assuming charge neutrality and by neglecting the displacement current. The generalized Ohm's law, which can include also electron inertia terms, allows to calculate the electric field while Faraday equation is exploited to advance the magnetic field. Further details can be found in Ref. [1]_.


References
----------

.. [1] Valentini, F. et al. A hybrid-Vlasov model based on the current advance method for the simulation of collisionless magnetized plasma. J. Comput Phys. 225, p. 753-770 (2007). `<https://doi.org/10.1016/j.jcp.2007.01.001>`_
.. [2] Servidio, S. et al. A kinetic model of plasma turbulence. J. Plasma Phys. 81, 325810107 (2015). `<https://doi.org/10.1017/S0022377814000841>`_    
.. [3] Finelli, F. et al. Bridging hybrid- and full-kinetic models with Landau-fluid electrons. I. 2D magnetic reconnection. Astron. Astrop. 653, A156 (2021). `<https://doi.org/10.1051/0004-6361/202140279>`_
.. [4] Pezzi, O. et al. Dissipation measures in weakly collisional plasmas. Mon. Not. R. Astron. Soc. 505, pp. 4857-4873 (2021). `<https://doi.org/10.1093/mnras/stab1516>`_
.. [5] Perrone, D. et al. Vlasov Simulations of Multi-ion Plasma Turbulence in the Solar Wind. Astrophys. J. 762, 99 (2013). `<https://doi.org/10.1088/0004-637X/762/2/99>`_
.. [6] Granier, C. et al. Electron-only Reconnection and Ion Heating in 3D3V Hybrid-Vlasov Plasma Turbulence. Astrophys. J. 974, 11 (2024). `<https://doi.org/10.3847/1538-4357/ad6a19>`_
.. [7] Pezzi, O. et al. Proton-Proton Collisions in the Turbulent Solar Wind: Hybrid Boltzmann-Maxwell Simulations. Astrophys. J. 887, 208 (2019). `<https://doi.org/10.3847/1538-4357/ab5285>`_
.. [8] Mangeney, A. et al. A numerical scheme for the integration of the Vlasov–Maxwell system of equations. J. Comput. Phys. 179, 495–538 (2002). `<https://doi.org/10.1006/jcph.2002.7071>`_

