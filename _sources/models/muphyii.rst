*muphyII* plasma simulation framework
=====================================

The *muphyII* code is a simulation framework for collisionless plasma physics and targeted at space plasmas in particular. The *muphyII* code utilizes a hierarchy of models with different inherent scales to address the separation of scales problem typically encountered in these plasmas. It allows stand-alone use of models as well as a model-based dynamic and adaptive domain decomposition and resorts to novel techniques for energy conservation, careful treatment of inner-domain model boundaries for interface coupling, and robust time stepping algorithms.

+------------------------+-------------------------------------------------------------+
| Additional information | [2]_                                                        |
+------------------------+-------------------------------------------------------------+
| WG Point of Contact    | Simon Lautenbach                                            |
+------------------------+-------------------------------------------------------------+
| Current code version   | 1.0                                                         |
+------------------------+-------------------------------------------------------------+
| code/repository        | `Zenodo <https://zenodo.org/doi/10.5281/zenodo.8061586>`_,  |
|                        | `GitHub <https://github.com/muphy2-framework/muphy2>`_      |
+------------------------+-------------------------------------------------------------+
| Legal Code License     | `MPL-2.0 <https://www.mozilla.org/en-US/MPL/2.0/>`_         |
+------------------------+-------------------------------------------------------------+
| Software code          | C++, Fortran, MPI, OpenACC                                  |
| languages and tools    |                                                             |
+------------------------+-------------------------------------------------------------+

Use cases
---------

*muphyII* has already been used in the study of a number of different scenarios of magnetic reconnection and decaying turbulence simulations [7]_ [8]_ [2]_. Current developments include extension of the model hierarchy and including AMR magnetohydrodynamic (MHD) models in *muphyII* with asymptotic preserving MHD-fluid coupling. Further two-fluid descriptions like a 14-moment system [9]_ or a gyrotropic fluid model might be added in the future.

Data availability
-----------------

There is no public data repository. Simulations intended to support Plasma Observatory will be made available to interested parties.

Simulations-on-demand
---------------------

Simulations are not generally offered on-demand. This excludes simulations requested for the support of Plasma Observatory.

Numerical Methods
-----------------

*muphyII* currently implements kinetic Vlasov-Maxwell, fluid 10-moment-Maxwell and fluid 5-moment-Maxwell models and provides up to five model combinations. These can be used standalone, statically coupled, or dynamically coupled. Here *static coupling* refers to prescribing a fixed model to each region, while *dynamic coupling* allows models to dynamically change in each region over the course of the simulation, based on predefined criteria that ideally identify the level of fidelity required in each spatial region [1]_ [3]_.

To account for differences of temporal scales in electron and ion physics, *muphyII* employs *electron subcycling*, i.e. the time discretization for electrons uses a smaller time step than for ions [2]_.

Maxwell's equations are solved on a Yee grid using the finite difference time domain (FDTD) method. The fluid models use a finite volume discretization with the centrally weighted essentially non-oscillatory (CWENO) reconstruction [4]_ and Runge-Kutta (RK3) time integration [5]_ and conserve mass, momentum, and energy by design. The Vlasov equation is solved with the third-order semi-Lagrangian positive flux-conservative (PFC) finite volume scheme [6]_ and conserves mass. A maximum-entropy moment matching technique using the advection of the Maxwellian part of the distribution function with a CWENO-RK3 scheme alongside the PFC Vlasov scheme reults in conservation of momentum and energy in addition to numeric mass conservation [1]_. The integration of a third-order Active Flux kinetic solver is under development.

References
-----------

.. [1] Lautenbach, S., & Grauer, R. (2018). Multiphysics simulations of collisionless plasmas. Front. Phys., 6, 113.
.. [2] Allmann-Rahn, F., Lautenbach, S., & Grauer, R. (2024). The *muphyII* code: Multiphysics plasma simulation on large HPC systems. Comp. Phys. Comm., 296, 109064.
.. [3] Lautenbach, S., & Grauer, R. (2021). Hierarchical fluid models for space plasma turbulence. Front. Phys., 9, 1537.
.. [4] Kurganov, A., & Levy, D. (2000). Third-order semidiscrete central scheme for conservation laws and convection-diffusion equations. SIAM J. Sci. Comput., 22(4), 1461-1488.
.. [5] Shu, C.-W., & Osher, S. (1988). Efficient implementation of essentially non-oscillatory shock-capturing schemes. J. Comput. Phys., 77(2), 439-471.
.. [6] Filbet, F., Sonnendrücker, E., & Bertrand, P. (2001). Conservative numerical schemes for the Vlasov equation. J. Comput. Phys., 172(1), 166-187.
.. [7] Allmann-Rahn, F., Grauer, R., & Lautenbach, S. (2021). Fluid modeling of three-dimensional magnetic reconnection through electron pressure anisotropy. Phys. Rev. E, 104(1), 015207.
.. [8] Allmann-Rahn, F., Lautenbach, S., & Grauer, R. (2022). Energy spectra in fully developed turbulence from two-fluid simulations. J. Plasma Phys., 88(5), 905880502.
.. [9] McDonald, S. W., & Grover, F. W. (2013). Affordable high-fidelity closures for modeling magnetic-confinement fusion plasmas. J. Comput. Phys., 235, 258-280.
