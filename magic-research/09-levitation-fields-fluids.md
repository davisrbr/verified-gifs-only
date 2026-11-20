# 09 - Levitation, contactless forces, fields and fluids as magic methods

Agent 9 of 14. Slice: acoustic, magnetic, electrostatic, aerodynamic, fluid, light-driven and
robotic ways to hold or move an object without visible contact, 2015 to 2026 plus foundations.

**Research note.** The project's shared web-search budget ran out after about 15 searches, so most
of this report was checked by opening known pages directly. Anything I recall but did not see on a
page in this session is marked **(unverified)**. Numbers marked **(my estimate)** are my own
back-of-envelope calculations, not published figures, and should be measured before a design
depends on them. Prices are as of late 2026 and mostly unverified because supplier pages could not
be searched.

**Scope note.** The report follows the original brief: it maps every levitation and
contactless-force method in the slice and gives payload, gap, hoop pass, visibility, noise, cost
and safety for each. A mid-project course correction (later withdrawn for this report) asked for
attention to contactless force as a **hidden input**: a few millinewtons applied through a table,
glass or cloth to an ordinary object at the moment when it is balanced, spinning, swinging or
falling. That material was kept as an addition (section 3 and several of the effect concepts)
because it turned out to be where the slice is most useful. Section 3 and the "level" labels in
section 4 come from that correction and can be ignored by a reader who only wants the original
scope.

---

## 1. Summary

- **True levitation is a poor fit for live magic; hidden millinewtons are a very good fit.** Every
  real levitation method either lifts almost nothing (acoustic: milligrams to 0.6 g), has a gap of
  1 to 3 cm above an obvious base (magnetic), or needs a chamber, cryogen or drone. Audiences also
  guess "magnets" or "it's a science thing" at once. The same physics used covertly is far
  stronger, because the force only has to be big enough to tip a decision.
- **The key design rule is: apply a small force where the system is unstable or resonant.** A
  pendulum with a quality factor of 100 to 300 turns a 0.1 mN periodic push into a swing of tens of
  degrees (my estimate). A coin on edge, a ball on a divider, a spinner about to stop and a die on
  an edge all need microjoules to decide. This is what makes cheap coils, tiny air jets and
  ultrasound useful.
- **Eddy currents give a force that passes the magnet test.** Braking force on a moving conductor
  is proportional to speed and is exactly zero at rest
  ([Wikipedia](https://en.wikipedia.org/wiki/Eddy_current_brake)). A solid aluminium or copper
  spinner, top or rolling coin can be slowed from under the table, yet a spectator's magnet does
  nothing to it. I found no magic product built on this (unverified absence).
- **A switchable field under a table now costs a few dollars and no moving parts**: coils, an
  H-bridge, a Hall sensor and a microcontroller. Robert-Houdin's Light and Heavy Chest (Palais
  Royal programme, from 1845) was the same idea with a single on/off electromagnet
  ([Wikipedia](https://en.wikipedia.org/wiki/Jean-Eug%C3%A8ne_Robert-Houdin)). What is new is
  closed-loop control, many coils, sensing through the surface, and battery operation.
- **Computer-controlled thread is the most practical "levitation" upgrade.** Cable-driven parallel
  robots are mature and open (Skycam, Hangprinter; ART+COM hung 714 spheres on thin steel wires in
  2008). A torque-controlled brushless winch (SimpleFOC) can hold a thread at a gram of tension.
  Unloading the prop (helium, magnet lift) lets the thread be thinner still.
- **Acoustic levitation: honest numbers.** TinyLev lifts beads up to about 4 mm at densities up to
  2.2 g/cm3 on 10 W and about 20 V, and a kit was reported at US$70. Phased arrays (SonicSurface,
  256 emitters) are open hardware. Sound fields can now be computed around obstacles at more than
  10,000 updates per second. The disguise problem (a tile of 256 silver cans) is partly solved by
  acoustically transparent fabric.
- **Silent hidden air is now possible.** Piezo microblowers (0.7 L/min, 1.4 kPa, driven at 24 to
  27 kHz, sold as "silent") and corona ion-wind jets have no audible motor. They give roughly 0.3
  to 10 mN (my estimate), enough for flames, smoke, tissue, balanced cards and pinwheels.
- **Electrostatics passes through glass and needs microwatts**, so a charged performer or a hidden
  electrode can move straws, foil, bubbles and thin water streams inside a sealed glass. A
  body-charging gimmick already exists in magic (Yigal Mesika's Electric Touch, unverified page).
- **Superconductors, photophoresis, ion-drive craft, induction levitation of aluminium and optical
  tweezers are dead ends for a hobbyist performing live** (logistics, vacuum, scale or power).
- **Vibrated-fluid phenomena** (walking droplets, a boat floating under a levitated liquid layer,
  Leidenfrost ratchets, the Kaye effect) are cheap and astonishing but are installations or video
  pieces, not hidden methods.

---

## 2. Catalog

### 2.0 Levitation methods compared

"Hoop" means the magician's standard proof: can a ring or hand pass around or over the floating
object?

| Method | What floats | Gap | Hoop / hand pass | Apparatus visible? | Noise | Cost | Main hazard |
|---|---|---|---|---|---|---|---|
| Standing-wave ultrasound (TinyLev) | Beads, droplets, insects; up to ~4 mm, a few mg | Object sits between two arrays ~10 cm apart | Thin wire hoop sideways only; a hand kills the trap | Two bowls of transducers, obvious | Inaudible carrier; faint hiss | ~$70 kit (reported) | Very high SPL close up |
| Single-sided phased array | Polystyrene beads 1 to 3 mm; special cases to 20 mm; far-field 30 mm, 0.6 g | 5 to 25 cm above the array | Hoop yes; hands now tolerated by newer solvers | Flat tile of 256 cans; can sit behind speaker cloth | As above | ~$150 to $400 self-build (unverified) | As above |
| Push-type feedback maglev module | 150 to 500 g with a large magnet inside (unverified) | 1 to 2.5 cm (unverified) | Non-ferrous hoop sideways through the gap | Base must be directly below; hides in a book or tabletop | Silent | $20 to $50 (unverified) | Strong magnets, pinch |
| Pull-type (hanging) feedback maglev | 10 to 200 g with magnet or steel | 1 to 5 cm below the coil | Yes, sideways | Coil above; hides in a lamp, hand or shelf | Silent | $15 to $60 kit (unverified) | Coil heating |
| Spin-stabilised (Levitron) | The spinning top only | A few cm | Yes, carefully | Base magnet below | Silent | ~$40 (unverified) | None; fussy to set up |
| Diamagnetic (pyrolytic graphite) | Thin graphite flake, or a tiny magnet between graphite plates | ~1 mm | No useful gap | Magnet array | Silent | $10 to $30 | None |
| Superconductor flux pinning | YBCO puck or magnet, tens of grams and more | 0.5 to 3 cm, any orientation | Yes | Fog, frost, dewar | Silent | $100 to $400 plus liquid nitrogen (unverified) | Cryogen burns |
| Electrostatic (charged wand) | Tinsel, foil, mylar shapes, < 1 g | 10 to 50 cm | Yes with an insulating hoop | Wand below | Silent | $10 to $30 toy | Small shocks |
| Air jet (Bernoulli/Coanda) | Ping-pong ball (2.7 g), balloons, beach balls | 5 to 50 cm | Yes, but airflow is felt and heard | Nozzle below | Fan or blower noise | $10 to $50 | None |
| Neutral buoyancy (helium) | Anything whose volume gives ~1 g of lift per litre | Unlimited | **Full pass, any direction** | None nearby | Silent | $5 to $50 | None |
| Micro-drone | 15 g payload on a 29 g airframe | Unlimited | Yes | It is a drone | Loud whine | $50 to $250 | Props near faces |
| Thread / cable robot | 1 to 50 g on fine thread, kilograms on wire | Unlimited | No (partial proofs only) | Thread visibility depends on light and background | Winches can be near silent | $50 to $200 | None |
| Photophoresis | 6 mm, sub-milligram film | mm, inside a vacuum chamber | No | Vacuum chamber | Pump | Lab | Laser/vacuum |

Only helium gives a clean hoop pass with no apparatus near the object, and it is the oldest of all.
That is the honest state of real levitation.

### 2.1 Acoustic levitation and manipulation

**What it is.** Arrays of 40 kHz ultrasonic emitters (wavelength about 8.6 mm in air) create
pressure nodes that trap small light objects. Three regimes matter
([Wikipedia](https://en.wikipedia.org/wiki/Acoustic_levitation)): standing-wave levitation
(strongest; objects about a tenth of a wavelength or less; a few milligrams); single-beam "tractor
beam" traps from one side (about 30 times weaker); and far-field boundary-hologram methods that
have lifted a 30 mm, 0.6 g expanded-polystyrene sphere and a 50 mm, 0.5 g octahedron. Near-field
levitation carries kilograms but only at a gap of hundreds of micrometres (an air-bearing in
effect).

**Key references.**
- Marzo et al. 2015, "Holographic acoustic elements for manipulation of levitated objects",
  *Nature Communications* 6:8661: first single-sided manipulation
  ([paper](https://www.nature.com/articles/ncomms9661),
  [Bristol news](https://bristol.ac.uk/news/2015/october/sonic-tractor-beam.html)).
- Marzo, Barnes, Drinkwater 2017, "TinyLev", *Rev. Sci. Instrum.* 88, 085105: 72 transducers in
  two bowls, about 20 V, 10 W, traps objects up to 4 mm and 2.2 g/cm3; US$70 Makerfabs kit reported
  ([IEEE Spectrum](https://spectrum.ieee.org/how-to-make-things-float-with-ultrasound),
  [Hackaday](https://hackaday.com/2018/11/28/72-tranducers-for-acoustic-levitation),
  [Instructables build](https://www.instructables.com/Acoustic-Levitator/)).
- Marzo, Corkett, Drinkwater 2018, "Ultraino", *IEEE TUFFC* 65(1): open 64-channel driver on an
  Arduino Mega, chainable
  ([Bristol record](https://research-information.bris.ac.uk/en/publications/ultraino-an-open-phased-array-system-for-narrowband-airborne-ultr/)).
- Morales et al. 2021, SonicSurface: single-board 16 x 16 array, FPGA-driven, files on GitHub
  ([paper](https://doi.org/10.3390/app11072981),
  [GitHub](https://github.com/upnalab/SonicSurface),
  [Instructables](https://www.instructables.com/SonicSurface-Phased-array-for-Levitation-Mid-air-T),
  [Hackaday](https://hackaday.com/2021/08/18/phased-array-levitation-is-science-in-action)).
- Marzo, Caleap, Drinkwater 2018, "Acoustic virtual vortices", *PRL* 120, 044301: rapidly switched
  vortices trap a sphere of about two wavelengths (16 to 20 mm; sources differ) with 192 emitters
  ([preprint](https://core.ac.uk/download/146503483.pdf),
  [Bristol news](https://bristol.ac.uk/news/2018/january/tractor-beam.html)).
- Marzo & Drinkwater 2019, "Holographic acoustic tweezers", *PNAS* 116:84: two 256-emitter arrays
  move up to 25 beads independently and "sew" a thread through cloth using two beads
  ([Bristol record](https://research-information.bris.ac.uk/en/publications/holographic-acoustic-tweezers/),
  [Physics World](https://physicsworld.com/a/holographic-acoustic-tweezers-could-be-used-to-create-3d-displays/)).
- Andrade, Bernassau, Adamowski 2016, *APL* 109, 044101: 50 mm expanded-polystyrene sphere on
  three 25 kHz transducers
  ([record](https://researchportal.hw.ac.uk/en/publications/acoustic-levitation-of-a-large-solid-sphere/),
  [Phys.org](https://m.phys.org/news/2016-08-acoustic-levitation-large-sphere.html)).
- Inoue et al. 2017/2019, boundary hologram: a 3.5-wavelength sphere held 24 wavelengths (about
  20 cm) above a 40 kHz array ([arXiv](https://arxiv.org/abs/1708.05988v1)).
- Hirayama et al. 2019, *Nature* 575:320: one bead moved at up to 8.75 m/s to draw persistence-of-
  vision images ([Sussex record](https://sro.sussex.ac.uk/id/eprint/86930/),
  [Scientific American](https://www.scientificamerican.com/article/hearing-is-seeing-sound-waves-create-a-3-d-display/)).
  Display use belongs to agent 5.
- Hirayama et al. 2022, *Science Advances* 8, eabn7614: fields computed around arbitrary
  sound-scattering objects at more than 10,000 updates per second, so levitation works next to
  walls, props and other static surfaces
  ([project page](https://ryujihirayama.github.io/web/projects/scattering.html),
  [PubMed](https://www.pubmed.gov/35714194/),
  [press release](https://www.eurekalert.org/news-releases/956455)).
- Morales et al. 2019, LeviProps (UIST): cut pieces of **acoustically transparent fabric** carried
  by a few trapped beads, moved in six degrees of freedom, with an optimiser for bead positions
  ([paper PDF](https://rafamg10.github.io/assets/pdf/Leviprops-UIST19.pdf)).
- Andrade et al. 2020, *APL* 116, 054104: contactless pick-and-place by inverted near-field
  levitation (reference seen on the Wikipedia page above).
- Also seen: OptiTrap trajectory optimisation ([arXiv](https://arxiv.org/pdf/2203.01987)), a VR
  levitation simulator ([arXiv](https://arxiv.org/pdf/2005.06291)), reflective metamaterials for
  levitation ([PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC7060201)), and single-sided
  levitation in high-pressure regions ([arXiv](https://arxiv.org/html/2412.15539v1)).
- Recalled, not checked: GS-PAT multi-point solver (Plasencia et al., SIGGRAPH 2020), OpenMPD
  engine (2023), TastyFloats levitated food (Vi et al., 2017), Pixie Dust (Ochiai et al., 2014),
  soap-bubble levitation (Zang et al., 2017), Hasegawa et al. 2017 on an electronically steered
  ultrasound-driven narrow air stream (all **unverified**).

**Accessibility.** Hobbyist-buildable. TinyLev is a weekend build. A 256-emitter array is a
PCB-assembly job with an FPGA module; parts are 256 emitters, 128 MOSFET drivers and 32 shift
registers per the build notes.

**Safety and noise.** The 40 kHz carrier is inaudible, but switching and amplitude modulation make
audible hiss and clicks. A Physics Today review lists a 40 kHz mid-air haptic source at 155 dB SPL
at 20 cm and warns that exposure guidelines rest on limited, old studies
([Physics Today](https://physicstoday.aip.org/features/ultrasound-in-air); see also
[Health Canada Safety Code 24](https://www.canada.ca/en/health-canada/services/environmental-workplace-health/reports-publications/radiation/guidelines-safe-use-ultrasound-part-industrial-commercial-applications-safety-code-24.html)).
Do not aim a focus at a spectator's head or ears, and keep children and pets away.

**Magic relevance.** As a shown levitation it reads as a science exhibit and lifts only beads.
As a hidden input it is more useful:
- A focused array delivers a force of roughly 10 to 20 mN on a 1 to 2 cm spot at 20 to 30 cm (my
  recollection of Hoshi et al. 2010, **unverified**). A ping-pong ball weighs 26 mN. That is
  enough to bend a flame, steer smoke or mist, flutter tissue, tip a balanced card, or pump a
  light pendulum.
- The array can sit **behind speaker-grille cloth** inside something that looks like a Bluetooth
  speaker, which has an innocent reason to be on the table. LeviProps relies on fabric that passes
  40 kHz sound.
- The scattering-aware solver means the field can be shaped around a glass, a candlestick or a
  hand that is known in advance.
- Ultrasound does not pass through glass or solid covers. It reflects, which can be used: a focus
  can be bounced off a table.

**Prior use in magic.** None found (unverified absence).

**More on what a hobbyist can do with it.**
- *What levitates well.* Expanded-polystyrene beads (1 to 3 mm), water and alcohol droplets,
  small insects, flower petals, paper confetti, tiny LEDs and surface-mount parts, flakes of
  food. Density matters less than size: the object must be well under half a wavelength (4 mm)
  for standing-wave traps. Liquids flatten and can atomise if the field is too strong.
- *Larger light things.* Three routes exist: vortex traps for foam spheres up to about two
  wavelengths; boundary holograms for foam shapes of 30 to 50 mm at 20 cm; and the LeviProps trick
  of hanging thin fabric or film from a few trapped beads. The last is the most stage-relevant: a
  10 cm piece of gauze, a paper butterfly or a small projection screen can be flown in six degrees
  of freedom over a table-sized array. Soap bubbles and thin films have also been levitated
  (Zang et al., unverified).
- *Working distance.* TinyLev: the object sits in the middle of an 8 to 12 cm gap. Flat arrays:
  single-sided traps work from about 3 to 25 cm; opposed pairs of flat arrays about 20 to 25 cm
  apart give the strongest and most flexible volume (the arrangement used in the PNAS and Nature
  work).
- *Power and cost.* TinyLev 10 W. A 256-emitter board runs on roughly 12 to 20 V and tens of
  watts (unverified). Transducers are the main cost at about $0.3 to $1 each in quantity
  (unverified), so a 256-element board is roughly $150 to $400 all in (my estimate).
- *Hands in the field.* Before 2020 a hand near the trap usually dropped the particle. Fast
  multi-point solvers and the 2022 scattering-aware solver make it practical to levitate beside
  static props and, with tracking, near slow-moving hands. A hobbyist can use the released code
  rather than write it (OpenMPD and the Ultraino extensions; repository links unverified).
- *Disguise.* Emitters are 10 or 16 mm metal cans in a grid. Options: behind acoustically
  transparent cloth or perforated metal (as loudspeakers are), in the ceiling of a lantern or
  cabinet, or presented openly as "a speaker". Passive 3D-printed metamaterial plates in front of
  a few emitters can replace per-element electronics for a fixed field (Polychronopoulos &
  Memoli's reflective metamaterials, source 28), which makes a cheap single-purpose levitator
  that does not look like an array.
- *Related sound phenomena.* The Rubens tube (flames mapping a standing wave), Chladni plates and
  cymatics in liquid are level-1 displays; they read as physics demonstrations. Sound at 30 to
  60 Hz can blow out a flame (student-built extinguishers, 2015, unverified). High-power
  ultrasound drives a steady "acoustic streaming" wind along a beam, which is the mechanism to
  use for steering smoke or mist with an array. Surface acoustic waves move droplets only on
  lithium-niobate chips at microlitre scale: lab-only. Inverted near-field levitation picks up
  flat millimetre parts without touching them (Andrade et al. 2020): useful to robots, not to
  performers.

### 2.2 Magnetic: static, feedback, eddy-current and coil arrays

**Stability rules.** Earnshaw's theorem forbids stable levitation with static magnets alone. The
ways round it are servo feedback, diamagnetic materials, superconductors, spin stabilisation,
induced (eddy) currents and oscillating fields
([Wikipedia](https://en.wikipedia.org/wiki/Magnetic_levitation)). A seventh, important for magic,
is **mechanical constraint in one direction**: a thread, a wall or a tabletop removes the unstable
axis.

**Feedback modules.** Push-type modules (ring of permanent magnets, four correction coils, Hall
sensors) float a 150 to 500 g magnet-bearing load about 1 to 2.5 cm above a base roughly 10 cm
square, on 12 V at 1 to 2 A, for $20 to $50 (**unverified** figures from memory of marketplace
listings). Crealev sells modules rated from a few hundred grams to 10 kg
([Crealev](https://www.crealev.com/technology)). Pull-type kits hang a magnet 1 to 3 cm below a
coil. In a hybrid design a permanent magnet carries the weight and the coil only corrects, so
average power is near zero. The floating object always contains a large magnet, so it cannot be
examined freely.

*Magic assessment of feedback modules.* Push-type: the gap is small and the base must be directly
under the object, so the natural disguises are a thick book, a box lid, a cake stand or a
tabletop. A sheet of paper, a card or a non-ferrous hoop passes through the gap, which is a real
proof. A cloth cover can be whisked off a floating object. The weak points are the heavy magnet in
the floater, the need to place the floater by hand at exactly the right spot (it snaps sideways if
missed), and public familiarity with floating lamps and globes. Pull-type: better for magic,
because the lifting unit is above, where a lampshade, a shelf, a hat brim or a hand can hide it,
and the object hangs in clear air above the table. A taller gap needs a bigger coil or a
permanent-magnet bias. Either type is a one-evening build from a kit. Both are silent and run
for hours on a small battery if a bias magnet is used.

**Spin-stabilised.** The Levitron top floats over a ring base while its spin rate stays inside a
window; Harrigan's patent is US 4,382,245 (1983)
([Wikipedia](https://en.wikipedia.org/wiki/Spin-stabilized_magnetic_levitation)). The top must be
weighted to within a fraction of a gram for the day's temperature, spun by hand on a lifter plate
and raised into the trap, and it falls after a few minutes as it slows unless a drive coil keeps
it turning. Only the top itself floats. Too fussy for performance, and widely sold as a toy.

**Diamagnetic.** Graphite levitates where the product of field and field gradient reaches about
375 T2/m; water needs 1400 T2/m, which is why the flying frog needed a 16 T, 4 MW magnet
(Wikipedia, as above). Pyrolytic graphite floats about a millimetre over a checkerboard of
neodymium magnets. Kobayashi & Abe 2012 (*JACS* 134:20593) showed a floating graphite disc can be
pushed or spun by a laser or strong sunlight, because heating weakens its diamagnetism locally
([Wikipedia](https://en.wikipedia.org/wiki/Pyrolytic_carbon),
[Chemistry World](https://www.chemistryworld.com/news/laser-guided-maglev-graphite-air-hockey/5776.article)).

**Superconductors.** Flux pinning locks a cooled type-II superconductor at a fixed distance and
angle from a magnet, even upside down
([Wikipedia](https://en.wikipedia.org/wiki/Flux_pinning)). The practical material is YBCO, which
superconducts below about 92 K, so liquid nitrogen at 77 K is enough (from memory). A wrapped
25 mm puck stays cold for one to a few minutes, follows a magnet track, hangs underneath it, and
keeps whatever tilt it is given, which no other method does. Kits with a puck and a track cost
roughly $100 to $400 and nitrogen needs a dewar and a supplier (unverified). It needs fresh
cryogen for every show and gives away its method in fog and frost. A science-show piece, and a
very good one, but not a secret method. Hazards: cold burns, and oxygen displacement in a closed
room.

**Ferrofluid and magnetically moved liquids.** A drop of ferrofluid in a sealed cell follows a
magnet behind the glass, climbs, splits and forms spikes. Hobby displays use an electromagnet grid
behind a flat tank (the open "Fetch" display, unverified). It stains everything and ages. As a
shown effect it is a known desk toy; as a method, a black liquid that crawls up the inside of a
sealed bottle toward a hidden magnet is a strong "animation" picture. Display use: agent 5.
Liquid-metal (gallium alloy) manipulation by fields is lab work and messy.

**Electrodynamic wheels and moving-magnet lift.** A spinning ring of magnets over a copper or
aluminium sheet produces lift and thrust (the hoverboard demonstrations of the mid-2010s; hobby
builds exist, unverified). It needs a metal floor, hundreds of watts and loud motors. Not useful.

**Eddy currents.** A conductor moving through a field feels a drag proportional to its speed; a
magnet dropped down a copper pipe falls slowly; at zero speed the force is zero
([Wikipedia](https://en.wikipedia.org/wiki/Eddy_current_brake)). Lift by induction needs AC or
motion, is inefficient at low speed, and heats the conductor
([Wikipedia](https://en.wikipedia.org/wiki/Electrodynamic_suspension)). Estimates for hidden use
(all my estimates):
- Braking: a 2 cm2 patch of 2 mm aluminium moving at 0.5 m/s through 0.05 to 0.2 T feels roughly
  5 to 80 mN. That stops a low-friction spinner within a turn.
- Switchable damping with no power: a magnet swinging over a coil is braked when the coil is
  shorted by a transistor and free when it is open.
- Impulse: a photoflash-class capacitor (about 5 to 20 J at 300 V) discharged into a flat coil
  under a thin tabletop should make an unprepared copper-cored coin hop a few centimetres. This is
  the Thomson jumping-ring effect in pulsed form. Untested; treat as speculative.

**Moving things across a surface from below.** Three architectures:
1. A magnet on a hidden XY gantry (the automatic chessboard). Moves a 5 to 30 g object carrying a
   small magnet anywhere on the surface through 3 to 10 mm of wood. Stepper drivers with silent
   chopping make it close to inaudible. About $60 to $150 in printer parts (my estimate).
2. A printed-circuit coil array with no moving parts. HCI examples from memory: Actuated Workbench
   (2002), Madgets (2010), Reactile (Suzuki et al., CHI 2018), and SRI's diamagnetically levitated
   micro-robots driven by PCB traces (all **unverified**; I could not confirm a project called
   "Fluxels"). MIT's ZeroN (Lee, Post, Ishii, UIST 2011) carried a pull-type levitator on a gantry
   to move a floating ball through a volume (**unverified**, page not found).
3. A rotating magnet under the surface (the magnetic stirrer): spins any ferromagnetic object
   above it, and drags conductors round by induction.

Disney's HoloTile floor (Lanny Smoot, 2024) is a mechanical omnidirectional surface, not a field
method (**unverified**; pointer only). Ferrofluid displays are level 1 and belong with agent 5.

**Which borrowed objects respond?** Steel-cored coins (UK 1p to 10p, euro 1c to 5c, most Canadian
coins) and steel hardware are attracted. US coins, gold and silver rings and brass keys are not
attracted but are good conductors, so they respond to eddy braking and to pulsed induction. This
split decides which method to use in which country (coin compositions from memory, **unverified**).

**Prior use in magic.** Very old: Robert-Houdin's chest; magnetic dice and "juice" tables; PK
rings; spirit bells. The static magnet under the table is known to magicians and guessed by
audiences. Closed-loop, eddy-current and addressed-coil methods appear to be unused (unverified
absence).

### 2.3 Electrostatic and electrohydrodynamic

**What it is.** A charged electrode attracts any light object by polarising it, through air,
glass or plastic. Forces are millinewtons at centimetres for kilovolts, and current is microamps.
The Fun Fly Stick toy is a battery Van de Graaff in a wand that floats mylar tinsel
(**unverified**). Small negative-ion modules (12 V in, several kV out, a few dollars; unverified)
can replace the belt generator and fit in a pocket.

**Ionic wind.** A corona wire and a collector at 20 to 50 kV, with about 1 mm of gap per kV, push
air with no moving parts; early lifters managed about a gram of lift per watt, fed by thin wires
from a ground supply ([Wikipedia](https://en.wikipedia.org/wiki/Ionocraft)). MIT's 2018 aircraft
(Xu et al., *Nature*) had a 5 m wingspan, weighed about 2.45 kg, used 40 kV and flew 60 m indoors
([MIT News](https://news.mit.edu/2018/first-ionic-wind-plane-no-moving-parts-1121)). As a lifter
it is a dead end on stage; as a **silent centimetre-scale blower** it is interesting (about 10 mN
per watt, my reading of the gram-per-watt figure).

**Liquid effects.** The floating water bridge: deionised water in two beakers at about 15 kV forms
a free bridge 1 to 3 mm thick that stretches to 25 mm
([Wikipedia](https://en.wikipedia.org/wiki/Water_thread_experiment)). A charged rod bends a thin
water stream by centimetres. Continuous-inkjet printers charge and deflect individual drops; the
same can be done at millimetre drop size with kilovolt plates (my extrapolation).

**Flying tinsel in detail.** A loop of thin aluminised mylar touches the charged wand, takes the
same charge, springs open into a ball and is repelled; the performer keeps the wand under it. It
is stable only because a person steers it, and it flies to the nearest grounded thing (a face, a
hand) and discharges. Payload is the tinsel itself, well under a gram. A hoop passes over it if
the hoop is an insulator. Miniaturising the source is easy; hiding it is harder, because the
electrode must be exposed, below the object and within tens of centimetres. The plausible hidden
forms are a charged tray, a "metal" wand, or the performer's own charged body with the hand held
palm-up under the shape. Humidity above about 60% ruins it.

**Electroadhesion** (kV on interdigitated electrodes gripping any surface) is agent 7's;
relevant here only as a silent hold-and-release.

**Electrospray and dielectric-barrier discharge.** A liquid at a needle tip under kV forms a cone
and a fine mist jet; barrier discharges make a quiet violet sheet of plasma and a wall-hugging
air jet with no moving parts. Both are small-scale and mostly lab curiosities, but the barrier
discharge "plasma actuator" (copper tape either side of Kapton, a few kV at kHz, a hobby build) is
another silent blower for smoke and flame control.

**Plasma.** Small solid-state Tesla coils ($10 to $40 kits, unverified) light neon and fluorescent
tubes and some LED bulbs held near them with no wires, draw small arcs, and can play music through
the arc (the "singing arc"). Plasma toroids in a globe are a recent hobby favourite. All are
spectacular but read as "electricity". A lamp lighting in a spectator's bare hand is the one
classic magic use, and near-field coils now make it a pocket-sized battery device. RF burns from
arcs, radio interference and risk to implants are the hazards.

**Safety.** Current-limited supplies sting but are not dangerous; stored energy is the risk, so
keep capacitance tiny. A person charged to 10 kV stores under 10 mJ (my estimate from roughly
100 pF body capacitance), which is a carpet-shock. Corona makes ozone. Keep high voltage away from
spectators with implants and from phones.

**Prior use in magic.** Body-charging shoe devices are sold to magicians for sparks and lighting
bulbs (Mesika's Electric Touch; the maker's site was reachable but the product page was not,
**unverified**: [yigalmesika.com](https://www.yigalmesika.com/)). The static-charged straw is an
old bar stunt.

### 2.4 Air: jets, rings and bearings

- **Piezo microblower.** Murata MZB1001T02: at least 0.7 L/min and 1.42 kPa at 15 Vpp, resonant
  drive at 24 to 27 kHz, described as silent
  ([Murata](https://www.murata.com/en-us/products/mechatronics/fluid/overview/lineup/microblower_mzb1001t02)).
  It is about 20 x 20 x 2 mm (unverified). Through a 0.8 mm nozzle that is a 20 m/s needle of air
  with about 0.3 mN of thrust (my estimate). It fits in a pen, a ring box or a book spine.
- **Small fans.** A 40 mm fan gives on the order of 10 mN (my estimate) but is audible.
- **Vortex rings.** A ring of air carries an impulse across a room: the 1965 Wham-O Air Blaster
  blew out a candle at 7.6 m ([Wikipedia](https://en.wikipedia.org/wiki/Air_vortex_cannon)).
  Disney's AIREAL (Sodhi et al., SIGGRAPH 2013) drove rings from speakers through a steerable
  3D-printed nozzle with 8.5 cm resolution at 1 m
  ([Disney Research](https://la.disneyresearch.com/publication/aireal-interactive-tactile-experiences-in-free-air/)).
  A ring is invisible, nearly silent if driven slowly, and arrives a noticeable fraction of a
  second after it is launched. Haptic use belongs to agent 11.
- **Bernoulli/Coanda ball.** A ball sits stably in a jet, even one tilted 30° or more, because the
  flow wraps round it and pulls it back to the axis. A hair dryer holds a ping-pong ball 20 to
  40 cm up; a leaf blower holds a beach ball metres up. A hoop passes over the ball freely. The
  problem is that the audience hears and feels the air. Partial fixes: a large slow laminar flow
  from a wide honeycomb outlet in the tabletop rather than a fast narrow jet (much quieter for the
  same lift on a light, large object such as a balloon or a foam ball); a remote blower feeding
  the outlet through a hose and silencer; music. Realistic claim: a 15 cm foam or film ball of 1
  to 3 g hovering 10 to 30 cm above a table on a few tenths of a metre per second of upward flow
  from a 20 cm outlet, with a low hum (my estimate; needs testing). Smoke shows the flow, so no
  haze.
- **Smoke and bubble rings on command.** The same vortex launcher loaded with fog makes visible
  rings; a membrane dipped in bubble solution over the aperture makes ring-shaped or ordinary
  large bubbles (toy "bubble ring" guns exist, unverified). Level 1, pretty, and a fog ring that
  travels 3 m to knock over a card is a clear picture.
- **Thermal effects.** Heat-driven paper spinners and "psi wheels" turn in the convection from a
  hand; the classic test is to put a glass over them. The Crookes radiometer turns in light (a
  thermal gas effect at low pressure, sealed in its bulb). Thermoacoustic engines (a test tube,
  steel wool and a flame make a loud tone; a piston version runs as an engine) are neat builds
  with little deception value.
- **Air bearings.** A perforated surface with a few hundred pascals under it removes friction, so
  that millinewton forces from any other source can slide a light flat object. Hidden in a
  close-up pad this is a force multiplier rather than an effect (speculative; pump noise is the
  problem).

### 2.5 Fluids and vibration

These are the cheapest and most visually striking items in the slice. Almost all are things to
show rather than things to hide, so their natural homes are an installation, a "cabinet of
impossible objects", or video.

- **Walking droplets.** A millimetre droplet bounces indefinitely on a vertically vibrated oil
  bath because a film of air never has time to drain, and near the Faraday threshold it walks
  across the surface guided by its own wave (Couder et al., *Nature* 2005; first noted by Walker
  in 1978) ([Wikipedia](https://en.wikipedia.org/wiki/Hydrodynamic_quantum_analogs)). Typical
  recipe from memory: 20 cSt silicone oil a few millimetres deep, about 80 Hz, a loudspeaker as
  shaker, drops made with a toothpick, walking speeds around 1 cm/s (**unverified**). Cost under
  $50. Drops orbit each other, form lattices, and are steered by submerged shapes, so a hidden
  relief under the oil can make a droplet "choose" a path. Needs a level, vibration-free bench and
  clean oil. Close viewing only (the drop is 1 mm), so pair it with a camera and screen or a
  magnifier.
- **Bouncing and non-coalescing drops generally.** The same air film lets a jet of water skate on
  a moving bath, drops of coffee roll on coffee, and soap bubbles sit on a vibrated film. Simple
  and unfamiliar.
- **Floating under a levitating liquid.** Apffel et al. 2020 (*Nature*): vertical shaking holds
  about half a litre of liquid, up to 20 cm wide, above a layer of air, and a toy boat floats
  upside down on the underside ([arXiv](https://arxiv.org/abs/2003.04777)). The liquid is viscous
  (glycerol or silicone oil) and the shaker is a substantial one at around 100 Hz (from memory).
  Hobby replications with a subwoofer driver are plausible at reduced width. A superb installation
  piece: it looks like a camera trick in person.
- **Faraday waves, Chladni figures, cymatics.** Standing patterns on a vibrated liquid or a
  sand-covered plate. Familiar from online video. A hidden use: sand on a thin tray over a
  concealed driver gathers into a chosen figure (one of a few resonant patterns selected by
  frequency), which is a slow "spirit drawing".
- **Granular effects.** Shaking makes large objects rise through small grains (the Brazil-nut
  effect) and, with air or light grains, sink again; a buried object can be made to surface from a
  bowl of rice or sand by a hidden vibration motor in the bowl's base. Vibrated sand also flows
  like a liquid, so heavy things sink into it and light things pop up. Sand flowing uphill has
  been shown with magnetically spun micro-rollers (Lehigh, 2023, **unverified**; lab-only).
- **Leidenfrost.** Above about 193 °C water drops skate on their own vapour; on sawtooth surfaces
  they propel themselves, even uphill, and a milled aluminium ratchet plate on a hot plate is a
  hobby build (Linke's group; Bath's "Leidenfrost maze"). Related: drops levitating on liquid
  nitrogen (2016) and a dry-ice "sublimation heat engine" (Wells et al., *Nat. Commun.* 2015)
  ([Wikipedia](https://en.wikipedia.org/wiki/Leidenfrost_effect)). Dry-ice pucks on a warm
  ratchet do the same at safe temperatures. Hot-plate burns are the hazard.
- **Kaye effect.** A falling stream of shampoo briefly leaps back out of the pile; it lasts about
  300 ms unless caught on a slope, where it can be sustained and even cascaded
  ([Wikipedia](https://en.wikipedia.org/wiki/Kaye_effect)). Free, but small and fast.
- **Rope coiling and the "liquid rope trick".** Honey or silicone oil poured from a height coils
  like rope; a chain of beads siphons itself up out of a jar (the chain fountain). Familiar from
  video.
- **Laminar jets.** A bundle of drinking straws and sponge in a pipe gives a glass-clear jet that
  carries light like a fibre; a cutter makes it a "jumping jet". A well-known theme-park effect
  and a weekend build for $30 to $60 (unverified). Needs plumbing and a splash zone.
- **Bubbles.** Bubbles can be bounced on gloves and held on wet hands; they freeze into crystal
  shells below about -10 °C; they float on a layer of carbon dioxide in a tank (dry ice in an
  aquarium), where they also swell; a foil boat floats on a tank of sulphur hexafluoride as if on
  nothing (expensive gas, a strong greenhouse gas, and now hard to buy). A helium-air mixture
  makes a bubble neutrally buoyant so it hangs in mid-air. Recipes: agent 8.
- **Euler's disk** and other long-lived spinners
  ([Wikipedia](https://en.wikipedia.org/wiki/Euler%27s_Disk)): relevant below as things a hidden
  coil can keep alive or kill early.
- **Strobe "time fountains".** Drops lit by a strobe near the drip frequency appear to hang or
  rise. This works for the naked eye only in a dark room with the strobe as the sole light. The
  popular "frozen water from a hose on a speaker" clips depend on camera frame rate and do not
  work live. (From memory; unverified.)
- **Neutral buoyancy.** Helium gives about 1 g of lift per litre (my figure from gas densities).
  Remote-control "air swimmer" fish, toy blimps and Festo's flying animals are the known forms
  (unverified). A modern ultralight prop is a film envelope shaped as something that is not a
  balloon: a lantern, a cube, a cloud, a ball. It is the only levitation here with no gap limit,
  no apparatus near the object and a free hoop pass. Its tells are slow drifting, sensitivity to
  draughts, and size (a litre per gram).
- **Useful fact from the coin-flip literature:** 350,757 recorded flips show a coin lands on the
  side it started 50.8% of the time ([arXiv](https://arxiv.org/abs/2310.04153)). The natural bias
  is tiny, so any hidden force that decides the outcome has to be supplied by the method.

### 2.6 Light and heat as force

Photophoresis lifted 6 mm discs of 0.5 µm mylar coated with carbon nanotubes at 10 to 30 Pa under
roughly sunlight-level intensity, with predicted payloads up to 10 mg (Azadi et al., *Science
Advances* 2021) ([arXiv](https://arxiv.org/abs/2005.06493),
[Wikipedia](https://en.wikipedia.org/wiki/Photophoresis)). Related: "nanocardboard" plates (Cortes
et al., *Advanced Materials* 2020) and perforated membranes flown in near-space conditions
(Schafer et al., *Nature* 2025), both listed on the same Wikipedia page. Realistic assessment: it
only works at about a ten-thousandth of an atmosphere, so the object is inside a pumped chamber or
bell jar, is millimetres across and weighs less than a milligram. No live use.

Photophoretic *trapping* of a dust-sized particle in a focused laser beam in ordinary air does
work on a bench (it is the basis of one volumetric display, agent 5), but the particle is tens of
micrometres across. Optical tweezers are microscopic and need a microscope objective.
Laser-induced bubbles and plasma dots need pulsed lasers that are unsafe outside a lab. The
Crookes radiometer is the one light-driven mover anyone can own; it is sealed and familiar. The
one practical new item is the light-steered graphite flake of section 2.2: a few hundred
milliwatts of laser pushes a centimetre flake around a magnet array (power from memory,
unverified), which is an eye hazard and must be enclosed or kept well away from sight lines.

### 2.7 Drones, cable robots and thread

- **Micro-drones.** Crazyflie 2.1+: 29 g, 92 mm, about 7 minutes, 15 g payload, open firmware,
  swarm support ([Bitcraze](https://www.bitcraze.io/products/crazyflie-2-1-plus/)). Noise is the
  giveaway, and it scales with disc loading, so the quiet route is a helium envelope that carries
  the weight with tiny slow propellers. Marco Tempest's "24 Drones" and Verity's stage drones are
  the known performance uses (**unverified**; his Wikipedia page does not mention them:
  [Wikipedia](https://en.wikipedia.org/wiki/Marco_Tempest)). Shown as drones they are
  choreography, not magic.
- **Cable-driven parallel robots.** Cables wound on motors position an end effector; they are
  light, fast and scale from desktop to stadium (Skycam)
  ([Wikipedia](https://en.wikipedia.org/wiki/Cable_robots)). Hangprinter is an open-source
  line-driven robot anchored to ceiling and floor, with camera-based calibration
  ([hangprinter.org](https://hangprinter.org/)). ART+COM's Kinetic Sculpture (BMW Museum, 2008)
  animates 714 metal spheres on thin steel wires
  ([ART+COM](https://artcom.de/en/?project=kinetic-sculpture)). ETH's PuppetMaster (2019) planned
  robot motions for string marionettes (**unverified**).
- **Torque-controlled winches.** SimpleFOC is an open library and board family for field-oriented
  control of brushless and stepper motors, giving smooth torque, velocity and position control
  ([simplefoc.com](https://simplefoc.com/)). A gimbal motor under torque control behaves like a
  programmable spring: it can hold a thread at about a gram of tension, pay out and reel in
  silently, and sense a tug.
- **Thread itself.** Invisible thread is nylon separated into single strands
  ([Wikipedia](https://en.wikipedia.org/wiki/Invisible_thread)). A single 12 µm aramid filament
  should break at about 40 g (my estimate from bulk strength). Materials belong to agent 7.
  Motorised reels are established products (Mesika's Tarantula and Spider Pen lines;
  [maker site](https://www.yigalmesika.com/)).

### 2.8 Mechanical "anti-gravity"

Tensegrity tables, precessing gyroscopes, rattlebacks and the Dzhanibekov flip are well known
from online video, so they read as puzzles. Their value here is as cover: an object that visibly
"could" balance by clever mechanics hides the fact that a field is helping it. Reaction-wheel
balancing belongs to agent 7.

---

## 3. Capability primitives

1. *Now possible:* apply 0.1 to 5 mN to a steel-cored coin, nail, clip or washer through 5 to
   20 mm of wood, glass or a hand, switched in a millisecond, silent, on a 9 V battery. *Because:*
   $2 coils, H-bridge chips, microcontrollers. *Before:* a fixed magnet moved by knee or hand.
   *Primitives:* move, control chance.
2. *Now possible:* build a 30° swing in a hanging object under a sealed glass dome from a 0.1 mN
   push repeated at its natural frequency, and stop it again in two or three swings (my estimate).
   *Because:* back-EMF or Hall sensing plus resonant drive; shorted-coil damping. *Before:*
   thread, breath, or the holder's own hand. *Primitives:* move, delay.
3. *Now possible:* slow or stop a solid aluminium or copper object (spinner, top, rolling coin)
   with 5 to 80 mN from below, while it shows no reaction to a test magnet at rest. *Because:*
   eddy-current drag is proportional to speed. *Before:* a hidden magnet or steel in the prop,
   found by the same test. *Primitives:* control chance, prove ordinariness.
4. *Now possible:* brake or free a moving magnet with zero supply power by shorting or opening a
   coil. *Because:* one MOSFET. *Before:* not done. *Primitives:* control chance.
5. *Now possible:* kick an unprepared copper-cored coin a few centimetres into the air through a
   tabletop (speculative, 5 to 20 J pulse). *Because:* photoflash capacitors, thyristors, flat
   coils. *Before:* thread, wax, a mechanical kicker. *Primitives:* move, prove ordinariness.
6. *Now possible:* release one chosen latch out of several inside a sealed prop that contains no
   battery or electronics, by playing that latch's resonant frequency (20 to 90 Hz) from a coil
   outside (speculative). *Because:* printed flexures with repeatable tuning, small magnets.
   *Before:* one magnetic catch, opened by any magnet. *Primitives:* hold/release, tell, prove
   ordinariness.
7. *Now possible:* carry 90% or more of a prop's weight by a permanent magnet above or by helium
   inside, leaving under 1 g for a thread. *Because:* N52 magnets; foil envelopes; ~1 g of lift
   per litre. *Before:* the thread carried everything, which set its thickness. *Primitives:*
   conceal, move.
8. *Now possible:* hold a thread at 1 g of tension, move it at programmed speeds, and feel a touch
   on it, with no audible motor. *Because:* gimbal motors and open field-oriented control, about
   $30 per axis. *Before:* spring reels and gear-motor reels with fixed pull and a whirr.
   *Primitives:* move, hold/release, know.
9. *Now possible:* position a 1 to 20 g object anywhere in a cubic metre to millimetres on three
   or four threads, repeating a path exactly. *Because:* open cable-robot firmware and camera
   calibration. *Before:* a human assistant off stage. *Primitives:* move.
10. *Now possible:* blow a 20 m/s needle of air with no audible motor from a 2 mm thick device, or
    a broader 1 m/s breeze from a bare needle electrode. *Because:* piezo microblowers; kV
    modules. *Before:* breath, bulbs and tubes, fans. *Primitives:* move, control chance, release.
11. *Now possible:* deliver an invisible push to a spot 1 to 7 m away that arrives about a second
    after it is sent. *Because:* speaker-driven vortex rings in a printed nozzle. *Before:*
    thread or a stooge. *Primitives:* delay, move, release.
12. *Now possible:* focus 10 to 20 mN (unverified) on a 1 to 2 cm spot 20 to 30 cm away and move
    that spot anywhere in a volume thousands of times a second, from behind cloth. *Because:* open
    256-channel 40 kHz arrays and fast solvers. *Before:* not possible. *Primitives:* move,
    control chance.
13. *Now possible:* compute that focus around known obstacles (a glass, a candlestick, a hand).
    *Because:* boundary-element solvers at 10 kHz update rates. *Before:* any object in the field
    wrecked it. *Primitives:* move, conceal.
14. *Now possible:* pull a straw, foil strip, soap bubble or water stream toward a bare hand or
    a picture frame through sealed glass, using microwatts. *Because:* pocket kV modules.
    *Before:* a rubbed comb, which is weak and uncontrolled. *Primitives:* move.
15. *Now possible:* decide which of two or three vessels a falling stream of drops lands in, with
    nothing near the stream (speculative). *Because:* induction charging and kV deflection plates,
    as in inkjet printers. *Before:* not done. *Primitives:* control chance.
16. *Now possible:* move a small magnet-bearing object along any drawn path across a table from
    below, with no sound. *Because:* 3D-printer mechanics and silent stepper drivers. *Before:* a
    hand-held magnet under the table. *Primitives:* move, swap.
17. *Now possible:* hold an object 1 to 5 cm below a palm or shelf with no thread, using a magnet
    for lift and a coil only for correction (hard build). *Because:* fast Hall sensors and
    microcontrollers. *Before:* thread. *Primitives:* move, prove ordinariness.
18. *Now possible:* stand a steel coin, needle or nail upright and let it fall on command, in a
    chosen direction, from under the table. *Because:* servo-raised magnet or coil pair. *Before:*
    known as a static magnet stunt; direction was not controlled. *Primitives:* control chance.
19. *Now possible:* heat a small steel part inside a sealed non-metal box by tens of degrees in
    seconds from outside. *Because:* $10 induction driver modules. *Before:* not done. Use:
    melting a wax or low-melt link. *Primitives:* hold/release, delay, erase the evidence.
    (Fusible links belong to agents 7 and 8.)
20. *Now possible:* remove sliding friction under a light flat object so that any of the forces
    above can move it (speculative). *Because:* laser-drilled surfaces and small pumps. *Before:*
    not done. *Primitives:* move.
21. *Now possible:* float a 4 g prop 20 cm across with no lift device near it and pass a hoop
    over it freely. *Because:* helium and micron-thick films. *Before:* same; the gain is lighter
    skins and quieter trim thrusters. *Primitives:* move, prove ordinariness.
22. *Now possible:* push a floating graphite flake with an invisible infrared beam from across a
    room. *Because:* cheap laser diodes; Kobayashi & Abe's effect. *Before:* not possible.
    *Primitives:* move. (Eye hazard.)

---

## 4. Effect concepts

Levels follow the brief: 1 = the phenomenon is the effect, 2 = hidden input to a classical method,
3 = new method architecture.

### 4.1 The pendulum under glass (level 3)

**Effect.** A spectator's steel-cored coin, or a steel nut from a handed-out box, is tied to a
thread on a small stand. A glass dome goes over it. The spectator asks questions; the pendulum
starts to swing by itself, changes from a line to a circle for "no", and stops dead when told.
**Method.** Two crossed pairs of flat coils and a controller inside a 20 mm base or tabletop. The
controller senses the bob by the voltage it induces in an idle coil, pushes at the natural
frequency, picks the swing plane by which pair it drives, and brakes by driving in antiphase. With
a small magnet in the bob, forces are ten to a hundred times larger and shorted-coil braking
works. The performer cues it with a hidden switch.
**Bill of materials.** Four coils, two H-bridges, microcontroller, LiPo, printed base: $25 to $40.
**Difficulty.** Moderate; the sensing is the work.
**Risks.** Soft steel gives weak forces, so start-up may take 10 to 20 s. Does not work with US
coins or precious-metal rings. A compass app on a phone would notice the field.
**Novelty.** The spirit pendulum is old; a sealed, self-starting, self-stopping, plane-switching
one driven closed-loop appears new (unverified).

### 4.2 The honest spinner (level 2)

**Effect.** A solid aluminium arrow on a pin is examined, tested with a spectator's fridge magnet,
and spun by the spectator. It stops on the predicted name.
**Method.** Iron-cored electromagnets under the board create a braking patch only while energised.
Drag is proportional to speed, so the arrow glides to a natural-looking stop instead of snapping.
An overhead phone camera or an optical sensor in the pivot reports the angle; the controller
applies braking over the last turn to land on target.
**Bill of materials.** Two to four 12 V electromagnets, driver, sensor, controller: $30 to $60.
**Difficulty.** Moderate.
**Risks.** Field at the disc through a thick board may be too weak: keep the board to 3 mm and the
arrow broad and thick. Coils warm up. The force estimate needs a bench test first.
**Novelty.** High as far as I can tell. The same idea makes one of two rolling copper coins lose a
race down twin ramps.

### 4.3 Edge decision (level 2 to 3)

**Effect.** A borrowed coin (UK, euro-cent or Canadian) is stood on its edge on the table, where
it stays, oddly steady. The spectator calls heads or tails, and the coin slowly tips over to show
the call.
**Method.** A vertical field from a coil or servo-raised magnet under the table holds a steel disc
upright, because a thin steel plate aligns its plane with the field. Two side coils add a slight
tilt to the field; reducing the vertical field lets the coin fall the chosen way. The performer
notes which way heads faces when placing it.
**Bill of materials.** Three coils or one servo and magnet plus two coils, controller: $20 to $40.
**Difficulty.** Easy to moderate.
**Risks.** Only for steel-cored coinage. The coin feels "sticky" if a spectator touches it while
the field is on.
**Novelty.** Standing a coin with a magnet is known; choosing the fall direction on command
appears new (unverified).

### 4.4 Addressed latches, no electronics inside (level 3)

**Effect.** Four small sealed wooden boxes, each holding a bell or a flag, sit on a table for the
whole evening and can be picked up and shaken. A spectator names one; that bell alone rings, or
that lid alone pops.
**Method.** Each box holds only a printed spring arm with a small magnet, tuned to its own
frequency (say 23, 31, 41 and 53 Hz). A coil under the table plays one frequency for a second; the
matching arm builds up a large swing and strikes the bell or knocks off a detent, while the others
barely move. Nothing in the boxes is powered, so they can be left out for hours and opened
afterwards to show a "clapper on a spring".
**Bill of materials.** Printed flexures, 3 mm magnets, one coil, audio amplifier module,
controller: $30.
**Difficulty.** Moderate; tuning and keeping the frequencies apart is the craft.
**Risks.** Footsteps and table knocks excite low-frequency arms. Selectivity depends on low
damping. Speculative; needs prototyping.
**Novelty.** High. It is the reed-frequency selector of old pagers applied to a spirit cabinet.

### 4.5 The unloaded thread (level 2)

**Effect.** A large paper lantern, a silk or a 20 cm ball drifts up from the performer's hands,
hovers, crosses the stage slowly and returns, in fairly bright light.
**Method.** The prop holds a sealed helium cell sized to leave 0.5 to 1 g of net weight. One
single-filament thread runs to a torque-controlled winch that keeps constant tension and plays a
programmed path; the performer's hands only frame it. Because the load is a gram, the thread can
be the finest available and the motion has the slow inertia of a floating thing, which thread
work usually lacks.
**Bill of materials.** Gimbal motor and driver, controller, foil envelope, helium: $50 to $80.
**Difficulty.** Moderate.
**Risks.** Air currents from ventilation move a near-neutral prop; helium leaks over hours.
**Novelty.** Each part is known; the combination and the tension-controlled winch look new.

### 4.6 The cage of threads (level 2)

**Effect.** Inside an open frame (a doorway, a birdcage without bars, a museum-style vitrine with
no glass) a ring or a paper bird flies in three dimensions, lands on a spectator's hand and takes
off again. No performer is needed.
**Method.** A desktop cable robot: four silent winches in the frame's corners, fine thread, a dark
or patterned backdrop, camera calibration borrowed from Hangprinter. The object lands and takes
off by slackening and tightening.
**Bill of materials.** Four gimbal motors and drivers, controller, frame: $120 to $200.
**Difficulty.** High (kinematics, thread management, lighting design).
**Risks.** Threads show at some angles; a hand swept through the volume hits one. Lighting and
viewing distance decide everything.
**Novelty.** Moderate. Kinetic-art winch systems exist; a close-range invisible-thread version
does not seem to.

### 4.7 The floating thing under the hand (level 2)

**Effect.** A small object rises to hover a few centimetres below the performer's open palm. A
ring is passed through the gap between hand and object.
**Method, easy version.** A strong magnet in the palm or sleeve cuff pulls the object up; a single
fine thread from the object runs *downward* to the other hand or the body and stops it jumping to
the magnet. The thread carries only the small excess pull, and it is below the object, where
nobody looks for a support. The gap above is genuinely empty.
**Method, hard version.** Replace the thread with a coil and Hall sensor in the palm unit that
trims the magnet's pull: true hand-held hanging levitation.
**Bill of materials.** Easy: magnets and thread, $10. Hard: coil, sensors, controller, cells, $40.
**Difficulty.** Easy / high.
**Risks.** "It's a magnet" is the obvious theory; the object should look non-magnetic (a paper
ball with a hidden steel shim). Strong magnets near phones, cards and implants.
**Novelty.** The tethered floating paperclip is a classroom toy; I do not know of its use as an
inverted thread levitation (unverified).

### 4.8 A breath from nowhere (level 2)

**Effect.** Five candles stand in a row. The spectator names an order and they go out in that
order. Or: smoke from an incense stick leans over to point at the chosen card; a card castle
collapses when the spectator snaps their fingers.
**Method.** Close range (5 to 30 cm): piezo microblowers or ion-wind needles hidden in the
candle-holder, a book spine or a pen on the table, each aimed at one target. Long range (1 to
5 m): a speaker-driven vortex-ring nozzle behind speaker cloth, aimed by two small servos; the
ring's one-second flight separates the performer's cue from the result.
**Bill of materials.** Five microblowers with drivers (unverified at about $15 to $30 each) or
five needle electrodes on one kV module ($10); or one 4-inch speaker, amplifier and servos ($40).
**Difficulty.** Easy to moderate.
**Risks.** Aim drifts; room draughts; ozone smell from corona; visible nozzle holes.
**Novelty.** Moderate. Air has always been used; silent, addressable, electrically triggered air
has not been cheap before.

### 4.9 Through the glass (level 2)

**Effect.** A straw balanced on a bottle cap under an upturned glass turns to follow the
performer's fingertip. A soap bubble follows the hand around the room. A thin stream of water from
a jug bends toward the hand.
**Method.** A pocket kV module charges the performer through a skin contact while they stand on
insulating soles; a toe switch turns it on and off and a resistor limits current. Glass does not
screen the field.
**Bill of materials.** kV module, cell, switch, resistor: $15.
**Difficulty.** Easy.
**Risks.** Humid rooms kill it. Touching a spectator gives them a spark. Not for anyone with an
implanted device.
**Novelty.** Low to moderate; overlaps existing body-charging products.

### 4.10 The quiet lantern (level 1, for completeness)

**Effect.** In an open brass lantern on a stand, a drop of water and a tiny paper moth hang in the
air; the moth flutters when breathed on.
**Method.** A TinyLev in a decorative housing with the transducer bowls behind mesh.
**Cost.** About $70 to $100. **Difficulty.** Easy. **Risks.** Reads as a science exhibit; payload
of a few milligrams; high sound levels inside the lantern. **Novelty.** Low.

---

## 5. Dead ends and overhyped items

- **Acoustic levitation of real props.** Coins, cards, rings and balls are thousands of times too
  heavy. The record objects are polystyrene foam. The "tractor beam" name oversells it.
- **Superconductor "quantum locking".** Liquid nitrogen at every show, minutes of hold time, and
  a visible cloud of fog. A museum demo.
- **Photophoretic and laser levitation.** Vacuum chamber only; sub-milligram films.
- **Ion-wind lifters and ion planes.** Tens of kilovolts on bare wires, tethered supplies, ozone,
  and a 5 m wing to carry 2.5 kg. Only the tiny-blower use survives.
- **Induction levitation of aluminium.** Works, but needs hundreds of watts and cooks the object.
- **Diamagnetic levitation of ordinary things.** Water needs 1400 T2/m. Only graphite and bismuth
  work with permanent magnets, at a millimetre.
- **Push-type maglev as an open effect.** Sold as lamps, globes and plant pots; audiences know it.
- **Micro-drones as secret levitators.** Too loud at any size that carries a prop.
- **Camera-synchronised water "levitation".** A frame-rate artefact; fails live.
- **Optical tweezers, surface-acoustic-wave droplet handling.** Microscopic scale only.
- **Walking droplets and levitated liquid as close-up.** They need a rigid, level, isolated
  bench and minutes of tuning.

---

## 6. Open leads

- **Measure the hidden-force numbers.** Force on a real steel-cored coin from a 30 mm coil
  through 5, 10 and 20 mm of tabletop; eddy drag on a 3 mm aluminium disc; hop height of a US
  quarter against capacitor energy. Everything in sections 3 and 4 rests on estimates.
- **Focused-ultrasound force at range**, from the mid-air haptics literature (agent 11), and the
  steerable ultrasound-driven air stream paper (Hasegawa et al., 2017).
- **Printed-circuit coil arrays**: Reactile, Madgets, Actuated Workbench and SRI's levitated
  micro-robots, for coil geometry and drive currents; planar-motor products.
- **Small-scale cable-robot papers** and marionette-control work (PuppetMaster) for path planning
  with slack threads.
- **Cheap maglev modules**: a teardown with real gap, load and power numbers, and whether the
  loop can be retuned for a taller gap with a lighter floater.
- **Reed-latch selectivity**: achievable quality factor in printed PETG or spring-steel flexures.
- **Blade-free helium drones** driven by piezo microblowers (NTT Docomo, 2019, unverified).
- **Drop charging and deflection** at millimetre drop size.
- **Light-steered maglev graphite**: flake size, laser power and speed for a table-scale version.
- **Air-bearing close-up pad**: hole pattern, pressure and pump noise.
- **Magic literature check** for prior eddy-current, resonant-latch or inverted-thread methods.

---

## 7. Sources

Pages opened or returned by search in this session:

1. https://spectrum.ieee.org/how-to-make-things-float-with-ultrasound - IEEE Spectrum on building TinyLev; $70 kit.
2. https://hackaday.com/2018/11/28/72-tranducers-for-acoustic-levitation - Hackaday on the TinyLev build.
3. https://www.instructables.com/Acoustic-Levitator/ - TinyLev build guide (title confirmed; body not readable).
4. https://www.nature.com/articles/ncomms9661 - Marzo et al. 2015, holographic acoustic elements.
5. https://bristol.ac.uk/news/2015/october/sonic-tractor-beam.html - Bristol press release, sonic tractor beam.
6. https://research-information.bris.ac.uk/en/publications/ultraino-an-open-phased-array-system-for-narrowband-airborne-ultr/ - Ultraino record.
7. https://doi.org/10.3390/app11072981 - Morales et al. 2021, SonicSurface paper.
8. https://github.com/upnalab/SonicSurface - SonicSurface design files.
9. https://www.instructables.com/SonicSurface-Phased-array-for-Levitation-Mid-air-T - SonicSurface build guide.
10. https://hackaday.com/2021/08/18/phased-array-levitation-is-science-in-action - Hackaday on SonicSurface.
11. https://www.hackster.io/news/write-spooky-messages-with-an-ultrasonic-phased-array-device-59a4b90f0f25 - Hackster on SonicSurface patterns (seen in results; page blocked).
12. https://core.ac.uk/download/146503483.pdf - Marzo, Caleap, Drinkwater 2018, virtual vortices.
13. https://bristol.ac.uk/news/2018/january/tractor-beam.html - Bristol press release, large-object tractor beam.
14. https://research-information.bris.ac.uk/en/publications/holographic-acoustic-tweezers/ - Holographic acoustic tweezers record.
15. https://physicsworld.com/a/holographic-acoustic-tweezers-could-be-used-to-create-3d-displays/ - Physics World coverage.
16. https://www.bristol.ac.uk/news/2018/december/sound-waves.html - Bristol press release, multiple objects.
17. https://researchportal.hw.ac.uk/en/publications/acoustic-levitation-of-a-large-solid-sphere/ - Andrade et al. 2016 record.
18. https://m.phys.org/news/2016-08-acoustic-levitation-large-sphere.html - Phys.org on the 50 mm sphere.
19. https://arxiv.org/abs/1708.05988v1 - Inoue et al., boundary hologram levitation.
20. https://sro.sussex.ac.uk/id/eprint/86930/ - Hirayama et al. 2019, acoustic-trap volumetric display.
21. https://www.scientificamerican.com/article/hearing-is-seeing-sound-waves-create-a-3-d-display/ - coverage of the above.
22. https://ryujihirayama.github.io/web/projects/scattering.html - Hirayama et al. 2022 project page.
23. https://www.pubmed.gov/35714194/ - PubMed record for the same.
24. https://www.eurekalert.org/news-releases/956455 - UCL press release for the same.
25. https://rafamg10.github.io/assets/pdf/Leviprops-UIST19.pdf - LeviProps paper.
26. https://arxiv.org/pdf/2203.01987 - OptiTrap.
27. https://arxiv.org/pdf/2005.06291 - Levitation Simulator.
28. https://pmc.ncbi.nlm.nih.gov/articles/PMC7060201 - Levitation with reflective metamaterials.
29. https://arxiv.org/html/2412.15539v1 - Single-sided levitation in high-pressure regions.
30. https://en.wikipedia.org/wiki/Acoustic_levitation - regimes, record payloads, reference list.
31. https://physicstoday.aip.org/features/ultrasound-in-air - Physics Today on airborne ultrasound exposure.
32. https://www.canada.ca/en/health-canada/services/environmental-workplace-health/reports-publications/radiation/guidelines-safe-use-ultrasound-part-industrial-commercial-applications-safety-code-24.html - Health Canada Safety Code 24.
33. https://en.wikipedia.org/wiki/Magnetic_levitation - Earnshaw and the ways round it; diamagnetic thresholds.
34. https://en.wikipedia.org/wiki/Spin-stabilized_magnetic_levitation - Levitron physics and patents.
35. https://en.wikipedia.org/wiki/Flux_pinning - superconductor locking.
36. https://en.wikipedia.org/wiki/Pyrolytic_carbon - graphite levitation; Kobayashi & Abe 2012.
37. https://www.chemistryworld.com/news/laser-guided-maglev-graphite-air-hockey/5776.article - coverage of the above (cited on Wikipedia; not opened).
38. https://en.wikipedia.org/wiki/Eddy_current_brake - drag proportional to speed, zero at rest.
39. https://en.wikipedia.org/wiki/Electrodynamic_suspension - induction levitation and its costs.
40. https://www.crealev.com/technology - commercial levitation modules to 10 kg.
41. https://en.wikipedia.org/wiki/Jean-Eug%C3%A8ne_Robert-Houdin - Light and Heavy Chest.
42. https://en.wikipedia.org/wiki/Ionocraft - lifter voltages and thrust.
43. https://news.mit.edu/2018/first-ionic-wind-plane-no-moving-parts-1121 - MIT ion-drive aircraft.
44. https://en.wikipedia.org/wiki/Water_thread_experiment - floating water bridge.
45. https://en.wikipedia.org/wiki/Electrohydrodynamics - background (little usable detail).
46. https://www.murata.com/en-us/products/mechatronics/fluid/overview/lineup/microblower_mzb1001t02 - piezo microblower specifications.
47. https://en.wikipedia.org/wiki/Air_vortex_cannon - vortex-ring ranges.
48. https://la.disneyresearch.com/publication/aireal-interactive-tactile-experiences-in-free-air/ - AIREAL.
49. https://en.wikipedia.org/wiki/Hydrodynamic_quantum_analogs - walking droplets.
50. https://arxiv.org/abs/2003.04777 - Apffel et al., floating under a levitating liquid.
51. https://en.wikipedia.org/wiki/Leidenfrost_effect - Leidenfrost point and related work.
52. https://en.wikipedia.org/wiki/Kaye_effect - leaping shampoo.
53. https://en.wikipedia.org/wiki/Euler%27s_Disk - Euler's disk.
54. https://arxiv.org/abs/2310.04153 - 350,757 coin flips.
55. https://arxiv.org/abs/2005.06493 - Azadi et al., photophoretic levitation of thin films.
56. https://en.wikipedia.org/wiki/Photophoresis - overview and 2020 to 2025 references.
57. https://www.bitcraze.io/products/crazyflie-2-1-plus/ - Crazyflie specifications.
58. https://en.wikipedia.org/wiki/Marco_Tempest - biography (no drone details).
59. https://en.wikipedia.org/wiki/Cable_robots - cable-driven parallel robots.
60. https://hangprinter.org/ - open line-driven robot.
61. https://artcom.de/en/?project=kinetic-sculpture - 714 spheres on steel wires.
62. https://simplefoc.com/ - open field-oriented motor control.
63. https://en.wikipedia.org/wiki/Invisible_thread - invisible thread basics.
64. https://www.yigalmesika.com/ - maker of motorised thread reels.

Pages that failed (403/404/login) and are therefore cited only from memory or from other pages:
Nature and Science article pages, ACS, the MIT ZeroN page, Reactile, HoloTile, PuppetMaster, the
NTT Docomo drone release, the Fun Fly Stick page and individual Mesika product pages.
