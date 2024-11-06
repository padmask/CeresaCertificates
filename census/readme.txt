This directory contains files related to the census of quartic curves of
height at most 1:

curves-ht-1.mag         list of curves
census-detail.mag       function for the first pass, using information from primes less than 30
census-to-100.mag       function for the second pass, using information from primes less than 100
remaining.mag           script to handle the curves that are not excluded by the previous two
bloch_new.mag           functions to compute the Bloch shadow for semidiagonal curves
semidiagonal-example.mag one single example that needs the Bloch shadow
do_invariants.mag       function to determine pairs of curves with the same Dixmier-Ohno invariants
five.mag                five curves for which the torsion status of the Ceresa cycle is undetermined
nine.mag                nine curves for which the Ceresa cycle is known to be torsion
interp.mag              helper functions to interpolate polynomials and maps

Consider the set of smooth plane quartic curves defined by equations with
coefficients -1, 0, 1.  The group of signed permutation matrices of order
3 acts on this set, with the scalar matrix -1 acting trivially.  This
is done in comments in curves-ht-1.mag; since it takes a while, the file
also contains a set of orbit representatives.

There are 255564 orbits that fall into 254704 isomorphism classes over C.
By running census-detail.mag on these (which tests the shadow for p < 30)
we show that the shadow is not torsion for all but 208 of these.  The results
are shown in census-detail.log.

We then rerun for p < 100 (census-to-100.mag) and eliminate all but 147
curves, representing 89 different C-isomorphism classes.  Of these 147
curves, 4 are C-isomorphic to y^3 = x^4 - 1 or y^3 = x^4 - x and so we get
torsion.  On the other hand, 3 are isomorphic to x^4 + y^4 = z^4 and so they
are not torsion.  Again, the log file for this is census-to-100.log, and
the code for checking C-isomorphism by means of Dixmier-Ohno invariants is
do_invariants.log.

All the rest is in remaining.mag.  We break up the remaining curves according
to automorphism group.  Note that, where bds disagrees with #aut_cs,
it is always the latter that is correct.  The results are as shown in the
paper.

There are 5 with trivial automorphism group.  3 of these have geometric
automorphism group of order 3 and are shown to give torsion by Laga-Shnidman.
One is a form of y^3 = x^4 + x, so it has automorphism group of order 9 over
C and is known to be torsion, and 1 is a form of y^3 = x^4 + 1 and is a
form of the Lilienfeldt-Shnidman curve..

There are 13 with automorphism group of order 2.  6 of these have geometric
automorphism group of order 2.  Of these, 1 is special because its genus-1
quotient is isogenous to a curve with torsion of order 12, and small primes
cannot exclude it from being torsion.  However, this happens quickly for
primes greater than 100.  The others are undecided.

The other 7 have geometric automorphism group of order 6.  Of these 1 (#116) is
torsion by Laga-Shnidman and the rest are not.

There are 88 curves with automorphism group of order 4.  Of these 3 are
forms of the Lilienfeldt-Shnidman curve and so have torsion Ceresa cycle.
The others are shown not to, mainly by the Bloch shadow, but in some cases
where the geometric automorphism group is larger by passing to a twist.

There are 24 curves with automorphism group of order 6.  All have geometric
automorphism group of order 6 and nontorsion by taking another Q-form.

There are 15 curves with automorphism group of order 8.  Two of these
are forms of the Fermat quartic; the others are shown to have nontorsion
Ceresa cycle by means of a suitable twist.

There are 2 curves with automorphism group of order 24.  One of these is a
form of the Fermat quartic; again, the other is dealt with by twisting.

