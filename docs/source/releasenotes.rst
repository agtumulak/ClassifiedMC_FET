.. _releasenotes:

==============================
Release Notes for OpenMC 0.7.1
==============================

This release of OpenMC provides some substantial improvements over version
0.7.0. Non-simple cell regions can now be defined through the ``|`` (union) and
``~`` (complement) operators. Similar changes in the Python API also allow
complex cell regions to be defined. A true secondary particle bank now exists;
this is crucial for photon transport (to be added in the next minor release). A
rich API for multi-group cross section generation has been added via the
``openmc.mgxs`` Python module.

Various improvements to tallies have also been made. It is now possible to
explicitly specify that a collision estimator be used in a tally. A new
``delayedgroup`` filter and ``delayed-nu-fission`` score allow a user to obtain
delayed fission neutron production rates filtered by delayed group. Finally, the
new ``inverse-velocity`` score may be useful for calculating kinetics
parameters.

.. caution:: In previous versions, depending on how OpenMC was compiled binary
             output was either given in HDF5 or a flat binary format. With this
             version, all binary output is now HDF5 which means you **must**
             have HDF5 in order to install OpenMC. Please consult the user's
             guide for instructions on how to compile with HDF5.

-------------------
System Requirements
-------------------

There are no special requirements for running the OpenMC code. As of this
release, OpenMC has been tested on a variety of Linux distributions, Mac OS X,
and Microsoft Windows 7. Memory requirements will vary depending on the size of
the problem at hand (mostly on the number of nuclides in the problem).

------------
New Features
------------

- Support for complex cell regions (union and complement operators)
- Generic quadric surface type
- Improved handling of secondary particles
- Binary output is now solely HDF5
- ``openmc.mgxs`` Python module enabling multi-group cross section generation
- Collision estimator for tallies
- Delayed fission neutron production tallies with ability to filter by delayed
  group
- Inverse velocity tally score
- Performance improvements for binary search
- Performance improvements for reaction rate tallies

---------
Bug Fixes
---------

- 299322_: Bug with material filter when void material present
- d74840_: Fix triggers on tallies with multiple filters
- c29a81_: Correctly handle maximum transport energy
- 3edc23_: Fixes in the nu-scatter score
- 629e3b_: Assume unspecified surface coefficients are zero in Python API
- 5dbe8b_: Fix energy filters for openmc-plot-mesh-tally
- ff66f4_: Fixes in the openmc-plot-mesh-tally script
- 441fd4_: Fix bug in kappa-fission score
- 7e5974_: Allow fixed source simulations from Python API

.. _299322: https://github.com/mit-crpg/openmc/commit/299322
.. _d74840: https://github.com/mit-crpg/openmc/commit/d74840
.. _c29a81: https://github.com/mit-crpg/openmc/commit/c29a81
.. _3edc23: https://github.com/mit-crpg/openmc/commit/3edc23
.. _629e3b: https://github.com/mit-crpg/openmc/commit/629e3b
.. _5dbe8b: https://github.com/mit-crpg/openmc/commit/5dbe8b
.. _ff66f4: https://github.com/mit-crpg/openmc/commit/ff66f4
.. _441fd4: https://github.com/mit-crpg/openmc/commit/441fd4
.. _7e5974: https://github.com/mit-crpg/openmc/commit/7e5974

------------
Contributors
------------

This release contains new contributions from the following people:

- `Will Boyd <wbinventor@gmail.com>`_
- `Sterling Harper <sterlingmharper@mit.edu>`_
- `Bryan Herman <hermab53@gmail.com>`_
- `Colin Josey <cjosey@mit.edu>`_
- `Adam Nelson <nelsonag@umich.edu>`_
- `Paul Romano <paul.k.romano@gmail.com>`_
- `Kelly Rowland <kellylynnerowland@gmail.com>`_
- `Sam Shaner <samuelshaner@gmail.com>`_
- `Jon Walsh <walshjon@mit.edu>`_
