SWMF
================================

The Space Weather Modeling Framework (SWMF) [1]_ [2]_ is a software framework which models a wide range of temporal and spatial scales as well as the different physical processes governing the different heliophysics domains through a modular approach. The heart of the framework is the BATS-R-US versatile, high-performance, generalized magnetohydrodynamic code with adaptive mesh refinement that can be configured to solve the governing equations of ideal and resistive MHD, semi-relativistic, anisotropic, Hall, multispecies, and multi-fluid extended magnetofluid equations (XMHD) and non-neutral multifluid plasmas. The BATS-R-US is used to model several physics domains, and its high efficiency (faster than real time) is crucial for the success of the framework. Further descriptions of the SWMF modules can be found below.

+------------------------+-----------------------------------------------------------------------------------------------------------------------+
| Additional information | `SWMF <https://clasp.engin.umich.edu/research/theory-computational-methods/space-weather-modeling-framework/>`_  	 |
|                        |  at University of Michigan                                      							 |
|           		 |                                                                     							 |
+------------------------+-----------------------------------------------------------------------------------------------------------------------+
| WG Point of Contact    | Tuija Pulkkinen                                                       						 |
+------------------------+-----------------------------------------------------------------------------------------------------------------------+
| Current code version   | 2023                                                               							 |
+------------------------+-----------------------------------------------------------------------------------------------------------------------+
| code/repository        | `GitHub <https://github.com/SWMFsoftware/SWMF>`_                     						 |
+------------------------+-----------------------------------------------------------------------------------------------------------------------+
| Legal Code License     | `Apache-2.0 <http://www.apache.org/licenses/LICENSE-2.0>`_ 								 |
+------------------------+-----------------------------------------------------------------------------------------------------------------------+
| Software code          | Fotran 77, Fortran 90, C++                                                                 				 |
+------------------------+-----------------------------------------------------------------------------------------------------------------------+
| Runs on request        | `Community Coordinated Modeling Center <https://ccmc.gsfc.nasa.gov/requests/GM/SWMF/swmf_user_registration.php>`_     |
+------------------------+-----------------------------------------------------------------------------------------------------------------------+

Use cases
---------

The SWMF/Geospace configuration couples the Global Magnetosphere (GM) model based on BATS-R-US to the Ionospheric Electrodynamics (IE) model (Ridley Ionosphere Model, RIM) and the Inner Magnetosphere (IM) model (Rice Convection Model, RCM). The Global Magnetosphere model supplies near-body field-aligned currents to the ionosphere, which solves for the electric potential.  This electric potential is returned to the magnetosphere to set the plasma tangential velocity at the inner boundary of the MHD domain.

The MHD with embedded PIC (MHD-EPIC) model couples the particle-in-cell (PIC) simulation with the SWMF components using an efficient parallel coupler that allows for different grids and different time steps and multiple PIC domains. To further improve the efficiency of the still computationally very expensive model, the MHD with an adaptively embedded PIC (MHD-AEPIC) algorithm decomposes the PIC grid into small blocks that can be activated and deactivated dynamically. A new PIC code, the Flexible Exascale Kinetic Simulator (FLEKS), is developed for MHD-AEPIC.

other domains tbd

Plots tbd

Data availability
-----------------

All data generated at CCMC via Runs on Request are public and are `archived <https://ccmc.gsfc.nasa.gov/ungrouped/GM_IM/GM_main.php>`_

tbd other links to rules of the road

Simulations-on-demand
---------------------

See CCMC website for `Runs on Request <https://ccmc.gsfc.nasa.gov/requests/GM/SWMF/swmf_user_registration.php>`_

Numerical Methods
-----------------

tbd


References
----------

.. [1] Tamas I. Gombosi, et al. What Sustained Multi-Disciplinary Research Can Achieve: The Space Weather Modeling Framework, J. Space Weather and Space Climate (2021) `<https://doi.org/10.1051/swsc/2021020>`_
.. [2] Toth G, et al. Adaptive numerical algorithms in space weather modeling. J Comput Phys (2012). `<https://doi.org/10.1016/j.jcp.2011.02.006>`_
