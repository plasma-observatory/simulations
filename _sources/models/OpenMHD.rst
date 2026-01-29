OpenMHD
=======

OpenMHD is a finite-volume magnetohydrodynamic (MHD) code, written in modern Fortran and CUDA fortran.
The program is parallelized by MPI+OpenMP on CPU and by MPI+CUDA on GPU.

+------------------------+---------------------------------------------------------------------+
| Additional information | `OpenMHD <https://sci.nao.ac.jp/MEMBER/zenitani/openmhd-e.html>`_   |
+------------------------+---------------------------------------------------------------------+
| WG Point of Contact    | Seiji Zenitani                                                      |
+------------------------+---------------------------------------------------------------------+
| Current code version   | 20241124                                                            |
+------------------------+---------------------------------------------------------------------+
| code/repository        | https://github.com/zenitani/OpenMHD                                 |
+------------------------+---------------------------------------------------------------------+
| Legal Code License     | `GPL-3.0 <https://www.gnu.org/licenses/old-licenses/gpl-3.0.html>`_ |
+------------------------+---------------------------------------------------------------------+
| Software code          | Fortran 90, CUDA Fortran                                            |
+------------------------+---------------------------------------------------------------------+

Use cases
---------

The code was originaly developed to study magnetic reconnection in space and solar plasmas [1]_, [2]_.
A double-polytropic version was used to study mirror-mode structures in the magnetosheath [3]_.


Data availability
-----------------

N/A

Simulations-on-demand
---------------------

There is no on-demand facility. Instead, we provide Jupyter notebooks for `Google Colaboratory <https://colab.research.google.com/>`_. If you have a Colab account, you can try examples in your browser.

Numerical Methods
-----------------

OpenMHD employs a collection of standard methods -- the HLLD solver for numerical fluxes, the 2nd (or 3rd) order slope limiters for spatial interpolation, the second-order Runge-Kutta methods for time-marching, and the hyperbolic divergence cleaning for the solenoidal condition. Please refer to the original papers [1]_, [2]_ for detail.


References
----------

.. [1] S. Zenitani and T. Miyoshi, Magnetohydrodynamic structure of a plasmoid in fast reconnection in low-beta plasmas, Phys. Plasmas, 18, 022105 (2011), `<https://doi.org/10.1063/1.3554655>`_
.. [2] S. Zenitani, Magnetohydrodynamic structure of a plasmoid in fast reconnection in low-beta plasmas: Shock-shock interactions, Phys. Plasmas, 22, 032114 (2015), `<https://doi.org/10.1063/1.4916104>`_
.. [3] W.-L. Teh and S. Zenitani, Thermodynamic Properties of Mirror Structures in the Magnetosheath: MMS Observations and Double-polytropic MHD Simulations, Astrophys. J., 885, 22 (2019), `<https://doi.org/10.3847/1538-4357/ab4417>`_
