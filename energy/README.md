# PBE energy of water to high precision

In this example we compute the total energy of water to micro-Hartree
precision with respect to the complete basis set limit. For calculations
where the only interesting quantity is the total energy, we can reduce
the convergence threshold in the SCF iterations. The default threshold is
to converge the orbitals within `10*world_prec`, but here we rather use
the energy update as criterion, since the total energy converges much
faster than the orbitals.

- Set `world_prec` to the target precision
- Coordinates given in Bohr atomic units (default, `world_unit = bohr` not necessary)
- PBE is one of the standard DFT functionals, so it can be given directly in the `method` keyword
- Use dynamic SCF precision: starting with `start_prec`, ending in `world_prec`
- Activate the energy convergence threshold and set it to micro-Hartree
- Deactivate the orbital convergence threshold by setting it to a negative value
