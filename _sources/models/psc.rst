PSC
================================

Plasma Simulation Code [PSC] [1]_ is a 3-dimensional fully electromagnetic particle-in-cell code for kinetic plasma simulations. It supports Nvidia GPUs and patch-based dynamic load balancing.

The table below has links to documentation.

+------------------------+---------------------------------------------------------------------+
| Additional information | `GitHub <https://github.com/psc-code/psc>`_                         |
| (table as              |                                                                     |
| placeholder)           |                                                                     |
+------------------------+---------------------------------------------------------------------+
| WG Point of Contact    | Jeffersson Agudelo Rueda                                            |
+------------------------+---------------------------------------------------------------------+
| Current code version   |    Under development                                                |
+------------------------+---------------------------------------------------------------------+
| code/repository        |     `GitHub <https://github.com/psc-code/psc>`_                     |
+------------------------+---------------------------------------------------------------------+
| Legal Code License     |                                                                     |
+------------------------+---------------------------------------------------------------------+
| Software code          | C++                                                                 |
| languages and tools    |         `<https://psc.readthedocs.io/en/latest/>`_                  |
+------------------------+---------------------------------------------------------------------+

Use cases
---------

PSC has been used to perform kinetic simulations of magnetic field generation and collisionless shock formation in expanding laboratory plasmas [2]_, to study the formation of magnetic holes in the Earth's magnetosheath [3]_, to study 3D magnetic reconnection events that occur as a result of the turbulent dynamics in the context of the solar wind [4]_, to study the effect of kinetic-scale fluctuations on a Harris current sheet [5]_ and to study intermittency in simulations of turbulence using a multi-spacecraft analysis [6]_.

.. image:: Images_PSC/Agudelo_Rueda_2021_fig4.png
  :width: 400
  :alt: Figure from a simulation.

Three-dimensional rendering of the magnetic-field component Bz (a) and the magnitude of the current density \|J\| (b) from a 3D simulation of anisotropic turbulence. Adapted from [4]_.

Data availability
-----------------

Data publically available on `Zenodo <https://zenodo.org/records/4313310>`_

Adittional data available via collaboration. 

Simulations-on-demand
---------------------

Simulations can be done on an on-demand basis.

Numerical Methods
-----------------

The Plasma Simulation Code is an explicit code that solves the equations of motion for the quasi-particles and self-consistently evolves the electromagnetic fields using Maxwell's equations. It employs a finite-difference time domain (FDTD) scheme and it uses the staggered Yee grid to represent magnetic fields on faces, electric fields and current densities on edges, and charge densities on corners of the computational mesh. It uses standard leapfrog method to advance quasi-particles.


References
----------

.. [1] Germaschewski, Kai, et al. "The Plasma Simulation Code: A modern particle-in-cell code with patch-based load-balancing." Journal of Computational Physics 318 (2016): 305-326. `<https://doi.org/10.1016/j.jcp.2016.05.013>`_
.. [2] Fox, W., et al. "Kinetic simulation of magnetic field generation and collisionless shock formation in expanding laboratory plasmas." Physics of Plasmas 25.10 (2018). `<https://doi.org/10.1063/1.5050813>`_
.. [3] Ahmadi, Narges, Kai Germaschewski, and Joachim Raeder. "Simulation of magnetic holes formation in the magnetosheath." Physics of Plasmas 24.12 (2017). `<https://doi.org/10.1063/1.5003017>`_
.. [4] Agudelo Rueda, Jeffersson A., et al. "Three-dimensional magnetic reconnection in particle-in-cell simulations of anisotropic plasma turbulence." Journal of Plasma Physics 87.3 (2021): 905870228. `<https://doi.org/10.1017/S0022377821000404>`_
.. [5] Agudelo Rueda, Jeffersson A., et al. "On the Effect of Driving Turbulent-like Fluctuations on a Harris Current Sheet Configuration and the Formation of Plasmoids." The Astrophysical Journal 971.1 (2024): 109. `<https://doi.org/10.3847/1538-4357/ad5e73>`_
.. [6] Guerrero Guio, Andres F., Jeffersson A. Agudelo Rueda, and Santiago Vargas Domínguez. "Exploring intermittency in numerical simulations of turbulence using single and multi-spacecraft analysis." Frontiers in Astronomy and Space Sciences 11 (2024): 1323993. `<https://doi.org/10.3389/fspas.2024.1323993>`_

