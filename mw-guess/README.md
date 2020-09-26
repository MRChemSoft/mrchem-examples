# Using MW orbitals from previous calculation as starting guess

In this example we compute the total energy of water in two steps,
first a low precision LDA calculation which is used as starting guess
for a high precision BLYP calculation.

In the first run we set up a SAD guess and converge the orbitals
within 1.0e-2 using the LDA (SVWN5) functional. Then we write the
converged orbitals to file by specifying the `write_orbitals` keyword
as well as giving the file path. Orbitals will only be written after
successful completion of the SCF iterations.

In the second run we use the computed MW orbitals as starting point for
a high precision calculation. This is done by changing to `guess_type = MW`,
and giving the path to the orbitals. Note that by default the orbitals
would have been written to a directory called `orbitals/`, while the MW
guess will by default search the `initial_guess\` directory for orbtials,
so one of the two must be changed for the guess to work. The MW guess
orbitals should be projected with the same `guess_prec` as was used as
`world_prec` in the first calculation, in order not to lose any precision
in this step.

In contrast to the similar `checkpoint` guess, the `mw` guess does not
require the two calculations to use the same MW basis, world size or
even the same molecule. Here the two calculations are truly independent,
and the orbitals of the new molecule will be filled from the Aufbau
principle using the orbitals that are available in the given file path.
