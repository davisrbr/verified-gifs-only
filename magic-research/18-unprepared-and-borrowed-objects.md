# 18. Unprepared, ordinary and borrowed objects: what technology can sense about them or do to them without modifying them

Scope: the object in the spectator's hands is honest (their coin, note, ring, phone, glass, a shop-fresh
deck). All the method lives in the environment (table, pad, sleeve, room, the performer's body) or in
information. Prices are as of late 2026. Items recalled from memory and not re-confirmed online are
marked "(unverified)". Order-of-magnitude calculations of my own are marked "(own estimate)" and need a
bench test before anything is built around them.

## 1. Summary

- **An ungimmicked object already carries a serial number; nobody has been reading it.** Paper, card
  stock, print and metal surfaces are unique at the 1 to 100 micron scale, and this has been readable
  with a commodity scanner since 2009 and with a phone camera since about 2015 to 2017 (Clarkson 2009;
  Toreini 2017, 0% false accept / 0% false reject on their datasets from one photo; Wong and Wu 2015 to
  2017). This turns "mark the object" into "enrol the object", which leaves nothing to find.
- **A shop-fresh deck is probably machine-distinguishable from the backs after one enrolment pass.** No
  paper on this was found (a real gap), but the ingredients are established: card makers accept back
  registration errors up to 1/32 inch (0.8 mm), which is the whole basis of casino edge sorting, and
  print-plus-paper microstructure fingerprints work on offset-printed stock. This is the most valuable
  open experiment in this slice and costs nothing but a flatbed scan.
- **Hobby metal-detector physics moves into the table.** Phase-sensitive eddy-current sensing (vending
  acceptors at 1 to 3 mm; TI LDC1612-class chips at about one coil diameter; hobby VLF detectors with
  target-ID at 15 cm and more) can tell that a borrowed coin or ring is present, roughly where, and
  which alloy family it is, through a tabletop or a closed fist. Existing magic "which hand" products
  all require a magnetic coin; the non-magnetic version appears to be unbuilt.
- **Currency metallurgy gives free information and free actuation.** UK 1p/2p since 1992 and 5p/10p
  since 2012 are plated steel; euro 1/2/5 cent are copper-plated steel; the centres of 1 and 2 euro
  coins are magnetic; many modern Canadian coins are steel. US notes carry enough iron-oxide ink to
  swing toward a neodymium magnet. The alloy changes also encode the date range, so an inductive or
  weight reading can "divine" that a penny is pre-1982 or pre-1992 without seeing it.
- **Non-magnetic metal can be pushed, dragged and spun without contact** by a rotating or travelling
  magnetic field (induction-motor principle). Pham et al. (Nature 2021) showed full 6-DOF manipulation
  of a copper sphere with rotating dipole fields. My estimate is that a flat copper-cored coin on a
  table will spin or creep above a 3,000 rpm two-pole neodymium rotor at 10 to 20 mm gap, with
  milliwatt heating; cupronickel, platinum, titanium and tungsten objects respond 5 to 15 times less.
- **Vibration is the universal actuator for non-metal objects.** A plate oscillated horizontally with
  an asymmetric waveform moves anything resting on it (Reznik and Canny's Universal Planar
  Manipulator; Vose, Umbanhowar and Lynch's programmable velocity fields; Zhou et al.'s Chladni-plate
  steering). The acceleration needed to break friction corresponds to only about 20 microns of travel
  at 60 Hz (own estimate), which is invisible; the giveaway is hum and ripples in drinks.
- **People now carry magnets and radios, so some "gimmicked" methods work on borrowed things.** A
  MagSafe phone, an earbud case and a steel bottle cap are all detectable by the magnet sensors magic
  already sells. Phones leak presence passively over BLE. The ethical line is clear and is stated in
  the catalog: presence and position are fine with consent; names, identifiers and payment data are
  not.
- **Thermal, acoustic and weight side channels identify "the one they touched".** Residual heat is
  readable for 30 to 60 s on plastic and longer on coins; a tap or a set-down has an object-specific
  sound (Knocker: 98% in the lab on 23 objects); a four-corner load-cell table knows the weight and
  position of everything on it.
- **A few quiet effectors act on paper, liquids and eyewear:** kilovolt electrodes (tissue lifts at
  roughly 2 kV/cm, own estimate), silent piezo blowers, breath-figure latent images on glass,
  a thermal print head acting on the spectator's own till receipt, and UV on photochromic lenses
  (15 to 60 s to darken). Each has a hazard or a tell that is listed below.
- **Overhyped for live use:** diamagnetic forces on water or fruit, acoustic levitation of borrowed
  objects, anything requiring a web page on the spectator's phone to read a sensor, and any reading of
  contactless bank cards (illegal and pointless).

## 2. Catalog

### A. Knowing: natural fingerprints as covert identity

**A1. Paper and card-stock surface fingerprinting.**
Paper is a random mat of fibres; its surface relief and its internal density are unique per square
millimetre and survive handling. Buchanan, Cowburn et al. (Nature 2005) read this with laser speckle
("laser surface authentication", later commercialised by Ingenia) on paper, plastic cards and
packaging. Clarkson et al. (IEEE S&P 2009) removed the laser: several passes of an ordinary flatbed
scanner at different orientations recover the 3D surface texture and a compact fingerprint; they report
robustness to harsh handling and that it works on blank paper. PaperSpeckle (Sharma, Subramanian,
Brewer, CCS 2011) used a sub-$100 USB microscope with built-in LED and reported well-separated
distributions even after crumpling, soaking and ageing. Toreini, Shahandashti and Hao (ACM TOPS 2017)
photographed light transmitted through the sheet with a commodity camera, took a 37 x 57 mm region and
produced a 2,048-bit code with 807 degrees of freedom (an iris code has 249) and 0% false accept / 0%
false reject on their benchmark (100 sheets of 80 gsm A4, 1,000 photos, about 1.3 s of Matlab per
photo). Their stress tests kept false accepts at 0% throughout; false rejects were 0% after
scribbling, soaking and heating, 0.32% under rotation up to 12 degrees and 3.2% after crumpling. Note
that this method needs light *through* the sheet (they used an overhead projector, then a 50 pound
tracing light box) and was not tested on card stock, so for opaque cards the reflective methods
(Clarkson; Wong and Wu) are the relevant ones. Wong and Wu (WIFS 2015, TIFS 2017, US patent 10,726,256) estimate the
microscopic surface-normal field from a few phone photos with flash, and their later work drops the
flash and uses room light. Berchtold, Suetter and Steinebach (IS&T Electronic Imaging 2021) fingerprint
the combination of print variability and paper structure with a phone at varying distance, on both
office and offset prints. Commercial equivalents (Alitheon FeaturePrint and similar) advertise
tag-free identification of trading cards and parts from one phone photo.
- References: nature.com/articles/436475a; pixl.cs.princeton.edu/pubs/Clarkson_2009_FBP;
  ar5iv.labs.arxiv.org/html/1705.02510; PaperSpeckle PDF (cs.nyu.edu); sigport.org (Wong and Wu);
  library.imaging.org/ei/articles/33/4/art00009; alitheon.com.
- Accessibility: hobbyist. A flatbed scanner ($60), a $25 USB microscope, or a phone with a macro lens
  and a ring of LEDs. Software is classical (Gabor filter, random projection, Hamming distance) and
  small enough for an LLM to write in an afternoon. A patent survey suggests about 2,400 dpi is needed
  to identify one item among many, but much less to confirm "is this item X or Y" among a handful
  (US 8,180,174), which is the magic case.
- Magic relevance: *know* and *prove ordinariness*. Any billet, business card, envelope, banknote,
  sugar packet, napkin, torn corner or signed card can be re-identified later with no mark, no nick,
  no crimp and no daub. Enrolment is one glimpse by a hidden camera at the moment the object is
  handed out; recognition is one glimpse later. Weaknesses: needs a controlled close view (5 to 15 cm,
  repeatable lighting, object flat), so the camera wants to live in a pad edge, a card box, a wallet,
  a pen pot or the performer's phone lying "idle" on the table.
- Prior use in magic: none found. Magic uses added marks (pencil dots, nail nicks, daub, marked
  envelopes); the idea that an unmarked billet is already marked seems unexploited.

**A2. Playing-card backs: registration and cut variation (speculative, high value).**
Edge sorting works because the back design is not centred identically on every card: Gemaco stated in
the Ivey litigation that the industry accepts pattern discrepancies up to 1/32 inch (0.8 mm). On a
bordered back (Bicycle Rider Back) this appears as unequal white margins and a slight rotation; on a
borderless back (Bee) it appears as a different phase of the diamond lattice at each edge. Because
every card of a deck comes from a different position on the press sheet and is cut separately, the
offset vector (dx, dy, rotation) should differ card to card within one deck. A 4K camera 50 cm above a
close-up mat resolves about 0.15 mm per pixel, and sub-pixel edge fitting reaches roughly 0.02 to
0.03 mm (own estimate), so three independent parameters each give 5 to 10 distinguishable levels:
enough to shrink 52 cards to a handful of candidates each, and with A1-style print texture (ink
speckle, hickeys, fibre shadows) enough for unique identity. For a borrowed, used deck the job is far
easier: wear, dog-ears, stains and warp are visible at arm's length. Chinese mahjong/poker-machine
patents already classify card backs with learned feature codes (US 11,986,725), and one of them
complains that back-pattern irregularity causes misidentification, which is the same signal seen from
the other side.
- A second-order idea: if cut offset is partly systematic by sheet position, then offset correlates
  with card identity across decks of the same print run, and a model trained on a few decks would
  recognise some values in a deck it has never seen. Entirely unverified; cheap to test.
- Accessibility: experiment needs only a scanner and a new deck. A performance system needs an
  overhead or pad-edge camera, controlled lighting, and an earpiece or tactile cue (agent 10).
- Magic relevance: full-deck *know* from the backs with a shop-sealed deck the spectator bought.
  Enrolment is the hard part: the camera must see each face and associate it with its back. A face-up
  ribbon spread followed by a turnover of the spread does this in about 3 s (order is preserved and
  reversed). What gives it away: needs a camera with line of sight, steady light, and cards lying
  reasonably flat; a spectator who swaps in a second deck defeats it.
- Prior use in magic: one-way backs and "natural" one-way decks from misregistration are classical;
  per-card machine identification from honest backs was not found in any source.

**A3. Coins: denomination, alloy, date range and individual identity.**
Four channels, all contact-free.
- *Inductive signature.* A coil forms a resonant tank; a coin nearby changes both its inductance and
  its loss, and the ratio depends on conductivity, permeability, thickness and diameter. Coin
  acceptors measure this at two or more frequencies (patents describe 100 and 160 kHz) at millimetre
  gaps. TI's LDC1612 (28-bit inductance-to-digital; Seeed Grove board about $10 to $15 (unverified
  price)) does it with a PCB spiral; Seeed's demo thresholds a coin at 1 to 5 and 5 to 10 mm, and
  range scales with coil diameter (roughly 0.5 to 1 diameter for presence, less for discrimination
  (unverified rule of thumb)). Hobby VLF metal detectors report a phase-based "target ID" that
  separates US nickel, zinc cent, dime and quarter at 15 cm and more (unverified, standard hobby
  knowledge), which shows that phase discrimination survives distance. Steel-cored coins give the
  opposite phase sign to copper-cored ones.
- *Composition changes encode dates.* UK 1p/2p: bronze before September 1992, copper-plated steel
  after; UK 5p/10p: cupronickel before 2012, plated steel after (Royal Mint). US cent: 95% copper, about
  3.1 g until 1982, copper-plated zinc 2.50 g since (both kinds exist dated 1982; Wikipedia); US
  dime/quarter: 90% silver before 1965 (unverified from memory, standard numismatics). Canada moved to plated steel around 2000 (dates
  vary by source). So phase or weight alone yields "this coin is older than X".
- *Acoustic signature.* A struck or dropped coin rings at modes in the 5 to 20 kHz band set by
  alloy, diameter and thickness. An LLNL teaching report shows a phone microphone at 48 kHz is enough
  and calls the spectrum a fingerprint; a 2026 arXiv paper classifies bullion coin types with neural
  networks; a 2023 Heritage Science paper builds acoustic IDs for 19 ancient coins; an older patent
  warns that drop height and impact point change the spectrum, so use mode frequencies, not
  amplitudes. An electromagnetic acoustic transducer (EMAT) rings a coin with no mechanical contact
  (Sensors 2022, PMC9740311): an 8 A, 1 ms pulse from a 5.4 V capacitor into a 7-turn, 27 mm spiral
  coil over concentric NdFeB magnets kicks the coin by Lorentz force, a microphone reads the ring,
  and the natural frequency is known in 22 ms. The important numbers for magic: thirty genuine coins
  of one denomination (Taiwan 50 dollar) spread from 16.92 to 17.45 kHz, while repeat readings of one
  coin scatter by only about 12 Hz (under 0.1%). A 530 Hz spread against 12 Hz repeatability means
  *individual coins of the same denomination are separable by pitch alone*, into some tens of bins.
  The catch is lift-off: their optimum is 0.5 mm and they tested only to 1.2 mm, so the EMAT works
  through a card or a thin mat, not through a tabletop; a flick, drop or spin heard by a microphone
  has no such limit.
- *Image.* Date and mint mark by OCR; individual re-identification from scratches and toning is easy
  for a camera at macro range although no paper specifically on same-coin re-identification was found
  (the literature is about type classification).
- Magic relevance: *know* for which-hand, coin-under-cups, "name the date", "which of five borrowed
  coins did you pocket" (weigh or ring the remaining four). Concealment: coil in a close-up pad, a
  book, a bar mat, a table edge; microphone anywhere. Gives it away: other metal near the coil
  (rings, watches, phone) unless a baseline is taken first; coil range is short.
- Prior use: Sixth Sense 3 (Hugo Shelley, $300, possibly discontinued), ESPionage (Iarvel, $149.95,
  claims 15 cm) and similar all sense a *magnet*, so the coin must be a magnetic shell or a magnetic
  currency. Retail copy states plainly that non-magnetic metal will not trigger them.

**A4. Banknotes.**
US notes are intaglio-printed with ink containing iron oxide; the portrait side is magnetic, the
Federal Reserve seal is not, and each denomination has a different magnetic layout (University of
Waterloo Chem 13 News). Bill validators read this with magnetoresistive heads at near-contact range
(TMR/GMR/AMR preferred over InSb Hall, patent US 9,721,415); euro notes carry magnetic material that
must be magnetised before sensing. Practical consequence: a magnetoresistive head in a pad surface can
tell a $1 from a $20 face-down, folded, or inside a thin envelope, but only when the note is dragged
across it within a millimetre or so. Every note also carries a printed serial (OCR from one 4K video
frame at 30 to 50 cm is routine (unverified, no specific source opened)), UV-fluorescent thread and
IR-contrast zones that a $5 UV LED or an IR-pass camera reads, and all the A1 fingerprints.
- Magic relevance: serial-number divination without a switch (hidden camera reads it while the
  spectator "checks it is real"); denomination through an envelope; re-finding one borrowed note
  among many by fibre fingerprint or serial.

**A5. Sound of contact, weight and heat: "which one did they touch?"**
- *Acoustic.* Knocker (Gong et al., IMWUT 2019) identifies 23 everyday objects from the sound and
  inertial response of a knock: 98% in the lab, 83% in the wild, 93% on a harder set of 12 similar
  books and bottles, using only phone sensors; the authors say it will not separate near-identical
  items such as two brands of the same can. A contact
  microphone or accelerometer under a table sees every set-down, pick-up, slide and tap; glass pitch
  shifts with fill level; each object in a small set has a distinct "clink". Enrolment is each object
  being put down once.
- *Weight.* Four load cells under a tabletop or tray give total weight and centre of pressure, so
  every pick-up and put-down is logged with its mass and position (HX711-class amplifiers, about $2
  per channel, resolve about 0.01 g on a 100 g cell and about 1 g on a 20 kg platform (unverified,
  typical hobby figures)). Agent 22 covers tables as a design space; the point here is that the
  objects are untouched. Mass differences that matter: US cent 2.5 vs 3.11 g; a playing card is about
  1.7 to 1.8 g (unverified), so packet counts by weight are exact to one card; a sealed can or bottle
  reveals its fill; a matchbox reveals its match count.
- *Heat.* Skin leaves a thermal trace. Abdelrahman et al. (CHI 2017) recover touchscreen PINs with 72
  to 100% success within 30 s; Thermanator (2018) recovers key presses up to 30 to 60 s later, and
  material matters (ABS holds heat, PBT and metal keys do not show it). A coin held in a fist for
  20 s is several kelvin warm and, having about 2 J/K of heat capacity, stays measurably warm for
  minutes (own estimate). Sensors: 32 x 24 thermopile arrays for about $40 to $60, phone-dongle
  microbolometer cameras for about $200 to $300 (unverified prices). Thin black polyethylene film is
  opaque to the eye and largely transparent in the 8 to 14 micron band (unverified from memory), so a
  thermal sensor can hide behind what looks like a black plastic panel or bag.
- Magic relevance: psychometry and "which object did you think of / hold" with the performer's back
  turned and without touching anything afterwards. The classic "warm coin" stunt done at 2 m with no
  handling. Tells: needs line of sight in the infrared; shiny metal has low emissivity and reads
  cooler than it is, so coins are better sensed from their painted or tarnished faces or by contact.

**A6. Through-cover sensing of liquids, hands and stacks.**
- *Capacitive.* TI reports proximity ranges up to tens of centimetres for large electrodes and
  touch sensing through 19 mm plywood and 25 mm particle board with CapTIvate MCUs; the FDC1004
  resolves femtofarads and lists remote liquid-level sensing as a use. Water (relative permittivity
  about 80) against wood (2 to 6) is a large contrast, so which of several opaque cups holds liquid,
  and roughly how much, is readable from below a thin top. Conductive or foil-backed surfaces block
  it.
- *Radar.* RadarCat (Yeo et al., UIST 2016) classified 26 materials and 16 transparent materials
  placed on a Google Soli 60 GHz chip with a random forest; the same group's "Exploring Tangible
  Interactions with Radar Sensing" (Yeo, Minami, Rodriguez, Shaker, Quigley, IMWUT 2018) counts,
  orders and identifies stacked flat objects and tracks their orientation and distance "with minimal
  training" (my recollection that the test objects included playing cards and poker chips is
  unverified; the abstract gives no accuracy figure). 60 GHz modules now cost
  about $10 to $40 (unverified) and see through wood, plastic, cloth and leather. LiquID (MobiSys
  2018) identifies liquids from UWB permittivity measurements through the container.
- Magic relevance: "which cup has the water", "how many cards did you cut", "is the fist open or
  closed", presence and breathing of a hand over a spot, with nothing visible. Tells: none visually;
  metal trays and foil defeat it; classification needs per-venue calibration.

**A7. What spectators' own devices give away (and the line not to cross).**
- *Magnets they already carry.* Every iPhone from the 12 onward (except SE and 16e) has a ring of
  rare-earth magnets in its back; so do the charging cases of AirPods 3 and AirPods Pro (not AirPods
  4), and many Android phones and cases now follow with Qi2 (unverified). Magnetic watch bands and
  bag clasps add more. The magnetometer gimmicks magic already sells will therefore detect "the phone
  is in the left pocket" or "the earbud case is under the middle cup" with no magnetic prop
  (field strengths not found; expect 5 to 20 cm depending on the item, to be measured).
- *Passive radio.* Phones, watches and earbuds advertise over BLE continuously. Research shows the
  payloads reveal device class, OS family and activity states such as lock/unlock even with
  randomised addresses (Martin et al., PoPETs 2019; arXiv 1904.10600), and RSSI is too noisy on its
  own to say which pocket. For magic this supports only coarse, non-identifying facts ("someone at
  this table just opened an earbud case", "a phone moved from the table to under it" using several
  receivers). Reading names from AirDrop/Quick Share/Bluetooth lists is hot reading of personal data;
  treat it as off limits without explicit consent, and never log identifiers.
- *The phone as an unwitting instrument.* Every phone has a compass; a hidden magnet steers the
  spectator's own Compass app (a 25 mm N52 cube gives about 100 microtesla, twice the Earth's field,
  at about 25 cm; own estimate). The generic web Magnetometer API is Chrome-Android only and
  unsupported in iOS Safari, and Web NFC is likewise Chrome-Android only, so "no app, any phone"
  browser tricks are not dependable. NFC tags that open a URL work on both platforms (on iPhone via
  background tag reading, which shows a notification that must be tapped; details unverified) but are
  screen magic, which the brief ranks low. Two further unwitting behaviours, both from memory and
  unverified: phone cameras, front cameras especially, register 850 to 940 nm LEDs that the eye
  cannot see, and rolling-shutter sensors turn a fast-flickering lamp into stripes, so a message can
  exist only when viewed through the spectator's own camera. Face-unlock systems fire an infrared
  flood illuminator and dot projector, which a hidden photodiode could use as a "their phone just
  woke" trigger.
- *Contactless cards and key fobs.* Do not read them. Pulling the card number from a contactless
  bank card without consent is unlawful in most jurisdictions and gains nothing a magician needs.
  Even "is there a card in this wallet" energises someone's payment instrument; get consent or leave
  it. Car-key relay or replay is out of the question.

### B. Acting: forces on unmodified objects

**B1. Eddy-current drag, spin and push on non-magnetic metal.**
A conductor in a moving magnetic field carries induced currents that pull it along with the field
(induction motor, eddy-current clutch, speedometer cup). Lecture demos spin an aluminium plate on a
magnetic stirrer (UMD K2-49) and drag a copper disc with a spinning magnet (UCSB 72.39); an
Instructables build hides a motor-driven rotor under a thin plate and keeps a copper top spinning
indefinitely, and reports that copper held above it is "dragged out of your hands". Pham et al. (Nature
598, 2021) formalised this: rotating dipole fields give controllable force and torque on a copper
sphere, enough for 6-DOF manipulation with four to six sources, with follow-ups on attraction (RA-L
2022) and position regulation (T-RO 2024).
- Numbers (own estimates). Field of a 25 x 10 mm N52 disc on axis: about 160 mT at 10 mm, 54 mT at
  20 mm, 23 mT at 30 mm. Torque on a flat disc of radius a, thickness t, conductivity s, from a
  two-pole field rotating at w is of order 0.1 to 0.5 x s t w B^2 pi a^4 / 4. For a US quarter
  (copper core, s t about 6e4 S) at 3,000 rpm and 50 mT that is about 1e-4 to 4e-4 N m, against a
  sliding-friction torque of about 1.3e-4 N m: it should spin at 10 to 20 mm and stall at 30 mm.
  Tangential drag on the same coin is about 0.01 to 0.05 N against 0.017 N of friction. Power
  dissipated in the coin is about 0.1 W, a few kelvin per minute, harmless.
- Which objects respond: copper-cored US dime, quarter, half; pre-1982 cents; zinc cents (half as
  well); silver rings and coins (best); 14 to 18 carat gold rings (3 to 5 times weaker than silver);
  aluminium cans, foil, tea-light cups, laptop lids (large area, tiny mass: easiest of all).
  Poor: cupronickel (US nickel, UK 20p/50p), platinum, titanium, tungsten carbide, stainless
  steel, brass keys (moderate). Conductivities are textbook values (unverified here).
- Hardware: brushless drone motor ($15) carrying two to four N52 magnets, or a three-phase stator
  from a ceiling fan or hoverboard motor driven by a $10 ESC for a silent, no-moving-parts
  travelling field. Concealment: under a thin (3 to 10 mm) tabletop, in a book, in a close-up case.
  Gives it away: rotor whine and vibration (use a stator instead), any steel object nearby leaping
  toward it, watches and phones on the table, and the short range.
- Magic relevance: *move* and *animate* a borrowed ring or coin that is provably non-magnetic (a
  spectator can test it with a magnet first, which cancels the obvious theory). Rolls an empty drinks
  can, spins a ring standing on edge, makes a coin crawl out from under a glass.
- Prior use: PK-ring and electromagnet work on steel or magnetised props is everywhere; induction
  drive of honest non-ferrous borrowed metal was not found as a marketed method.

**B2. Native ferromagnetism: what in a pocket already answers a magnet.**
Plated-steel coins (UK 1p, 2p, 5p, 10p of the dates above; euro 1, 2, 5 cent; inner part of 1 and 2
euro; many Canadian coins since about 2000); crown bottle caps and champagne wire cages; split key
rings and steel keys; the hood and wheel of a disposable lighter; pen clips and springs; table knives
and cheap ferritic cutlery (good austenitic forks and spoons barely respond); paper clips, staples
(tea bags, matchbooks, magazines); US banknotes (a hanging or balanced note swings to a neodymium
magnet: University of Iowa demo 5G10.18). Force is not the limit (a 2 g steel cap feels several times
its weight at 20 mm from a 25 mm N52 magnet, own estimate); control is, because attraction is
unstable and snaps. Use gradients that drag along the surface, and electromagnets or servo-moved
magnets for timing.
- Magic relevance: "haunted" motion with objects that were never out of the spectator's possession.
  A US note balanced on a pencil point or folded into a tent is the most deceptive, because people do
  not believe paper is magnetic.

**B3. Controlled vibration: moving anything on a surface.**
Reznik and Canny's Universal Planar Manipulator moves several objects along independent paths on one
flat plate driven horizontally by four voice coils, using sliding friction and time-varying local
"jet" fields (WAFR 1998, IROS 2001). Vose, Umbanhowar and Lynch (IJRR 2009) showed that small periodic
six-axis motions of a rigid plate produce programmable velocity fields with sinks, sources and
circulation, so parts gather, line up or orbit with no sensing. Zhou, Sariola, Latifi and Liimatainen
(Nature Communications 2016) steer up to six objects at once on a centre-driven Chladni plate by
choosing which of 59 notes (1 to 30 kHz) to play for 0.1 to 0.5 s, with camera feedback; their plate is
a 50 x 50 x 0.5 mm silicon wafer with one small piezo, the objects are millimetre-scale (solder balls,
seeds, SMT resistors, a 7 mm washer, water droplets on carriers) and path error is about 0.1 mm. That
is a pocket-sized demonstration that closed-loop control makes "random" plate vibration steerable; it
has not been shown at coin scale. Ultrasonic squeeze-film plates reduce friction on command or convey
parts on travelling waves.
- Numbers: to make a part slip, plate acceleration must exceed friction coefficient times g, about
  3 m/s^2, which is 21 microns of amplitude at 60 Hz or 84 microns at 30 Hz (own estimate): not
  visible. Net transport comes from waveform asymmetry (slow forward, fast return) or from combining
  horizontal with vertical motion; speeds of millimetres to a few centimetres per second are typical
  of this literature (unverified figure). Objects with different friction have different thresholds,
  which allows selective motion.
- Hardware: two to four voice-coil exciters or surface transducers ($5 to $15 each), a plate on
  flexures (3D-printable), a class-D amp board, a microcontroller generating waveforms; $60 to $150.
- Magic relevance: *move* with no magnetism, so it works on a sugar cube, a die, a pen cap, a plastic
  chip, a borrowed wooden ring. The spectator may hold a magnet-detecting phone over it and find
  nothing. Tells: low hum (mask with music or a fridge-like ambient source), ripples in any drink on
  the surface, tingling under fingertips, and everything on the plate moving at once unless fields
  are shaped.

**B4. Electrostatics from a hidden electrode.**
A conductor at 10 to 30 kV polarises and attracts light objects. Paper behaves as a conductor on a
timescale of seconds at normal humidity, so the lift condition is roughly e0 E^2 / 2 greater than
weight per area: about 2 kV/cm for 18 gsm tissue or cigarette paper and about 4.3 kV/cm for 80 gsm
copier paper (own estimate), below air breakdown at about 30 kV/cm. Electroadhesion studies confirm
force rising with the square of voltage and strong sensitivity to humidity and dust; paper-handling
patents use 0.5 to 10 kV. Demonstrations deflect a thin water stream with a charged rod (the stream
carries induced charge, University of Iowa 5A40.40). Sources: negative-ion or electrostatic modules
(12 V in, 10 to 20 kV out at microamps, a few dollars (unverified)). The electrode can be a foil
under a plastic or glass top, or the performer's own body standing on insulating soles.
- Magic relevance: a napkin corner lifts, a straw wrapper crawls, a balanced straw or matchstick
  turns, cigarette smoke in a glass collapses, a thin stream from a bottle bends, an empty can rolls
  toward a hand. All on venue objects.
- Hazards and tells: sparks to spectators (unpleasant though low energy if capacitance is kept
  small), risk to phones and hearing aids, absolutely no use near solvent vapour or lighter gas;
  fails above about 60 to 70% relative humidity and on damp wooden tables which screen the field.

**B5. Air: silent jets and vortex rings.** Vortex rings stay coherent for metres (Purdue demo: knock
over a plate or snuff a candle beyond 5 m; the 1965 Wham-O toy at 7.6 m) but aim is erratic unless the
piston is symmetric. Piezoelectric microblowers (Murata MZB1001T02: driven at 24 to 27 kHz, at least
0.7 L/min and 1.42 kPa at 15 V peak-to-peak, described by the maker as silent; about 20 x 20 x 2 mm
and $20 to $30 (size and price unverified)) give a thin, cold jet from a sleeve, pad edge or pen. Magic relevance: flames,
smoke, a card balanced on edge, a paper ball, a feather; classic "air" methods without a mouth or a
squeeze bulb. Agent 9 covers levitation; this is a pointer.

**B6. Heat at a distance.** Induction: a pancake coil under a thin top couples a few watts into a
coin at 5 to 10 mm (own estimate; hobby ZVS drivers of 100 to 1,000 W are $10 to $40). A US quarter
has about 2.2 J/K, so 5 W raises it 15 K in about 7 s. Steel-cored coins heat far faster.
**Hazard:** the same field heats rings on fingers, watch cases, phone coils and medical implants;
never energise with a hand in the field, cap temperature below 45 C, and interlock on a timer.
Radiant IR works poorly on shiny metal. Spinning-magnet heating (KJ Magnetics' "induction stove")
is the same physics and needs kilogauss fields at close range.

**B7. Thermal paper is a writable surface people carry.** Till receipts, parking tickets and many
boarding passes are direct-thermal paper whose coating develops colour when it melts, at around
100 C; a fingernail dragged quickly across it leaves a grey line by friction heat alone, and a warm
cup can fog it (Wikipedia, Thermal paper). The low-tech corollary: a hard, smooth stylus or thimble
edge under the performer's finger writes on a borrowed receipt with no ink at all. A thermal
print-head line (58 mm, 384 dots, $10 to $20 as part of a receipt-printer mechanism (unverified))
set flush in a pad can write on the spectator's own receipt if the paper is pressed and drawn across
it; an optical-mouse sensor beside it clocks the lines to the paper's motion. This is a modification,
but of a borrowed object, in two seconds, under the performer's palm, with no ink, and it is
permanent and examinable. No laser is needed (lasers that mark thermal paper are eye hazards and are
not recommended in a room with people).

**B8. Wettability patterns and breath figures (pointer to agent 17).** Clean glass wets as a clear
film; contaminated glass fogs into scattering droplets, so an invisible pattern becomes visible when
vapour condenses (Rayleigh and Aitken in Nature, 1911 to 1913; a 1923 Nature letter on flame-cleaned
tracks; modern reviews). A fingertip stroke of skin oil or a wipe with a surfactant-damped cloth is a
two-second treatment; the image appears when the spectator breathes on their own glass, phone screen,
spectacle lens or watch crystal, or when a cold drink is poured, and disappears as it evaporates.

**B9. Photochromic spectacles.** Lenses darken under UV in about 15 s (ZEISS PhotoFusion X claim, to
30% transmission at 23 C) to 30 to 60 s (typical), and clear in 2 to 5 minutes; some newer products
also respond to short-wavelength visible light. A 365 to 395 nm LED array hidden in a glasses case,
book or lamp darkens a borrowed pair lying on the table. **Hazard:** never aim UV at a wearer's eyes
or skin; do it only with the glasses off the face. Works only on the minority of spectators with
such lenses, so it is an opportunistic bonus, not a routine.

**B10. Sound placed on an object.** An ultrasonic parametric array emits a narrow beam that
demodulates into audible sound in the air and "appears to radiate from any surface that the beam
strikes" (Wikipedia, Sound from ultrasound; commercial units include Holosonics Audio Spotlight;
carriers of 40 to 60 kHz; hobby transducer-array boards $50 to $150 (price unverified)). Aimed at a borrowed can, shell, book or
empty glass, the object seems to whisper. Separately, an audio-frequency electromagnet under the
table will make an aluminium can or a coin buzz by eddy-current forces (the EMAT principle, A3).

## 3. Capability primitives

1. *Now possible:* re-identify any one of about 100 pieces of unmarked paper or card from a single
   phone-class photo, with error rates reported as 0% on research datasets. *Because:* paper texture
   fingerprinting (Clarkson, Toreini, Wong and Wu). *Before:* secret marks, nicks, crimps, daub.
   *Primitives:* know, prove ordinariness.
2. *Now possible:* (speculative) identify cards of a sealed, shop-bought deck from their backs after
   a 3 s enrolment. *Because:* 0.8 mm registration tolerance plus 4K cameras and sub-pixel fitting.
   *Before:* marked decks, or memory plus peeks. *Primitives:* know, prove ordinariness.
3. *Now possible:* detect a non-magnetic coin or ring through 5 to 40 mm of table or a closed fist
   and classify its alloy family. *Because:* LDC-class inductance converters ($5 chip) and VLF phase
   discrimination. *Before:* magnetic shells and coins only. *Primitives:* know.
4. *Now possible:* tell a pre-1982 from a post-1982 US cent, or pre-1992 from post-1992 UK penny,
   unseen. *Because:* alloy changes plus inductive phase or a 0.6 g weight step. *Before:* peeking.
   *Primitives:* know.
5. *Now possible:* know which of N identical-looking objects was picked up, put down or tapped, with
   back turned, from sound alone. *Because:* contact-mic classification (Knocker-style, 98% lab).
   *Before:* stooge, peek, reflective surfaces. *Primitives:* know.
6. *Now possible:* log weight (to about 1 g) and position (to about 1 cm) of every object on a table
   continuously. *Because:* four load cells and $8 of amplifiers. *Before:* nothing comparable.
   *Primitives:* know, delay.
7. *Now possible:* see which object was handled 30 to 120 s ago without touching it. *Because:* $40
   thermopile arrays and $250 thermal cameras. *Before:* touching the coin to feel warmth.
   *Primitives:* know.
8. *Now possible:* know which opaque cup holds liquid, through the table. *Because:* femtofarad
   capacitance converters; 60 GHz radar modules. *Before:* weight feel, sound, marked cups.
   *Primitives:* know.
9. *Now possible:* count cards in a cut packet to the card, unseen. *Because:* gram-level weighing
   (1.7 g per card) or millimetre-wave ranging. *Before:* estimation by eye, crimps, breather cards.
   *Primitives:* know.
10. *Now possible:* read a banknote serial in one video frame at half a metre. *Because:* 4K sensors
    and on-device OCR. *Before:* note switches, memorised serials. *Primitives:* know.
11. *Now possible:* read the denomination of a US note face-down or in an envelope by sliding it over
    a pad. *Because:* $5 magnetoresistive heads. *Before:* marked envelopes. *Primitives:* know.
12. *Now possible:* locate a spectator's phone or earbud case on their person or under a cover.
    *Because:* they contain magnets; magnetometers cost $2. *Before:* required planting a magnet.
    *Primitives:* know.
13. *Now possible:* spin, drag or roll a provably non-magnetic silver ring, copper-cored coin or
    aluminium can at 10 to 20 mm gap with about 0.1 W dissipated in the object. *Because:* cheap N52
    rotors and BLDC drivers; eddy-current drive. *Before:* threads, or steel/magnetic props.
    *Primitives:* move, prove ordinariness.
14. *Now possible:* translate any small rigid object across a surface at mm/s to cm/s with surface
    motion of tens of microns. *Because:* voice-coil exciters and waveform synthesis (UPM, Vose).
    *Before:* threads, magnets, tilting. *Primitives:* move.
15. *Now possible:* make several loose objects gather to one point or orbit, without sensing.
    *Because:* programmable vibratory velocity fields. *Before:* not possible. *Primitives:* move,
    control chance.
16. *Now possible:* lift tissue or attract foil from 3 to 5 cm with a 20 kV, microamp source the size
    of a matchbox. *Because:* $5 ion-generator modules. *Before:* rubbed combs, threads.
    *Primitives:* move.
17. *Now possible:* a silent, cold, pencil-thin air jet from a sleeve. *Because:* piezo microblowers.
    *Before:* breath, bulbs. *Primitives:* move.
18. *Now possible:* warm a coin by 15 K in under 10 s through a tabletop. *Because:* $20 resonant
    induction drivers. *Before:* chemical heat (toxic), pre-warming. *Primitives:* transform.
19. *Now possible:* print 8 dots/mm text onto a spectator's own thermal receipt in 2 s with no ink.
    *Because:* salvaged thermal print heads plus optical-flow clocking. *Before:* switching the
    paper. *Primitives:* transform, prove ordinariness.
20. *Now possible:* leave an image on glass that is invisible until condensation and gone a minute
    later. *Because:* wettability contrast (breath figures). *Before:* known as a parlour curiosity,
    seldom engineered. *Primitives:* delay, erase the evidence.
21. *Now possible:* steer the compass in a spectator's own phone from 25 cm. *Because:* compact N52
    magnets on a servo. *Before:* gimmicked compasses. *Primitives:* tell, move.
22. *Now possible:* excite and read a coin's acoustic resonance with no contact. *Because:* EMAT
    coils. *Before:* flicking it. *Primitives:* know.
23. *Now possible:* tell coarse device events at a table (an earbud case opened, a phone woke) from
    passive BLE. *Because:* $5 BLE sniffers. *Before:* not possible. *Primitives:* know (with strict
    privacy limits).
24. *Now possible:* darken a borrowed pair of photochromic glasses in 15 to 60 s from a hidden UV
    source. *Because:* 365 nm LEDs at $1 each. *Before:* not possible. *Primitives:* transform.
25. *Now possible:* make a sound appear to come from a borrowed object 2 to 5 m away.
    *Because:* hobby parametric arrays. *Before:* ventriloquism, hidden speakers in props.
    *Primitives:* tell, conceal.

## 4. Effect concepts

Levels refer to the brief: 1 phenomenon is the effect, 2 hidden input to a classical method, 3 new
architecture.

**E1. The unmarked billet test (level 3).**
*Effect:* five spectators each take a blank business card from a stack one of them supplied, write a
word, and drop the cards writing-side down into a hat. The performer returns each card to its writer
and names the words, never turning a card over until the reveal.
*Method:* a macro camera and LED ring inside the lip of the pad (or the performer's phone lying on the
table) photographs the blank back of each card as it is handed out and fingerprints a 30 x 30 mm patch
(A1). Later each card passes the same spot on its way back; the match says whose it is. Words are
obtained by any classical means or simply not needed (ownership alone is strong).
*BOM:* Raspberry Pi Zero 2 W or ESP32-S3 camera, macro lens, 4 LEDs, bone-conduction or thumper cue:
about $60. *Difficulty:* medium (software; capture geometry must be repeatable). *Risks:* glossy or
plastic cards have less texture; the card must pass within the capture window. *Novelty:* high; I found
no magic use of substrate fingerprinting.

**E2. Shop-sealed deck, read from the backs (level 3, speculative).**
*Effect:* the spectator buys a deck, opens it, shuffles; the performer deals face-down hands and
calls them.
*Method:* A2. Ribbon-spread face up "to check they are all there", flip the spread, gather: an overhead
or lamp-mounted 4K camera has now tied each face to its back offset and micro-texture. Software tracks
or re-recognises backs after the shuffle. Classical cover: the performer also does genuine false
cuts so the audience credits skill.
*BOM:* 4K USB camera, small PC or phone, diffuse light, earpiece: $100 to $200. *Difficulty:* high;
first verify separability on scans. *Risks:* may not separate all 52 on bordered backs without macro
detail; lighting. *Novelty:* high if it works.

**E3. Any coin, either hand, with a magnet test first (level 2).**
*Effect:* the spectator proves their coin and ring are non-magnetic with a fridge magnet, then hides
the coin in a fist behind their back and rests both fists on the table. The performer names the hand,
then the denomination.
*Method:* two LDC1612 coils (60 to 100 mm spirals) inside a close-up pad. Baseline both fists before
the coin is taken (rings, watches), then read the differential. Phase angle classifies alloy family;
A3. The magnet test up front cancels the standard theory.
*BOM:* two coil PCBs, LDC1612 board, ESP32, haptic cue: $40. *Difficulty:* medium. *Risks:* range;
spectators who hover fists high; steel table frames. *Novelty:* medium-high (magnet-free which-hand).

**E4. The date in the fist (level 2).**
*Effect:* spectator picks any penny from their change and holds it; performer says "older than you
are" or names the decade bracket, then narrows to the year by ordinary pumping.
*Method:* E3 hardware or a pad load cell reads alloy/mass: pre/post 1982 (US), pre/post 1992 (UK), and
steel vs cupronickel 5p/10p (2012). Combine with known mintage distributions to bias guesses.
*BOM:* as E3 plus a 100 g load cell: $50. *Difficulty:* low-medium. *Novelty:* medium.

**E5. The ring that cannot be magnetic (level 3).**
*Effect:* a borrowed silver or gold ring, tested with a magnet, is stood on edge under an upturned
glass. It begins to turn, stops on command, reverses.
*Method:* B1. A three-phase stator or BLDC rotor under a thin top creates a rotating field; an
on-edge ring is a shorted turn and behaves like a squirrel-cage rotor. Speed and direction by ESC.
The glass is honest and serves to exclude threads and breath.
*BOM:* small BLDC motor with N52 pair or salvaged stator, ESC, ESP32, LiPo: $50 to $80.
*Difficulty:* medium; bench-test gap and ring alloys. *Risks:* platinum, titanium, tungsten rings
barely move, so pre-qualify ("is it silver or gold?"); rotor noise; steel cutlery nearby. *Novelty:*
high as a borrowed-object method.

**E6. Gathering (level 3).**
*Effect:* a spectator scatters a handful of their own small objects (coin, button, sugar cube, mint,
pen cap) on a tray; they slowly drift together to a point the spectator chose, then disperse.
*Method:* B3. A tray on flexures with four exciters runs a Vose-type sink field centred on a chosen
node; node position is steered by phase. No magnets, so non-metal objects move too.
*BOM:* four exciters, amp, MCU, printed flexures: $100. *Difficulty:* high (waveform tuning).
*Risks:* hum; objects that roll; liquids on the tray. *Novelty:* high.

**E7. Psychometry at two metres (level 2).**
*Effect:* while the performer is out of the room, one of six borrowed objects is held by a spectator
for twenty seconds and replaced. The performer returns, never approaches the table, and names it; then
names the order in which three were handled.
*Method:* A5. A thermal array hidden behind a black polyethylene window in a speaker, lamp or case
watches the table; warmest object, and for order, the cooling curves. A table load-cell log (pick-up
order by weight) backs it up.
*BOM:* MLX90640-class array or thermal dongle, ESP32: $60 to $250. *Difficulty:* low-medium.
*Risks:* bright lamps, hot drinks, shiny metal. *Novelty:* medium (thermal cameras are an obvious
idea, but a covert redundant heat-plus-weight log is not sold).

**E8. Serial number, never touched (level 2).**
*Effect:* a spectator takes a note from their wallet, glances at it, folds it; the performer writes
the serial.
*Method:* A4. A 4K camera in the performer's glasses frame, a pen pot or the venue ceiling OCRs the
serial during the "check it is genuine" beat. The same note is re-found among others later by serial
or fibre fingerprint, allowing a signed-note-free "your note in the lemon" verification.
*BOM:* camera, phone app, earpiece: $80 to $200. *Difficulty:* low. *Risks:* angle and focus.
*Novelty:* low-medium (camera peeks are known); the fingerprint follow-up is new.

**E9. Writing on their receipt (level 3).**
*Effect:* a spectator finds any shop receipt in their wallet and signs it. The performer rubs it once
against the table; the spectator's thought-of word is now printed across the back of the printed
area in the same grey-black as the till's own printing.
*Method:* B7. Flush print-head line in the pad, optical-flow sensor, MCU with the word entered by a
confederate device or prior force.
*BOM:* 58 mm thermal mechanism (strip for its head), mouse sensor, boost supply: $40. *Difficulty:*
medium-high (pressure and flatness). *Risks:* some receipts are not thermal or are coated on one side
only; heat-faded old receipts. *Novelty:* high.

**E10. The paper note that obeys (level 2).**
*Effect:* a borrowed US note is tented over a toothpick held in a cork; it turns to point at the
selected card or person.
*Method:* B2. A servo-swung magnet under the table (or in a sleeve) pulls the iron-oxide ink; the
audience does not consider paper magnetic, and the note is theirs. Works with euro cents and UK
coppers balanced on a needle as well.
*BOM:* servo, magnet, MCU: $25. *Difficulty:* low. *Risks:* draughts; non-US notes may not respond.
*Novelty:* low-medium (the science demo is known, the routine use is rare).

**E11. Condensation message on their own glass (level 2).**
*Effect:* the spectator's cold drink fogs, and a symbol they merely thought of stands out clear in
the fog, then fades.
*Method:* B8 after a force: the symbol is drawn on the dry glass with a fingertip or a surfactant
stylus while handing it over; pouring the cold drink develops it. Pointer to agent 17 for better
invisible treatments.
*BOM:* none to $5. *Difficulty:* low. *Risks:* humidity too low, glass too warm. *Novelty:* medium.

**E12. Which cup, which pocket (level 2).**
*Effect:* Russian-roulette format with the spectator's own phone or earbud case hidden under one of
five opaque cups (or water poured into one of five mugs) while the performer is away.
*Method:* A7 magnet sensing for the phone or case; A6 capacitive or load-cell sensing for water.
Nothing is added to any object.
*BOM:* magnetometer array or FDC1004 with electrodes under a mat: $30. *Difficulty:* low.
*Novelty:* medium (the object needs no magnet because it already has one).

## 5. Dead ends and overhyped items

- **Diamagnetic or paramagnetic forces on water, fruit, wood, pencil lead.** Real, but micronewtons;
  only visible on floating or thread-hung objects with a large magnet within a centimetre. A
  spectator will see the magnet before the grape moves.
- **Acoustic levitation or radiation-force pushing of borrowed objects.** Works on millimetre-scale
  foam beads, not on coins, rings or cards; and it reads as a science demo (agent 9).
- **Web-page sensor tricks on the spectator's phone.** Magnetometer and NFC web APIs are Chrome on
  Android only; iOS needs permission prompts for motion data. Half the audience is excluded and the
  effect is on a screen.
- **RSSI "which pocket" from BLE.** Body shadowing and multipath swamp it; address randomisation
  breaks tracking between observations.
- **Reading contactless cards, AirDrop names, Bluetooth names, car fobs.** Illegal or a privacy
  violation; no.
- **UV or laser changes to ordinary paper and newsprint.** Yellowing takes hours of strong UV; a
  laser strong enough to mark paper quickly is an eye and fire hazard in a room.
- **Induction heating a coin in the spectator's hand.** Works physically and is exactly why it must
  not be done: rings, watches and implants are in the same field.
- **Individual identification of cards or coins by weight.** Variation between like items is small
  compared with handling dirt and humidity; weight is good for counting and for alloy steps only.
- **Photochromic lenses as a routine.** Too few spectators have them; UV near faces is a hazard.
- **Eddy-current levitation of a coin from under a table.** Lifting needs kilowatt AC coils and
  heats the coin to burning within seconds; only drag, spin and roll are practical.

## 6. Open leads

- Scan three new decks at 1,200 dpi and measure back-offset vectors: within-deck spread, and
  whether offsets repeat by card identity across decks of the same run (A2).
- Bench-test eddy-current torque and drag versus gap for common coins and ring alloys; map which
  currencies are worth routining (B1).
- Whether same-denomination coins can be separated by precise ring frequencies, and whether an EMAT
  under a tabletop can ring a coin at 5 to 10 mm lift-off (A3).
- A minimal two-axis vibratory pad: what waveform gives visible motion with inaudible, sub-100 Hz
  drive, and how to stop ripples in drinks (B3).
- Soli-style radar counting of cards through a tabletop; verify the original paper's accuracy (A6).
- Thermal print-head geometry that prints on a hand-dragged receipt (B7).
- Field strengths at 5 to 20 cm from MagSafe phones and earbud cases, to size detection range (A7).
- Face-unlock infrared flashes and NFC polling bursts as covert "phone just woke" triggers
  (not researched; unverified).
- Audio-frequency magnetic fields inducing sound in wired earbuds or hearing-aid telecoils: likely
  possible, ethically and regulatorily doubtful (exposure limits); not researched.

## 7. Sources

Paper, print and surface fingerprints
- https://www.nature.com/articles/436475a - Buchanan et al. 2005, laser speckle fingerprint of paper, cards, packaging.
- https://ui.adsabs.harvard.edu/abs/2005Natur.436..475B/abstract - abstract record of the same.
- https://impact.ref.ac.uk/casestudies/CaseStudy.aspx?Id=11782 - Ingenia / Laser Surface Authentication spin-out case study.
- https://pixl.cs.princeton.edu/pubs/Clarkson_2009_FBP/index.php - Clarkson et al. 2009, fingerprinting blank paper with commodity scanners.
- https://ar5iv.labs.arxiv.org/html/1705.02510 - Toreini, Shahandashti, Hao 2017, transmissive texture fingerprint, 2,048 bits.
- https://www.ncl.ac.uk/press/articles/archive/2017/05/paperfingerprints - Newcastle press note, 37 x 57 mm capture box.
- https://cs.nyu.edu/~lakshmi/Lakshmi/Pubs/PaperSpeckle-Microscopic%20Fingerprinting%20of%20Paper.pdf - PaperSpeckle, CCS 2011.
- https://patents.google.com/patent/US8781153 - PaperSpeckle patent.
- https://sigport.org/documents/counterfeit-detection-using-paper-puf-and-mobile-cameras - Wong and Wu, paper PUF with mobile cameras.
- https://patents.justia.com/patent/10726256 - Wu and Wong patent, surface normals from phone photos.
- https://library.imaging.org/ei/articles/33/4/art00009 - Berchtold et al. 2021, print-plus-paper smartphone fingerprint.
- https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/8180174 - microstructure-as-identifier patent, resolution remarks.
- https://www.alitheon.com/ - commercial optical fingerprinting of unmarked items.

Cards
- https://en.wikipedia.org/wiki/Edge_sorting - edge sorting overview.
- https://www.casino.org/news/gemaco-denies-that-design-flaw-led-to-phil-iveys-edge-sorting-win/ - Gemaco's 1/32 inch tolerance statement.
- https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/11986725 - card machine patent with learned back-pattern recognition.

Coins and banknotes
- https://www.royalmint.com/stories/collect/why-are-some-uk-coins-magnetic/ - UK plated-steel dates.
- https://economy-finance.ec.europa.eu/euro/euro-coins-and-notes/euro-coins/types-euro-coins_sv - euro coin composition and magnetic centre.
- https://learn.apmex.com/learning-guide/coin-collecting/why-are-some-canadian-coins-magnetic/ - Canadian steel and nickel coins.
- https://wiki.seeedstudio.com/Grove-2_Channel_Inductive_Sensor-LDC1612/ - LDC1612 board and coin distance demo.
- https://community.element14.com/challenges-projects/design-challenges/experimenting-with-magnetic-components/b/blog/posts/smart-coin-sorter-by-inductive-sensing-01-how-coins-change-coil-impedance - inductive coin sorter build log.
- https://patents.google.com/patent/US4488116A/en - multi-parameter inductive coin sensor.
- https://st.llnl.gov/sites/default/files/inline-files/Mechanical_Waves_Sound_TechReport_1.pdf - LLNL report, coin resonances with a phone.
- https://arxiv.org/abs/2604.27803 - 2026 preprint, acoustic authentication of bullion coins.
- https://heritagesciencejournal.springeropen.com/articles/10.1186/s40494-023-00891-x - acoustic ID of ancient coins with deep learning.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC9740311/ - EMAT system for coin classification.
- https://patents.google.com/patent/US9721415 - magnetoresistive head for banknote detection.
- https://uwaterloo.ca/chem13-news-magazine/node/123 - chemistry of US currency magnetic ink.
- https://instructional-resources.physics.uiowa.edu/demos/5g1018-money-and-magnets - US note attracted to NdFeB magnet.
- https://stevespangler.com/experiments/magnetic-money/ - folded-bill magnet demo.

Side channels
- https://nmsl.kaist.ac.kr/projects/knocker - Knocker, object ID from a knock.
- https://www.medien.ifi.lmu.de/pubdb/publications/pub/abdelrahman2017chi/abdelrahman2017chi.pdf - thermal attacks on touchscreens, CHI 2017.
- https://arxiv.org/abs/1806.10189 - Thermanator, thermal residue on keyboards.
- https://ti.com/lit/pdf/snoa928 - TI capacitive proximity sensing note.
- https://ti.com/lit/pdf/sszta60 - TI note on capacitive touch through wood.
- https://forum.arduino.cc/t/capacitive-sensor-through-30mm-of-wood/640578 - hobby experience through thick wood.
- https://research-portal.st-andrews.ac.uk/en/publications/radarcat-radar-categorization-for-input-amp-interaction/ - RadarCat.
- https://sens.epfl.ch/documents/slides/mobisys2018liquid.pdf - LiquID, UWB liquid identification.
- https://arxiv.org/abs/2511.02694 - DropleX, liquid sensing on capacitive touchscreens.

Spectators' devices
- https://www.petsymposium.org/popets/2019/popets-2019-0036.pdf - Apple Continuity BLE leakage.
- https://arxiv.org/abs/1904.10600 - companion preprint on Continuity tracking.
- https://developer.mozilla.org/en-US/docs/Web/API/Magnetometer - Magnetometer API and permissions.
- https://caniuse.com/mdn-api_magnetometer - browser support table.
- https://developer.chrome.com/docs/capabilities/nfc - Web NFC on Chrome for Android.
- https://caniuse.com/webnfc - Web NFC support table.
- https://vanishingincmagic.com/close-up-magic/sixth-sense-3 - Sixth Sense 3 product page.
- https://www.vanishingincmagic.com/close-up-magic/espionage-iarvel - ESPionage product page.

Forces on unmodified objects
- https://www.nature.com/articles/s41586-021-03966-6 - Pham et al. 2021, magnetic manipulation of conductive non-magnetic objects.
- https://mmrobotics.mech.utah.edu/wp-content/uploads/2024/06/Pham_Nature2021_wSI.pdf - same with supplement.
- https://communities.springernature.com/posts/magnetic-manipulation-of-non-magnetic-objects-our-solution-to-a-seemingly-paradoxical-problem - authors' plain-language account.
- https://www.instructables.com/Never-Ending-Eddy-Current-Spinning-Top/ - hidden rotor driving a copper top.
- https://web.physics.ucsb.edu/~lecturedemonstrations/Composer/Pages/72.39.html - eddy-current rotation demo.
- https://lecdem.physics.umd.edu/k/k2/2174-k2-49.html - aluminium plate on a magnetic stirrer.
- https://www.kjmagnetics.com/blog/eddy-currents - eddy-current basics with magnets.
- https://www.kjmagnetics.com/blog/diy-induction-stove - heating by spinning magnets.
- https://people.eecs.berkeley.edu/~jfc/dreznik/UPM2000/ - Universal Planar Manipulator.
- https://people.eecs.berkeley.edu/~jfc/dreznik/Pubs/wafr98.pdf - Reznik and Canny, WAFR 1998.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC5023966 - Zhou et al. 2016, multiple objects on a Chladni plate.
- https://www.asiaresearchnews.com/node/21622 - squeeze-film levitation transport device.
- https://www.mdpi.com/1996-1073/14/9/2517 - electroadhesive attraction of paper.
- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5455829/ - electroadhesion force versus voltage.
- https://instructional-resources.physics.uiowa.edu/demos/5a4040-electrostatic-deflection-water-stream - water-stream deflection.
- https://www.physics.purdue.edu/demos/display_page.php?item=2C-14 - vortex cannon range.
- https://www.open-electronics.org/?p=37437 - 1,000 W ZVS induction heater build.
- https://www.zeiss.com/vision-care/en/need-new-lenses/photofusion-x.html - photochromic activation time.
- https://www.allaboutvision.com/eyewear/eyeglasses/lenses/photochromic - photochromic lens behaviour.
- https://arxiv.org/pdf/2110.00691 - breath-figure physics.
- https://www.nature.com/articles/111743a0.pdf - 1923 letter on breath figures and flame-cleaned tracks.
