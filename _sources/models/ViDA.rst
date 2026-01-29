ViDA - Vlasov–DArwin
================================

Overview
---------
ViDA[1]_ is a massively-parallelized fully-kinetic Eulerian Vlasov-Darwin code. It solves the Vlasov equation of both protons and electron distribution functions in the full six-dimensional (3D-3V, three physical space dimensions and three velocity space dimensions) phase-space. The Vlasov equations are coupled to the Maxwell system, numerically integrated under the Darwin approximation. By neglecting the transverse displacement current the Darwin approximation retains all plasma modes but the propagation of light waves, the latter requiring a very small time-step and, hence, increasing the computational cost of the simulations. ViDA exploits a hybrid parallelization based on MPI, OpenMP, and CUDA.

ViDA has been developed to study electron-scale plasma physics relevant for important scientific topics including magnetic reconnection and plasma turbulence. Thanks to detailed and clean description of small-scale dynamics in the entire phase space, ViDA can tackle issues such as energy conversion and dissipation in nearly-reversible space plasmas.

Developer team: Oreste Pezzi (National Research Council of Italy), Davide Manzini (Queen Mary University of London), Francesco Califano (University of Pisa)

+------------------------+---------------------------------------------------------------------+
| WG Point of Contact    | Oreste Pezzi                                                        |
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

ViDA is currently utilized to address important aspects of electron-scale physics in magnetic reconnection and turbulence. The former is initialized with Harris-like current sheets, the latter can be investigated both in freely-decaying and forced conditions. Scientific papers on these scientific cases are currently in preparation.

Data availability
-----------------

Upon request and based on collaborations.

Simulations-on-demand
---------------------

No.

Numerical Methods
-----------------

ViDA assumes periodic boundary conditions in physical space while the velocity distribution function is set to zero at the velocity-space boundaries. Hence, velocity-space boundaries are usually a large multiple of the particle thermal speed (5-6). The Vlasov equations are solved through the splitting algorithm [2]_ which splits the multi-advection Vlasov equation in phase space into six one-dimensional advection equations in each phase-space direction ($x$, $y$, $z$, $v_x$, $v_y$, and $v_z$). Each one-dimensional equation is then integrated the through third-order van Leer scheme. The Maxwell system of equations, simplified through the Darwin approximation, is rewritten as a set of Poisson and Helmholtz-like equations which are integrated exploiting the periodic boundary conditions and implementing standard fast Fourier transforms (FFT). Further details can be found in Ref. [1]_.


References
----------

.. [1] Pezzi, O. et al. ViDA: a Vlasov–DArwin solver for plasma physics at electron scales. J. Plasma Phys 85, 905850506 (2019). `<https://doi.org/10.1017/S0022377819000631>`_
.. [2] Mangeney, A. et al. A numerical scheme for the integration of the Vlasov–Maxwell system of equations. J. Comput. Phys. 179, 495–538 (2002). `<https://doi.org/10.1006/jcph.2002.7071>`_
