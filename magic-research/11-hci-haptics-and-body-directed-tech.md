# 11. HCI, haptics and body-directed technology as sources of magic methods (2015 to 2026)

Scope: research from CHI, UIST, TEI, IEEE Haptics and SIGGRAPH Emerging Technologies that acts on a
person's body and senses, or that makes everyday objects move and change, judged as sources of
magic methods. The report follows the original brief. Section 3 ("Capability primitives") and
the level tags in section 4 were written in response to a mid-project course correction that was
later withdrawn; they are kept as extra material. The tags mean: level 1, the phenomenon is the
effect; level 2, a hidden input to a traditional method; level 3, a new method structure.

**Research limits, stated up front.** The shared web-search budget ran out after about ten of my
queries, so most checking was done by opening primary pages directly (lab pages, arXiv, GitHub,
datasheets, author PDFs read with `pdftotext`, Semantic Scholar records by DOI). Several
publisher and shop pages refused the fetch (MDPI, PNAS, Disney's REVEL page, DuoSkin, Tristate,
Yigal Mesika's site). Anything I could not open or see in a search result is marked
**(unverified)**. Prices are as of late 2026 unless a date is given.

---

## 1. Summary

- **The strongest transfer in this slice is the private channel, and the cheapest version is not
  ultrasonic.** A $9 bone-conduction transducer under a table sends audio through a person's
  elbows when they block their own ears (Adafruit's own product page describes the elbow-bone
  route). The act of "proving you cannot hear" becomes the listening method.
- **Parametric (ultrasonic) directional speakers are now a $50 to $150 hobby build** (a 95-element
  open design is on GitHub), but cheap ones sound thin, leak by reflection in small rooms, and run
  the ultrasound carrier well above the 110 dB occupational guideline. They are a parlor tool for
  short bursts, not a close-up tool.
- **Mid-air ultrasonic touch is real but weak and fussy.** A 16x16 array gives an 8.6 mm pressure
  point over roughly 5 to 70 cm in a ±30° cone. It needs bare palm skin, clothing absorbs it, it
  buzzes audibly, and the focus sits around 145 to 155 dB. A loudspeaker-driven air-vortex cannon
  gives a clearer "breath" at 1 m for a tenth of the cost and has a perfect disguise (a ported
  speaker).
- **Electrical muscle stimulation cannot secretly choose for a spectator.** The agency results are
  specific: stimulation 160 ms after a cue speeds a reaction by 80 ms and still feels self-caused,
  but only for a movement the person was already about to make. Fired earlier, people say "it
  moves before I do". EMS is an overt, consent-based "puppet" effect, not a covert force.
- **Body steering without electrodes on a limb exists**: galvanic vestibular stimulation (1 mA
  behind the ears moved untrained standers about 4 cm toward the anode), the hanger reflex (skin
  shear on the head, waist or wrist), and 80 Hz tendon vibration (illusory arm movement in 12 of
  16 people, eyes closed). All need a worn device and informed consent.
- **Held-object feel is controllable without changing true mass**: moving an internal weight
  changes perceived heft and length (Shifty, Transcalibur); asymmetric vibration produces a felt
  pull (Traxion, Grabity). A box that weighs the same on a scale can be made to "feel heavier" on
  demand. This turns spectator examination into a channel the performer controls.
- **Chemistry beats electronics for skin and tongue.** 10% menthol feels cold within about 10 s;
  capsaicin warmth builds over minutes (a usable delay); miraculin turns sour to sweet for up to
  30 minutes; atomised eucalyptol makes inhaled air feel colder with no cooling hardware. None of
  it may be applied covertly.
- **Flat PCB coil arrays are a general secret mover.** Reactile's 4-layer boards (10 mm grid,
  about $80 per 16x40 cm board) move small magnets silently with no moving parts. Built into a
  close-up pad this replaces threads, reels and under-table gantries for small objects.
- **On-skin and battery-free output is mature at craft level**: sub-35 µm electro-tactile tattoos,
  silent shape-memory "Springlets" skin stickers, and NFC-powered e-ink that holds its image with
  no battery. These are mainly performer-cueing and "printed mark that changes" primitives.
- **Prior use in magic is thin.** The classic precedents are Robert-Houdin's Light and Heavy Chest
  (the 1856 Algeria version added an electric shock through the handle) and sleight-based "PK
  touches".
  I found no documented performing use of phased-array haptics, coil-array pads, or chemical
  taste modulators as method; parametric speakers have long been joked about for "making someone
  hear voices" but I found no marketed magic product (search was limited).

---

## 2. Catalog

### A. Touch and force delivered through the air

**A1. Ultrasonic phased-array mid-air haptics.**
Hundreds of 40 kHz transducers are phased so the waves add at one point; acoustic radiation
pressure there is modulated at 1 to 500 Hz so skin receptors feel it. The Ultrahaptics STRATOS
Explore datasheet gives: 256 Murata transducers (16x16), 242 x 207 x 34 mm, 0.7 kg, 24 V 3.75 A,
pressure point "as little as 8.6 mm", interaction zone about 50 to 700 mm in a ±30° cone. It
ships with five cover materials, three of them acoustic fabric, so hiding an array behind speaker
cloth is vendor-supported. Force at the focus is small: Hoshi et al. 2010 reported on the order
of 16 mN from a 324-element array (number from memory, unverified). What a naive person feels on
the palm: a faint breeze, tingle or buzz, clearly located, not a "poke". It is felt best on
glabrous skin (palm, fingertips), poorly on hairy skin, and the University of Tokyo glove work
shows cotton mesh absorbs the beam (it becomes heat instead), so it does not work through
clothing. The modulation is audible as a hum or buzz near the array.
- References: Carter et al., "UltraHaptics", UIST 2013 (https://doi.org/10.1145/2501988.2502018);
  Hoshi et al., IEEE ToH 2010 (https://doi.org/10.1109/TOH.2010.4); Rakkolainen et al. survey,
  IEEE ToH 2020 (https://doi.org/10.1109/TOH.2020.3018754); Fleig retrospective, arXiv 2512.07613;
  STRATOS datasheet (SparkFun PDF).
- Open hardware: Ultraino (Marzo, Corkett, Drinkwater 2018; 64-channel Arduino Mega driver,
  https://github.com/asiermarzo/Ultraino); SonicSurface (UpnaLab, 256 emitters, FPGA, 200 Hz
  haptic mode, levitation and directional audio from the same board; Instructables guide and
  https://github.com/upnalab/SonicSurface); OpenMPD (about 10,000 field updates per second,
  https://github.com/RMResearch/OpenMPD); a hobby 16x16 design on Hackaday.io aimed at "under
  $250" but stalled on driver overheating.
- Accessibility: hobbyist-buildable but a serious project (256 soldered transducers, FPGA).
  Roughly $200 to $400 in parts for a 16x16 (my estimate from transducer and board prices, not a
  quoted figure). Commercial kits were sold through Arrow and Mouser; current price not found.
- Safety: focal levels above 145 dB are needed for a perceptible touch (Hoshi, Springer 2022), and
  Leighton lists haptic devices at about 155 dB at 20 cm, against a consensus occupational limit
  of 110 dB for 22.4 to 56.2 kHz. Never aim at the head or ears; palm only; brief exposure;
  children and pets hear and feel more. ICNIRP is revisiting its 1984 limits.
- Magic relevance: level 1 as "invisible touch". More useful as a hidden input: a 2 to 10 mN
  nudge can tip a balanced card, move smoke, flutter tissue or disturb a flame from 20 to 40 cm
  inside a prop that is visibly sealed against air currents only if the cover is acoustically
  transparent. Too-perfect risk is low because nobody suspects sound, but the hum gives it away
  in a quiet room.
- Prior magic use: none found. The sleight-based "PK touches" plot (Banachek) is the benchmark
  it would have to beat (unverified attribution, from memory).

**A2. Thermal sensation from airborne ultrasound.**
Shinoda's lab heats a glove or bare skin with a strong focused field (palm warmed 5.4 °C in 5.0 s
in Iwabuchi et al. 2024) and cools skin by vaporising a fine mist at the focus (Nakajima et al.,
IEEE ToH 2021). Lab-only power levels; of interest as a non-contact "this spot on your hand is
getting warm". References: arXiv 2411.05108; arXiv 2002.02635.

**A3. Air vortex rings and jets (AIREAL and descendants).**
A loudspeaker pushes a slug of air through an aperture and forms a vortex ring that holds
together over a metre. AIREAL (Sodhi, Poupyrev, Glisson, Israr, SIGGRAPH 2013) used five 2-inch
speakers and a 3D-printed pan-tilt nozzle: 75° field of view, 8.5 cm resolution at 1 m; press
reports give useful accuracy to about 1.5 m and roughly 150 ms latency for the larger unit. A
naive person feels a soft puff or tap, on any skin, through hair and thin clothing.
- Accessibility: easy, $20 to $60 (woofer, class-D amp, printed nozzle, two servos).
- Magic relevance: the capability is "apply about a breath's worth of force to a 5 to 10 cm
  patch at 1 m, silently enough to hide under speech, from an object that already has a hole in
  it". A ported bookshelf speaker or a subwoofer is a vortex cannon by construction. Uses: a
  touch on the neck in a séance, a candle put out at a distance, a chime or a house of cards
  disturbed, smoke pushed. Replaces reaching rods, threads and confederates.
- Limits: the ring travels at a few m/s, so timing lags by 0.2 to 0.5 s; aim drifts in
  draughts; a low "thup" is audible.

**A4. Pointers.** Laser-induced thermoelastic touch and electrostatic "hair-raising" at a
distance exist in the haptics literature (unverified, not checked) and are lab-only or
high-voltage. Not recommended.

### B. Moving or steering a person's body

**B1. Electrical muscle stimulation (EMS).**
Surface electrodes over a muscle, pulses of roughly 100 Hz and 150 to 200 µs, contract it.
Affordance++ (Lopes, Jonell, Baudisch, CHI 2015) used a medically compliant stimulator limited to
100 mA, calibrated per user and per channel (2 to 5 minutes per pose), to make a hand shake a
spray can or pull away from a hot cup. Later work: Muscle-plotter (UIST 2016), back-of-hand
electrodes for finer finger control (CHI 2021), neck stimulation that turns the head (CHI 2022),
and in 2024 a smartwatch band with 12 electrodes that produced thumb extension, index extension
and flexion and middle-finger flexion at no more than 12 to 15 mA, calibrated by the wearer.
Magnetic muscle stimulation (UIST 2023) works over clothing with less tingling but needs a large
coil and stimulator.
- Agency: "Preemptive Action" (Kasahara, Nishida, Lopes, CHI 2019) found that EMS delivered 160 ms
  after a visual cue made reactions 80 ms faster while people still felt they had moved
  themselves; with larger lead times agency collapses. Follow-ups: My(o) Action (CHI 2026,
  EMG-triggered) and Primed Action (UIST 2025, sub-threshold brain stimulation).
- Hardware: openEMSstim (Arduino Nano board that only attenuates the output of an approved
  commercial stimulator; https://github.com/PedroLopes/openEMSstim); consumer TENS/EMS units are
  typically $25 to $60 (marketplace prices, not checked).
- What the volunteer feels: strong tingling under the pads, then the limb moving "by itself".
  Works on nearly everyone after calibration; drifts with fatigue and pad movement.
- Safety and consent: never across the chest, on the front of the neck, on the head or over
  broken skin; not for people with pacemakers or ICDs, epilepsy, or during pregnancy over the
  abdomen. Use only an unmodified certified stimulator, pre-gelled electrodes, written consent,
  and let the volunteer set their own maximum. Never covert.
- Magic relevance: an overt "my hand is being moved" piece with a briefed volunteer (control,
  spectator failure). The visible pads are the obstacle; a wristband with an innocent reason
  ("pulse monitor") is now technically possible but ethically requires that the wearer knows it
  stimulates. As a covert forcing tool it fails: it sets timing only for a movement already
  under way.

**B2. Galvanic vestibular stimulation (GVS).**
A small direct current between electrodes on the mastoids biases the balance organs; the person
sways or veers toward the anode. Yang et al. 2015: thresholds 0.1 to 0.6 mA; at 1.0 mA
non-pilots swayed a mean 42 to 45 mm sideways (pilots 7 mm); electrodes 2 cm² Ag/AgCl. Research
stimulators span ±5 mA. Four-pole layouts add forward/back and yaw (Aoyama et al., Sci. Rep.
2015, unverified details). Lopes' group used GVS in 2025 to hide VR hand redirection.
- Accessibility: constant-current, isolated, hard-limited stimulators are medical or research
  devices. A hobby build is an electrical hazard on the head and I do not recommend one.
- Experience: a real, painless pull to one side; tingling or itching under the electrodes;
  possible nausea, metallic taste or flashes at higher currents (commonly reported; not
  confirmed in the pages I opened).
- Magic relevance: steer a blindfolded, consenting volunteer who honestly reports "something
  pulled me". Electrodes fit inside over-ear "isolation" headphones. Strong but ethically heavy.

**B3. Hanger reflex and skin-shear steering.**
Light pressure with shear on the temple makes the head turn (a wire coat-hanger does it).
Kajimoto's group named and studied it; Sato et al. built a head-rotation interface in 2009; the
same shear principle works at the waist (belt devices that steer walking), wrist, elbow and
shoulder, and vibration strengthens it. Susceptibility varies with head shape. No current,
no chemicals. Cost: a printed band and two hobby servos or air bladders. Source: Wikipedia
"Hanger reflex" and references there.

**B4. Tendon vibration (illusory movement).**
About 80 Hz vibration on a relaxed muscle's tendon makes the brain read the muscle as
stretching, so the limb seems to move (biceps tendon: elbow seems to extend; holding the nose at
the same time gives the "Pinocchio" illusion). Ferrari, Clemente and Cipriani 2018: 80 Hz, 0.2
to 0.8 mm amplitude, 1 to 4 N press; 12 of 16 recruits felt it at every site, 3 immediately and
the rest after 3 to 5 two-second bursts, 3 felt the opposite direction; participants were
blindfolded with the arm supported. A $15 massager or a linear resonant actuator driven at 80 Hz
is enough. The audience sees a still arm while the volunteer swears it moved: a reverse dual
reality. Classic illusion detail belongs to agent 4.

### C. Thin channels on the skin (mostly for cueing the performer)

**C1. Electro-tactile tattoos and rings.** Tacttoo (Withana, Groeger, Steimle, UIST 2018) is a
temporary-tattoo electrode layer under 35 µm thick that delivers localised tingles while leaving
normal touch intact, with a DIY screen-printing recipe and "private notifications" as a stated
use. Lopes' group has put electro-tactile output on the back of the hand (CHI 2023), the lips
(LipIO), the feet (FeetThrough) and a ring (RingIO, UIST 2026).

**C2. Springlets** (Hamdan et al., CHI 2019): shape-memory-alloy springs in a skin sticker give
six silent primitives (pinch, directional stretch, press, pull, drag, expand), usable even on the
neck. No motor noise, which is the weakness of every vibrating "thumper".

**C3. Thermal cues.** A 15 mm Peltier element ($3 to $5 typical) gives a warm or cold spot in
about a second; alternating 20 °C and 40 °C bars feel burning hot (thermal grill, Thunberg 1896)
without any harmful temperature. Useful as a silent yes/no channel or as a held object that
"burns".

**C4. Chemical haptics** (Lu, Liu, Brooks, Lopes, UIST 2021): topical menthol 10% (cool,
sometimes within 10 s, fades in minutes once removed), capsaicin 0.025% on the face (warm, builds
roughly linearly over minutes, lingers), lidocaine 5% (numb, "my skin feels like rubber"),
cinnamaldehyde 5% (sting), sanshool (tingle). All are over-the-counter ingredients. The
capability is a sensation with a built-in delay and no device on the body. Allergy and eye
contact are real risks; participants were screened.

### D. How a held object feels

**D1. Weight shifting.** Shifty (Zenner and Krüger, IEEE TVCG 2017) slides a mass along a rod
inside a handheld prop so it feels heavier, longer or thicker; Transcalibur (Shigeyama et al.,
CHI 2019) moves two masses in a plane and uses a perception model to render shapes. True mass
never changes; the wrist torque does.

**D2. Asymmetric vibration ("pulling" illusion).** A voice-coil mass accelerated fast one way
and slowly back is felt as a steady pull. Traxion (Rekimoto, UIST 2013) and NTT's Buru-Navi
(unverified) are thumb-sized; Grabity (Choi et al., UIST 2017) uses two voice coils to render
weight during grasp. Felt force is small (tens of grams-equivalent, unverified) but directional.
Parts: a $10 to $20 linear voice-coil haptic actuator and a small class-D amp.

**D3. Gyroscopic and propulsive force.** A spinning flywheel inside a prop resists being tipped
(a 100 g, 60 mm disc at 10,000 rpm gives about 0.05 N·m·s of angular momentum, so a 3 rad/s tip
is met by roughly 0.15 N·m of sideways torque; my calculation). Thor's Hammer (Heo et al., CHI
2018) and Aero-plane (Je et al., UIST 2019; two ducted fans, up to 14 N within 0.3 s) use
propellers. Both are loud; the gyroscope at least can be spun up beforehand and coast.

**D4. Electrovibration and reverse electrovibration.** A fingertip sliding over a thin insulator
on top of an electrode driven at about 100 V AC feels rubbery or sticky (Mallinckrodt 1953;
TeslaTouch, Bau et al., UIST 2010). REVEL (Bau and Poupyrev, SIGGRAPH 2012) injects the signal
into the person instead, so any insulated grounded conductor they stroke changes feel (details
unverified; Disney page 404). The sensation exists only while the finger moves and only that
person feels it. Currents are microamp-level by design but this is still mains-range voltage on a
person: current-limit in hardware, exclude pacemaker wearers.

**D5. Temperature and stiffness of held objects.** Peltier-backed surfaces (ThermalGrasp, IEEE VR
2024, keeps the palm free) and jamming or fluidic stiffness changes are well covered in the
literature; component detail belongs to agent 7.

### E. Private and directed sound

**E1. Parametric (ultrasonic) speakers.** An array of 40 kHz emitters carries amplitude-modulated
audio; air's nonlinearity demodulates it along the beam, so sound is heard in a narrow column or
appears to come from the surface the beam hits. Wikipedia's summary: the carrier must exceed
about 100 dB SPL at 1 m; plain AM distorts heavily; bass is absent; OSHA's ceiling is 145 dB
and a UK recommendation for the public is 100 dB. Commercial units: Holosonics Audio Spotlight
(from 2000), Focusonics Model A €1,300 and Model B €950 (both listed sold out; the maker
advertises "virtual source" reflection off a surface), Akoustic Arts A Junior $600 with a beam
about 65 cm wide at up to 70 dB and A Original $1,000 at up to 90 dB (2016 figures), Soundlazer
kits $249 to $399 (all out of stock, page dated 2022), an assembled 48-emitter eBay kit at about
$133. Hobby designs: Orange_Murker's 95 x 16 mm array with an STM32 and one H-bridge (open
source; "MOSFETs get really hot"), and a 555-based hexagonal array whose audio was "not
wonderful but still recognizable" (Hackaday, 2025 and 2026).
- What one listener hears: a thin, tinny voice that seems to be at their own head, or at the
  wall or object behind them. Neighbours within roughly half a metre of the beam, or anyone in
  the reflection path, hear a quieter version; in a small hard room reflections spoil privacy.
- Safety: same airborne-ultrasound caveats as A1. Keep bursts short, mount overhead or bounce
  off an object so no ear sits in the direct beam at close range.

**E2. Focused audible spots.** Holographic Whisper (Ochiai, Hoshi, Suzuki, CHI 2017) focuses a
phased array so the audible sound originates at a point in mid-air. "Audible enclaves" with
self-bending ultrasound beams (PNAS 2025, unverified; page refused) localise it further. Lab
builds, but SonicSurface-class hardware can attempt the first.

**E3. Bone and structure conduction.** A surface transducer has no cone and plays through
whatever it is pressed against. Adafruit's 8 ohm 1 W unit is 14 x 21.5 mm, 9.6 g, $8.95, 300 Hz
to 19 kHz depending on the surface; the product page describes pressing it to the jaw, turning a
table or wall into a speaker, and pressing it to the elbow bone with a finger in the ear.
Lollipop Star sells $9.99 lollipops that play a song through the teeth: "only the person biting
hears it". The capability: a voice channel that exists only for a person in physical contact
with an ordinary object, and that gets louder when they block their ears (occlusion effect).

**E4. Pointers.** Beamforming with arrays of ordinary speakers steers audible sound without
ultrasound, but at speech frequencies a tight beam needs an array a metre or more across, so it
suits installations, not props (general acoustics, not checked against a source). The microwave
auditory (Frey) effect needs pulsed radar-class peak power and is unsafe. Ultrasonic messages to
microphones belong to agent 10.

**E5. Prior magic use of the electrical and audio channels.** Yigal Mesika's Electric Touch is a
body-worn static generator that lets the performer give a spark or tingle by touch (product page
not reachable; unverified, and such devices carry pacemaker warnings). Radio "thumpers" and
earpieces are the standard cueing tools. I found no dealer item built on parametric audio or
bone conduction, though the search was cut short.

### F. Smell, taste and breath

**F1. Scent on cue.** A vibrating-mesh piezo atomiser ($2 to $5 typical) and a micro-pump release
a scent within a second. Brooks, Nagels and Lopes (CHI 2020) atomised eucalyptol every 6 to 12 s
to make inhaled air feel cold and a capsaicin tincture to make it feel warm, from a nose-worn
device on a 1200 mAh cell: a temperature illusion with no heating or cooling. Smell & Paste (CHI
2023) prototypes with scratch-and-sniff stickers, the zero-electronics version.

**F2. Electric taste.** Miyashita's lab and Kirin sell the Electric Salt Spoon (19,800 yen, CR2
cell, 200 units at launch in May 2024): a weak current from the tip makes low-sodium food taste
about 1.5 times saltier. The effect exists only while the utensil touches the tongue.

**F3. Chemical taste modulators.** Taste Retargeting (Brooks, Amin, Lopes, UIST 2023) used
droplets of miraculin (sour becomes sweet), gymnemic acid (sweetness removed), lactisole (sweet
and umami suppressed, with a "sweet water" after-effect), zinc sulfate (sweet and bitter
suppressed) and clofibric acid. Miraculin lasts up to about 30 minutes; gymnema tea or lozenges
make sugar taste like sand for a similar time (duration from memory, unverified). Food-grade,
cheap, and already sold as a "party trick".

### G. Everyday objects that move or change

**G1. PCB coil arrays.** Reactile (Suzuki, Kato, Gross, Yeh, CHI 2018): 3,200 printed coils
(15 mm, 15 turns, 4-layer, 10 mm pitch) over 80 x 40 cm, five boards at about $80 each including
parts, moving many small magnets independently. FluxPaper (Ogata and Fukumoto, CHI 2015) puts a
thin magnetic layer in paper so sheets move, stand and self-align over coils. Older: Actuated
Workbench and Pico from MIT (unverified).

**G2. Small robots.** Zooids (Le Goc et al., UIST 2016; 26 mm, open source, unverified size),
Sony toio cubes (two motors, absolute position from a printed mat, BLE), ShapeBots, HERMITS,
and Rovables (MIT; climb unmodified clothing on magnetic rollers, 45 minutes per charge, carry
1.5 N).

**G3. Shape-changing sheets and print.** Thermorph (An et al., CHI 2018): flat FDM prints that
fold themselves into 3D forms with heat, up to 70 faces, on a consumer printer. Printed Paper
Actuator, aeroMorph, bioLogic, PneUI and SMA-animated paper (unverified, MIT and CMU pages not
opened) give paper and fabric that curl, inflate or flap. Component detail: agent 7.

**G4. Pin displays** (inFORM, TRANSFORM; unverified) move passive objects from below but are
large and loud: installation only.

**G5. Droplets.** Programmable Droplets (Umapathi et al., MIT): electrowetting on ordinary PCBs
moves and merges water drops under 100 V. A drop that walks across a "plain" surface.

**G6. On-skin, on-nail and battery-free output.** DuoSkin (Kao et al., ISWC 2016, unverified)
makes gold-leaf temporary tattoos with thermochromic patches; AlterWear (Dierk, Nicholas, Paulos,
CHI 2018) drives bistable e-ink from NFC with no battery, so the image persists unpowered;
Photo-Chromeleon (Jin et al., UIST 2019) recolours a photochromic CMY coating with a projector.
Skintillates, NailO and HairIO (SMA-braided hair that moves and changes colour) are in the same
family (unverified, not opened). For the classic "mark appears on the spectator's skin" plot
these are a poor fit: a thermochromic tattoo has to be applied beforehand, wired or heated, and
the dyes are not cosmetic-grade. The realistic route is a changing mark on something the
spectator wears with an innocent reason, such as an event wristband, a sticker or a hand-stamp
substitute, using body-heat thermochromic or UV-developed photochromic ink (materials: agent 7).

**G7. Pointers.** Mid-air and tabletop levitation interfaces (ZeroN, Pixie Dust, LeviPath,
Floating Charts) belong to agent 9. Ferrofluid and liquid-metal displays read as "science demo"
and need bulky electromagnets. Self-actuating textiles, plant interfaces and food that changes
shape in water (pasta that folds as it cooks) are real HCI lines I did not have budget to check;
shape-changing food is the one I would look at first, as a production or transformation that
happens in the spectator's own bowl.

### H. HCI research about magic, agency and redirection

- Marshall, Benford and Pridmore, "Deception and magic in collaborative interaction" (CHI 2010)
  is the reference HCI paper on borrowing conjuring structure.
- Sense-of-agency work (Preemptive Action; "Whose touch is this?", TOCHI 2021; Veillette et al.,
  J. Neurosci. 2023) gives the usable rule: an externally caused movement is owned if it is
  congruent with an intention and arrives within tens of milliseconds of when the person would
  have moved.
- Haptic Retargeting (Azmandian et al., CHI 2016) and redirected touching need a headset: sight
  is replaced, so a hand can be steered several centimetres off. In real space the equivalents
  are darkness, blindfolds and tendon vibration. GVS raises the detection threshold further
  (Katori et al., UIST 2025).
- Pseudo-haptics does transfer without a headset: changing what a person sees while they press
  or lift changes how soft or heavy the object feels, and projection onto a real object has been
  used to make it feel softer (SoftAR, Punpongsanon et al. 2015, unverified). A projector or a
  hidden light change during the spectator's test is therefore a way to bias their report.
- "Wizard of Oz" prototyping (a hidden human does what the system claims to do) is conjuring's
  hidden-assistant method under another name; "Magic Finger" (UIST 2012, unverified) is a
  fingertip sensor and belongs to agent 10.

---

## 3. Capability primitives

1. *Now possible:* speak to one seated person through their forearms while their own fingers block their ears. *Because:* $9 surface transducer plus 3 W amp under a table. *Before:* earpiece or stooge. *Primitives:* tell, prove ordinariness.
2. *Now possible:* put a voice in a 0.5 to 1 m wide column at 2 to 5 m, or make it seem to come from a wall or skull. *Because:* 50 to 100 element 40 kHz parametric array, $50 to $150. *Before:* ventriloquism, hidden speakers. *Primitives:* tell, conceal.
3. *Now possible:* audio that only the person biting or holding an object hears. *Because:* bone conduction (lollipop, glass, pen). *Before:* impossible without an earpiece. *Primitives:* tell.
4. *Now possible:* deliver a breath-strength puff to a 5 to 10 cm patch at 1 to 1.5 m with about 0.3 s delay. *Because:* loudspeaker vortex cannon, $30. *Before:* confederate, thread, reaching rod. *Primitives:* move, conceal.
5. *Now possible:* press on a palm with an 8.6 mm spot from 5 to 70 cm through speaker cloth. *Because:* 256-element phased array, $200 to $400 DIY. *Before:* not possible. *Primitives:* move (weakly), tell.
6. *Now possible:* cue the performer with six distinct silent skin gestures. *Because:* SMA Springlets stickers, about $15. *Before:* buzzing thumper motors. *Primitives:* tell.
7. *Now possible:* a 35 µm tattoo-thin tingle channel on a fingertip that survives handling props. *Because:* printed electro-tactile tattoos. *Before:* no fingertip channel. *Primitives:* tell.
8. *Now possible:* make a sealed box feel clearly heavier or lighter in the hand while a scale reads the same. *Because:* 20 to 50 g internal mass on a micro lead screw. *Before:* electromagnet under the stage, visible switch of boxes. *Primitives:* transform, prove ordinariness, control choice.
9. *Now possible:* make a held object tug in a chosen direction with no external connection. *Because:* asymmetric voice-coil vibration. *Before:* thread or magnet. *Primitives:* tell (to the holder), move.
10. *Now possible:* make one zone of a laminated sheet feel sticky to one sliding fingertip, switchable in milliseconds. *Because:* electrovibration at about 100 V, microamps. *Before:* wax or roughing fluid, fixed. *Primitives:* tell, control choice.
11. *Now possible:* a cold sensation that starts about 10 s after contact, or warmth that builds over 2 to 10 minutes. *Because:* menthol 10%, capsaicin 0.025%. *Before:* toxic "hot foil" chemistry. *Primitives:* delay, transform.
12. *Now possible:* the same food tastes different to two people, or to one person before and after, for up to 30 minutes. *Because:* miraculin, gymnemic acid, lactisole. *Before:* switch the food. *Primitives:* transform, tell (privately).
13. *Now possible:* make the air "turn cold" for people breathing it, with no cooling. *Because:* atomised eucalyptol, mW-level power. *Before:* dry ice, air conditioning. *Primitives:* transform.
14. *Now possible:* release a chosen smell within 1 s from a coin-sized battery device. *Because:* piezo mesh atomisers. *Before:* pre-scented objects. *Primitives:* tell, delay.
15. *Now possible:* slide any small magnet-bearing object anywhere on a 40 x 80 cm surface, silently, 10 mm grid, no moving parts, 2 mm thick. *Because:* 4-layer PCB coil arrays at $80 per board. *Before:* threads, under-table XY gantry. *Primitives:* move, swap, conceal.
16. *Now possible:* make a seated or standing person lean about 4 cm, or veer while walking, on command. *Because:* 1 mA GVS. *Before:* suggestion only. *Primitives:* control choice (with consent).
17. *Now possible:* turn someone's head a few degrees with no current. *Because:* hanger-reflex skin shear from a hat band. *Before:* suggestion only. *Primitives:* control choice.
18. *Now possible:* make a blindfolded person feel their arm move 20 to 40° while it stays still. *Because:* 80 Hz tendon vibration, about 75% of people. *Before:* suggestion. *Primitives:* transform (of experience).
19. *Now possible:* move a consenting volunteer's individual fingers from a watch strap at 12 mA or less. *Because:* cross-sectional wrist EMS, 12 electrodes. *Before:* forearm full of pads. *Primitives:* move.
20. *Now possible:* shave 80 ms off a person's reaction and have them own the movement. *Because:* EMS timed 160 ms after the cue. *Before:* nothing. *Primitives:* control timing (overt only).
21. *Now possible:* change a printed-looking mark with no battery in the object, and have it stay changed. *Because:* NFC-powered bistable e-ink. *Before:* switch the object. *Primitives:* transform, erase evidence.
22. *Now possible:* a flat printed sheet that folds itself into a specific 3D shape in hot water or under a heat gun. *Because:* Thermorph-style FDM prints. *Before:* spring-loaded production items. *Primitives:* transform, conceal.
23. *Now possible:* a 3 cm robot that crawls unseen inside a jacket and carries 150 g. *Because:* Rovables-style magnetic-roller robots. *Before:* pulls and reels. *Primitives:* move, swap.
24. *Now possible:* a water drop that travels across a board to a chosen spot. *Because:* PCB electrowetting below 100 V. *Before:* tilt or thread. *Primitives:* move.

---

## 4. Effect concepts

**1. "Hands over your ears" (level 3; private channel).**
*Effect:* a volunteer sits at the table, elbows on it, fingers pressed in their ears so they
"cannot be prompted". Another spectator silently chooses a card; the deaf volunteer names it.
*Method:* a surface transducer under the table top plays a whispered voice. Through wood it is a
faint murmur in the room (masked by music or patter); through the volunteer's forearm bones with
ears occluded it is clear. They are an instant stooge created at the moment of isolation, with no
pre-show. The audience's proof of fairness is the method.
*Parts:* Adafruit bone transducer $9 (two or three for coverage), 3 W class-D amp $5, ESP32 with
I2S audio $8, battery; text-to-speech or a hidden assistant. Under $50.
*Difficulty:* low. *Risks:* table leakage (test with thick tops; rubber feet reduce it); the
volunteer may blurt "I can hear a voice" unless the script makes playing along the fun option;
elbow contact must be scripted. *Novelty:* I believe high; I found no magic use of the
elbow-conduction route.

**2. "It only talks to you" (level 2).**
*Effect:* a borrowed-looking object (a shell, a tin, a doll) is held to one person's ear or
simply stared at; they hear it whisper a name the performer could not know. Nobody else hears.
*Method:* a parametric array in a lamp, picture frame or ceiling tile bounces its beam off the
object, so the virtual source is the object. Dual reality: the room sees a person reacting.
*Parts:* 95-element array and driver (open design), $60 to $150, or a used commercial unit.
*Difficulty:* medium (driver heat, aiming). *Risks:* tinny audio, reflection leakage in small
hard rooms, ultrasound exposure (overhead mounting, bursts of seconds). *Novelty:* medium.

**3. "Feel for it" (level 3; speculative).**
*Effect:* a laminated alphabet or map lies on the table. A spectator slowly drags a fingertip
across it with eyes closed and stops where it "catches": the thought-of letter or place.
*Method:* the sheet is a PCB or ITO film with zoned electrodes under a 25 to 50 µm insulating
print. Only the target zone carries the 100 to 200 V AC signal, so only there does the moving
finger feel rubbery drag. The spectator honestly reports a physical sensation the audience
cannot feel; hand the sheet out afterwards with the driver unplugged and it is inert.
*Parts:* custom 2-layer PCB with printed overlay $20 to $40, small HV boost and current limit
(series megohm resistors, under 0.5 mA available), return path via a metal table edge. Under
$80. *Difficulty:* medium to high; the insulator thickness and humidity matter. *Risks:* weak or
absent sensation for dry or very sweaty fingers; high voltage near a person demands a hardware
current limit and a pacemaker exclusion. *Novelty:* high as far as I can tell.

**4. "Which one is heavier?" (level 3; examination misleads).**
*Effect:* three identical sealed boxes; one holds a borrowed ring. A spectator hefts each and
finds the ring "by weight", correctly, every time, even after the performer shuffles them. On a
kitchen scale all three weigh the same, which makes it stranger.
*Method:* each box hides a 30 g slug on a micro lead screw along its long axis plus an IMU
(agent 10). Driving the slug to the far end raises wrist torque and the box feels heavier and
"fuller"; the performer chooses by radio which box feels loaded. An asymmetric-vibration
actuator can add a brief downward tug at pick-up.
*Parts:* per box: N20 geared motor with lead screw $6, slug, ESP32-C3 $4, 150 mAh cell, printed
shell. About $25 per box. *Difficulty:* medium. *Risks:* motor noise during the move (move
while boxes are being mixed), rattle, and people who shake instead of heft. *Novelty:* high for
magic; it is Robert-Houdin's chest with the secret moved inside the spectator's own judgement.

**5. The coil pad (level 3; a general secret mover).**
*Effect (one of many):* a signed card pushed into a face-down spread creeps out by itself; a
coin slides to the selected spot; a planchette spells.
*Method:* a Reactile-style 4-layer coil board laminated inside a close-up pad. Cards carry a
0.3 mm magnet foil dot or a 5 x 1 mm disc; coins are steel-cored. Software sequences coils at
10 mm pitch. Combine with sleight: only the gaffed card moves, everything else is examinable.
*Parts:* one or two boards at about $80 each (2018 figure), driver ICs, 12 V supply, foam and
cloth. $150 to $300. *Difficulty:* high (PCB design, heat, drive electronics). *Risks:* force
is small, cloth friction must be tuned, coils warm up, compasses and phones reveal fields.
*Novelty:* medium; moving-magnet tables exist in chess boards, but a thin solid-state pad
does not appear in magic catalogues I know of.

**6. Silent six-symbol thumper (level 2).**
*Effect:* none visible; the performer receives card identities, drawings categories or "stop
now" cues with no sound, in a quiet close-up setting.
*Method:* two Springlets-type SMA stickers on the upper arm or behind the ear, driven from a
pocket receiver: pinch, stretch-left, stretch-right, press. Two symbols encode 52 cards in about
2 s. An electro-tactile fingertip tattoo is the higher-bandwidth option.
*Parts:* 100 µm SMA wire, kinesiology tape, MOSFET driver, ESP32. About $20. *Difficulty:*
low to medium. *Risks:* SMA runs warm (limit duty), slow relaxation (about 1 s per symbol).
*Novelty:* medium; the silent, non-vibrating part is the gain.

**7. "The room goes cold" (level 2).**
*Effect:* at the moment the "presence" arrives, the people nearest the table feel the air chill
and smell earth or roses; a thermometer on the table does not change.
*Method:* two hidden mesh atomisers, one with dilute eucalyptol for the trigeminal cold illusion
and one with a scent, fired on cue; optionally the vortex cannon of A3 carries the puff to one
person. Declare in advance that the show uses scents.
*Parts:* atomiser modules $5 each, ESP32, vials. Under $30. *Difficulty:* low. *Risks:*
lingering smell on repeat shows, asthma and fragrance sensitivity. *Novelty:* medium.

**8. One lemon, two truths (level 2; dual reality by taste).**
*Effect:* two spectators bite slices of the same lemon. One winces; the other insists it is as
sweet as lemonade. Later the first tries again and now it is sweet for them too.
*Method:* miraculin tablet dissolved on the tongue a few minutes earlier, presented openly as
"a berry sweet, tell me about allergies first" without explaining its function. Gymnema does
the reverse with chocolate.
*Parts:* miracle-berry tablets, about $1 to $2 each (typical, not checked). *Difficulty:* none.
*Risks:* some people know the party trick; disclosure of ingredients is mandatory.
*Novelty:* low as a phenomenon, moderate as a structured dual-reality piece.

**9. The dowser (level 3; consent-critical).**
*Effect:* a blindfolded volunteer in isolation headphones walks the room and stops in front of
whoever hid the object, saying "I just felt pulled".
*Method:* a certified constant-current GVS unit with mastoid electrodes inside the ear cups,
steered by the performer at 1 mA or less; or, with no current at all, a waist band using the
hanger-reflex shear. The volunteer is told beforehand, privately and in writing, what the device
is and can decline.
*Parts:* commercial research or clinical GVS stimulator (hundreds of dollars and up); the
hanger-reflex belt is a $30 print-and-servo build. *Difficulty:* medium. *Risks:* nausea,
skin irritation, falls (spotter needed); do not home-build a head stimulator. *Novelty:* high.

**10. Light and Heavy, in the hand (level 2).**
*Effect:* a wand or small case passes from hand to hand; for the chosen person it refuses to
be turned over, twisting out of line as if alive.
*Method:* a pre-spun flywheel on a brushless motor inside, coasting silently for 20 to 30 s
after spin-up in the pocket; orientation of the spin axis decides which motion is resisted.
*Parts:* small outrunner and ESC $20, steel disc, cell. About $40. *Difficulty:* medium
(balance, noise). *Risks:* hum, bearing noise, heat. *Novelty:* low to medium.

**11. Breath on the neck (level 1 to 2).**
*Effect:* in dim light a sitter feels a distinct breath on the back of the neck; a candle
across the room goes out.
*Method:* vortex cannon built into a ported bookshelf speaker that is also playing the
soundtrack; pan-tilt behind the grille. *Parts:* $40. *Difficulty:* low. *Risks:* aim,
delay. *Novelty:* medium.

**12. Ultrasonic PK touch (level 1; brief).**
A phased array under a cloth-topped table presses a moving spot onto an upturned palm held 20 cm
above it. Works, but the sensation is faint, the array hums, exposure limits are exceeded at the
focus, and the build costs ten times concept 11.

Ten of twelve concepts are level 2 or 3.

---

## 5. Dead ends and overhyped items

- **Covert EMS forcing.** The agency window only covers movements the person was already making;
  anything else is felt as external. Pads tingle. Also unethical without consent.
- **Covert chemistry on a spectator's skin or in their food.** Menthol, capsaicin, lidocaine
  and taste modulators all work, but allergy, eye contact and plain consent rule out secret
  dosing. Use only with declared ingredients.
- **Ultrasonic touch through clothing or on the back.** Fabric absorbs 40 kHz; hairy skin is far
  less sensitive. Palm and fingers only.
- **Parametric speakers at close-up range or in tiled rooms.** Leakage by reflection, thin audio,
  and the carrier level make it a parlor and installation tool.
- **Microwave auditory effect, laser plasma haptics, photoacoustic "laser whisper".** Hazardous or
  lab-only.
- **Electric taste as a hidden method.** Works only while a powered utensil touches the tongue.
- **Pin displays and propeller force feedback.** Too large and loud to hide.
- **VR redirection (haptic retargeting, redirected walking).** Depends on replacing vision; only
  the blindfold and darkness versions transfer.
- **Thermochromic or electronic tattoos on a spectator as a surprise "mark on the skin".**
  Needs applied hardware and heating; dyes are not cosmetic-grade. Put the changing mark on a
  wristband or sticker instead.

## 6. Open leads

- Measure table-to-elbow conduction: leakage level in the room against intelligibility for the
  listener, by table material and thickness. This decides concept 1.
- Electrovibration through printed overlays: minimum voltage against insulator thickness, and
  whether a card-thin laminate can work (force falls with the square of thickness).
- REVEL-style body-side injection: could a performer's handshake-coupled signal make a metal
  object feel textured to one person? Needs the original paper.
- Magnetic muscle stimulation through clothing (UIST 2023): coil size, noise and cost were in a
  PDF too large to fetch.
- Waist and wrist hanger-reflex devices from Kajimoto's lab as no-current steering; effect size
  across people is not in the sources I opened.
- Holographic Whisper and PNAS "audible enclaves" on SonicSurface-class open hardware.
- Sony toio and Zooids as under-table or in-prop movers; Rovables for in-clothing loads.
- Whether any magic dealer already sells parametric or bone-conduction cueing (search budget ran
  out before I could survey dealers).

---

## 7. Sources

Opened or seen in search results:

- https://www.ultraleap.com/datasheets/STRATOS_Explore_Development_Kit_datasheet.pdf and https://cdn.sparkfun.com/assets/e/2/f/0/2/DS-16661-Ultrahaptics_STRATOS_Explore.pdf - STRATOS Explore specs (256 emitters, 8.6 mm point, 50 to 700 mm, fabric covers).
- https://www.xrtoday.com/?p=39543 - STRATOS Inspire review (seen in search results).
- https://github.com/asiermarzo/Ultraino - Ultraino open phased-array driver.
- https://research-information.bris.ac.uk/en/publications/ultraino-an-open-phased-array-system-for-narrowband-airborne-ultr/ - Ultraino paper record.
- https://www.instructables.com/SonicSurface-Phased-array-for-Levitation-Mid-air-T - SonicSurface build guide (title only retrieved).
- https://makiuto.github.io/p/sonicsurface-diy-ultrasonic-phased-array-for-levitation-haptics-and-directi.html - SonicSurface overview and links.
- https://www.mdpi.com/2076-3417/11/7/2981/htm - SonicSurface paper (seen in search; fetch refused).
- https://hackaday.io/project/159467-open-source-ultrasonic-phased-array - hobby 16x16 array, "under $250" goal, stalled.
- https://github.com/RMResearch/OpenMPD - OpenMPD engine.
- https://arxiv.org/abs/2512.07613 - Fleig, retrospective on ultrasound mid-air haptics.
- https://arxiv.org/abs/2002.02635 - Kamigaki, Suzuki, Shinoda: thermal and vibrotactile display through mesh gloves.
- https://arxiv.org/abs/2411.05108 - Iwabuchi et al.: palm warmed 5.4 °C in 5 s by airborne ultrasound.
- https://repository.dl.itc.u-tokyo.ac.jp/record/2007163/files/A38415.pdf - Nakajima thesis, mist-vaporisation cooling (search result).
- https://la.disneyresearch.com/publication/aireal-interactive-tactile-experiences-in-free-air/ - AIREAL.
- https://cacm.acm.org/news/ready-aim-puff and https://community.element14.com/technologies/robotics/b/blog/posts/disney-s-aireal-provides-haptic-feedback-allowing-users-to-feel-virtual-objects - AIREAL range and latency in press (search results).
- https://physicstoday.aip.org/features/ultrasound-in-air - Leighton, "Ultrasound in air", 2020: limits and symptoms.
- https://eprints.soton.ac.uk/444416/1/Public_Exposure_to_Airborne_Ultrasound_and_Very_High_Frequency_Sound_Timothy_G._Leighton.pdf - Leighton, public exposure (search result).
- https://link.springer.com/chapter/10.1007/978-3-031-04043-6_17 - "Ultrasound exposure in mid-air haptics" chapter, above 145 dB (search result).
- https://arpansa.gov.au/more-research-needed-airborne-ultrasound-health-effects - ICNIRP review note, 2024 (search result).
- https://lab.plopes.org/ - Lopes lab publication list (EMS, chemical haptics, smell, taste, agency, GVS).
- https://plopes.org/wp-content/uploads/papers/2015-CHI-AffordanceLopes.pdf - Affordance++.
- https://lab.plopes.org/published/2019-CHI-AgencyEMS.pdf - Preemptive Action (160 ms, 80 ms).
- https://lab.plopes.org/published/2024-UIST-WristEMS.pdf - EMS in a smartwatch band.
- https://lab.plopes.org/published/2021-UIST-ChemicalHaptics.pdf - Chemical Haptics.
- https://lab.plopes.org/published/2023-UIST-TasteRetargeting-AuthorCopy.pdf - Taste Retargeting.
- https://lab.plopes.org/published/2020-CHI-trigeminal.pdf - Trigeminal temperature illusions.
- https://lab.plopes.org/published/2023-UIST-MMS-AuthorCopy.pdf and https://lab.plopes.org/published/2022-CHI-ElectricalHeadActuation.pdf - magnetic muscle stimulation; head actuation (listed; PDFs too large to read).
- https://github.com/PedroLopes/openEMSstim - openEMSstim.
- https://hpi.de/baudisch/projects/ems.html - HPI EMS project index.
- https://en.wikipedia.org/wiki/Transcutaneous_electrical_nerve_stimulation - contraindications.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC4302968 - Yang et al. 2015, GVS sway figures.
- https://ntrs.nasa.gov/api/citations/20170001373/downloads/20170001373.pdf - NASA GVS stimulator, ±5 mA (search result).
- https://en.wikipedia.org/wiki/Galvanic_vestibular_stimulation - GVS overview.
- https://en.wikipedia.org/wiki/Hanger_reflex - hanger reflex.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC6514251 - Ferrari et al. 2018, tendon vibration thresholds.
- https://pubmed.ncbi.nlm.nih.gov/4258209/ - Goodwin et al. 1972, original vibration illusions (search result).
- https://en.wikipedia.org/wiki/Thermal_grill_illusion - thermal grill.
- https://lab.rekimoto.org/projects/traxion/ - Traxion.
- https://shape.stanford.edu/research/grabity/ - Grabity.
- https://doi.org/10.1145/3290605.3300241 - Transcalibur (Semantic Scholar record).
- https://doi.org/10.1109/TVCG.2017.2656978 - Shifty (record).
- https://doi.org/10.1145/3173574.3174099 - Thor's Hammer (record).
- https://doi.org/10.1145/3332165.3347926 - Aero-plane, 14 N in 0.3 s (record).
- https://en.wikipedia.org/wiki/Electrovibration - Mallinckrodt, TeslaTouch.
- https://doi.org/10.1145/2185520.2185585 - REVEL (record only).
- https://en.wikipedia.org/wiki/Sound_from_ultrasound - parametric arrays.
- https://www.holosonics.com/technology - Audio Spotlight.
- https://www.focusonics.com/ - Focusonics prices and "virtual source".
- https://www.soundlazer.com/ - Soundlazer kits and prices.
- https://www.soundandvision.com/content/akoustic-arts-directional-speaker - Akoustic Arts figures (search result).
- https://www.ebay.com/itm/375200034723 - 48-emitter kit at $132.99 (search result; may be stale).
- https://hackaday.com/2025/03/04/build-a-parametric-speaker-of-your-own/ and https://github.com/Orange-Murker/parametric_speaker - open 95-element design.
- https://hackaday.com/2026/01/18/accurately-aiming-audio-with-an-ultrasonic-array/ - 555-based array.
- https://doi.org/10.1145/3025453.3025989 - Holographic Whisper (record).
- https://www.adafruit.com/product/1674 - bone conductor transducer, $8.95.
- https://lollipopstar.com/ - bone-conduction lollipop, $9.99.
- https://en.wikipedia.org/wiki/Microwave_auditory_effect - Frey effect.
- https://www.kirinholdings.com/en/newsroom/release/2024/0520_01.html - Electric Salt Spoon.
- https://en.wikipedia.org/wiki/Miracle_fruit - miraculin.
- https://ryosuzuki.org/reactile/ - Reactile coil array.
- https://doi.org/10.1145/2702123.2702516 - FluxPaper (record).
- https://doi.org/10.1145/2984511.2984547 - Zooids (record).
- https://toio.io/ and https://toio.github.io/toio-spec/en/docs/hardware_components/ - toio.
- https://www.media.mit.edu/projects/rovables/overview/ - Rovables.
- https://tangible.media.mit.edu/project/programmable-droplets/ - Programmable Droplets.
- https://doi.org/10.1145/3173574.3173834 - Thermorph (record).
- https://doi.org/10.1145/3242587.3242645 - Tacttoo (record).
- https://doi.org/10.1145/3290605.3300718 - Springlets (record).
- https://doi.org/10.1145/3173574.3173794 - AlterWear (record).
- https://doi.org/10.1145/3332165.3347905 - Photo-Chromeleon (record).
- https://doi.org/10.1145/1753326.1753410 - Marshall, Benford, Pridmore (record).
- https://doi.org/10.1145/2858036.2858226 - Haptic Retargeting (record).
- https://en.wikipedia.org/wiki/Jean-Eug%C3%A8ne_Robert-Houdin - Light and Heavy Chest.

Recalled from memory, not confirmed in this session (unverified): Hoshi 2010 force figure; NTT
Buru-Navi; DuoSkin (ISWC 2016); inFORM, TRANSFORM, aeroMorph, bioLogic, PneUI, Printed Paper
Actuator, Actuated Workbench, Pico; Aoyama four-pole GVS (Sci. Rep. 2015); PNAS 2025 audible
enclaves; Banachek's "Psychokinetic Touches"; Yigal Mesika's Electric Touch (page not reachable);
typical marketplace prices for TENS units, Peltier elements, atomisers and miracle-berry tablets.
