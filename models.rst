
Model descriptions
==================

Models overview
---------------

Vlasiator
^^^^^^^^^

Vlasiator is a 6D ion-kinetic hybrid-Vlasov model for the Earth's global magnetosphere. Vlasiator simulates the dynamics of plasma using a hybrid-Vlasov model, where protons are described by their distribution function f(r,v,t) in ordinary (r) and velocity (v) space, and electrons are a charge-neutralising fluid. This approach neglects electron kinetic effects but retains ion kinetics. The time-evolution of f(r,v,t) is given by Vlasov's equation, which is coupled self-consistently to Maxwell's equations giving the evolution of the electric and magnetic fields E and B. Maxwell's equations neglect the displacement current. The equations are closed by a generalised Ohm's law including the Hall term.

.. toctree::
   Vlasiator details<models/vlasiator>


HYPSI
^^^^^

HYPSI is an hybrid-kinetic PIC code, where ions are modelled as macroparticles and advanced using the standard PIC method while the electrons are modelled as a massless, charge-neutralizing fluid with an adiabatic equation of state. 

HYPSI supports several initialisations and boundary conditions, the most used one of which allows the propagation of a shock wave in the simulation domain. This is done thorugh the injection method, employing an open inlow boundary and a reflective wall. The other two directions have periodic boundary conditions. Importantly, HYPSI was one of the first codes supporting a realistic turbulent initialisation for the shock upstream. Such turbulent initialisation is performed through a combination of MHD and hybrid kinetic simulations, where the output of an MHD model becomes the initial condition for the shock simulation. An important aspect of this initialisation is that the perturbation is finite in both space and time extent. Recent improvements allow for continuous injection of upstream turbulence.  

Two-dimensional datasets covering a large shock parameter range (0 to 90 degrees shock normal angles, 0.1 to 10 plasma beta, Alfvanic Mach numbers 2 to 30) are easily provided upon request, useful to look at electromagnetic fields, plasma moments, particle distributions. Turbulent and three-dimensional runs can also be provided, though they require more planning due to computational constraint. An extensive set of software to analyse HYPSI output is also available upon request in both MATLAB and Python, with the Python version 'hypy' being released soon.

For further details, see below:

.. toctree::
   HYPSI details<models/hypsi>

HVM
^^^^

`Hybrid-Vlasov-Maxwell <https://doi.org/10.1063/1.4893301>`_ (HVM)  is an Eulerian ion-kinetic simulation code, used for e.g. large-scale local turbulence simulations.

.. toctree::
   HVM details<models/HVM>

ViDA
^^^^

`ViDA <https://doi.org/10.1017/S0022377819000631>`_ is a Vlasov-Darwin solver targeting electron-scale physics, providing Eulerian Vlasov simulations for both ions and electrons.

.. toctree::
   ViDA details<models/ViDA>

MAGE
^^^^

`MAGE <https://cgs.jhuapl.edu/Models/mage.php>`_, or the Multiscale Atmosphere-Geospace Environment model is coupled model developed to include the whole geospace to resolve global dynamics and mesoscale processes. The magnetospheric backbone model of MAGE is the Grid Agnostic MHD for Extended Research Applications model, or `GAMERA <https://cgs.jhuapl.edu/Models/gamera.php>`_.

SWMF
^^^^

The Space Weather Modeling Framework (SWMF) is a software framework which models a wide range of temporal and spatial scales as well as the different physical processes governing the different heliophysics domains through a modular approach. The heart of the framework is the BATS-R-US versatile, high-performance, generalized magnetohydrodynamic code with adaptive mesh refinement that can be configured to solve the governing equations of ideal and resistive MHD, semi-relativistic, anisotropic, Hall, multispecies, and multi-fluid extended magnetofluid equations (XMHD) and non-neutral multifluid plasmas. The BATS-R-US is used to model several physics domains, and its high efficiency (faster than real time) is crucial for the success of the framework. Further descriptions of the SWMF modules can be found below.

.. toctree::
   SWMF details<models/swmf>

MENURA
^^^^^^

`Menura <https://menura.readthedocs.io/en/latest/>`_ is parallel-GPU hybrid Particle-in-Cell code, with the speciality of being able to both simulate and introduce solar wind turbulence into global simulations.

.. toctree::
   Menura details<models/menura>

Amitis
^^^^^^

`Amitis <www.amitiscode.com>`_ is a three-dimensional, time-dependent, hybrid-kinetic plasma model, providing high performance via parallel GPU-based supercomputing.

COHMPA
------
The “COmpressible Hall Magnetohydrodynamics simulations for Plasma Astrophysics” (COHMPA)[1] is a pseudo-spectral algorithm which solves the three-dimensional magnetohydrodynamics equations on a three-periodic Cartesian domain. It eventually includes the Hall and the electron pressure terms in the induction equation for the magnetic field. COHMPA exploits a MPI-based parallelization and employs fast Fourier transform routines (FFTW).

.. toctree::
   COHMPA detais<models/COHMPA>

Hall-MHD
^^^^^^^^

A code for solving the viscous-resistive, fully compressible Hall-MHD equations, used for local turbulence and reconnection studies, especially by providing large-scale input for CAMELIA.

CAMELIA
^^^^^^^

CAMELIA is a hybrid Particle-in-Cell simulation, used for studying turbulence and reconnection in local simulations, especially from larger-scale background from the Hall-MHD code described above. CAMELIA has already generated a large archive of simulations over a large parameter space.

.. toctree::
   CAMELIA details<models/camelia>


iPIC3D
^^^^^^

iPIC3D is a massively parallel, moment-implicit Particle-in-Cell (PIC) code for large-scale kinetic plasma simulations, particularly targeting global magnetospheric dynamics. Developed in C++ with hybrid MPI/OpenMP parallelism, it is designed for exascale platforms and optimized for both CPU and GPU architectures including AMD MI300A and NVIDIA Grace Hopper.

.. toctree:: 
   iPIC3D details<models/iPIC3D_SM>

.. Athena++
.. ^^^^^^^^

GPAT
^^^^

GPAT is an open source code solving energetic particle transport equations by integrating `stochastic differential equations <https://stochastic-parker.readthedocs.io/en/latest/index.html>`_, available on GitHub at `<https://github.com/xiaocanli/stochastic-parker>`_.


VPIC
^^^^

`VPIC <https://doi.org/10.1109/TPDS.2021.3084795>`_ is an open source, fully kinetic, relativistic, general purpose particle-in-cell (PIC) code for modeling a broad range of plasmas—from short-pulse laser-plasma interactions to Earth-scale magnetospheric plasmas, including energetic particle acceleration, magnetic reconnection, and laser plasma interaction. VPIC is available on GitHub: `<https://github.com/lanl/vpic-kokkos>`_.


*muphyII* 
^^^^^^^^^^

The *muphyII* code is a simulation framework for collisionless plasma physics and targeted at space plasmas in particular. The *muphyII* code utilizes a hierarchy of models with different inherent scales to address the separation of scales problem typically encountered in these plasmas. It allows stand-alone use of models as well as a model-based dynamic and adaptive domain decomposition and resorts to novel techniques for energy conservation, careful treatment of inner-domain model boundaries for interface coupling, and robust time stepping algorithms.


.. toctree::
   muphyII details<models/muphyii>

PSC
^^^

Plasma Simulation Code (PSC) is a 3-dimensional fully electromagnetic particle-in-cell code for kinetic plasma simulations. It supports Nvidia GPUs and patch-based dynamic load balancing.

.. toctree::
   PSC details<models/psc>

PIRAN: Particles In ResonANce
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Quasilinear diffusion coefficients can be used to characterise the statistical response of charged particles to perturbations by plasma waves, via resonant wave-particle interactions. The open-source PIRAN software package ("Particles In ResonANce") is written using Python, and allows the user to calculate relativistic diffusion coefficients in kinetic energy and pitch-angle space via the two main current proposed methods in the literature.

.. toctree::
   PIRAN details<models/piran>

OpenMHD
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

OpenMHD is a finite-volume magnetohydrodynamic (MHD) code, written in modern Fortran and CUDA fortran. The program is parallelized by MPI+OpenMP on CPU and by MPI+CUDA on GPU.

.. toctree::
   OpenMHD details<models/OpenMHD>
