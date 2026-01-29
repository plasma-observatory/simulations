CAMELIA
================================
 
CAMELIA (Current Advance Method Et cycLIc leApfrog) [1]_ is a hybrid kinetic code where ions are described as macro-particles using a particle-in-cell model while electrons are considered as a massless charge-neutralising fluid.
 
It is based on the CAM-CL code by Alan Matthews [2]_.
 
+------------------------+---------------------------------------------------------------------+
| Additional information | `CAMELIA <https://https://www.asu.cas.cz/~helinger/camelia.html>`_  |
+------------------------+---------------------------------------------------------------------+
| WG Point of Contact    | Luca Franci                                                         |
+------------------------+---------------------------------------------------------------------+
| Current code version   | N/A                                                                 |
+------------------------+---------------------------------------------------------------------+
| Code/repository        | Unpublished/Closed-source                                           |
+------------------------+---------------------------------------------------------------------+
| Legal Code License     | N/A                                                                 |
+------------------------+---------------------------------------------------------------------+
| Software code          | Fortran + extensions of Fortran 95                                  |
| languages and tools    |                                                                     |
+------------------------+---------------------------------------------------------------------+
 

Use cases
---------
 
CAMELIA has been extensively used to model and study plasma turbulence, magnetic reconnection, kinetic instabilities, and particle energisation in collisionless space plasmas.
In particular, the turbulence studies have investigated how the turbulent cascade develops self-consistently from large fluid scales down to ion kinetic scales both in 2D [3]_ [4]_ and in 3D [5]_, how it is controlled by key parameters such as the plasma beta [6]_, and its interplay with magnetic reconnection [7]_ and with kinetic instabilities such as the firehose [8]_ and mirror [9]_ instabilities.
Numerical simulations performed with CAMELIA has been used to provide a turbulent plasma background on which to advance test-particle trajectories to investigate the acceleration of energetic electrons [10]_, to directly compare different complementary numerical models (Hall-MHD [11]_ [12]_, Hybrid-Vlasov [13]_ [14]_, and fully kinetic [15]_) and to compare numerical and observational data [16]_ [17]_, also obtaining a remarkable quantitative agreement with to in-situ spacecraft measurements in both the near-Earth space [18]_ and in the near-Sun space [19]_.

 
Data availability
-----------------
 
Some data is available publicly. More will be uploaded online over the next few months.

Access to data existing data, e.g., data associated to publications can be requested.
 
+------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------+
| Name       | Access                                                                                               | Used                                                                                 | Comments                                       |
+------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------+
| Dataset 1  | ` <https://b2share.eudat.eu/records/a58135af9c9d429f92c15ce88bdfdd55>`_                              | `Franci et al. ApJ 2016 <https://www.doi.org/10.3847/1538-4357/833/1/91>`_           | Magnetic field data from 2D hybrid simulations |
|            |                                                                                                      |                                                                                      | of plasma turbulence with 12 different values  |
|            |                                                                                                      |                                                                                      | of the plasma beta                             |
+------------+------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------+------------------------------------------------+

 
Simulations-on-demand
---------------------
 
CAMELIA is extremely efficient and performs very well on thousands of cores simultaneously, meaning that even quite big simulations can be run in just a few days on HPC systems (provided we have an active HPC allocation with enough computing time at the time of request).

Small/local simulations can be set up and supported for external users on best-effort basis.
 
We are always open for new collaborations.
 
Numerical Methods
-----------------
 
The ions are represented as a collection of macro-particles, i.e., portions of the ion velocity distributions functions with a fixed number of real ions that are close in phase space, whose positions and velocities are updated solving the usual equations of motion.
The electrons are represented as a fluid under specific assumptions: quasi-neutrality, negligible mass, constant temperature, and ideal gas law.
 
The plasma has only two time-dependent components: (i) ion macro-particles with their individual positions and velocities, and (ii) magnetic field specified at the nodes of the computational grid. The electric field is computed using the generalised Ohm's law, which is an equation of state with no time evolution.
 
The time derivative of a variable is evaluated at the midpoint of its time-step. Originally, the code implemented the Current Advance Method (CAM) for advancing the ion macro-particles and a Cyclic Leapfrog (CL) to evolve the magnetic field. Hence, its name CAMELIA (Current Advance Method Et cycLIc leApfrog). The CAM was replaced with the Boris method, that requires the fields to be known at half time steps ahead of the particle velocities.
 
CAMELIA is written in Fortran 77 with extensions in Fortran 95.
It includes 1D, 2D, and 3D versions.
Bi/trilinear interpolation/weighting is used to determine the interaction of a macro-particle with the computational grid and the deposition of its contribution to the particle moments (density, velocity, current density) on the computational grid.
An explicit form of the time-dependent differential equations is used.
Spatial derivatives are approximated by centred finite-differences (a version using spectral methods has been developed recently).
The code is parallelised via MPI using spatial and/or particle decompositions (the spatial decomposition could be in all spatial directions). It also implements a hybrid openMP/MPI parallelisation.
The output can be written in simple ASCII, binary, or HDF5 files, including parallel binary (MPI-IO) and parallel HDF5.
A checkpoint/restart procedure in parallel HDF5 allow us to run simulations exceeding the maximum wall-time of a single job.
A preliminary GPU version of the code, ported using OpenACC directives, is under development.

 
References
----------
 
.. [1] Franci, L., P. Hellinger, M. Guarrasi, C. H. K. Chen, E. Papini, A. Verdini, L. Matteini, and S. Landi, Three-dimensional simulations of solar wind turbulence with the hybrid code CAMELIA, J. Phys.: Conf. Ser., 1031, 012002, 2018 `<https://www.doi.org/10.1088/1742-6596/1031/1/012002>`_
.. [2] Matthews, A., Current advance method and cyclic leapfrog for 2D multispecies hybrid plasma simulations, J. Comput. Phys., 112, 102–116, 1994 `<https://www.sciencedirect.com/science/article/abs/pii/S0021999184710849>`_ 
.. [3] Franci et al., High-resolution hybrid simulations of kinetic plasma turbulence at proton scales, Astrophys J., 812(1):21, 2015, `<https://www.doi.org/10.1088/0004-637X/812/1/21>`_ 
.. [4] Franci et al., Solar wind turbulence from MHD to sub-ion scales: high-resolution hybrid simulations, Astrophys J. Lett., 804(2):L39, 2015, `<https://www.doi.org/10.1088/2041-8205/804/2/L39>`_
.. [5] Franci et al., Solar Wind Turbulent Cascade from MHD to Sub-ion Scales: Large-size 3D Hybrid Particle-in-cell Simulations, Astrophys J., 2018, `<853(1):26, https://www.doi.org/10.3847/1538-4357/aaa3e8>`_
.. [6] Franci et al., Plasma beta dependence of the ion-scale spectral break of solar wind turbulence: high-resolution 2D hybrid simulations, Astrophys J., 833(1):91, 2016, `<https://www.doi.org/10.3847/1538-4357/833/1/91>`_
.. [7] Franci et al.., Magnetic reconnection as a driver for a sub-ion scale cascade in plasma turbulence, Astrophys J. Lett., 850(1):L16, 2017, `<https://www.doi.org/10.3847/2041-8213/aa93fb>`_
.. [8] Hellinger et al., Plasma turbulence and kinetic instabilities at ion scales in the expanding solar wind, Astrophys J. Lett., 811(2):L32, 2015, `<https://www.doi.org/10.1088/2041-8205/811/2/L32>`_
.. [9] Hellinger et al., Mirror instability in the turbulent solar wind, Astrophys J., 838(2):158, 2017, `<https://www.doi.org/10.3847/1538-4357/aa67e0>`_
.. [10] Trotta et al., Fast acceleration of transrelativistic electrons in astrophysical turbulence, Astrophys J., 894(2):136, 2020, `<https://www.doi.org/10.3847/1538-4357/ab873c>`_
.. [11] Papini et al., Can Hall Magnetohydrodynamics Explain Plasma Turbulence at Sub-ion Scales?, Astrophys J. 870(1):52, 2019 , `<https://www.doi.org/10.3847/1538-4357/aaf003>`_
.. [12] Papini et al., Multidimensional Iterative Filtering: a new approach for investigating plasma turbulence in numerical simulations, J. Plasma Phys., 86(5), 871860501, 2020, `<https://www.doi.org/10.1017/S0022377820001221>`_
.. [13] Cerri et al., Plasma turbulence at ion scales: a comparison between PIC and Eulerian hybrid-kinetic approaches, J. Plasma Phys., 83(2):705830202, 2017,  `<https://www.doi.org/10.1017/S0022377817000265>`_
.. [14] Cerri et al., Kinetic plasma turbulence: recent insights and open questions from 3D3V simulations, Front. Astron. Space Sci., 6:64, 2019,  `<https://www.doi.org/10.3389/fspas.2019.00064>`_
.. [15] Franci et al., Anisotropic electron heating in turbulence-driven magnetic reconnection in the near-Sun solar wind, Astrophys J., 936:27, 2022, `<https://www.doi.org/10.3847/1538-4357/ac7da>`_
.. [16] Bandyopadhyay et al, In situ observation of Hall Magnetohydrodynamic Cascade in Space Plasma, Phys. Rev. Lett., 124, 225101, 2020, `<https://www.doi.org/10.1103/PhysRevLett.124.225101>`_
.. [17] Matteini et al., Magnetic field turbulence in the solar wind at sub-ion scales: in situ observations and numerical simulations, Front. Astron. Space Sci., 2020, 7:83, `<https://www.doi.org/10.3389/fspas.2020.563075>`_
.. [18] Franci et al., Modeling MMS observations at the Earth's magnetopause with hybrid simulations of Alfvénic turbulence, Astrophys J., 898:175, 2020, `<https://www.doi.org/10.3847/1538-4357/ab9a47>`_
.. [19] Franci et al., Evidence of a "current-mediated" turbulent regime in space and astrophysical plasmas, arXiv, 2020, `<https://arxiv.org/abs/2010.05048>`_
