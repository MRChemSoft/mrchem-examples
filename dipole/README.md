# Electric moments of water to high precision

In this example we compute the dipole and quadrupole moments of water
to three digits precision with Hartree-Fock. This example is similar
to the energy calculation, but since the moment errors are linear with
respect to the density errors, we need to fully converge the orbitals
to get good values. In this case we keep the default `orbital_thrs`,
which is an order of magnitude above `world_prec`.

The dipole moment is computed by default, so there is no need to give
the `dipole_moment` keyword, but `quadrupole_moment = true` is necessary.
Note that the quadrupole moment is explicitly origin dependent in MRChem,
in the sense that the computed output tensor will depend on where you
place the `world_origin` relative to the molecular geometry. Usually,
the moment is reported relative to the molecular center of mass (CoM),
and this can be achieved by keeping the default `world_origin` but
translating the molecular coordinates so that the CoM coincides with
the true origin (this is done with the `translate = true` keyword).
