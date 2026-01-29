Vlasiator
=========

Vlasiator [1]_ [2]_ is a 6D ion-kinetic hybrid-Vlasov model for the Earth's global magnetosphere. Vlasiator simulates the dynamics of plasma using a hybrid-Vlasov model, where protons are described by their distribution function f(r,v,t) in ordinary (r) and velocity (v) space, and electrons are a charge-neutralising fluid. This approach neglects electron kinetic effects but retains ion kinetics. The time-evolution of f(r,v,t) is given by Vlasov's equation, which is coupled self-consistently to Maxwell's equations giving the evolution of the electric and magnetic fields E and B. Maxwell's equations neglect the displacement current. The equations are closed by a generalised Ohm's law including the Hall term.

+------------------------+---------------------------------------------------------------------+
| Additional information | `Vlasiator <https://www.helsinki.fi/en/researchgroups/vlasiator>`_  |
|                        | group at Helsinki University                                        |
+------------------------+---------------------------------------------------------------------+
| PI                     | Prof. Minna Palmroth                                                |
+------------------------+---------------------------------------------------------------------+
| WG Point of Contact    | Markku Alho                                                         |
+------------------------+---------------------------------------------------------------------+
| Current code version   | 5.3.1                                                               |
+------------------------+---------------------------------------------------------------------+
| code/repository        | `Zenodo <https://doi.org/10.5281/zenodo.3640593>`_,                 |
|                        | `GitHub <https://github.com/fmihpc/vlasiator>`_                     |
+------------------------+---------------------------------------------------------------------+
| Legal Code License     | `GPL-2.0 <https://www.gnu.org/licenses/old-licenses/gpl-2.0.html>`_ |
+------------------------+---------------------------------------------------------------------+
| Software code          | C++;                                                                |
| languages and tools    | `Analysator <https://github.com/fmihpc/analysator>`_ Python toolkit |
+------------------------+---------------------------------------------------------------------+

Use cases
---------

Vlasiator has been used to describe magnetic reconnection in global magnetospheric context, especially in the magnetotail [3]_ and the kinetic features of the tail reconnection processes [4]_ [5]_ and the global evolution of flux transfer events [6]_.

Data availability
-----------------

Data access subject to `Rules of the Road <https://www.helsinki.fi/en/researchgroups/vlasiator/rules-of-the-road>`_. Some data is available publicly.

+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| Name | Access                                                                                               | Used                                                                                   | Comments                                        |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| ABA  | `Full bulk data available <https://etsin.fairdata.fi/dataset/bf93afde-009e-4a46-a9e3-d3dde0875452>`_ | `Palmroth+2018 <https://angeo.copernicus.org/articles/36/1171/2018/>`_,                | Equatorial run with 30deg cone angle, 5 nT IMF  |
|      |                                                                                                      | `Palmroth+2021 <https://angeo.copernicus.org/articles/39/289/2021/>`_,                 |                                                 |
|      |                                                                                                      | `Suni+2021 <https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2021GL095655>`_,  |                                                 |
|      |                                                                                                      | `Suni+2023 <https://angeo.copernicus.org/articles/41/551/2023/>`_                      |                                                 |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| ABC  | `Full bulk data available <https://etsin.fairdata.fi/dataset/bf93afde-009e-4a46-a9e3-d3dde0875452>`_ | `Palmroth+2015 <https://agupubs.onlinelibrary.wiley.com/doi/10.1002/2015JA021526>`_,   |                                                 |
|      |                                                                                                      | `Palmroth+2018 <https://angeo.copernicus.org/articles/36/1171/2018/>`_,                |                                                 |
|      |                                                                                                      | `Turc+2018 <https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2018JA025466>_,        |                                                 |
|      |                                                                                                      | `Turc+2019 <https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2019GL084437>`_,       |                                                 |
|      |                                                                                                      | `Battarbee+2020 <https://doi.org/10.5194/angeo-38-625-2020>`_,                         |                                                 |
|      |                                                                                                      | `Suni+2021 <https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2021GL095655>`_,  |                                                 |
|      |                                                                                                      | `Run RAD_B5 in Turc+2022 <https://doi.org/10.3389/fspas.2022.989369>`_,                |                                                 |
|      |                                                                                                      | `Dorfman+2023 <https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2023JA031724>`_     |                                                 |
|      |                                                                                                      | `Suni+2023 <https://angeo.copernicus.org/articles/41/551/2023/>`_                      |Equatorial run with 5deg cone angle, 5 nT IMF    |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| AEA  | `Full bulk data available <https://etsin.fairdata.fi/dataset/bf93afde-009e-4a46-a9e3-d3dde0875452>`_ | `Palmroth+2021 <https://angeo.copernicus.org/articles/39/289/2021/>`_,                 |                                                 |
|      |                                                                                                      | `Suni+2021 <https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2021GL095655>`_,  |                                                 |
|      |                                                                                                      | `Suni+2023 <https://angeo.copernicus.org/articles/41/551/2023/>`_                      | Equatorial run with 30deg cone angle, 10 nT IMF |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| AEC  | `Full bulk data available <https://etsin.fairdata.fi/dataset/bf93afde-009e-4a46-a9e3-d3dde0875452>`_ | `Turc+2018 <https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2018JA025466>`_,       |                                                 |
|      |                                                                                                      | `Turc+2019 <https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2019GL084437>`_,       |                                                 |
|      |                                                                                                      | `Battarbee+2020 <https://doi.org/10.5194/angeo-38-625-2020>`_,                         |                                                 |
|      |                                                                                                      | `Palmroth+2021 <https://angeo.copernicus.org/articles/39/289/2021/>`_,                 |                                                 |
|      |                                                                                                      | `Suni+2021 <https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2021GL095655>`_,  |                                                 |
|      |                                                                                                      | `Run RAD_B10 in Turc+2022 <https://doi.org/10.3389/fspas.2022.989369>`_                |Equatorial run with 5deg cone angle, 10 nT IMF   |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| AFC  | Full bulk data                                                                                       | `Takahashi+2021 <https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2020JA028474>`_,  |                                                 |
|      | `available <https://a3s.fi/swift/v1/AUTH_81f1cd490d494224880ea77e4f98490d/vlasiator-2d-afc>`_        | `Run MC_B14 in Turc+2022 <https://doi.org/10.3389/fspas.2022.989369>`_,                |Equatorial run with 30deg cone angle             |
|      |                                                                                                      | `Turc+2023 <https://www.nature.com/articles/s41567-022-01837-z>`_                      | IMF and strong driving conditions               |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| BCB  | Request                                                                                              | `Pfau-Kempf+2016 <https://angeo.copernicus.org/articles/34/943/2016/>`_                | The original southward Vlasiator Conditions run |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| BCQ  | Request                                                                                              | Existing collaboration                                                                 | Southward with 45° IMF and foreshock, used      |
|      |                                                                                                      |                                                                                        | in many marketing plots too.                    |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| DCA  | Request                                                                                              | `Pfau-Kempf+2020 <https://doi.org/10.1063/5.0020685>`_                                 | 2.9D southward                                  |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| EGI  | `Partially open bulk data <http://urn.fi/urn:nbn:fi:att:471b6af3-7a46-4640-91fc-05e27962d328>`_      | `Palmroth+2023 <https://doi.org/10.1038/s41561-023-01206-2>`_,                         | 3D Magnetosphere w/o ionosphere, Southward IMF. |
|      |                                                                                                      | `Alho+2024 <https://doi.org/10.5194/angeo-42-145-2024>`_,                              | Investigations into tail RX processes.          |
|      |                                                                                                      | `Tesema+2024 <https://doi.org/10.1029/2023GL106756>`_,                                 |                                                 |
|      |                                                                                                      | `Cozzani+2025 <https://doi.org/10.1029/2024GL111848>`_,                                |                                                 |
|      |                                                                                                      | `Zaitsev+2025 <https://doi.org/10.1029/2024JA032615>`_                                 | 1506s second run, initialization until ~1000s.  |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| EGL  | Request                                                                                              | `Horaites+2023 <https://doi.org/10.1029/2023JA031374>`_                                | Pressure pulse simulation. EGI branched with    |
|      |                                                                                                      |                                                                                        | an enhanced dynamic pressure pulse              |
|      |                                                                                                      |                                                                                        |                                                 |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+
| FHA  | `Open bulk data available <http://urn.fi/urn:nbn:fi:att:3ce0f038-2c69-4c7c-8f67-7a71e9e57b56>`_      | `Pfau-Kempf+2025 (accepted) <https://doi.org/10.5194/angeo-2024-26>`_                  | EGI with ionosphere. Good for tail RX processes |
|      |                                                                                                      | `Pänkäläinen+2025 (accepted) <https://doi.org/10.22541/essoar.174139373.33536293/v1>`_ | incl. flux rope detection flags                 |
|      |                                                                                                      |                                                                                        |                                                 |
+------+------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+-------------------------------------------------+

Simulations-on-demand
---------------------

Global Vlasiator simulations take months to complete, and are not offered on an on-demand basis; larger collaborations can of course be planned.

Small/local simulations can be set up and supported for external users on best-effort basis.

Numerical Methods
-----------------

Vlasiator propagates the distribution function forward in time with a conservative fifth-order accurate Semi-Lagrangian algorithm. This algorithm allows using long time steps even in the presence of strong magnetic fields, as the propagation in velocity space is not limited by the Courant-Friedrichs-Levy (CFL) condition. The field solver is a second-order accurate divergence-free upwind-constrained transport method.

Vlasiator has a parallel Cartesian mesh in ordinary space. In each spatial cell there is a 3-dimensional sparse velocity grid, modelling the in the full 6-dimensional distribution function. Empty velocity space cells are neither stored nor propagated, which in a typical case reduces the total number of phase space cells by a factor of at least 100 while impacting mass conservation to a relative level of no more than 10:sup:`-6`.

The ordinary space grid is implemented using the open source `DCCRG <https://github.com/fmihpc/dccrg>`_ grid library developed by the group. It is parallelized using MPI-based domain decomposition and OpenMP-based threading is used to further parallelise the work done by each process. The Vlasov solver is vectorised using AVX intrinsics. The load is balanced with the `Zoltan <http://www.cs.sandia.gov/zoltan/>`_ library using its recursive coordinate bisection partitioner. I/O is performed using our own parallel `VLSV <https://github.com/fmihpc/vlsv>`_ file format, which can be analyzed using VisIt or by using the Python-based `Analysator <https://github.com/fmihpc/analysator>`_ package.


References
----------

.. [1] Palmroth, M. et al. Vlasov methods in space physics and astrophysics. Living Rev Comput Astrophys (2018). `<https://doi.org/10.1007/s41115-018-0003-2>`_
.. [2] Ganse, U. et al. Enabling technology for global 3D + 3V hybrid-Vlasov simulations of near-Earth space. Phys. Plasmas (2023). `<https://doi.org/10.1063/5.0134387>`_
.. [3] Palmroth, M. et al. Magnetotail plasma eruptions driven by magnetic reconnection and kinetic instabilities. Nat. Geosci. (2023). `<https://doi.org/10.1038/s41561-023-01206-2>`_
.. [4] Cozzani, G. et al. Interplay of magnetic reconnection and current sheet kink instability in the Earth's magnetotail. Geophysical Research Letters (2025). `<https://doi.org/10.1029/2024GL111848>`_
.. [5] Zaitsev, I. et al. Ion‐mediated tearing and kink instabilities in the Earth's magnetosphere: Hybrid‐Vlasov simulations. Journal of Geophysical Research: Space Physics. (2025). `<https://doi.org/10.1029/2024JA032615>`_
.. [6] Pfau-Kempf, Y. et al. Global evolution of flux transfer events along the magnetopause from the dayside to the far tail. Ann. Geophys. Discuss. (preprint, 2024), `<https://doi.org/10.5194/angeo-2024-26>`_, in review.
