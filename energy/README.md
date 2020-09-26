# Total energy of water to high precision

In this example we compute the total energy of water to micro-Hartree
precision with respect to the complete basis set limit. For calculations
where the only interesting quantity is the total energy, we can reduce
the convergence threshold in the SCF iterations. The default threshold is
to converge the orbitals within `10*world_prec`, but here we rather use
the energy update as criterion, since the total energy converges much
faster than the orbitals.
