java c
CHEN   E4880 – Atomistic Simulations 
Project 1: Properties of an Elemental Transition Metal 
(Due on   February 27, 2025 at   11:59   PM)Transition metals are of   great technological relevance   for   the chemical industry due to their unique   properties   and   versatility   in   various   applications,   including   catalysts,   magnetic   materials,   and   electronics. In this project, you   will explore the properties of   an elemental transition metal, for now,   in the absence of temperature or pressure.The technical objective of this project is to familiarize yourself with the   LAMMPS software   and   its      input/output   file   formats. Scientific objectives are to   find the ground-state energy, lattice parameter,   vacancy   formation   energy,   and   one   surface   energy   of   a   face-centered   cubic   (FCC)   transition      metal. As you work through the   project, you will also   learn   about   the   importance   of convergence parameters and the limitations of interatomic potentials   used   in   atomic-scale   simulations.
Geometry optimizations (relaxations) In nature, a crystal in equilibrium is automatically in the lowest energy (ground-state) configuration.   The ground-state lattice parameters and atomic positions define the ground-state lattice geometry that   minimizes the   lattice energy. The ground-state   lattice   parameters are generally   not   known a priori. Given a reasonable guess, we can perform. a geometry optimization, also sometimes called relaxation, that finds the lowest energy   configuration by adjusting the   atomic   positions   and   lattice      parameter(s) until an energy   minimum   is found.
Vacancy formation energy 
The vacancy formation energy Ev   is defined as the energetic cost to remove an atom from a lattice   site and reinsert   it into the bulk   of the   material.   This   leads   to   the   energy   difference
where   Ebulk and   EN   -   1 are   the   energies   of   the   perfect   bulk   structure   with   Nbulk atoms   and   the defect structure with one vacancy containing   (N   −   1)   atoms,   respectively.   By evaluating the   bulk   energy per atom (Ebulk   /Nbulk)   and   multiplying   by   the   number   of   atoms   in   the   vacancy   structure   (N   −   1), we obtain the bulk energy of (N   −   1)   atoms   and   can   compare   the   two   structures.
Surface energy The surface energy is   the energy required   to   truncate an infinitely extended crystal along a specific   lattice    plane.    Calculating    surface    energies follows a similar overall approach to calculating   vacancy formation energies, but different convergence parameters   must   be   considered.
Surface relaxations and pair potentials 
The following equation gives the   Lennard-Jones potential

Pair   potentials,   such   as   the   Lennard-Jones   potential,   show   outward   surface   relaxations,   which   disagrees with experimental observation.
1.       Lattice constant of elemental platinum 
a.       Calculate   the   lattice   constant   (in Å)   and   total   energy   (in   eV)   using   the   supplied   LJ   potential.   First,   use   LAMMPS’   built-in   minimizer   (input   file lmp-in.1a-relax),   then   find   the   lattice   constant   by   manually   adjusting   the   lattice   parameter   (input   file lmp-in.1a-single).   Start   with   a   lattice   parameter   close to the   relaxed   lattice   parameter.   Plot the   energy   as   a function   of the   lattice   parameter from   above to   below the   optimized value (Figure 1)   and   identify   the   equilibrium lattice constant.
Hint: See the project guide for an explanation   of the   LAMMPS   input format.
b.       Repeat the calculations, both automated and   manual   (Figure 2), for the   supplied   embedded-
atom model (EAM) potential   (input file: lmp-in.1b-single). Hint: Don’t forget to upload the   EAM potential file to   nanoHUB.
c.       How do the calculated   lattice constants   compare to   the   experimental   value?
d.      Which potential agrees better with experiment?   Is this   result expected?   Explain   your   answer. Hint: Consider how the different potentials were constructed   (see   table   below).
2. Vacancy formation energy of Pt 
a.       Compute the vacancy formation energy (in eV) with the provided   LJ   potential   as   a   function   of   the   supercell   size. Do not relax the   atomic   positions   after   taking   out   an   atom.   Perform   a   convergence test and plot the energy against the   convergence   parameter   (Figure 3).
b.       Calculate    the    ratio    of    the    vacancy    formation    energy    to    the    cohesive    energy      per    代 写CHEN E4880 – Atomistic Simulations 2025 Project 1: Properties of an Elemental Transition MetalMatlab
代做程序编程语言  atom.   Document   how   you   calculated   the   cohesive   energy. Hints: The   (conventional)   FCC   unit   cell   contains 4 atoms.   Use the optimized   LJ lattice parameter from   problem   1.
c.       Repeat   your   calculation,   but relax the   atomic   positions   after   creating   the   vacancy.   Perform   another   convergence test   and   add   results to Figure 3.   Describe   how the vacancy   formation   energy changes compared to the unrelaxed calculations. Hint: Adjust your LAMMPS input file   for relaxations (see   problem   1).
d.       Now    compute   the   vacancy   formation   energy using   the   provided    EAM   potential.    Do    it   as   accurately   as   you   can.   Report   your   convergence   test   (Figure 4).   Use   what   you   learned   in parts a. and b. Hint: Use the optimal EAM lattice parameter   from problem   1 as the initial value. 
e.      Without   relaxation,   the   absolute   value   of   the   ratio   of   the   vacancy   formation   energy   to   the cohesive energy per atom equals   1 for the   Lennard-Jones potential.   Explain why.
f.         Why does the vacancy formation energy decrease when the   atoms are   allowed to   relax?
3.       Surface energy of the Pt(100) facet 
a.      Which two convergence parameters need to   be considered for   surface   slab   calculations?
b.       Compute   the   surface   energy   of   the   Pt(100)   surface   using   the   LJ   potential.   Document   your   approach.   Perform. and   plot convergence tests (Figure 5).   Report your   result   in   meV/Ǻ2   .
c.       Repeat with the   EAM potential,   including convergence tests   (Figure 6). Please do not perform. relaxations for problem 3. 
4.       Conceptual understanding 
a.       Calculate the distance r/    where the LJ potential reaches its minimum (Derivation 1).   Express   r/      in terms of ε   and σ   , and evaluate using   the   values from   your   calculations.
b.       Determine    the      nearest-neighbor    distance    dNN            in      the      optimized      structure      of      problem       1   (Derivation 2).
c.       Why   is   dNN      different   from   r/   ?
d.      Why are numerical simulations needed even for   simple   models   such   as   the   LJ   potential?
5.       Short answers a.       For what class of compounds are Lennard-Jones potentials most   suitable (name   1 example)?b.       For what class of compounds/materials are EAM potentials most suitable   (name   1   example)?c.       Name   1 example of materials/interactions for which   neither   LJ   nor   EAM are   appropriate.
d.
Assignment 
1.       Perform. the simulations described on the   previous   page.
2.       Document your work in a two-page memo.
a.      Address all questions.
b.       Highlight key results   (lattice   parameters,   energies,   etc.).
c.       Refer to   all figures   and   derivations.
d.       Keyword style. is fine   if the   presentation   is   clear.
3.       Include Figures 1–6 and Derivations 1 and 2 in   the   appendix.   Pictures   of   hand-written   notes are fine for derivations.
4.       For problems   1–3, include examples of your   input files   in   the   appendix.
Make sure to follow the formatting guidelines. Limit the text portion of your report to no more than   two   pages.
Provided Files 
File 
Description 
Comment 
lmp-in.1a-single 
LAMMPS input file for a single point calculation of FCC Pt using a Lennard-Jones potential 

lmp-in.1a-relax 
LAMMPS input file for geometry optimizations (relaxations) using a Lennard-Jones potential 

lmp-in.1b-single 
LAMMPS input file for a single point calculation of FCC Pt using an EAM potential 
EAM potential file required 
lmp-in.1b-relax 
LAMMPS input file for geometry optimizations (relaxations) using an EAM potential 
EAM potential file required 
Pt-Adams1989.eam EAM potential for Pt. This potential was published in Adams et al., J. Mater. Res. 4, 102-112 (1989) and can be obtained from 
http://www.ctcms.nist.gov/potentials 
The   Lennard-Jones   potential   parameters   (ε = 0.200 eV; σ =   2.540 Å) were   determined   by   a   fit   to   the lattice constant and the   vacancy   formation energy. The EAM potential   was   fitted to sublimation   energies, elastic constants, and vacancy formation energies.
Problems 2 and 3: We do   not   provide separate files for   Problems 2   and   3.   Use   the files   provided   for   problem   1   and   start   from   there.   See   the   project   guide   for   hints   regarding   creating   vacancies   and   surface   slab   models.



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
