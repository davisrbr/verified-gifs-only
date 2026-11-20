# 22. The instrumented environment: technology in the surface, furniture and room

Slice: put all the technology in the pad, table, chair, floor, lamp and room, so that every object
the audience sees and handles is passive and ordinary.

Conventions: [n] refers to the numbered source list in section 7. "(est.)" marks my own
arithmetic or engineering estimate, not a published figure. "(unverified)" marks recall I could
not confirm. Prices are as seen in late 2026. The shared web-search budget ran out part-way
through this task, so several lines of inquiry rest on fewer sources than I wanted; section 6
lists them.

## 1. Summary

- **A research-grade sensing mat already has the exact footprint and thickness of a close-up pad.**
  Microsoft's Project Zanzibar mat is 30 x 42 cm and 2.5 mm thick, rolls to a 50 mm tube, reads
  and locates up to 16 NFC tags up to 30 mm above the surface, and images touches and object
  footprints at 7 mm pitch with 2 mm accuracy, on two 400 mAh cells for 2+ hours [1]. Its NFC
  antennas are litz wire zigzag-stitched onto stretch cotton with a consumer sewing machine [1].
  Nothing sold to magicians comes close to this.
- **What magic dealers sell today is single-function and thick.** The Faraday Pad needs a 30 mm
  wooden frame plus a 14 mm, 0.84 kg black box underneath [4]; the Quantum Pad is 74 mm thick and
  3.5 kg with a 73 x 98 mm working area [3]; scales are separate 20 mm bricks or card boxes
  [7][8]; RFID readers are separate 77 x 33 mm units read at 11 cm [11]. None fuses modalities,
  none identifies unprepared objects by footprint, and none lives in the chairs, floor or lighting.
- **Sensing fits in a pad; actuation mostly does not.** Antennas, capacitive matrices, Hall grids
  (2 mm [25]), heater films, 0.5 mm power coils [45] and piezo pickups fit in 3 to 6 mm. Gantries,
  load cells, electropermanent magnets, air plenums, cameras and coil arrays with useful force
  need 15 to 80 mm and belong in a tray, tabletop, apron or the performer's case.
- **The strongest use of the surface is to know and to prepare, not to visibly act.** When an
  object moves by itself on a mat, the mat is the only causal candidate. When the mat merely knows
  (which object left, where, in what order, what it weighs) the effect happens in the performer's
  mouth or the spectator's hands and the surface is never in the frame.
- **Furniture can weigh people, which is far more reliable than reading their pulse.** A chair
  accelerometer identifies who is sitting (96% balanced accuracy over 105 people [31]), but
  heart-rate changes detect concealed knowledge only weakly (d about 0.89, AUC about 0.74 in lab
  protocols with repeated questions [34]). A stool on load cells that notices a 250 g object
  arriving is a much better "who has it" method than any physiology.
- **Lighting is an unexamined actor.** A multi-channel LED source can change the colour of chosen
  dyes while still looking white (NTT, shown at Paris Fashion Week 2024 [39]); modulation above
  roughly 2 to 3 kHz is invisible even during eye movements [40], so a lamp can broadcast timing
  or data to anything with a photodiode.
- **Slow and unattended methods are nearly free.** 96.6% of 417 viewers missed a colour change
  that unfolded over 16 s in the centre of a video [41]. Shelf-scale props can move millimetres
  per minute, or only when sensors say nobody is facing them.
- **The glass table is an opportunity, not a constraint.** It "proves" there is nothing in the
  surface while exposing the face of every face-down card to a camera at floor level.
- **Borrowed objects increasingly arrive pre-tagged.** Bank cards, transit cards, hotel keys and
  phones answer a 13.56 MHz reader through a wallet at 30 mm [1]. A mat can fingerprint a wallet
  by the set of tags inside it without reading any payment data (legal and ethical limits in 2.2).
- **Trust has a history.** Robert-Houdin replaced floor-length draped tables with light undraped
  ones [50] and hid his electromagnet under the floor [51]. The modern equivalent: keep the pad
  thin, rollable and handed out, and put the method in something nobody thinks of as a prop.

## 2. Catalog

### 2.1 Budget: what fits where

| Location | Depth available | Fits | Does not fit |
|---|---|---|---|
| Close-up pad | 3 to 6 mm | NFC antenna array + capacitive matrix (2.5 mm total [1]); Hall grid (2 mm [25]); film heaters; 70 mm x 0.5 mm power coil [45]; piezo discs; thin LED matrix; thin LiPo in a stiff edge | load cells, gantry, EPM, plenum, camera, high-force coil arrays |
| Hard-backed pad, tray, clipboard, bar mat | 8 to 20 mm | all of the above + four load cells in the feet [7]; 4- to 14-layer coil cells [17]; Qi transmitter; exciters | gantry, camera throw |
| Tabletop + apron, performer's case used as a table | 40 to 80 mm | XY or SCARA magnet gantry [20]; EPM; fan and plenum; cameras; rotating magnet | nothing important |
| Under-table clip-on | 15 to 30 mm box | piezo/accelerometer pickups [26], magnetometers, radar, exciter | NFC (range too short through 30 mm of wood) |
| Chair, stool, floor, lamp, shelf | large | load cells, accelerometers, pressure film [30], multi-channel LEDs, gantries | - |

Power. Zanzibar's full-rate capacitive plus NFC scanning ran over 2 hours on 2 x 400 mAh
(35 x 25 x 5 mm each) [1], which is roughly 1.3 to 1.5 W (est.). Scanning NFC only when the
capacitive image or weight changes should cut that by an order of magnitude (est.). Zanzibar hid
its rigid electronics in a 35 x 2.4 x 3.8 cm aluminium "baton" along one edge [1]; a pad can use a
stitched leather edge roll, a wooden rail (the Faraday Pad already ships with a frame [4]) or the
card box sitting on its corner.

Weight. A full 400 x 300 x 0.8 mm FR4 board would add about 180 g (est., density 1.85 g/cm3) and
make the pad a plank. Stitched wire antennas and a flex or printed electrode layer add tens of
grams (est.). Spectators have no reference weight for a pad, so the tell is stiffness and sound
rather than mass: keep 1.5 to 2 mm of foam above any rigid island and keep islands at the edge
(est., untested).

### 2.2 Large-area identification: NFC antenna arrays

*What.* Zanzibar switches one TI TRF7970A transceiver across overlapping row and column loop
antennas (single-turn rows, double-turn columns). Signal strength per row and column gives a tag
position to about 20 mm in hover; once the tag touches down, its capacitive footprint refines
that to 2 mm. Tag-presence latency is about 1 s; footprint updates run at 25 Hz with about 100 ms
latency. Custom tags harvest power for LEDs and buttons; "stackers" report stack order up to
four high [1]. Student and DIY poker tables use one PN532 reader per seat under the felt with
2 to 4 cm range [53]; RFID poker tables are also patented [53].

*Access.* Hobbyist. Antennas are sewn [1]; the reader chip and RF switches are catalogue parts
(agent 14). The A3-size flex capacitive layer is the expensive part; the authors also
screen-printed it in silver with slightly worse performance [1].

*Magic relevance.* Know (identity and position of many tagged objects at once), tell (power and
command a batteryless prop), prove ordinariness (the pad rolls up and can be handed out).
Existing magic RFID is a single reader with one antenna: Insight reads 3 cards at once at 11 cm
from a 77 x 33 mm unit that "can be positioned under a table" [11]; Second Sight reads at 110 mm
[12]; the Bat System claims 2 to 3 m, which implies UHF tags [13]; a hobbyist hid an Arduino
reader under a table and sent reads to a server [15]. None locates tags.

*Limits and betrayals.* Stacked HF tags detune each other, so a squared deck of tagged cards will
not read (unverified in detail; Zanzibar needed special switched tags to stack four [1]). A
reader field may wake a phone's wallet or NFC prompt when a spectator's phone lies on the pad
(unverified; mitigate by not scanning under a phone-sized footprint).

*World-tagged objects.* Contactless bank cards, transit cards, hotel keys and passports are
ISO 14443 tags. Anticollision alone lists how many answer and their type bytes without touching
application data. **Do not read payment application data from a spectator's card: that is
skimming.** Some cards randomise their identifier, so fingerprints may not persist (unverified).

### 2.3 Capacitive imaging through fabric

*What.* Zanzibar: 41 x 58 copper electrodes in a diamond pattern on flex, 7 mm pitch, raw image
at 25 Hz, hover gestures in a time-multiplexed self-capacitance mode; large conductive objects
cause false touches [1]. Capacitivo (Dartmouth and Microsoft, UIST 2020): a 12 x 12 grid of
conductive-fabric diamonds on cotton recognises 20 non-metallic household objects at 94.5%
(10 participants), tells water from milk, cider and soda in a container, and is weak on objects
with no firm footprint such as credit cards [24].

*Access.* Hobbyist for coarse grids (conductive fabric, a touch controller or MCU capacitive
pins); the fine FPC is an ordered part.

*Magic relevance.* Know: where hands are (which pile was touched, which hand reached), outline
and orientation of conductive or water-bearing objects, full versus empty glass, without tags.
Playing cards are nearly invisible to it, which is useful: hands are seen, cards are not.

### 2.4 Weight and centre of pressure

*What.* Four load cells under a rigid plate give total weight and, from the ratio, the position
of whatever was added or removed (principle in [28][29]; agent 10 covers the ADCs). Position
error is roughly span x noise / object mass (est.): on a 400 mm plate with 0.05 g of noise a
5.67 g coin is located to about 3.5 mm, a 1.8 g card to about 11 mm, a 95 g deck to 0.2 mm.
Dealer products prove the precision is real in small housings: the PITATA Smart Scale claims
0.01 g in 77 x 63 x 20 mm with Bluetooth 5.2 and is sold as fitting "in a card case or close-up
pad" [7]; DragonScale hides a scale in a card box and resolves one card [8]; SoulMate claims
0.001 g for three pre-programmed objects [10]; MindScale identifies objects added to or removed
from a mat [9].

*Under table legs.* A 15 kg table with elbows on it will not resolve a card, but will resolve a
glass, a phone, a deck, and which side people lean on (est.). The 2002 Lancaster load-sensing
table used exactly this to turn a table into a pointing surface [28].

*Betrayals.* Draughts, a resting hand, and a plate that rocks. Read step changes while hands are
off; use capacitive sensing to know when they are.

*What is new.* Fusing weight with position and a footprint image, so objects need no
pre-registration and "where" comes free. I found no dealer product that does this.

### 2.5 Pressure imaging

Sensel's Morph packed about 20,000 force sensors into a 230 x 130 mm active area, 240 x 169.5 mm
overall and about 7 mm thick, 0.4 kg [23]. It was discontinued in May 2022 and the company was
acquired by Cirque in April 2025 [23], so it is a second-hand part. MIT's "intelligent carpet"
used commercial pressure-sensitive film and conductive thread for 9,000+ sensing points over
36 x 2 ft, at a reported cost near $100, and inferred 3D body pose within about 10 cm for one
person [30]. Pressure film is the right tool for feet, seats, cups, dice and coin edges; a card
exerts about 0.03 g/cm2 (est.) and is invisible to it.

### 2.6 Magnet tracking from below

GaussSense is a 2 mm-thick Hall-sensor grid (192 sensors over 60 x 80 mm, so about 5 mm pitch)
that tracks a magnet's position and tilt within 2 cm of any non-ferrous surface [25]. A DIY
chessboard reads 500 SS39E analogue Hall sensors through veneer with HC4067 multiplexers [20].
Pose solvers with eight magnetometers are agent 10's item. In a pad: a 25 mm-pitch grid is
about 190 sensors (est.), enough with interpolation to know where every magnetised object is and
which pole is up. Commercial "which hand" and PK detectors are point sensors.

### 2.7 Vibration: the table listens, and pings itself

VibSense (Stevens/Rutgers) uses one piezo receiver, optionally with one small vibration
transmitter, stuck to an ordinary surface. Passively it classifies where a tap landed (paper
keyboard keys at 87 to 97%). Actively it sweeps the surface and recognises which trained object
sits at which of nine spots 5 cm apart on a 120 x 50 x 3 cm wooden table: over 86% for a glass,
phone or drink can from a single training sample and 100% after four, but only 60% and up for a
coin or paper cup [26]. Smatable classifies swipe direction on an ordinary table with four
sensors at 0.67 across unseen users and 0.90 with one calibration session [27]. Time-of-arrival
tap bearing (Toffee) is in agent 10's report.

*Magic relevance.* This is the one sensing family that clips under a **borrowed** table in
seconds and needs nothing on top. It needs per-table training, so it suits "three places, three
heavy objects" and tap or rap detection, not fine localisation.

### 2.8 Looking up through the surface

*Cloth.* Near-infrared passes through many textiles; transmission depends mainly on weave
openness and fibre, less on dye colour, and denim passes far less than open cotton [42]. A
silicon camera with 850 or 940 nm LEDs under an open-weave black cloth can therefore see hands
and object outlines above it. It will not read red pips: red printing inks are typically
transparent in the near infrared (unverified for specific decks).

*Glass.* A glass tabletop needs no trick optics. A wide phone camera 1.2 m below a card gives
roughly 2.7 px/mm (est.), so a 6 mm index is about 16 px tall: readable. See concept B.

*Contact imaging.* Anything lying in contact with a thin diffuser is sharp from behind while
things a few millimetres away blur; this is how diffuse-illumination tabletop computers read
fiducials (unverified citation, from memory). A flatbed-scanner contact image sensor under a slit
would read whatever is slid across it. Untested through pad fabric.

### 2.9 Moving things from below (packaging only; physics is agents 9, 11 and 18)

*XY or SCARA gantry with a magnet.* Self-moving chessboards are the existence proof. The Phantom
board (about $799 cordless at crowdfunding [21]) is marketed as whisper-quiet with no published
decibel figure [21]. A DIY builder's log is more useful: an electromagnet needed too much current
for heavy pieces, so he switched to a neodymium magnet on a motorised lift (engage and disengage
by distance); light pieces wobble when the carrier passes neighbours; and the box came out "too
high" [20]. Sisyphus tables steer a ball through sand with "silent" motors under the bed [22].
Budget 40 to 80 mm of depth. The Faraday Pad's black box (27 x 17.5 x 1.4 cm) under a pad already
does coin jumps, dice control and a haunted deck silently for 5 to 8 hours per charge [4]; the
Quantum Pad uses a sliding track and lift [3].

*Coil arrays with no moving parts.* Reactile: 15 mm, 15-turn coils on a 10 mm grid, 4-layer
boards, 3,200 coils over 80 x 40 cm at about $80 per board, with a camera for position feedback
[16]. A single catalogue coil, Bugeja's CoilCell 2.5 W (14 layers, 200 turns, 5 V, EUR 5.50),
reaches 10 mT at its face, 17 mT with an iron backplate, and "can make lightweight magnets
bounce" [17]. That gradient puts roughly 4 gram-force on a 5 x 1 mm disc magnet at the surface
(est.), enough to slide a card carrying one, less through 3 mm of foam. Each coil dissipates
watts, so a pad-sized array is a warm, stiff, amp-hungry plank: table, not pad.

*Whole-surface vibration.* A single piezo under a 50 mm silicon plate steered six sub-millimetre
objects independently by choosing among 59 notes between 1 and 30 kHz, with camera feedback and
about 175 micron steps per half-second note [43]. That is a lab result at seed scale; see dead
ends. A sawtooth (stick-slip) drive of a floating top plate is the hobby route to drifting coins
(speculative; agent 18).

### 2.10 Hold and release zones

Electropermanent magnets (agent 7) are about 16 mm thick in catalogue form (unverified, agent 14),
so they go in a tabletop or tray. They hold any steel object: copper-plated steel euro cents and
UK 1p/2p coins are magnetic (unverified by search here), US coins are not. Electroadhesion works
only within tens of microns of the electrodes, so the top surface must be a thin film (a vinyl or
"leather" mat) rather than cloth. In a pad, the practical switched hold is a Hall-sensed magnet
on a small lift, as in the DIY chessboard [20].

### 2.11 Power through the surface

A $14.95 hobby kit drives ten 16 x 12 x 2.5 mm LED receivers from a 70 mm, 0.5 mm-thick coil on
5 V at 0 to 80 mm [45]. Qi runs at 105 to 205 kHz, typically across 5 mm and up to 40 mm, and
checks for foreign metal before delivering power [46], so it will not light a bare coil but will
feed a $2 receiver module. Furniture with a built-in phone charger is ordinary, which gives a
coil, a cable and a warm spot an innocent reason to exist. Room-scale wireless power is in dead
ends.

### 2.12 Heat zones

Film heaters are 0.2 mm (unverified, agent 14). Warming a 0.5 mm fabric layer by 10 K takes about
0.2 J/cm2 (est.), so a 5 x 5 cm mark needs tens of joules: trivial for a pad battery, a few
seconds at 0.5 to 1 W/cm2. Uses: thermochromic topcoats (2.13), and selectively erasing
heat-erasable ink on a card lying on the pad (concept E). **Keep any touchable surface under
about 45 C; a 65 C zone must be covered by the object it heats.**

### 2.13 Display through the surface

*Hidden-until-lit.* Google's "Hidden Interfaces" drove a 128 x 96 PMOLED with parallel rendering
to shine through textile, 0.2 mm mirror film, acrylic and wood veneer, 3.6 to 40 times brighter
than an AMOLED depending on content; 1.6 mm basswood passed little light with any display [36].
An LED matrix under 0.3 to 0.6 mm veneer or thin pad cloth is the hobby version. Deception
problem: it reads as a screen.

*Thermochromic cloth.* Ebb coated conductive threads with thermochromic pigment and wove them
into swatches that change "slowly, subtly, even ghostly" (CHI 2016 best paper) [37]. A mark that
blooms and fades in cloth reads as a stain or breath, not a display. Use pigments that switch
well above hand temperature.

*Photochromic.* ChromoUpdate rewrites photochromic coatings with a UV projector: a grayscale
preview in about 60 s, full colour in about 20 min, yellow saturating in 7 s and magenta in 60 s
[38]. Too slow for a reveal with a projector; contact UV LEDs under cloth should be much faster
(est., untested). **UV-A at the eye is a hazard; keep it under the fabric.**

*Magnetic.* A child's magnetic drawing board is a commercial, examinable magnetophoretic
display; a magnet moving behind it rearranges the particles (concept D). Stroke width is about
the magnet stand-off (est.).

### 2.14 Chairs and floors

*Who is sitting.* NF-Heart mounts a light accelerometer on an office chair and authenticates the
sitter from heart-induced vibration: 96.45% mean balanced accuracy, 3.83% median equal error
rate, 105 people [31]. A fibre-sensor cushion identified 15 people at 100% and 30 at 90% [32]; an
instrumented toilet seat managed 75% [33].

*Who is hiding something.* Not from pulse. The 2014 meta-analysis of the concealed information
test gives heart rate d* = 0.89 against 1.55 for skin conductance [34], AUC about 0.74 versus 0.85
second-hand [34], in lab protocols with repeated questions. One question to five seated guests
would land little above the 20% chance line (est.).

*What chairs do well.* Weigh. Four bathroom-scale cells under a seat know who sat, stood, leaned
or swapped. A chair shares load with the feet on the floor, which varies by kilograms (est.); a
bar stool with its own footrest is a closed system, so a 250 g object arriving on a seated
person shows as a clean step (est., untested).

*Floors.* Geophones or accelerometers locate footsteps by time difference of arrival
(CMU/Virginia Tech work [35]; I could not extract error figures). Results depend on floor type,
carpet and shoes, and simultaneous walkers are unsolved [35]. A pressure carpet gives pose [30].

### 2.15 Lighting

*Metamerism on demand.* NTT's system computes an LED spectrum that shifts chosen dye colours
while the light still appears white; dresses changed colour on a Paris Fashion Week runway in
2024 [39]. Related patents hide information in ink pairs that match in daylight and separate
under 10 to 20 nm LED bands such as 620 versus 660 nm [39]; an IS&T paper proposes narrowband LEDs
to break metameric matches as a watermark [39].

*Invisible modulation.* Flicker is seen up to about 80 Hz; stroboscopic and phantom-array
artefacts persist to about 2 kHz, beyond for some people; above 3 kHz is recommended [40]. So a
lamp can carry a kilohertz data or timing channel to a photodiode in a prop or on the performer,
and strobing between 100 Hz and 2 kHz makes a spinning or vibrating object appear frozen while
static objects look normal. **Avoid any component below about 100 Hz (photosensitive epilepsy).**

*Infrared flood* for hidden cameras (2.8), and *polarised light*: a polariser on the lamp, clear
birefringent film on glossy objects, and a polarising spectacle lens (speculative; no source
found in budget).

### 2.16 Magnetic fields at table scale

An N52 20 mm cube has a moment near 9 A m2 (est.), giving 34 to 68 microtesla at 30 cm depending
on orientation (est.), against a horizontal Earth field of about 20 microtesla (unverified
typical). One magnet on a servo 25 cm under a tabletop therefore steers every compass, floating
needle and phone compass within about 30 cm, silently and with no power at rest. A DC coil in
the apron does the same with no moving parts for a few watts (est.).

**Safety.** Pacemakers and ICDs must tolerate 1 mT static fields [48]; ICNIRP cites interference
below 0.5 mT [49]. A 25.4 x 25.4 x 12.7 mm neodymium block reaches 1 mT at 11 cm and a 50 mm block
at 22 cm [48]. Keep large magnets at least 25 cm below the surface and away from seat height.

### 2.17 Slow motion and unattended action

Gradual changes escape notice because they produce no transient (Simons, Franconeri and Reimer
2000 [41]); 96.6% of 417 participants missed a 16 s central colour morph [41]. Classical motion
thresholds are around 1 to 2 arcmin/s with stationary references (unverified, from memory), about
0.6 mm/s at 2 m. An hour-hand tip moves about 0.015 mm/s (est.). Design rule: 0.01 to 0.05 mm/s,
or 36 to 180 mm per hour (est.). Better still, move at normal speed only when a head-pose camera
or radar (agent 10) says nobody is facing the shelf.

### 2.18 The phone lying on the table

It is a magnetometer, an NFC reader with 2 to 4 cm range (unverified), a vibration motor, a
loudspeaker coupled to the tabletop, a flash LED, and on many Android phones a reverse wireless
charger of about 4.5 W [47] that only powers a Qi-compliant receiver [46]. Face-down, its coil and
NFC antenna face up: something laid on top of it is read or powered with no screen ever shown.

### 2.19 History and the trust problem

Robert-Houdin dressed his stage as a Louis XV drawing room [50] and "suppress[ed] the
suspiciously-draped tables of his predecessors", using light undraped tables and gueridons [50].
His Light and Heavy Chest (mid-1840s) put an electromagnet under the floorboards, switched by an
offstage assistant, with an iron plate in the box [51]: the first instrumented environment, with
a nearly passive prop. Séance tables were moved by pins and slotted rings, hooks, extended boot
soles, knees and feet; Faraday's 1853 apparatus showed sitters pushing unconsciously [52]. The
Losander floating table (about 1997) descends from Karson's 1940s work via Tommy Wonder [52].

Lessons. A surface is trusted while it has an innocent function and never appears to cause
anything. Thickness is the tell: draped tables then, framed pads now. Remedies: (a) a pad thin
enough to roll and hand out [1]; (b) a passive pad with the electronics in the tray beneath, as
the Faraday Pad already does [4]; (c) no pad, using a bar mat, coaster, menu, placemat or
notebook; (d) a clip-on under their table (2.7); (e) method in the lamp, stool or floor.

## 3. Capability primitives

1. *Now possible:* identify and locate up to 16 tagged objects within 30 mm of a 30 x 42 cm
   surface, 20 mm accuracy in hover and 2 mm on contact, in a 2.5 mm rollable laminate. *Because:*
   switched row/column NFC antennas plus capacitive imaging [1]. *Before:* one reader, one spot,
   no position [11][12]. *Primitives:* know, prove ordinariness.
2. *Now possible:* sew that antenna array on a domestic sewing machine. *Because:* litz wire
   zigzag-stitched on stretch cotton [1]. *Before:* rigid reader boards. *Primitives:* conceal.
3. *Now possible:* see every hand and conductive footprint on a pad at 7 mm pitch, 25 Hz, while
   cards stay invisible. *Because:* fabric capacitive matrices [1][24]. *Before:* watching.
   *Primitives:* know.
4. *Now possible:* tell a full glass from an empty one and water from milk or soda from under a
   tablecloth. *Because:* Capacitivo [24]. *Before:* marked glasses. *Primitives:* know.
5. *Now possible:* weigh to 0.01 g inside 20 mm and locate a 6 g coin to a few millimetres on a
   pad-sized plate. *Because:* load cells and 24-bit ADCs [7][8]; centre of pressure [28][29].
   *Before:* weight only, pre-registered objects [9][10]. *Primitives:* know.
6. *Now possible:* fingerprint a borrowed object by weight plus footprint in the second it is
   set down, with no registration step. *Because:* fusing 3 and 5. *Before:* memorised object
   sets. *Primitives:* know, prove ordinariness.
7. *Now possible:* track the position, tilt and polarity of magnets through a 2 mm grid within
   20 mm. *Because:* Hall arrays [25][20]. *Before:* point detectors. *Primitives:* know.
8. *Now possible:* instrument a borrowed wooden table in seconds with one stuck-on pickup and
   know which of nine spots holds which heavy object (86 to 100%). *Because:* active vibration
   sensing [26]. *Before:* nothing on borrowed furniture. *Primitives:* know.
9. *Now possible:* read the faces of face-down cards on a glass table from floor level at about
   16 px per index. *Because:* phone cameras (est.). *Before:* shiners and peeks. *Primitives:*
   know.
10. *Now possible:* move a magnetised object anywhere on a tabletop silently from 40 to 80 mm of
    depth, engaging by lifting a permanent magnet. *Because:* printer mechanics, chessboard
    practice [20][21][4]. *Before:* threads, assistants. *Primitives:* move.
11. *Now possible:* put about 4 gf on a 5 mm magnet from a EUR 5.50, 5 V flat coil. *Because:*
    multi-layer PCB coils [17][16]. *Before:* wound electromagnets. *Primitives:* move, release.
12. *Now possible:* power a 16 x 12 x 2.5 mm batteryless receiver up to 80 mm above a 0.5 mm
    coil. *Because:* hobby induction kits [45]. *Before:* batteries and switches in the prop.
    *Primitives:* tell, prove ordinariness.
13. *Now possible:* give a coil, cable and warm spot in furniture an innocent reason. *Because:*
    Qi chargers in tables [46]. *Before:* any wire was suspect. *Primitives:* conceal.
14. *Now possible:* make a mark appear in cloth for about 60 J and have it vanish by itself.
    *Because:* thermochromic pigment over a film heater [37]. *Before:* chemical developers.
    *Primitives:* transform, erase the evidence.
15. *Now possible:* selectively erase chosen lines on a hand-written card from beneath.
    *Because:* heater matrix plus heat-erasable ink (est.). *Before:* multiple outs in pockets
    and indexes. *Primitives:* control choice after the fact, erase the evidence.
16. *Now possible:* show bright text through 0.2 to 1 mm of veneer, textile or mirror.
    *Because:* parallel-rendered PMOLED [36]. *Before:* visible displays. *Primitives:* tell.
17. *Now possible:* write on a shop-bought magnetic drawing board from under the table.
    *Because:* gantry magnet [20]. *Before:* flap slates. *Primitives:* transform, prove
    ordinariness.
18. *Now possible:* recognise which of 105 people is in a chair from one accelerometer.
    *Because:* seat ballistocardiography [31]. *Before:* asking. *Primitives:* know.
19. *Now possible:* know which seated guest took possession of a 250 g object, and when it
    changed hands. *Because:* load cells under stools (est.). *Before:* stooges, tells.
    *Primitives:* know.
20. *Now possible:* get 3D body pose from the floor for about $100 of film and thread, no camera.
    *Because:* tactile carpets [30]. *Before:* a watching assistant. *Primitives:* know.
21. *Now possible:* change the colour of one dye while the room light still looks white.
    *Because:* spectrum-optimised LED mixing [39]. *Before:* coloured gels, obvious.
    *Primitives:* transform, conceal.
22. *Now possible:* broadcast kilohertz data or timing from a lamp with no visible flicker.
    *Because:* LEDs modulate above the 2 to 3 kHz artefact limit [40]. *Before:* radio.
    *Primitives:* tell, delay.
23. *Now possible:* steer every compass within 30 cm of a table point with no power at rest and
    under 1 mT at the surface. *Because:* a neodymium cube on a servo (est.) [48]. *Before:*
    palmed magnets. *Primitives:* move, tell.
24. *Now possible:* move a shelf object 36 to 180 mm per hour unseen, or at full speed whenever
    nobody faces it. *Because:* slow-change blindness [41] and cheap attention sensing.
    *Before:* stagehands. *Primitives:* move, delay.
25. *Now possible:* hold a borrowed steel coin to a tabletop with newtons, then release it with
    a pulse and leave no field. *Because:* EPMs (agent 7). *Before:* always-on magnets.
    *Primitives:* hold/release.
26. *Now possible:* count and fingerprint the contactless cards inside a closed wallet at 30 mm.
    *Because:* ISO 14443 anticollision over a mat antenna [1]. *Before:* impossible.
    *Primitives:* know.

## 4. Effect concepts

Every visible object is ungimmicked or passive. Levels as in the brief.

### A. The pad that knows borrowed objects (level 2)

*Effect.* Five borrowed objects go on the pad. The performer leaves. Spectators pocket, swap or
return objects as they like. He comes back and says who holds what, in what order they moved,
and that one was secretly put back.

*Method.* Hard-backed pad on four load cells; coarse capacitive grid in the top. Each object is
fingerprinted by weight and footprint as it is set down. Events are logged with time and
position and sent to a thumper or earpiece (agent 21). Capacitive sensing gates out readings
while a hand rests on the pad.

*BOM.* Four 100 g to 1 kg cells, ADC, conductive fabric, ESP32, LiPo: $60 to $120.
*Difficulty.* Moderate. *Risks.* Two objects of equal weight; draughts; leaning.
*Novelty.* Dealer scales weigh pre-registered objects [7][9][10]; position and footprint are new.

### B. The glass table (level 3)

*Effect.* At a glass café table a spectator shuffles their own deck, deals cards face down and
slides any one out. The performer never touches anything and names it, then names them all.

*Method.* The glass argues that nothing is under the surface. A phone in the performer's bag on
the floor, or lying camera-up by a chair leg, films the underside; software reads indices and
reports by earpiece or watch. Card faces are lit by light bounced off the floor, so a pale floor
or napkin helps.

*BOM.* A phone and software; $0 to $50. *Difficulty.* Software only.
*Risks.* Dark floors, patterned or frosted glass, a spectator glancing under the table (a bag is
innocent; a tripod is not). *Novelty.* The shiner principle is old; using the venue's glass
furniture and a floor-level camera is, I believe, unexploited.

### C. Wallets that identify themselves (level 3)

*Effect.* Four spectators drop their wallets into a bag. The performer draws them out one at a
time, lays each on the pad "to feel it", and returns each to its owner, adding "you carry three
cards in here and one is a transit pass".

*Method.* A Zanzibar-style antenna pad enumerates the contactless tags inside each wallet when it
was first set down and again on return, matching by tag set. Only anticollision and type bytes
are used.

*BOM.* Reader IC, RF switches, sewn antennas: $40 to $80. *Difficulty.* Moderate (RF tuning).
*Risks.* Stacked cards detune each other, so counts above two or three will be wrong; shielded
wallets; randomised identifiers; phones waking. **Never read payment data; disclose nothing
personal.** *Novelty.* High.

### D. Spirit slate from the toy shop (level 3)

*Effect.* A child's magnetic drawing board, bought sealed, is wiped and placed under the
spectator's own hand on the table. A freely named word is found written on it.

*Method.* A gantry in the table apron or in the performer's case carries a small magnet on a
lift [20]. The word arrives by keypad or speech recognition (agent 12). The board is the
display; the table is the pen.

*BOM.* Printer mechanics, drivers, magnet, MCU: $80 to $150. *Difficulty.* Moderate to hard.
*Risks.* Whether a magnet behind the board draws or erases depends on its construction, and
stroke width grows with stand-off, so expect two or three large letters; test before building.
Gantry noise under a hand. *Novelty.* High. Speculative until tested.

### E. Erasing the outs (level 3)

*Effect.* The performer writes "a prediction" on a blank card in full view and leaves it face
down on the pad. A card is freely named. The spectator turns over the prediction: one line, the
named card. The card is theirs to keep.

*Method.* The card was pre-written with many outcomes in heat-erasable ink in a grid; the
visible writing is misdirection on the other side or in ordinary ink. A heater matrix under the
pad cover erases every line but one in a few seconds while the card lies there.

*BOM.* Custom heater PCB (8 mm cells), MOSFET drivers, MCU: $40 to $80 plus pens.
*Difficulty.* Moderate. *Risks.* Erasable ink leaves a faint ghost and returns in a freezer
(agent 8); the grid must not look like a grid afterwards, so 6 to 18 outs on a business card is
realistic; heat must stay under the card. *Novelty.* High as an architecture: brute-force outs,
physically removed by the furniture.

### F. The stools know (level 3)

*Effect.* Five guests on bar stools pass a borrowed bottle or heavy book behind the performer's
back until one keeps it under a coat. He points to the holder, then recounts the route it took.

*Method.* Load cells in each stool base log weight steps. A stool with its own footrest carries
the sitter's full weight, so +250 g on stool 4 as stool 2 drops 250 g is unambiguous. Pulse
"reading" is the presentation, not the method.

*BOM.* Four cells and an amplifier per stool, one ESP32: $60 to $100 for five.
*Difficulty.* Easy electronics, awkward carpentry. *Risks.* Feet on the floor, objects under
100 g, people shifting bags. *Novelty.* High; installation or home-venue only.

### G. The lamp changes the print (level 3)

*Effect.* A printed card has lain on the table all evening and has been read aloud. At the
climax a second line is visible on it, or one word is now a different colour. Under a
spectator's phone torch it is just ink.

*Method.* A table lamp with five to seven LED channels holds a white point while shifting its
spectrum to split a metameric ink pair [39]. Photo inkjets with many inks contain such pairs;
choose them with a hobby spectrometer.

*BOM.* LED channels, drivers, MCU, spectrometer: $100 to $300. *Difficulty.* Hard (colour
science). *Risks.* Any other light source dilutes it; observers differ; the shift must be slow.
*Novelty.* High.

### H. The slow room (level 3)

*Effect.* An ordinary magnetic travel chess set sits mid-game on a side table. Nobody goes near
it. At the end of the evening its position matches a diagram sealed in an envelope at the start,
or a move a guest called out an hour ago has been played.

*Method.* A gantry in the side table moves pieces at 0.02 mm/s, or briskly whenever a head-pose
sensor reports nobody facing it. Travel-set pieces already contain magnets.

*BOM.* $80 to $200. *Difficulty.* Moderate. *Risks.* Neighbouring pieces wobble [20]; someone
filming a time-lapse. *Novelty.* Self-moving boards are public [21]; using one covertly and
slowly, as a delayed method, is not.

### I. Their table, your clip (level 2)

*Effect.* At a spectator's own dining table: raps answer questions from inside the wood, and the
performer, blindfolded, knows which of three places a heavy object was moved to.

*Method.* A 60 x 40 x 15 mm unit pressed under the table edge on gel tape while pulling up a
chair: accelerometer or piezo pickup, small exciter, magnetometer, radio. Raps come from the
exciter; object location from active vibration sensing after a 30 s "arrange the objects"
calibration [26].

*BOM.* $30 to $60. *Difficulty.* Moderate (signal processing). *Risks.* Glass and stone tables;
low accuracy for light objects [26]; forgetting to remove it. *Novelty.* Moderate to high.

### J. The cloth remembers (level 2)

*Effect.* A coin is covered and vanishes. A faint coin-shaped shadow in the cloth where it lay
drifts across the pad and stops. The coin is found there. The shadow fades.

*Method.* Sleight of hand does the vanish and load. A coarse heater matrix under a thermochromic
top layer draws the travelling mark. The sleight cancels "it's electronic"; the mark cancels
"he just moved it".

*BOM.* $40 to $80. *Difficulty.* Moderate. *Risks.* Slow fade in a warm room; hands trigger a
low-temperature pigment. *Novelty.* Moderate.

### K. Every compass on the table (level 1, brief)

Borrowed compasses and a needle floating in a borrowed glass swing to the chosen person. A servo
turns a magnet 25 cm below the top. $20. Observe the pacemaker distances in 2.16.

### L. Drift (level 1 to 2, brief, speculative)

Borrowed coins creep a few centimetres toward a chosen card over half a minute, driven by
sawtooth vibration of a floating top plate. Betrayed by hum and by everything moving the same
way. Physics in agent 18.

## 5. Dead ends and overhyped items

- **Room-scale wireless power.** Disney's room is aluminium on all six faces with a copper pole
  and capacitors; 1.9 kW is a simulation [44]. The newer multimode version quotes 50 W, also
  simulated [44]. Use an 80 mm hobby coil [45].
- **Chladni-plate steering of coins.** The published system moves 0.6 mm solder balls and 7 mm
  washers on a 50 mm silicon wafer with a camera in the loop [43].
- **"Which of five is lying" from a chair.** Identity yes [31], guilt no [34].
- **Footstep identification on an arbitrary floor.** Depends on slab, carpet and shoes; fails
  with several walkers [35].
- **Reading a squared deck of NFC cards.** Stacked tags detune; research needed switched tags to
  stack four [1].
- **Pressure mats for cards.** A card is far below the threshold of pressure film (est.).
- **Sensel Morph as a platform.** Discontinued 2022, company defunct [23].
- **Self-lit text in the pad as a climax.** Works [36], reads as a screen.
- **Projector-written photochromics.** Minutes per image [38].
- **Coil arrays inside a soft pad.** Watts per coil [17]; heat, stiffness and current.
- **Infrared camera reading red pips through cloth.** Red inks vanish in near infrared
  (unverified); outlines and hands only.
- **Ultrasonic arrays under cloth.** I found only patents about tuning cover spacing, and one
  noting that air trapped in fabric attenuates ultrasound [55]. No transmission data.

## 6. Open leads

- Measure whether a hobby NFC mat wakes iPhone and Android wallets, and how many stacked cards
  in a wallet can be enumerated.
- Magnetic drawing boards: draw-versus-erase from behind, and stroke width against stand-off.
- Erasable-ink ghosting on different card stocks; minimum heater cell size.
- Stool load cells: real noise with a breathing, fidgeting sitter.
- Near-infrared and 40 kHz transmission of actual close-up pad fabrics.
- Metameric pairs available from a 6- to 12-ink photo printer; the NTT paper's channel count [39].
- Polarised-light markings: no source found before the search budget ran out.
- Footstep localisation error figures (PDFs would not parse) [35]; the 2002 Lancaster
  load-sensing paper (redirect failed) [28].
- Square Off and GoChess mechanisms and thickness; Phantom noise measurements.
- Classical motion-threshold figures (quoted from memory in 2.17).
- Robert-Houdin's own chapter on stage arrangements (Gutenberg returned 503) [50].
- MindScale and TCC Portal specifications (pages blocked or empty) [5][9].

## 7. Sources

"Opened" means I read the page or extracted the PDF text; "search" means the URL and the facts
cited came from search results only.

1. https://sites.cs.ucsb.edu/~sra/publications/zanzibar.pdf - Villar et al., Project Zanzibar, CHI 2018 (opened, full text).
2. https://www.microsoft.com/en-us/research/publication/project-zanzibar-portable-flexible-tangible-interaction-platform/ - Zanzibar publication page (search).
3. https://shop.52kards.com/products/the-quantum-pad-by-tcc-magic-mental-tom-trick - Quantum Pad specifications (opened).
4. https://alakazam.co.uk/products/the-faraday-pad-by-infinity-tcc-trick and https://shop.52kards.com/products/the-faraday-pad-by-infinity-trick - Faraday Pad specifications (opened).
5. https://vanishingincmagic.com/stage-and-parlor-magic/portal-tcc - TCC Portal (search; 403 on fetch).
6. https://stevensmagic.com/products/iarvel-pad-iarvel-magic - Iarvel Pad writing-capture clipboard, 170 x 107 x 8 mm, $215 (opened).
7. https://alakazam.co.uk/products/smart-scale-by-pitata-magic-trick - PITATA Smart Scale (opened); https://vanishingincmagic.com/mentalism/smart-scale (search).
8. https://wholesale.penguinmagic.com/products/dragonscale - DragonScale (opened); https://patents.google.com/patent/US11788878 - scale patent (search).
9. https://magicshopsandiego.com/products/mindscale-with-black-bowl-by-illuminati-magic - MindScale (search; empty on fetch).
10. https://shop.52kards.com/products/soul-gimmicks-and-online-instructions-by-wenzi-trick - SOUL scale (search).
11. https://shop.52kards.com/products/insight-esp-by-hugo-shelley-trick - Insight ESP RFID reader (opened).
12. https://thegadgetflow.com/portfolio/illuminati-magic-second-sight-rfid-system-for-mentalists-detect-cards-4point5inches-away/ - Second Sight (opened).
13. https://vanishingincmagic.com/stage-and-parlor-magic/the-bat-system - Bat System (search).
14. https://vanishingincmagic.com/mentalism/dave-forrests-chip-reader - Chip Reader (search).
15. https://hackernoon.com/how-i-hacked-a-news-channel-to-report-fake-news-aa2f4b4f5b95 - hobbyist RFID reader under a table (search).
16. https://ryosuzuki.org/reactile/ - Reactile coil array (opened).
17. https://microbots.io/products/coilcell - CoilCell planar coil (opened).
18. https://cdn.shopify.com/s/files/1/0766/9855/0605/files/Flexar_12L_Datasheet_Rev1.6.pdf - Flexar 12L datasheet (search).
19. https://hackaday.io/project/158017-linear-pcb-motor - Bugeja linear PCB motor (search).
20. https://hackaday.io/project/179268/logs - DIY automatic chessboard build logs (opened).
21. https://indiegogo.com/projects/phantom-the-robotic-chessboard-made-of-real-wood ; https://tribune.com.pk/story/2481958/phantom-real-automated-chessboard-to-play-with-remote-friends-online ; https://www.chess.com/forum/view/chess-books-equipment/phantom-the-automated-chessboard-60945653?page=4 - Phantom chessboard (search).
22. https://sisyphus-industries.com/ - Sisyphus kinetic sand tables (opened).
23. https://thenextweb.com/news/review-sensels-morph-is-the-perfect-trackpad-controller-for-musicians-and-other-creatives - Morph dimensions (search); https://en.wikipedia.org/wiki/Sensel - company status (opened).
24. https://www.microsoft.com/en-us/research/publication/capacitivo-contact-based-object-recognition-on-interactive-fabrics-using-capacitive-sensing/ ; https://home.dartmouth.edu/news/2020/10/smart-tablecloth-can-find-fruit-and-help-watering-plants - Capacitivo, UIST 2020 (search).
25. https://howieliang.github.io/projects/GaussSense.html - GaussSense (opened); https://howieliang.github.io/projects/GaussSense/resources/GS_UIST.pdf (search).
26. https://personal.stevens.edu/~ychen6/papers/VibSense%20Sensing%20Touches%20on%20Ubiquitous%20Surfaces%20through%20Vibration.pdf - VibSense (opened, text extracted).
27. https://ubi-naist.github.io/paper/others/202306_IE2023_MakotoYoshida_Smatable.pdf - Smatable (search).
28. https://www.eti.uni-siegen.de/ubicomp/papers/lancs_uia2002.pdf - load-sensing table, 2002 (search; redirect failed).
29. https://patents.google.com/patent/US8921717 - weight magnitude and position systems (search).
30. https://news.mit.edu/2021/intelligent-carpet-gives-insight-human-poses-0624 (opened); https://cdfg.mit.edu/assets/files/Luo_CVPR2021.pdf (search).
31. https://unpaywall.org/10.1145%2F3580851 - NF-Heart, chair accelerometer authentication (search).
32. https://bohrium.dp.tech/paper/arxiv/5d0b00d88607575390fe746c - BCG identification with a fibre cushion (search).
33. https://researchconnect.buffalo.edu/en/publications/novel-biometrics-analysis-of-an-unattended-health-monitoring-syst/ - toilet-seat biometrics, BTAS 2018 (search).
34. https://pubmed.ncbi.nlm.nih.gov/24916920 - Meijer et al. 2014 CIT meta-analysis (search; AUC values second-hand).
35. https://www.frontiersin.org/articles/10.3389/fbuil.2017.00065/full (opened); https://patents.google.com/patent/US10614299 ; https://www.microsoft.com/en-us/research/wp-content/uploads/2014/10/ipsn_mmirshek.pdf (search) - footstep vibration sensing.
36. https://research.google/blog/hidden-interfaces-for-ambient-computing/ - Olwal and Dementyev, CHI 2022 (opened).
37. https://www.ischool.berkeley.edu/news/2016/color-changing-smart-thread-turns-fabric-computerized-display - Ebb (opened).
38. https://hcie.csail.mit.edu/research/chromoupdate/chromoupdate.html - ChromoUpdate, CHI 2021 (opened).
39. https://arxiv.org/abs/2407.09511 - Yamaguchi et al., illumination-spectrum colour control (opened); https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/9979853 ; https://library.imaging.org/cic/articles/18/1/art00005 (search).
40. https://en.wikipedia.org/wiki/Flicker_fusion_threshold - flicker and stroboscopic limits (opened).
41. https://pmc.ncbi.nlm.nih.gov/articles/PMC11401121/ - slow change blindness, J. Vision 2024 (opened); https://visualcognition.psych.northwestern.edu/publications/Simons_etal_gradual.pdf (search; 503).
42. https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/8933405 ; https://www.digitec.ch/en/page/infrared-photography-through-clothes-the-physics-behind-it-16731 ; https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/9951446 - near-infrared and textiles (search).
43. https://pmc.ncbi.nlm.nih.gov/articles/PMC5023966 - Zhou et al., Chladni plate manipulation, Nat. Commun. 2016 (opened).
44. https://la.disneyresearch.com/innovations/wireless-power-room/ (opened); https://arxiv.org/pdf/2502.05891 (search).
45. https://www.adafruit.com/product/5140 - inductive coil and 10 wireless LED kit (opened).
46. https://en.wikipedia.org/wiki/Qi_(standard) - Qi frequencies, distances, foreign-object detection (opened).
47. https://www.androidpolice.com/samsung-wireless-powershare-everything-you-need-to-know/ - reverse wireless charging (search).
48. https://www.bag.admin.ch/dam/en/sd-web/v8XQEESvnPtg/Fact%20sheet%20magnets.pdf - Swiss FOPH magnets fact sheet (opened, text extracted).
49. https://www.icnirp.org/cms/upload/publications/ICNIRPstatIR.pdf - ICNIRP static-field material (search).
50. https://en.wikipedia.org/wiki/Jean-Eug%C3%A8ne_Robert-Houdin (opened); https://gutenberg.org/cache/epub/36659/pg36659-images.html - Hopkins, Magic, 1897 (search; 503); Wikipedia "Théâtre Robert-Houdin" (search).
51. https://jimsteinmeyer.com/?p=956 - Steinmeyer on the Light and Heavy Chest (search).
52. https://en.wikipedia.org/wiki/Table-turning (opened); https://illusionrepository.com/?p=571 - floating table history (opened).
53. https://courses.physics.illinois.edu/ece445/getfile.asp?id=25235 - student RFID poker table (search); https://patents.justia.com/patent/20070052167 - RFID poker table application (search).
54. https://www.oneahead.com/p/close-up-mat-placement - composition on a close-up mat (opened).
55. https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/9776212 - ultrasonic transducer cover spacing (search).
