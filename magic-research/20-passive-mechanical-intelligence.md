# 20 - Passive mechanical intelligence: props with no electronics, batteries or magnets that hold state, count, remember, compute, or treat the performer differently

Slice: objects that can be sawn in half and shown to be plain plastic, rubber, wood, oil and
perhaps a steel ball, and that have nevertheless done something conditional. Prices are as of
late 2026 and come from the pages cited.

**Research-method note.** The shared web-search allowance cut out twice during this work. About
45 searches and 15 page opens were completed. Everything with a URL in section 6 was seen in a
search result or opened. Anything recalled from memory and not confirmed is marked
"(unverified)". Numbers labelled "my estimate" are my own back-of-envelope physics, shown with
the inputs so they can be checked; they are not from a source. Coverage of the internal workings
of specific commercial magic props (Tenyo, trick locks by named makers) is thin, because makers
and collectors do not publish them; the magic-survey agents should be treated as authoritative
there.

**Level tags** (from the course correction): L1 = the phenomenon is the effect; L2 = a hidden
input that removes a weakness of a traditional method; L3 = a new method architecture the
audience never suspects.

---

## 1. Summary

- **There is now a published design vocabulary for "matter that computes", and almost all of it
  is printable or castable at desk scale.** Bistable beams as bits, snap-through as a switching
  event, and coupled bistable cells as gates are demonstrated in FDM ABS at 250 mm scale (Song et
  al. 2019), in single-piece printed cell lattices with a combination lock as the demo (Ion et
  al. 2017), and in cast silicone slabs that count squeezes (Kwakernaak and van Hecke 2023).
- **The single most transferable result is the counting and sequence-recognising slab.** A
  rubber block with slits counts compression cycles up to 10, resets when the squeeze is fully
  released, and a "lock and key" variant reaches one particular internal state only if three
  different squeeze depths arrive in the order B, A, C. A hand-held version works with manual
  squeezing. It is one material, with no separate parts.
- **Delay is the cheapest new primitive.** A viscoelastic dome held inverted and then released
  stays put and snaps back later. The 2025 "metashell" paper programs that delay from seconds to
  2.4 days. The physics (Gomez, Moulton and Vella 2019) says why it is touchy: the delay scales as
  the inverse square root of how close the shell is to true bistability, so small geometry or
  temperature changes move it a lot. Viscous dashpots (a ball sinking through silicone oil) are
  the more predictable alternative: my estimate is 30 s to 5 min for a 3 mm steel ball over 10 mm
  depending on oil grade.
- **Puzzle and lock craft already contains every "condition" a magician could want**, and
  hobbyists have printable examples: open only when spun (centrifugal balls), only after a tilt
  sequence (a 1929 gravity-lock patent and a 1999 "sequential attitude-responsive" puzzle patent),
  only after a tap, only one way up. What magic has not done is treat these as *who-is-holding-it
  discriminators* and as *out selectors* instead of as puzzles.
- **Rate dependence separates performer from spectator.** A dashpot, a seat-belt-style inertia
  pawl or a viscoelastic latch gives an object that yields to slow handling and locks against
  fast handling, or the reverse. "Pull as hard as you can" then guarantees failure, and the prop
  contains nothing a spectator would call a mechanism.
- **Frequency is an addressing scheme.** Printed cantilever reeds follow simple beam formulas;
  my estimate is that a 0.8 mm x 40 mm PLA reed sits near 135 Hz and that 6 to 8 reeds per octave
  can be told apart. One of several identical-looking objects on a shared base can be made to
  respond to a rhythm, a hum or a tuning fork while the others stay still. The pendulum version
  is a standard physics lecture demonstration.
- **Electronics-free fluidic logic is now a desktop print.** A TPU bistable valve prints in about
  3 h on a Prusa MK3S and switches at about 134 kPa; whole grippers with embedded control print
  in one piece; modular printed gates respond in about 100 ms. They need a pressure source, so in
  magic they suit a squeezed bulb, a blown tube or a hidden syringe.
- **Printed plastic is a poor long-term spring.** Printed PLA loses 11 to 14% of its stress in
  the first 500 s at room temperature. Folded PLA, PETG and nylon hinges fail in the low hundreds
  of cycles; TPU and polypropylene survive one to two million. Design rule: never store a printed
  mechanism cocked; make the as-printed shape the armed state, or use TPU, polypropylene or a
  steel spring for the energy store.
- **Classical magic already has mechanical state** (Okito box 1909, Lippincott box about 1949,
  Tenyo's plastic mechanisms, locking card boxes), but always as rigid separate parts with a seam
  somewhere. What is new is: no seam (one printed piece, moving parts hidden behind layer lines);
  state that depends on history (count, order, elapsed time, rate); and unit cost low enough
  (cents to a few dollars) that the prop can be broken open or given away every show.
- **Inverse design exists but stops short of a hobbyist button.** Differentiable design of
  multistable structures from a target energy curve, optimisation of planar multistable
  mechanisms, and a path-to-shape code for rolling "trajectoids" are published. In practice an
  LLM writing parametric CAD plus beam formulas plus two or three print-and-test rounds is the
  realistic loop for single bistables, reeds, centrifugal thresholds and dashpots.

---

## 2. Catalog

### 2.1 Mechanical logic and memory in one piece of material

**A. Digital mechanical metamaterials (bistable-spring cells that pass a signal).**
A printed lattice in which each cell contains a bistable spring. Triggering a cell discharges
its spring, and the impulse triggers neighbouring cells, so a "bit" travels through the block.
The authors extend the cell to simple logic functions and show a combination lock, with a custom
editor for placing cells, routing signals and simulating them. The object prints in one piece
with no assembly. The cells are single-shot until re-cocked.
- Refs: Ion, Wall, Kovacs, Baudisch, "Digital Mechanical Metamaterials", CHI 2017,
  doi 10.1145/3025453.3025624; project page https://hpi.de/baudisch/projects/digital-mechanical-metamaterials.html.
  Predecessor: Ion et al., "Metamaterial Mechanisms", UIST 2016 (a door latch printed as one
  block of shear cells that turns handle rotation into latch travel),
  https://researchr.org/publication/IonFWKALLCB16.
- Accessibility: hobbyist-buildable on FDM or resin; cell size is centimetre scale (the paper's
  exact cell dimensions were not on the pages I could open).
- Magic relevance: *hold/release*, *control*, *prove ordinariness*. A latch that is a lattice
  has no hinge pin, no spring, no screw. L3 when the lattice sits under a printed skin. Weakness:
  a visible cell lattice reads as "designed"; it must be hidden or passed off as decorative
  infill.
- Prior use in magic: none found.

**B. Buckled-flexure logic gates (NOT, AND, OR, NAND, NOR).**
Gates built from pre-compressed flexures with two stable positions; inputs and outputs are forces
and displacements. Demonstrated at three scales: about 250 mm in FDM ABS on a Stratasys F370,
about 25 mm by projection microstereolithography, and a 38 x 38 x 3 micrometre bistable element
by two-photon lithography. Each flexure must be pre-compressed past its buckling threshold to
become bistable, and the authors keep pre-compression below 0.163 of flexure length to avoid a
second buckling mode. No cycle life is reported.
- Refs: Song, Panas, Chizari, Shaw, Jackson, Hopkins, Pascall, Nature Communications 10 (2019),
  https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6382908/.
- Accessibility: the 250 mm FDM version is hobbyist-buildable; a hand-sized 25 mm version needs a
  resin printer and careful pre-load.
- Magic relevance: an AND gate is "releases only if two things are both true" (both buttons
  squeezed, lid shut and box inverted). Conditions can be combined without adding parts.

**C. Soliton lines: a signal that travels through rubber like dominoes.**
Bistable elastomer beams joined by soft springs. When one snaps it releases stored energy into
the next, giving a transition wave of constant speed and shape over any distance, with printed
diodes (one-way lines) and logic gates. Damping stabilises the wave instead of killing it.
- Refs: Raney, Nadkarni, Daraio, Kochmann, Lewis, Bertoldi, PNAS 113 (2016),
  https://pmc.ncbi.nlm.nih.gov/articles/PMC5024640.
- Accessibility: printed in the paper by direct ink writing of silicone; a TPU FDM or cast
  silicone version is hobbyist-plausible (my judgement).
- Magic relevance: *move* and *tell* at a distance inside a soft object: press one end of a
  rubber strip, and something happens at the other end 300 mm away, with no rod, thread or wire
  and no rigid part to feel through a cloth. The diode means it cannot be worked backwards by a
  spectator. Single-shot until reset by pressing the beams back.

**D. Counting and sequence-recognising metamaterials (the key item).**
A silicone slab with slits forms a row of unit cells. Each cell has a thin "memory beam" that is
buckled left or right. Each full squeeze-and-release cycle moves a marker state one cell along,
so the slab counts cycles; the 11-cell sample counts ten. Samples were cast in Zhermack Double
Elite 32 silicone in 3D-printed moulds, with beams 37.1 mm long and memory beams 1.2, 1.5 or
1.8 mm thick. Counting uses compression strains between about 2.6% and 9.9%. Letting the strain
go fully to zero resets the counter. Because beam thickness sets the threshold strain, cells of
three thicknesses respond to three squeeze depths (A = 7.8%, B = 8.9%, C = 9.9%), and a composite
of four small counters reaches one unique state only for the sequence B, A, C: a mechanical lock
whose key is an ordered sequence of squeezes. A scaled-down hand-held four-cell counter works
under manual squeezing. A follow-up shows that coupled "hysterons" in series behave as finite
state machines and can parse strings of inputs.
- Refs: Kwakernaak and van Hecke, Phys. Rev. Lett. 130, 268204 (2023),
  https://arxiv.org/abs/2302.06947 (full text read at https://ar5iv.labs.arxiv.org/html/2302.06947);
  Liu, Teunisse, Korovin, Vermaire, Jin, Bense, van Hecke, PNAS 121 (2024),
  https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11145188/; background on "pathways":
  https://arxiv.org/pdf/2204.06488 and https://arxiv.org/pdf/2106.14441.
- Accessibility: hobbyist-buildable. A printed mould plus two-part platinum silicone is about
  $30 to $40 of material for many samples (my estimate). Tolerance is the difficulty: the three
  thresholds are only about 1% strain apart, so amplitude must be set by hard stops, not by feel.
- Magic relevance: *know*, *delay*, *control*. It lets a prop distinguish the third press from
  the second, or the order in which three different-sized things were pushed against it, with
  nothing inside but slits. L3. Readout is the open question for magic: the beam states must be
  felt, seen through a pinhole, or coupled to a latch.
- Prior use in magic: none found.

**E. Multistable origami as memory and logic.**
Bistable waterbomb folds act as bits and are coupled into AND, OR and three-input majority
gates in polypropylene sheet, with a humidity-driven write and erase. Kresling "bellows" cells
are two-state memory units; a chain of four with graded switching forces can be driven to any of
its 16 states by one push-pull input, following the Preisach hysteresis model. Kresling-inspired
switches have been assembled into memory boards.
- Refs: Treml, Gillman, Buskohl, Vaia, "Origami mechanologic", PNAS 115 (2018),
  https://pmc.ncbi.nlm.nih.gov/articles/PMC6142273; Jules, Reid, Daniels, Mungan, Lechenault,
  Phys. Rev. Research (2022), https://arxiv.org/pdf/2106.08243.pdf; Yasuda, Tachi, Lee, Yang,
  Nature Communications (2017), https://www.nature.com/articles/s41467-017-00670-w; Kresling
  switch memory board, https://publishing.aip.org/publications/latest-content/building-mechanical-memory-boards-using-origami/.
- Accessibility: paper, polypropylene sheet or a craft cutter; under $20.
- Magic relevance: the Jules result is the interesting one. A paper bellows (a party blower, a
  drinking-straw concertina, a paper lantern) driven only by "push in, pull out by this much"
  can be set to any 4-bit pattern, and the pattern is readable from which cells are collapsed. It
  is a covert 16-state memory that looks like folded paper. L2 or L3.

**F. Mechanical computing as a field; Turing-complete marble machines.**
The Nature Perspective frames information processing as a material property and surveys
bistable-bit architectures. Turing Tumble (a consumer marble-and-flip-flop board) is
Turing-complete in an idealised unbounded form, and its bit is a gravity-driven rocker that each
ball flips. These are existence proofs: a falling ball plus a rocker is a 1-bit counter, and any
finite conditional behaviour can in principle be built from them.
- Refs: Yasuda, Buskohl, Gillman, Murphey, Stepney, Vaia, Raney, Nature 598, 39 (2021),
  https://raney.seas.upenn.edu/wp-content/uploads/2022/01/Yasuda-2021-Mechanical-computing.pdf;
  Pitt, "Turing Tumble is Turing-Complete", https://arxiv.org/abs/2110.09343;
  https://en.wikipedia.org/wiki/Turing_Tumble.
- Magic relevance: a rocker that alternates left and right on successive balls or coins is a
  one-part "every second time" mechanism (see concept 5).

**G. Mechanical neural networks.** A lattice of beams whose stiffnesses are tuned so the lattice
"learns" several input-to-output shape behaviours. The demonstrator is the size of a microwave
oven and uses powered tunable beams, so it is not passive. Pointer only; lab-scale.
- Refs: Lee, Mulder, Hopkins, Science Robotics (2022),
  https://www.eurekalert.org/news-releases/968328.

### 2.2 Fluidic and pneumatic logic without electronics

**H. Soft valves, ring oscillators and printed gates.**
A soft bistable valve (a snapping membrane that kinks one of two tubes) gives NOT, AND and OR,
set-reset latches and shift registers, and three in a ring give an oscillator from a constant
pressure. A walking quadruped ran on three such valves as memory elements. Since 2023 the valves
print on desktop FDM machines: the WPI valve prints in about 3 h in Filaflex 60A TPU on a
$649 Prusa MK3S, with snap-through at 134 kPa and snap-back at 56 kPa, and unit-to-unit spread
up to 50 kPa. The UC San Diego gripper prints as one airtight piece including its control
valves, with no post-processing, and its STL files are public. The Freiburg modules print in
standard filaments, run from about 80 to over 750 kPa and respond in about 100 ms. A
straws-and-balloons logic element costs $0.45 and takes a novice five minutes.
- Refs: Preston et al., "Digital logic for soft devices", PNAS 116 (2019),
  https://pmc.ncbi.nlm.nih.gov/articles/PMC6475414; Preston et al., "A soft ring oscillator",
  Science Robotics (2019), https://www.gmwgroup.harvard.edu/publications/soft-ring-oscillator;
  Drotman, Jadhav, Sharp, Chan, Tolley, Science Robotics (2021),
  https://pubmed.ncbi.nlm.nih.gov/34043527; Kendre et al., arXiv 2312.01131,
  https://arxiv.org/html/2312.01131v1; Zhai et al., Science Robotics (2023),
  https://www.eurekalert.org/news-releases/997028 with files at https://zenodo.org/record/8127332;
  Conrad et al., Science Robotics (2024), doi 10.1126/scirobotics.adh4060, summary at
  https://www.hackster.io/news/these-3d-printed-pneumatic-logic-gates-make-for-robust-electronics-free-soft-robotics-1e0448a85961;
  tube-balloon logic and other printed fluidic circuits via https://par.nsf.gov/biblio/10279902
  and https://par.nsf.gov/biblio/10556530. The Harvard Octobot (Wehner et al., Nature 2016) is the
  well-known ancestor (unverified in this session).
- Accessibility: hobbyist-buildable, $5 to $30 of TPU and tubing. Needs a pressure source.
- Magic relevance: *hold/release*, *delay*, *move* inside soft props (a glove, a balloon animal,
  a rubber chicken, a squeezed bulb) where rigid mechanism would be felt. A ring oscillator turns
  one squeeze of a bulb into a timed sequence of events. Weaknesses: hiss, the visible bulb or
  tube, and spread between printed valves.
- Wall-attachment fluidics: 1960s "fluidic amplifiers" are bistable switches with no moving
  parts at all, in which a jet attaches to one of two walls and a puff at a side port flips it
  (unverified in this session; recalled from the fluidics literature). They are pure channel
  geometry, so they print trivially. See concept 9.

**I. Capillary and paper timers.** Paper-fluidic devices delay a liquid front with dissolvable
sugar barriers (seconds to hours), wax (about 1 min to 2 h) or dissolvable films in channels
(0.6 s to 11 min). One-line pointer: this belongs to the time-delay chemistry agent.
- Refs: https://pmc.ncbi.nlm.nih.gov/articles/PMC4240780;
  https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6953116/.

### 2.3 Condition-sensitive mechanisms from puzzle and lock craft

**J. Centrifugal locks (open only when spun).**
Steel balls or sliding latches sit in radial channels and block the lid. Spinning the box flat
on a table throws them outward and frees it. Hobby examples: a 2014 Make write-up; a Shapeways
box using four 6 mm ball bearings; a printable "spin-to-open" box with four floating latches
that must all move outward at once; a spin box in which spinning both ways moves pins and "a
little shake" re-locks them. A 2023 US patent describes the same ball-channel arrangement for a
storage box. My estimate of the threshold: a ball at radius r behind a ramp of angle theta
releases when (spin rate)^2 x r exceeds g x tan(theta); for r = 20 mm and a 30 degree ramp that
is about 2.7 revolutions per second, and 3.5 rev/s for 45 degrees. Carrying, shaking and
turning in the hands does not reach this in all channels at once; a table spin does.
- Refs: https://makezine.com/2014/12/09/a-3d-printed-centrifugal-puzzle-box/;
  https://shapeways.com/product/QVL2F63G2/centrifugal-puzzle-box; https://thangs.com/m/1266146;
  https://makerworld.com/es/models/495201-spin-box; https://patents.google.com/patent/US11612807.
- Accessibility: off-the-shelf models; $2 of filament plus ball bearings.
- Magic relevance: *hold/release* keyed to an action that has an innocent meaning (spinning a
  bottle, a coin, a top, a lazy Susan). L2 as a lock; L3 when spin *direction* or spin *rate*
  selects one of several outcomes (concept 2).

**K. Gravity pins and tilt-sequence locks.**
Pins or balls fall into or out of a blocking position according to orientation. A 1929 patent
describes a lock in which the box must be tilted through a sequence of orientations so the
locking balls clear their keepers; a later patent is titled "Sequential attitude-responsive
enclosure puzzle". A ball in a hidden labyrinth is a state machine whose input alphabet is "which
way is down".
- Refs: https://patents.google.com/patent/US1733772; US 5,944,311 at
  https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/5944311;
  https://brainvoyage.blog/puzzle-box-mechanisms; https://en.wikipedia.org/wiki/Lock_puzzle.
- Magic relevance: the same hardware run in reverse is a *recorder*: a one-way trap makes the
  ball remember the first orientation after arming (concept 4). FDM printing can seal a steel
  ball inside a part by pausing the print, so there is no lid or plug to find.

**L. Inertia and tap locks.** A mass on a spring or detent that moves only above an
acceleration threshold. My estimate: a 2 g steel ball held by a 0.2 N detent releases at about
10 g, which a rap on a table exceeds easily and normal handling (under about 3 g) does not.
Puzzle guides also describe weak-magnet catches that a precise tap dislodges. The vehicle seat
belt is the mass-produced example of the opposite logic: a pawl that locks the reel above a set
acceleration and leaves it free below (thresholds near 0.45 g for the vehicle sensor and about
1 to 2 g for the webbing sensor; unverified, recalled from seat-belt regulations).
- Refs: https://brainvoyage.blog/puzzle-box-mechanisms;
  https://www.firgelliauto.com/es/blogs/mechanisms/curious-padlock.
- Magic relevance: direction-sensitive tap release is a *hold/release* trigger that reads as a
  gesture. The seat-belt logic gives *spectator failure* by speed (concept 7).

**M. Hidden-compartment furniture and trick locks.** Roentgen's 18th-century cabinets coordinate
"hidden springs, lead weights, mechanisms and locks" so drawers open to reveal further drawers
at the touch of a button. Trick padlocks hide the real release behind a false interface or need
a multi-stage sequence. In magic, Vanishing Inc. sells a gimmicked lock that advertises that it
does *not* rely on gravity, which implies that gravity locks are the known earlier method.
- Refs: https://www.metmuseum.org/press-releases/extravagant-inventions-2012-exhibitions;
  https://www.metmuseum.org/es/essays/abraham-and-david-roentgen;
  https://vanishingincmagic.com/close-up-magic/the-larry-lock.

**N. One-time mechanisms.** Shear tabs, snap-off whiskers and one-way barbs that make a
mechanism work once and then become a solid, honest object. This is ordinary packaging
engineering (tamper-evident caps, cable ties, snap rivets); no magic-specific source was found.
In FDM a 0.4 mm single-wall tab breaks at a few newtons (my estimate), and a barbed snap-fit
cannot be reopened without breaking the part. See concept 3.

### 2.4 Time: delays without clocks

**O. Viscoelastic snap-through ("pseudo-bistability").**
A dome or arch that is only just short of bistable, made of a rubbery material, stays inverted
when released and snaps back by itself later. The toy "jumping popper" is the everyday example.
Theory: with epsilon measuring how far the structure is from true bistability, the snap delay
scales as epsilon^(-1/2) once the hold time is long, and grows exponentially with hold time when
the hold is short; the dimensional delay scales with the material's viscous time constant. So
delay rises with how long the shell was held inverted, and is very sensitive to geometry. A
minimum hold time is needed at all. The 2025 PNAS metashell combines a viscoelastic layer with a
monostable architected shell and programs delays from seconds to 2.4 days by setting the
pre-stored elastic energy, with the jump falling from over 9 body heights to 0.5 as the delay
grows. Related work shows creep lowers a shell's buckling load in a predictable way.
- Refs: Gomez, Moulton, Vella, J. Mech. Phys. Solids 124 (2019), https://arxiv.org/pdf/1807.05978
  (read at https://ar5iv.labs.arxiv.org/html/1807.05978); Gomez, Moulton, Vella, "Critical slowing
  down in purely elastic snap-through instabilities", https://arxiv.org/pdf/1609.03809;
  Brinkmeyer et al., pseudo-bistable domes,
  https://pure.ul.ie/en/publications/pseudo-bistable-self-actuated-domes-for-morphing-applications/;
  Qing, Zhou, Qi, Yin, PNAS 122 (2025), doi 10.1073/pnas.2503313122,
  https://par.nsf.gov/biblio/10638666-programmable-seconds-days-long-delayed-snapping-jumping-metashells;
  Stein-Montalvo et al., https://par.nsf.gov/biblio/10439540-pseudo-bistability-viscoelastic-shells
  and https://arxiv.org/pdf/2104.02554.
- Accessibility: hobbyist-buildable by casting silicone or urethane rubber in printed moulds, or
  by buying popper toys (under $1 each) and trimming them. Expect to tune by trial: rim
  thickness, a trimmed edge and room temperature all shift the delay.
- Magic relevance: *delay* plus *move*. A thing jumps, flips, opens or falls 5 to 60 s after the
  performer last touched it, and the actuator is a rubber bump that looks like a furniture foot.
  L2 or L3. Weakness: timing spread; plan routines that tolerate plus or minus 50%.

**P. Viscous dashpots and settling weights.** A mass moving through a thick liquid. Patents on
delay mechanisms note that simple dashpots and rotary plates usually give only a few seconds
unless the gap is very small, and describe a ball driven through a spiral passage of viscous
liquid to stretch the delay in a small package; rotary dampers filled with silicone oil are
standard catalogue parts, and trapped air makes their torque wander. My estimate from Stokes
drag for a free 3 mm steel ball: about 0.34 mm/s in 100,000 cSt silicone oil (10 mm in 30 s) and
about 0.034 mm/s in 1,000,000 cSt oil (10 mm in 5 min); a close-fitting tube slows this by a
further one to two orders of magnitude. Silicone oil viscosity moves by roughly 2% per degree C
(unverified), far less than the snap-through delay does.
- Refs: spiral orifice dashpot timer, https://patents.justia.com/patent/4109455; viscous delay
  mechanism for an auto-injector, US 8,409,138 at
  https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/8409138; visco-elastic delayed
  actuator, US 4,948,927 at https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/4948927.
- Accessibility: silicone oil in a sealed printed cavity; about $10 to $20 for 100 ml of a
  high-viscosity grade (my estimate of hobby prices; check supplier).
- Magic relevance: silent, repeatable *delay*; also a slow hidden *move* of the centre of mass
  (concept 8). The historical ancestor is the "tapper" die: mercury and oil in a dumbbell
  cavity, shifted to one end by tapping the die on the table and back again by a reverse tap;
  period accounts call them unreliable and say the tapping drew suspicion.
- Refs for tappers: https://www.inventionandtech.com/node/86011;
  https://www.doresabanning.com/casino-dice-designed-to-thwart-customer-cheating/.

### 2.5 Objects whose ordinary behaviour is conditional

**Q. Frequency-selective structures (reeds and pendulums).** The vibrating-reed frequency meter
is a row of 11 or 21 tuned steel reeds on one base; only the reed matching the drive frequency
swings visibly. The lecture-demo version is three or more pendulums of different lengths on one
bar: "with a bit of practice, via small movements of your hands you can drive any one of the
pendula you choose", and with equal lengths energy passes back and forth between two pendulums
through the shared support. A study of the hand-held Chevreul pendulum found success depends on
length (62% of participants with a 40 cm pendulum against 8% with a short one), which is the
same resonance seen from the ideomotor side. My estimate for printed reeds, from the cantilever
formula f = 0.16 (t / L^2) sqrt(E / rho) with PLA at E = 3.5 GPa and 1,250 kg/m^3: t = 0.8 mm,
L = 40 mm gives about 135 Hz, and L = 30 mm about 240 Hz; with a quality factor around 30 to 50
(my assumption) channels 10% apart in frequency are distinct.
- Refs: reed meter and coupled-reed models, https://core.ac.uk/download/518710702.pdf;
  https://lecdem.physics.umd.edu/g/g2/g2-07.html;
  https://raft.net/wp-content/uploads/2020/08/197-Magic-Pendulum.pdf;
  https://www.biorxiv.org/content/10.1101/841445v1;
  https://stevespangler.com/experiments/swinging-pendulum-stop-go-trick/.
- Magic relevance: *move* and *control* addressed to one of N identical objects with no contact
  and no line of sight. L1 as a demo, L2 or L3 when the responding object releases something
  (concept 6).

**R. Vibration ratchets.** Slanted bristles or pillars turn vibration into one-way travel by
alternating stick and slip; the direction of a bristle-bot can even reverse with drive
frequency. On a vibrating surface the physics is the same as for a self-vibrating bot.
- Refs: Cicconofri et al., https://arxiv.org/abs/1702.00343v1; https://arxiv.org/pdf/1410.8153;
  https://www.nature.com/articles/srep01851.
- Magic relevance: an object with a printed slanted-fibre sole walks one way across a table that
  is being drummed on, sung at through a speaker elsewhere, or sitting on a running fridge. It
  is also the missing link that turns a small resonant vibration into a large one-way latch
  travel (concept 6). L2.

**S. Rattlebacks, tippe tops, self-righting shapes.** A rattleback spun the "wrong" way
wobbles and reverses; printable designs use either a skewed base or a symmetric base with offset
end weights. The tippe top inverts only above a spin threshold; Gomboc-type shapes right
themselves (both unverified here; well known). These are L1 curiosities. The transferable idea is
narrower: an object that behaves identically to its twin except under one input (spin sense,
spin rate), which lets a performer and a spectator get different results from "the same" object
with the same visible action. Chance and dice physics belong to another agent.
- Refs: https://en.wikipedia.org/wiki/Rattleback; https://ar5iv.labs.arxiv.org/html/1202.6506;
  https://arxiv.org/pdf/1112.4913.

**T. Trajectoids.** Given a periodic path, an algorithm computes the shape that rolls along it
down a gentle slope. The test bodies are printed shells of 15.875 mm outer radius around a
1-inch steel ball; the code needs Python and the trimesh library, outputs cutting solids for a
boolean subtraction in CAD, and the calibration sphere must roll on a 0.5 degree slope, so print
accuracy matters. Shape files are on Zenodo.
- Refs: Sobolev, Dong, Tlusty, Eckmann, Granick, Grzybowski, Nature 620, 310 (2023),
  https://www.nature.com/articles/s41586-023-06306-y.pdf;
  https://github.com/yaroslavsobolev/trajectoids/blob/main/README.md.
- Accessibility: hobbyist-buildable, about $5 a piece.
- Magic relevance: *control chance or choice*. A lumpy "pebble" released on a barely tilted tray
  wanders along a pre-chosen zigzag to one of several targets. Slow, slope-sensitive and
  start-orientation-sensitive; best as an installation piece. L1 to L2.

**U. Granular jamming.** A bag of grains is soft until the air is removed and then hardens; the
universal jamming gripper is the reference. Note the correction to a common assumption:
vibration fluidises a jammed pack more than it locks one, so "shake to lock" is not supported
by what I found. The passive route is stored vacuum: a vacuum-packed brick is rigid until a
pinhole lets air in.
- Refs: Brown et al., https://arxiv.org/pdf/1009.4444; https://www.arxiv.org/abs/2212.06498.
- Magic relevance: *transform* rigid to limp once, silently, on a pin prick or a peeled sticker
  (concept 10). Limp to rigid needs a vacuum reservoir, which is bulkier.

**V. Rate-dependent materials and latches.** Shear-thickening fills (cornstarch and water is the
kitchen example) resist fast motion and yield to slow motion; dashpots do the same with a
defined law; viscoelastic foams and putties are soft to slow loads and stiff to impact. No
single primary source was opened for these in this session (unverified; textbook behaviour).
- Magic relevance: an object that passes a fast test (rap it, tug it, shake it) and fails a slow
  one, or the reverse. See concept 7.

### 2.6 Inverse design: from wanted behaviour to geometry

- **Differentiable design of multistable structures.** Mirramezani, Oktay and Adams take a
  target strain-energy-versus-displacement curve (how many stable states, how deep) and return a
  snap-through geometry using a differentiable isogeometric solver.
  https://arxiv.org/pdf/2309.04970.
- **Planar multistable compliant structures.** Zhang, Auzinger and Bickel (ACM Trans. Graphics
  2021) optimise bar-and-joint mechanisms to hold several chosen poses. Indexed at
  https://core.ac.uk/download/426963588.pdf (author-title match from search summary; not opened).
- **Cell-based editors.** Ion's metamaterial editors place shear and bistable cells and simulate
  them (2.1 A).
- **Morphology co-design for multistable grippers.** https://arxiv.org/html/2407.08111v1.
- **Trajectoid code** (2.5 T) is the cleanest example of "behaviour in, STL out" a hobbyist can
  run today.
- **General tools a hobbyist can run** (all unverified in this session; recalled): the BYU
  Compliant Mechanisms Research group's design library and Howell's handbook formulas; the
  Qiu-Lang-Slocum curved-beam bistable formulas (bistable when apex height exceeds about 2.3
  times beam thickness; peak force about 740 E I h / L^3); Sigmund-style 99-line topology
  optimisation codes; CalculiX through FreeCAD for nonlinear buckling and modal analysis;
  linkage synthesis programs such as Pyslvs and MotionGen.
- **What an LLM-plus-simulation loop can realistically do (my assessment).** Reliable: reed and
  pendulum frequencies (modal analysis lands within about 10% and the part is then trimmed);
  centrifugal and gravity thresholds (closed-form); dashpot delays (closed-form, then one
  calibration run); a single bistable beam's force and strain (formula plus one nonlinear FE
  check). Unreliable without physical iteration: anything contact-rich with friction, multi-step
  sequences in FDM where clearances vary by 0.1 mm, and pseudo-bistable delays, which are
  sensitive by their nature. A practical loop is: LLM writes parametric OpenSCAD or CadQuery with
  the governing dimension exposed, prints a five-step "ladder" of that dimension in one job, and
  the builder picks the rung that works.

### 2.7 Classical magic prior art (what already exists)

Sources here are dealer pages, collector blogs and histories; internal workings are mostly not
published and are described only in general terms.

- **Robert-Houdin's Light and Heavy Chest** (1840s) is the canonical "behaves differently for
  the performer" prop. Its method was an electromagnet under the stage, so it is the ancestor of
  the "it's electric" explanation this slice tries to escape.
  https://jimsteinmeyer.com/2022/04/14/what-we-hide-problems-in-algeria-part-two/;
  https://gutenberg.org/files/77917/77917-h/77917-h.htm.
- **Okito box (about 1909) and Lippincott box ("Quarter Go", about 1949).** Small rigid boxes
  with a concealed second way in. The Lippincott box is locked by a spectator with a padlock and
  a marked coin is later found inside. Later makers changed the mechanism so the box can be
  examined before and after (Porper's Strong Box), and one lookalike drops the mechanism
  entirely. The recurring weakness is the seam of the secret panel and the need to keep the box
  away from determined hands.
  https://www.martinsmagic.com/allmagic/close-up/the-lippinkito-by-douglas-wayne-illusioneering;
  https://stevensmagic.com/blogs/gemini/1995-mike-rogers-all-magicians-do-it;
  https://www.penguinmagic.com/tricks/tagged/coin-to.
- **Tenyo.** The reference for injection-moulded mechanical props. The company's own account of
  its process shows the pattern: Zig-Zag Cig (1981) began with a mirror method and was replaced
  by a mechanical one; Vault Vision became a product once Shigeru Sugawara "created a new
  mechanism to display the marks"; Mystery China Box (2001) relocated a hidden pocket and added a
  mechanical gimmick so it works inches from the eyes. Reviewers of Crystal Cleaver report that
  "poking and prodding revealed nothing". Critics note the props read as toys and some are
  fragile. The mechanisms are rigid sliding and pivoting parts in a moulded shell: state is
  held by position, friction and gravity, and it is binary and immediate, with no memory of
  history, count or time.
  https://tenyo-magic.blogspot.com/p/tenyo-development-process.html;
  https://tenyo-magic.blogspot.com/2010/05/t-201-mystery-china-box.html;
  https://magicfakers.blogspot.com/2007/10/vault-vision.html;
  https://www.vanishingincmagic.com/close-up-magic/crystal-cleaver/;
  https://www.vanishingincmagic.com/blog/talking-tenyo-toy-tricks/;
  https://boingboing.net/2017/03/08/i-am-oz-the-great-and-powerful.html.
- **Other mechanical classics** (unverified in this session; recalled from the general
  literature): the imp bottle and Chinese sticks (a hidden sliding or removable weight makes the
  object behave differently for the performer); the die box (a sliding weight supplies a false
  sound); locking card boxes and mechanical decks (a flap or shutter switches a face);
  "Seven Keys to Baldpate" lock routines (only one key works, by a concealed setting); Himber
  ring (a locking linking ring); Robert-Houdin's mystery clock (hands driven through transparent
  parts); Hofzinser's mechanical card props.
- **What printed and compliant methods add that these could not do:**
  1. One piece. No pin, screw, glued panel or parting line that differs from the layer lines
     all over the part.
  2. History. Count (2.1 D), order (2.1 D), elapsed time (2.4 O, P), rate (2.5 V), spin (2.3 J).
  3. Sealed inclusions. A ball, a drop of oil or a folded billet is enclosed during the print
     with no closure.
  4. Disposability. A PLA prop costs cents to a few dollars, so the ending can be "break it
     open", "keep it", or a one-shot mechanism that destroys its own secret (2.3 N).
  5. Variants on demand. Twenty copies each tuned to a different count, spin threshold or
     frequency are one overnight print.

### 2.8 Fabrication limits that decide whether any of this works

- **Fold-fatigue of printed hinges.** In a 2016 folding test, PLA specimens averaged roughly 136
  to 211 cycles, nylon 126 to 276 and PETG 733 to 960, while TPU reached the 2 million cycle cap
  and polypropylene about 1 million. A 2019 study agrees: TPU over two million, PP about one
  million, the rest under 1,000. These are full fold-over hinges, the worst case; a flexure kept
  under about 0.5 to 1% strain lasts far longer (my judgement), but the ranking of materials
  holds. Use TPU or PP wherever something must flex many times.
  https://utw10945.utweb.utexas.edu/sites/default/files/2016/188-Balderrama-Armendariz.pdf;
  https://link.springer.com/10.1007/s00170-019-04196-x;
  https://repository.tudelft.nl/record/uuid:7df15c93-e792-4a35-9b16-a74b0fdb7ea7.
- **Stress relaxation.** Printed PLA lost 11 to 14% of its stress in 500 s at room temperature,
  and more after 8 h at 50 C. PLA bilayer bistability "is temporary" under repeated actuation
  because of the same relaxation. Hour-to-month data for preloaded printed springs were not
  found. Working assumption: a PLA or PETG part left cocked in a drawer for a month will have
  lost a large part of its force and may have taken a set; a hot car will finish it. Design so
  that the as-printed, stress-free shape is the armed state and the "fired" state is the
  strained one, or put the energy in a steel spring or a TPU element.
  https://pmc.ncbi.nlm.nih.gov/articles/PMC9147248/;
  https://www.ntu.edu.sg/sc3dp/research-capabilities/research-projects/rationalising-the-onset-of-bistability-in-polylactic-acid-(pla)-bilayer-laminates-using-fused-filament-fabrication-(fff);
  https://www.sv-jme.eu/article/short-term-creep-behavior-of-different-polymers-used-in-additive-manufacturing-under-different-thermal-and-loading-conditions/.
- **Unit-to-unit spread.** Ten nominally identical printed TPU valves differed by up to 50 kPa
  in a 134 kPa switching pressure, and a printed pneumatic bistable valve drifted upward in
  critical pressure during fatigue testing. Expect plus or minus 20 to 40% on any printed
  threshold and design in a trim (a screw, a sanded tab, a ladder of variants).
  https://arxiv.org/html/2312.01131v1; https://arxiv.org/pdf/2110.01743.
- **Beam sizes (my estimates from the recalled Qiu-Lang-Slocum formulas, unverified).** With a
  0.4 mm nozzle the thinnest dependable flexure is one or two extrusion widths, 0.4 to 0.8 mm.
  A PETG curved beam 40 mm long, 5 mm deep, 0.4 mm thick with 1.2 mm apex height snaps at about
  0.7 N at about 0.6% peak strain; at 0.6 mm thick and 2 mm apex it is about 4 N but 1.5% strain,
  which is too much for PLA and marginal for PETG. Print flexures lying in the XY plane so the
  filament runs along the beam.
- **Print-in-place clearances.** Common hobby guidance is 0.2 to 0.3 mm between moving faces on
  a tuned FDM machine and 0.1 mm or less on resin (unverified in this session). A 0.2 mm gap that
  lies along a layer boundary is visually identical to every other layer line on the part; a
  gap that crosses layers is visible. "Fuzzy skin" slicer texture hides the rest.
- **Noise.** A snapping PLA or PETG bistable clicks audibly (the toy "clicker" is a snap dome);
  TPU and silicone snaps are dull thuds; dashpots, gravity pins in oil and centrifugal balls on
  felt are silent. Loose steel balls rattle, which is either a tell or, in a rattle or a shaker,
  the cover.
- **Brittleness.** Standard resin is too brittle for flexures; tough or flexible resins are
  needed, and they creep more (unverified; general hobby experience).

---

## 3. Capability primitives

1. *Now possible:* a solid-looking rubber block that counts 1 to 10 squeezes and resets on full
   release. *Because:* counting metamaterial with buckled memory beams. *Before:* ratchet wheels
   and pawls with visible parts. *Primitives:* know, delay, control.
2. *Now possible:* a block that reaches one state only if three different inputs arrive in one
   particular order out of six. *Because:* heterogeneous hysteron counters. *Before:*
   combination locks with dials. *Primitives:* know, control, hold/release.
3. *Now possible:* a latch, hinge and spring printed as one lattice with no separate part.
   *Because:* metamaterial mechanisms and bistable cells. *Before:* pins, screws, glued panels.
   *Primitives:* hold/release, prove ordinariness.
4. *Now possible:* a touch at one end of a 300 mm soft strip causes an event at the other end,
   one way only, with no rigid link. *Because:* bistable soliton lines with diodes. *Before:*
   threads, rods, pneumatic tubes. *Primitives:* move, tell.
5. *Now possible:* a 16-state memory set and read by pushing and pulling a folded paper bellows.
   *Because:* Kresling cells with graded thresholds. *Before:* pencil dots, crimps, memory.
   *Primitives:* know, tell.
6. *Now possible:* something moves by itself 5 s to 2.4 days after it was last touched, powered
   by a rubber dome. *Because:* viscoelastic snap-through. *Before:* clockwork, burning fuses,
   melting ice, an assistant. *Primitives:* delay, move, release.
7. *Now possible:* a silent hidden weight shift that takes 30 s to 5 min to complete and
   reverses when the object is turned over. *Because:* steel ball in 100,000 to 1,000,000 cSt
   silicone oil in a sealed printed cavity. *Before:* mercury "tappers" needing a visible tap.
   *Primitives:* delay, control chance, erase the evidence.
8. *Now possible:* a box that no handling opens except a table spin faster than about 3 rev/s.
   *Because:* centrifugal ball latches printed in place. *Before:* hidden catches a spectator can
   find by prodding. *Primitives:* hold/release, spectator failure, prove ordinariness.
9. *Now possible:* spin direction or spin speed selects which of 2 to 4 compartments opens.
   *Because:* one-way pawls plus graded centrifugal thresholds. *Before:* multiple-out boxes
   worked by a finger on a slide. *Primitives:* control choice, swap.
10. *Now possible:* a sealed object records the first orientation it was placed in after arming
    and keeps that record through later handling. *Because:* a ball in a one-way trap labyrinth
    sealed during the print. *Before:* electronic orientation sensors with radio. *Primitives:*
    know.
11. *Now possible:* a lid that opens to a slow pull and locks against a jerk, or the reverse.
    *Because:* inertia pawl or dashpot latch. *Before:* a secret catch held by the performer.
    *Primitives:* spectator failure, control.
12. *Now possible:* release triggered by a 10 g rap in one direction and by nothing else.
    *Because:* a detented mass on a flexure. *Before:* magnets and reed catches. *Primitives:*
    hold/release.
13. *Now possible:* one of 6 to 8 identical-looking objects on a shared base responds to a
    chosen rhythm or pitch. *Because:* printed reeds and pendulums tuned 10% apart. *Before:*
    threads, magnets, radio. *Primitives:* move, control, tell.
14. *Now possible:* table vibration is rectified into millimetres of one-way travel.
    *Because:* slanted-bristle stick-slip ratchets. *Before:* not available without a motor.
    *Primitives:* move, release.
15. *Now possible:* a mechanism that works exactly once and leaves a part with no working
    opening. *Because:* 0.4 mm shear tabs and one-way barbs printed in place. *Before:*
    hand-made breakaway gimmicks. *Primitives:* erase the evidence, prove ordinariness.
16. *Now possible:* a steel ball, a drop of oil or a folded paper enclosed in a part with no
    lid, plug or glue line. *Because:* pause-and-insert during FDM printing. *Before:* drilled
    and plugged holes. *Primitives:* conceal, prove ordinariness.
17. *Now possible:* twenty copies of a prop each with a different count, threshold or frequency
    for a few dollars. *Because:* parametric CAD and overnight printing. *Before:* one
    hand-built prop. *Primitives:* brute-force outs, personalise.
18. *Now possible:* one squeeze of a bulb produces a timed sequence of three or more events.
    *Because:* printed soft-valve ring oscillators and latches. *Before:* clockwork or
    electronics. *Primitives:* delay, move.
19. *Now possible:* a breath is steered to one of two outlets with no moving part. *Because:*
    printed wall-attachment fluidic switch (unverified). *Before:* a finger over a hole, or a
    valve. *Primitives:* control, move.
20. *Now possible:* a rigid bar goes limp silently on a pin prick. *Because:* stored-vacuum
    granular or layer jamming. *Before:* jointed "stiff rope" props with internal mechanics.
    *Primitives:* transform.
21. *Now possible:* a rolling body follows a pre-drawn zigzag down a tray. *Because:* trajectoid
    solver and a printed shell around a 1-inch ball. *Before:* tilting the tray, magnets under
    the table. *Primitives:* control chance.
22. *Now possible:* a moving gap that cannot be seen. *Because:* a 0.2 mm print-in-place
    clearance aligned with layer lines under fuzzy skin. *Before:* tight woodwork and paint.
    *Primitives:* conceal, prove ordinariness.
23. *Now possible:* a spring force chosen to within about 20% before the first print.
    *Because:* closed-form beam formulas an LLM can apply, plus a printed ladder of variants.
    *Before:* filing and bending by trial. *Primitives:* (design speed).

---

## 4. Effect concepts

Eleven mechanisms. Nine are L2 or L3. All are meant to end with the prop handed over, broken
open or kept. None has been built; each is labelled with how speculative it is.

### 4.1 The Order Witness (L3, know; speculative but grounded)
- **Effect.** While the performer's back is turned, a spectator pushes three coins of different
  values through the slot of a small rubber-walled money box in any order they like. The
  performer picks up the box and names the order. The box is then cut open with scissors: rubber
  and three coins.
- **Method.** One wall of the slot is a cast silicone counting slab of the lock-and-key kind
  (2.1 D). Each coin's thickness sets a compression depth as it passes two hard lips; the three
  thicknesses play the roles of amplitudes A, B and C. The slab's final beam pattern differs for
  each of the six orders. Readout: the memory beams bulge a thin outer skin, read by a thumb
  stroke, or by a glance at a row of slits that looks like a moulded grip pattern. Full release
  of a hidden pre-compression strap resets it.
- **BOM and cost.** Printed two-part mould, 100 g platinum silicone, PLA lips: about $15.
- **Difficulty.** High. Coin thicknesses differ by only 0.2 to 0.4 mm, so the lips must turn that
  into strain steps of about 1%. Start with three custom tokens 2, 3 and 4 mm thick.
- **Risks.** Threshold scatter; a spectator pushing a coin halfway and withdrawing it.
- **Novelty.** High. No electronics-free order-recording prop was found.

### 4.2 Spin the Bottle Out-Selector (L3, control choice)
- **Effect.** A sealed wooden-looking capsule is spun on the table to choose a spectator. The
  chosen person names a card colour, or one of four suits. They unscrew the capsule themselves:
  inside is a single slip with their choice. The capsule is theirs to keep.
- **Method.** The capsule has two (or four) internal cells. One-way centrifugal pawls set a
  shutter according to spin *direction* (two outs); a second pair of balls with a higher
  threshold adds spin *speed* (four outs). The selecting spin happens after the choice, as a
  second "spin to see who opens it". The selection balls then drop into a pocket of grease and
  stay there, so later shaking changes nothing.
- **BOM and cost.** PLA print in place, four to six 4 mm steel balls dropped in at a print
  pause, a dab of grease: under $2 each.
- **Difficulty.** Medium. Thresholds are closed-form (2.3 J).
- **Risks.** The unused slips are still in the capsule; they must be locked away by a shutter
  whose seam follows a layer line. A wobbly spin gives a half-set shutter.
- **Novelty.** Medium-high. Centrifugal puzzle boxes exist; using spin sense and speed as a
  secret selector with a plot reason for spinning was not found.

### 4.3 The Honest Block (L3, erase the evidence, prove ordinariness)
- **Effect.** A signed coin vanishes. A printed plastic cube that has been on the table
  throughout is handed out with a junior hacksaw. Sawn open, it has the coin in a closed cavity
  in its centre.
- **Method.** The cube prints with a coin chute closed by a print-in-place slide whose seam is a
  layer line. Loading the coin pushes a carrier past one-way barbs; a 0.4 mm shear tab snaps and
  the carrier seats flush. From then on the block has no working opening: the chute is filled by
  the carrier, which is the same plastic with the same layer pattern. The load is by the usual
  sleight; the technology removes the "secret door" theory, since the door no longer exists.
- **BOM and cost.** About 40 g PLA, $1 per performance.
- **Difficulty.** Medium. Hiding the last seam is the craft problem; put it on the bottom face
  and saw across it.
- **Risks.** A spectator who examines the cube closely *before* the load; keep it in view but
  out of hands until after.
- **Novelty.** Medium-high as an architecture: a Lippincott-type box that turns into a solid
  object. Nest-of-boxes and sealed-container plots are old; a self-destroying entrance in a
  give-away print is, as far as I found, not marketed.

### 4.4 First-Face Die (L3, know)
- **Effect.** A large plain die is given to a spectator, who sets it on the table with any
  number up, covers it, and may afterwards pick it up, shake it and hand it back any way round.
  The performer weighs it in the hand and names the number. The die is then smashed with a
  mallet: plastic shards and one steel ball.
- **Method.** Inside is a six-armed chamber. On arming (a specific two-tilt move by the
  performer) a ball sits on a central pedestal. The first time the die rests on a face, the ball
  rolls down into that face's arm past a one-way gate and cannot return. The performer reads it
  by the shift in the centre of mass (my estimate: a 4 g ball in a 30 g, 40 mm die moves the
  balance point about 2 mm, easily felt by rolling the die on the fingertips), or by which face
  the die prefers when set on an edge.
- **BOM and cost.** PLA, one 10 mm steel ball inserted at a print pause: under $1.
- **Difficulty.** Medium. The one-way gate is a TPU or thin-PETG flap.
- **Risks.** Rattle (pack the arms with felt or grease); a spectator who notices the bias later
  (the mallet ending removes the die).
- **Novelty.** High against current practice, which uses radio dice. Loaded-shell and peek
  methods are old; a history-recording passive die was not found.

### 4.5 The Nth Opening (L3, delay, release)
- **Effect.** A small box is passed along a row. Each person opens it, sees it empty and closes
  it. The person the audience chose in advance, or the person at a freely named position, opens
  it and finds the borrowed ring.
- **Method.** Each open-close cycle advances a hidden counter one step: either a print-in-place
  ratchet behind the hinge or, for a soft pouch version, a counting slab squeezed by the clasp
  (2.1 D counts to ten). On the Nth cycle the counter frees a false floor. N is set beforehand by
  where the counter starts; with a quick dial under the base it can be set after the number is
  named. The alternating rocker of a marble computer (2.1 F) gives the "every second person"
  version with one moving part.
- **BOM and cost.** PLA or wood-fill print, one steel pin: $2.
- **Difficulty.** Medium.
- **Risks.** Someone opens it twice or only half closes it. Make the lid snap shut over-centre so
  half cycles cannot happen.
- **Novelty.** Medium-high. Counting escapements are ancient; a hand-round box that changes
  behaviour on a chosen count with the performer nowhere near it was not found as a product.

### 4.6 The Tuning-Fork Lock (L3, hold/release, control; speculative)
- **Effect.** Five tuning forks of different notes and a sealed wooden box. A spectator chooses
  a fork, strikes it and touches its stem to the box lid. Four forks do nothing. One makes the
  lid creep open. Variation: the box opens when the performer hums at it and for nobody else.
  The box is then split along the grain to show wood and plastic.
- **Method.** Inside the lid a printed reed is tuned to one fork (2.5 Q). At resonance its tip
  amplitude is tens of times larger than off resonance, and its tip drives a slanted-tooth
  ratchet (2.5 R) that walks a locking pin out a tooth per cycle; a few seconds of tone free the
  lid, which a weak spring then lifts. Off-resonance forks cannot advance the ratchet because the
  amplitude stays below one tooth pitch. My estimate for airborne drive: a hummed note at about
  100 dB on a 10 cm^2 diaphragm gives about 3 mN, and a 200 Hz reed with Q of 50 would swing a
  few tenths of a millimetre, which is marginal; the fork stem pressed on the lid delivers far
  more and is the version to build first. Which fork "works" can be changed by sliding a tip
  mass, so the chosen fork can be made the right one after the choice.
- **BOM and cost.** Tuning-fork set $15 to $30, printed reed and ratchet, small box: about $40.
- **Difficulty.** High. Tooth pitch near 0.1 mm suggests a resin print or a strip of fine file
  as the ratchet.
- **Risks.** Reed frequency drifts with temperature and humidity (PLA modulus changes); a metal
  reed (a feeler-gauge strip) is more stable.
- **Novelty.** High. The reed meter is 19th-century technology; a frequency-keyed passive latch
  in a magic prop was not found.

### 4.7 Sword in the Stone (L3, spectator failure, control)
- **Effect.** A small dagger stands in a printed "stone". The strongest person present cannot
  pull it out. A child, or whoever the performer nominates, lifts it out with two fingers. The
  stone is handed round.
- **Method.** The blade sits in a sleeve gripped by an inertia pawl of the seat-belt type
  (2.3 L): above a set acceleration a small mass swings a pawl into the blade's notches; below
  it the blade slides free. A dashpot version does the same job more smoothly: the blade end is
  a piston in thick silicone oil, so a 20 N steady pull takes about three seconds and a 300 N
  heave gets a few millimetres before the person gives up (drag scales with speed). The performer
  controls the outcome only by coaching: "pull as hard as you can" against "just lift it gently
  while I count to three". The reverse logic (opens to a jerk, not to a slow pull) is the 10 g
  tap latch.
- **BOM and cost.** PLA or stone-effect filament, 5 ml silicone oil or one steel ball: $3.
- **Difficulty.** Low to medium.
- **Risks.** A strong person who happens to pull slowly. Add a second condition (a slight
  twist, or stone flat on the table so a gravity pin is clear) for security.
- **Novelty.** Medium. Rate-dependent release is common engineering; its use as the discriminator
  between two people in a spectator-failure plot was not found.

### 4.8 The Patient Die (L2, control chance, delay)
- **Effect.** Spectators roll a die as often as they like and it behaves. Later, on the one roll
  that matters, it lands as required. It can be rolled again afterwards and is fair.
- **Method.** A sealed cavity along one body diagonal holds a steel ball in 100,000 to
  1,000,000 cSt silicone oil (2.4 P). Rolling and handling average out; the ball stays near
  mid-cavity. Left standing on a chosen face for one to five minutes during patter, the ball
  sinks to the low end and the die is loaded toward the opposite face. Standing it on the
  opposite face, or keeping it in a pocket, undoes it. This is the 19th-century "tapper" with the
  tell removed: no tap, no click, no mercury. The size of the bias and how to use it belong to
  the dice-physics agent.
- **BOM and cost.** Resin-printed or drilled die, 3 mm ball, oil: $2.
- **Difficulty.** Medium (sealing oil without a bubble).
- **Risks.** Temperature shifts the timing; opaque die only. Gambling use is cheating; this is a
  stage prop.
- **Novelty.** Medium. A direct descendant of tappers with a time constant in place of a tap.

### 4.9 The Honest Breath (L2 to L3, control; speculative, fluidic part unverified)
- **Effect.** A spectator answers yes-or-no questions by blowing through a carved wooden pipe
  with two small pinwheels or whistles on top. For true answers one spins, for lies the other.
  The pipe is then split lengthwise: only smooth channels.
- **Method.** A wall-attachment fluidic switch (2.2 H): the jet clings to one of two diverging
  walls and exits by that branch. A pinhole control port under the performer's thumb, or a
  squeezed pulse from the hand holding the pipe, flips it. No moving part exists to find. The
  performer knows the truth by ordinary means (a force or a peek); the prop only removes the
  "there's a valve" theory.
- **BOM and cost.** One print, $1. Channel dimensions need experiment; breath jets are slow and
  the switch may need a narrow nozzle of 1 to 2 mm.
- **Difficulty.** Medium; unknown whether breath flow rates give reliable wall attachment at
  this scale.
- **Risks.** Performer must hold the pipe.
- **Novelty.** High in magic if it works.

### 4.10 The Rubber Foot (L2, delay, move)
- **Effect.** A matchbox, a coin under a glass, or a face-down card is left on the table. The
  performer walks away. Twenty to forty seconds later it jumps or flips by itself.
- **Method.** A pseudo-bistable dome (2.4 O) disguised as one of four rubber feet on a box, or a
  clear silicone dot on a coin. Pressing the box down while setting it on the table inverts the
  dome; it snaps back after its delay and kicks. Hold time is part of the setting: a longer
  press gives a longer wait. Buy poppers and trim, or cast domes with rim thickness varied in
  0.1 mm steps and keep the ones that land in the wanted window at room temperature.
- **BOM and cost.** Silicone, printed mould: $10 for dozens.
- **Difficulty.** Low to build, medium to tame.
- **Risks.** Delay spread and temperature; structure the routine so the moment is "sometime in
  the next minute".
- **Novelty.** Medium. Poppers are toys and have surely been used for gags; a dome tuned for a
  long delay and built into an object as an innocent part was not found.

### 4.11 The Tired Wand (L1 to L2, transform)
- **Effect.** A rigid wand or a stiff newspaper tube is rapped on the table, then visibly wilts
  in the spectator's hands. It can be cut up: grains or paper strips in a sleeve.
- **Method.** Stored-vacuum jamming (2.5 U): a sleeve packed with coarse grains or stacked paper
  strips, evacuated and sealed, is rigid. A pinhole under a sticker, opened by the performer or
  by a slow-leak plug of the right size, lets air in and it goes limp over a second or over a
  minute.
- **BOM and cost.** Vacuum-sealer bag, coffee grounds or paper strips: $2.
- **Difficulty.** Low.
- **Risks.** Leaks before the show; crinkly feel.
- **Novelty.** Low to medium; included as the passive rigid-to-soft primitive.

---

## 5. Dead ends and overhyped items

- **Mechanical neural networks.** Microwave-oven-sized and powered. Not passive, not small.
- **Micro-scale logic gates.** The 38 micrometre element needs two-photon lithography and
  optical tweezers; nothing below about 25 mm gate size is hobby territory.
- **Large mechanical computers hidden in props.** Each bit is a beam centimetres long. Ten bits
  fill a paperback. Useful computation here means one to four bits and a counter, not arithmetic.
- **Shake-to-lock granular bags.** Vibration loosens jammed packs; I found no support for a bag
  that locks solid on shaking without a pressure change.
- **Printed plastic as a stored spring over weeks.** PLA relaxes by more than a tenth in minutes.
  A PLA mechanism left cocked will let the builder down.
- **Pseudo-bistable delays as a precise timer.** The inverse-square-root law near the
  bistability threshold means the delays that are long enough to be interesting are the least
  repeatable. Use a dashpot when the second matters.
- **Rattlebacks, tippe tops, Euler's disk, chain fountains, Gomboc shapes as effects.** They are
  recognised physics toys. Their value is the narrower idea of spin-sense or spin-rate
  dependence.
- **Trajectoids on a performing table.** They need a slope accurate to a fraction of a degree,
  a clean hard surface and a careful start; slow and fussy for live work.
- **Pneumatic logic inside rigid hand props.** It needs a pressure source and tubing and it
  hisses; a ratchet or a ball does the same job in a hard prop.
- **Voice-keyed latches by airborne sound alone.** My estimate puts reed motion at tenths of a
  millimetre at shouting level. Contact drive (a fork stem, a tapped rhythm) is the workable
  version.

---

## 6. Open leads

- Kwakernaak's 2025 Leiden thesis "Counting Metamaterials" probably has design rules and
  smaller, 3D-printed (not cast) counters; the supplementary "Handheld_Counter" video shows the
  hand-squeezed version. Worth a full read before building 4.1 or 4.5.
- The full text of Qing et al. (PNAS 2025) for the metashell's size, materials and how the delay
  is set; this decides whether 4.10 can be tuned by design instead of by sorting.
- Hour-to-month creep data for preloaded FDM springs in PETG, nylon, PP and TPU. Not found.
- Named puzzle-lock and puzzle-box designers (Popp, Strijbos, Stickman, Karakuri group) publish
  little, but reviewers describe mechanisms in general terms; a puzzle-collector forum trawl
  would turn up more condition types (temperature, two-hand, blow-to-open).
- Wall-attachment fluidic switches at breath flow rates: needs a primary source and a test
  print.
- Whether a printed slanted-tooth ratchet can be driven by a resonant reed at 0.1 mm amplitude;
  a resin printer or a strip of needle file may be needed.
- Temperature and humidity as secret inputs (wax pellets, bimetal, moisture-swelling wood or
  paper hinges) belong to the smart-materials agent but combine naturally with every latch here.
- The ACM full texts of Ion et al. for cell sizes and reset force of the bistable cells.

---

## 7. Sources

Mechanical logic, memory and counting
- https://arxiv.org/abs/2302.06947 - Kwakernaak and van Hecke, counting metamaterials (abstract).
- https://ar5iv.labs.arxiv.org/html/2302.06947 - same, full text with dimensions and strains.
- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11145188/ - Liu et al., coupled hysterons as finite state machines.
- https://arxiv.org/pdf/2204.06488 - sequential snapping and pathways in a metamaterial.
- https://arxiv.org/pdf/2106.14441 - pathways and memory in compressed corrugated sheets.
- https://hpi.de/baudisch/projects/digital-mechanical-metamaterials.html - Ion et al., digital mechanical metamaterials.
- https://researchr.org/publication/IonFWKALLCB16 - Ion et al., Metamaterial Mechanisms, UIST 2016.
- https://publishup.uni-potsdam.de/files/42986/ion_diss.pdf - Ion's dissertation (listed, not opened).
- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6382908/ - Song et al., printable mechanical logic gates.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC5024640 - Raney et al., soliton signal lines, diodes, gates.
- https://raney.seas.upenn.edu/wp-content/uploads/2022/01/Yasuda-2021-Mechanical-computing.pdf - Nature Perspective.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC6142273 - Treml et al., origami mechanologic.
- https://arxiv.org/pdf/2106.08243.pdf - Jules et al., Kresling bellows memory.
- https://www.nature.com/articles/s41467-017-00670-w - Yasuda et al., origami mechanical memory.
- https://publishing.aip.org/publications/latest-content/building-mechanical-memory-boards-using-origami/ - Kresling switch memory board.
- https://arxiv.org/abs/2110.09343 - Pitt, Turing Tumble is Turing-complete.
- https://en.wikipedia.org/wiki/Turing_Tumble - Turing Tumble overview.
- https://www.eurekalert.org/news-releases/968328 - mechanical neural networks press release.

Fluidic logic
- https://pmc.ncbi.nlm.nih.gov/articles/PMC6475414 - Preston et al., digital logic for soft devices.
- https://www.gmwgroup.harvard.edu/publications/soft-ring-oscillator - soft ring oscillator.
- https://pubmed.ncbi.nlm.nih.gov/34043527 - Drotman et al., electronics-free walking robot.
- https://spectrum.ieee.org/soft-legged-robot-pneumatic-circuitry - coverage of the same.
- https://arxiv.org/html/2312.01131v1 - Kendre et al., FDM-printed soft bistable valve.
- https://www.eurekalert.org/news-releases/997028 - Zhai et al., monolithic printed gripper.
- https://zenodo.org/record/8127332 - STL files for the same.
- https://www.hackster.io/news/these-3d-printed-pneumatic-logic-gates-make-for-robust-electronics-free-soft-robotics-1e0448a85961 - Conrad et al. printed gates.
- https://techxplore.com/news/2024-02-scientists-3d-pneumatic-modules-movements.amp - same.
- https://par.nsf.gov/biblio/10279902 - printed or tube-balloon fluidic circuit record.
- https://par.nsf.gov/biblio/10556530 - FDM-printed logic gates from flexing beams.
- https://arxiv.org/pdf/2110.01743 - printed pneumatic bistable valve with tunable characteristics.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC4240780 - paper-fluidic delays (sugar, wax).
- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6953116/ - paper time-delay valves.

Delays and snap-through
- https://arxiv.org/pdf/1807.05978 - Gomez, Moulton, Vella, viscoelastic snap-through.
- https://ar5iv.labs.arxiv.org/html/1807.05978 - same, HTML.
- https://arxiv.org/pdf/1609.03809 - critical slowing down in elastic snap-through.
- https://pure.ul.ie/en/publications/pseudo-bistable-self-actuated-domes-for-morphing-applications/ - pseudo-bistable domes.
- https://par.nsf.gov/biblio/10638666-programmable-seconds-days-long-delayed-snapping-jumping-metashells - Qing et al., PNAS 2025.
- https://par.nsf.gov/biblio/10439540-pseudo-bistability-viscoelastic-shells - pseudo-bistability of shells.
- https://arxiv.org/pdf/2104.02554 - delayed buckling of spherical shells.
- https://patents.justia.com/patent/4109455 - spiral orifice dashpot timer.
- https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/8409138 - viscous delay mechanism, auto-injector.
- https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/4948927 - visco-elastic delayed actuator.
- https://www.inventionandtech.com/node/86011 - history of gaffed dice including tappers.
- https://www.doresabanning.com/casino-dice-designed-to-thwart-customer-cheating/ - tappers and casino countermeasures.

Puzzle and lock craft
- https://makezine.com/2014/12/09/a-3d-printed-centrifugal-puzzle-box/ - centrifugal puzzle box.
- https://shapeways.com/product/QVL2F63G2/centrifugal-puzzle-box - same, product page.
- https://thangs.com/m/1266146 - centrifugally unlocked lock box.
- https://makerworld.com/es/models/495201-spin-box - spin box with shake re-lock.
- https://patents.google.com/patent/US11612807 - puzzle storage box with centrifugal balls.
- https://patents.google.com/patent/US1733772 - gravity-control lock, 1929.
- https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/5944311 - sequential attitude-responsive enclosure puzzle.
- https://brainvoyage.blog/puzzle-box-mechanisms - overview of puzzle-box mechanism families.
- https://en.wikipedia.org/wiki/Lock_puzzle - puzzle locks.
- https://www.firgelliauto.com/es/blogs/mechanisms/curious-padlock - trick padlock mechanisms.
- https://www.metmuseum.org/press-releases/extravagant-inventions-2012-exhibitions - Roentgen exhibition.
- https://www.metmuseum.org/es/essays/abraham-and-david-roentgen - Roentgen essay.

Conditional objects
- https://core.ac.uk/download/518710702.pdf - reed frequency meter and coupled reeds.
- https://lecdem.physics.umd.edu/g/g2/g2-07.html - selectively driven pendulums demo.
- https://raft.net/wp-content/uploads/2020/08/197-Magic-Pendulum.pdf - "Magic Pendulum" activity.
- https://www.biorxiv.org/content/10.1101/841445v1 - Chevreul pendulum study.
- https://stevespangler.com/experiments/swinging-pendulum-stop-go-trick/ - coupled pendulum demo.
- https://arxiv.org/abs/1702.00343v1 - bristle-bot direction inversion.
- https://arxiv.org/pdf/1410.8153 - model bristle-bot.
- https://www.nature.com/articles/srep01851 - vibration-driven vehicle with slanted pillars.
- https://en.wikipedia.org/wiki/Rattleback - rattleback.
- https://ar5iv.labs.arxiv.org/html/1202.6506 - rattleback dynamics.
- https://arxiv.org/pdf/1112.4913 - rattleback with viscous friction.
- https://www.nature.com/articles/s41586-023-06306-y.pdf - trajectoids.
- https://github.com/yaroslavsobolev/trajectoids/blob/main/README.md - trajectoid code.
- https://arxiv.org/pdf/1009.4444 - universal jamming gripper.
- https://www.arxiv.org/abs/2212.06498 - vibration in jamming grippers.

Inverse design
- https://arxiv.org/pdf/2309.04970 - differentiable design of multistable structures.
- https://core.ac.uk/download/426963588.pdf - planar multistable compliant structures (not opened).
- https://arxiv.org/html/2407.08111v1 - co-design of multistable grippers.

Magic prior art
- https://jimsteinmeyer.com/2022/04/14/what-we-hide-problems-in-algeria-part-two/ - Light and Heavy Chest.
- https://gutenberg.org/files/77917/77917-h/77917-h.htm - Robert-Houdin, Secrets of Stage Conjuring.
- https://www.martinsmagic.com/allmagic/close-up/the-lippinkito-by-douglas-wayne-illusioneering - Lippincott and Okito history.
- https://stevensmagic.com/blogs/gemini/1995-mike-rogers-all-magicians-do-it - Lippincott box described.
- https://www.penguinmagic.com/tricks/tagged/coin-to - Porper Strong Box listing.
- https://vanishingincmagic.com/close-up-magic/the-larry-lock - gimmicked lock, "no gravity".
- https://tenyo-magic.blogspot.com/p/tenyo-development-process.html - Kondo on Tenyo's process.
- https://tenyo-magic.blogspot.com/2010/05/t-201-mystery-china-box.html - Mystery China Box.
- https://magicfakers.blogspot.com/2007/10/vault-vision.html - Vault Vision development.
- https://www.vanishingincmagic.com/close-up-magic/crystal-cleaver/ - Crystal Cleaver.
- https://www.vanishingincmagic.com/blog/talking-tenyo-toy-tricks/ - Tenyo as "toy tricks".
- https://boingboing.net/2017/03/08/i-am-oz-the-great-and-powerful.html - critique of gadget tricks.

Fabrication limits
- https://utw10945.utweb.utexas.edu/sites/default/files/2016/188-Balderrama-Armendariz.pdf - fold cycles by material.
- https://link.springer.com/10.1007/s00170-019-04196-x - living hinge study, six materials.
- https://repository.tudelft.nl/record/uuid:7df15c93-e792-4a35-9b16-a74b0fdb7ea7 - fatigue of printed compliant joints.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC9147248/ - stress relaxation of printed PLA.
- https://www.sv-jme.eu/article/short-term-creep-behavior-of-different-polymers-used-in-additive-manufacturing-under-different-thermal-and-loading-conditions/ - creep of printed polymers.
- https://www.ntu.edu.sg/sc3dp/research-capabilities/research-projects/rationalising-the-onset-of-bistability-in-polylactic-acid-(pla)-bilayer-laminates-using-fused-filament-fabrication-(fff) - PLA bilayer bistability.
- https://repository.tudelft.nl/record/uuid:0e079f8c-873f-4645-8c18-c381c0554ccb - print-induced prestress for bistability.
