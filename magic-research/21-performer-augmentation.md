# 21. Performer augmentation: wearable robotics, body-worn conveyance, and body modification

Slice: what wearable engineering changes about secretly holding, moving, delivering, stealing and
ditching objects on the performer's body, and about what the performer can sense. The classical
ancestors are the sleeve holdout, the pull, the topit and the thumb tip.

Conventions used here. Numbers in square brackets point to section 7. "(unverified)" marks
anything recalled from memory or seen only in a search-result summary and not confirmed on the
page itself. "My calculation" marks arithmetic done for this report from cited inputs. Prices are
as of late 2026. Research note: the shared web-search budget ran out part-way through, so the
magic-forum side (performer complaints) and a few price checks are thinner than intended; section
6 lists what that left open.

## 1. Summary

- **The classical body-worn devices are already latch-and-spring machines, and their weaknesses
  are specific and fixable.** A pull or holdout stores energy in elastic and releases it; what it
  lacks is a latch that is not the performer's own arm or knees, a silent stop, a re-arm without
  the hands, and independence from a loose long sleeve. Buyer reviews of current products repeat
  the same four complaints: needs wide sleeves, fails in short sleeves, needs fiddly personal
  adjustment, and (disputed) noise [10][11]. Each of those now has an off-the-shelf engineering
  answer.
- **A sub-millimetre textile electrostatic clutch is the missing latch.** EPFL's textile clutch
  holds about 20 N per cm2 at 300 V, weighs 30 mg per cm2, draws about 1 mW per cm2 and engages or
  releases in under 15 ms [31]; a 2025 Northwestern design holds 22 N on 1 cm2 at 100 V [34]. It
  has no moving parts, so it has no click, and because it is a variable-friction brake it can
  also stop a moving line quietly. This is lab-built today, but the construction is film,
  electrode and a small high-voltage supply.
- **The 150 ms target is a spring problem, not a motor problem.** Moving a half-dollar-sized load
  35 cm in 150 ms needs about 0.17 J and a 4.7 W peak (my calculation). A 10 x 12 mm N20 gearmotor
  tops out near 1.5 W [63], so a motor alone manages roughly 0.3 to 0.4 s. A spring pre-loaded by
  that same motor and released by a silent latch does it easily. The motor's job becomes the
  hands-free reset.
- **Speed alone no longer hides anything from a phone.** Human pursuit fails above roughly
  90 deg/s and a corrective saccade takes 200 ms or more [64], so a 150 ms exit beats the eye. At
  240 fps a phone records 36 frames of it. The design rule is therefore: travel under cover, and
  make the exposed gap a few centimetres, crossed in under two high-speed frames.
- **Garment-scale conveyance exists in the HCI literature and nobody in magic has used it.**
  Calico (UMD, 2022) is an 18 g robot that runs on a sewn-in track at 115 to 227 mm/s carrying
  20 g, with turntables to change route [36]. That is a borrowed ring carried from one cuff to
  the other, or to the collar, in about six seconds with both hands in view. A motor-driven cord
  loop in a bonded fabric channel does the same job faster and more simply.
- **Pneumatics in the lining are now silent and flat.** A Murata piezo microblower is
  20 x 20 x 1.85 mm, runs at 26 kHz (above hearing), and gives about 2.5 kPa and 1.2 L/min [43].
  Heat-sealed pouch motors give 28% stroke and up to 100 N [44]. Together: pockets that open
  themselves, loads that eject themselves, and suction ports that hold a card with no grip. A
  spring-driven bellows and a lay-flat duct could draw a loose banknote or card up a sleeve with
  nothing attached to it (speculative, section 4.1).
- **Extra digits are easy to learn and easy to control with the feet.** The Third Thumb is a
  3D-printed flexible digit pulled by two wrist motors through Bowden cables and steered by
  pressure sensors under the big toes; 98% of 596 members of the public could use it within a
  minute [48][49]. The transferable part is less the thumb than the control scheme: two
  proportional, invisible, learnable channels in the shoes, where magic currently uses on/off
  toe switches [18][19].
- **Most of what implants offer performers is available without surgery.** Implanted magnets and
  NFC chips are in real use by at least three magicians [76][79][80]. A magnet glued to a nail or
  hidden under a ring gives a weaker version of the same sensing [68], NFC tags are sold as nail
  stickers [81][82][83], and one magician's password-locked implant is the cautionary tale [80].
  Risks are stated in section 2.11; no procedure is recommended.
- **An implanted or nail-mounted magnet is a battery-free receiver.** A coil in a watch can
  vibrate a magnet in the hand at 16 to 640 Hz as a private haptic channel [67]. The performer
  carries no electronics on the hand at all.
- **Bare arms remain the hard case.** With short sleeves the surviving real estate is the nail,
  the ring, the watch and its strap, the waistband, the collar and the shoes. The ideas that
  still work there are suction or adhesion at the wrist, magnets and tags on the nail, toe
  control, thread, and the cross-body routes that end at a collar or pocket.

## 2. Catalog

### 2.1 Classical baseline, stated as engineering specifications

| Device | What it does | Actuation and trigger | Limits as a spec |
|---|---|---|---|
| Kepplinger ("San Francisco") holdout, 1888 | Carries a card between palm and a double shirt sleeve on a slide with steel jaws | Cord from knee to knee through pulleys; spreading the knees extends the slide [1][2] | Seated only; long sleeve; one card or a few; sold at about $100 in the 1890s [2]; "considerable skill" still needed [1] |
| Arm-pressure, cuff, ring and vest holdouts | Hold cards out of play | Arm pressure or hand position [1] | Visible arm set; single position |
| Jack Miller holdout and its descendants (Vernet "Invisible Hand") | Elastic-driven retraction of balls, coins, silks, cards, watches up the sleeve | Arm extension stretches and releases | $55 device, about $138 with instruction set [7][8]; "requires lots of practice and adjustment" [9]; one-shot until reset by hand |
| Elastic pulls (De Kolta, 1875 onward) | Object in a cup or clip flies up the sleeve or under the jacket | Hand releases; elastic does the rest [15] | Object must be loaded into the pull; one shot; De Kolta already had a "bare-armed" pull that avoids the sleeve [14] |
| The Raven (Chuck Leach) | Vanish of small magnetic objects | Magnet on an elastic line | $39.95; buyers report it needs "decently big sleeves", short sleeves are "the main problem", no borrowed coins without a switch, close range for quarter-size objects, one review calls it loud and another disputes that [10] |
| Blackbird (Jeff Copeland) | Coin holdout in the sleeve | Gravity and sleeve | Fails with narrow cuffs or tapered sleeves [11] |
| Topit | Large hidden pouch in the jacket front | Throw under cover of a gesture [12] | Jacket required; standing; ditch only (Topit 180 adds steal and switch [13]) |
| Thumb tip, finger shells, sixth finger | Flesh-coloured hollow carriers | Worn and stolen away [22] | Passive; volume a few cm3; colour and angle sensitive (sixth finger from memory, unverified) |
| Thread reels (ITR, Tarantula II) | Reel in and pay out invisible thread | Spring, or motor in Tarantula II | $75; roughly 80 to 100 performances per charge by one user report [16][17] |
| Programmable reels (Joao Miranda Gravity Reel) | Motorised reel with stored motion programs | Toe switch in an insole starts a program or runs one motor live [18] | On/off control only |
| Quick-change costume rigging | Whole garment swap | Magnets, snaps, hook-and-loop, layering [23][24][25] | Hook-and-loop is loud; magnets are the quiet closure [24] |

Conjuring Archive indexes 504 published pull and holdout items [14], so the design space has
been worked hard by hand. What it has not had is powered reset, sensing, silent electrical
latches, or cheap pneumatics.

Common failure modes, collected from the sources above:

1. **Trigger is a visible body motion.** Knee spread, arm extension, a throw. The spectator
   theory "it went up his sleeve" is available because the arm did something.
2. **Single shot, manual reset** of 10 to 30 s (my estimate), so one use per routine.
3. **Sleeve dependence.** Wide, long sleeves or a jacket [10][11][12].
4. **End-of-travel noise** and the "snap" of elastic (reported, disputed) [10].
5. **The object must be prepared or attached**: magnetic, clipped, cupped [10].
6. **Per-performer fitting** by trial and error [9].

### 2.2 Tendons, winches and strings

**Bowden-cable tendons.** A motor at the waist or back pulls a cable inside a sheath to a
distant point, like a bicycle brake. Harvard's soft exosuits deliver around 300 N to the hip this
way from backpack-mounted actuators [30]; the Third Thumb uses the same thing at toy scale with
Teflon tube and wire [49]. *Accessibility:* PTFE tube and Dyneema or steel line are hobby parts.
*Magic relevance:* the actuator and battery can sit anywhere on the body, leaving only a 2 mm
sheath at the wrist. This removes the bulk argument against powered holdouts.

**Twisted-string actuators (TSA).** A small motor twists a pair of strings, which shortens
them. The twist acts as a very high gear ratio with no gearbox, so a small fast motor gives a
large quiet pull. A reported prototype with a Pololu 100:1 gearmotor lifted 2 kg; overtwisting
began after about 20 turns with two strings (search summary of the Bologna-line papers [29],
unverified against the paper). An exosuit patent family states full-stroke contraction in under
200 ms and bandwidth above 5 Hz with fast motors ([28], search summary, unverified). The MIT
twisted-winch hybrid adds a winch for long travel and reserves twisting for the final high-force
part [26]; a 2025 review covers modelling and wearable uses [27]. *Limits:* stroke is a fraction
of string length (commonly quoted near 25 to 30%, unverified), the string must run straight and
free, and life is finite. *Magic relevance:* strong, slow, near-silent pulls of a few centimetres
along a forearm or across the back: opening a pocket, releasing a body load, tensioning a
garment, drawing a flap.

**Micro-winch.** The N20 micro metal gearmotor is 10 x 12 mm in cross-section. Pololu's 6 V
high-power versions give 6500 rpm and 0.09 kg cm stall at 5:1, 3300 rpm and 0.17 kg cm at 10:1,
1100 rpm and 0.45 kg cm at 30:1 [63]. On a 10 mm spool the 5:1 motor gives about 3.4 m/s no-load
line speed and 1.8 N stall pull; peak mechanical power is about 1.5 W (my calculations). That is
the Tarantula class of device with ten times the pull. Gear whine is the cost (level not
measured here).

**Springs.** Elastic cord, badge-reel and tape-measure constant-force springs store the fraction
of a joule this job needs in a gram or two (order of magnitude from textbook energy densities,
unverified). The classical pull is correct in principle.

### 2.3 Latches, clutches and brakes

**Latch-mediated spring actuation (LaMSA)** is the biomechanics term for systems that load a
spring slowly and release it through a latch, so that output power is not limited by the motor.
Patek's review frames it as small energies (microjoules to millijoules) released over
microseconds to milliseconds [61]; engineered versions jump, launch and strike [62]. The useful
lesson for a wearable is that the *latch* sets the release profile and the noise, and the motor
only sets the reset time.

**The finger snap is a body-native LaMSA.** High-speed measurement gives a peak angular velocity
of 7,800 deg/s and peak angular acceleration of 1.6 x 10^6 deg/s2, complete in about 7 ms, with
skin friction between thumb and finger acting as the latch; lubricated or thimble-covered
fingers snap three to four times slower [60]. That is a fingertip at roughly 10 to 13 m/s (my
calculation), and about twenty times faster than a blink [60]. Relevance: it is the fastest
motion a hand can make, it is socially invisible as "the magic gesture", and it produces a sharp
sound that can serve as both a trigger and an acoustic mask (section 4.9).

**Electrostatic (electroadhesive) clutches.** Two overlapping flexible electrodes separated by a
thin dielectric lock together in shear when charged.

- DextrES (EPFL and ETH, UIST 2018): 20 N holding force per finger, whole glove under 8 g [32].
- Textile clutch (Hinchet and Shea, 2019): about 20 N per cm2 at 300 V, 30 mg per cm2, about
  1 mW per cm2, engage and release under 15 ms [31].
- Glove and sleeve formats (2022): 1.3 mm thick glove, up to 50 N per finger, plus elbow sleeve
  and shoulder cable versions [33].
- Northwestern multilayer design (Science Advances, Feb 2025): 22 N on 1 cm2 at 100 V; a soft
  interlayer spreads stress and stops peeling [34].
- CMU's earlier electroadhesive clutch for exoskeletons shows the same idea at larger scale [35].

*Accessibility:* lab-built; hobbyist-plausible with metallised film, a cast or laminated
dielectric and a current-limited boost module, but the high-permittivity polymer in [31] is a
speciality material. *Magic relevance:* a silent, flat, millisecond latch that holds a
spring-loaded line with tens of newtons and costs milliwatts; and, by ramping the voltage, a
silent brake. *Safety:* hundreds of volts on the body. Current-limit to microamps, insulate
fully, keep away from wet skin.

**Eddy-current braking.** A small magnet moving through a copper or aluminium tube is slowed in
proportion to its speed with no contact and no sound. Putting 5 to 8 cm of thin tube at the end
of a pull's travel, and a 2 g magnet on the shuttle, replaces the end-stop click with a soft
arrival (textbook physics; not found in magic literature in this search).

**Other quiet releases** (pointers to agents 7, 14 and 27): electropermanent magnets, shape
memory pins, burn-through thread, bistable springs.

### 2.4 Pneumatics inside clothing

**Pouch motors.** Flat heat-sealed plastic bladders that shorten when inflated. Linear pouches
reach about 28% stroke and up to 100 N; hinge pouches rotate up to 80 degrees [44]. Made with a
soldering iron or heat press from film. A pouch is under 0.5 mm thick when empty.

**Thin fluidic muscles and OmniFiber.** MIT's OmniFiber is a fluidic fibre 0.6 to 1.8 mm in
diameter with an embedded strain sensor, up to 19 N, machine-knittable, driven by the small
FlowIO pneumatic module [38][39]. Thin McKibben muscles paired with a stretchable
electrohydrodynamic pump give 0.84 N and 4 mm from a 2 g unit at 10 to 20 kPa [40].

**Silent pressure sources.**

- Murata MZB1001T02 microblower: 20 x 20 x 1.85 mm, piezo disc driven at about 26 kHz, typical
  1.2 L/min free flow and 2.5 kPa static at 21 V (rated 1.42 kPa minimum at 15 Vpp), about 0.2 W
  [43]. Across a 10 cm2 pouch, 2.5 kPa is 2.5 N; across a 1 cm2 sealed port it is 0.25 N, about
  fourteen times the weight of a playing card, taking a card as 1.8 g (my calculations; card
  mass from memory).
- EPFL stretchable pumps: solid-state, silent, about 10 kPa per 1 g module [41][42]. Lab-only.
- A spring-loaded bellows or syringe re-cocked by a motor: tens of kPa for a fraction of a
  second, silent until release. This is the pneumatic version of the LaMSA idea.

*Magic relevance:* the lining of a jacket can now contain flat actuators that push, open, close
and eject, powered by a coin-sized silent blower. See 4.1 and 4.5.

### 2.5 Shape-memory and active textiles (pointer: agent 7)

Knitted nitinol garments contract 4 to 50% but press on the body at only about 10 mmHg and work
on thermal timescales of seconds [45]; KnitDema modulates SMA compression by PWM [46]. Useful for
slow, silent, strong-enough jobs (cinching a cuff shut after a load passes), not for conveyance.

### 2.6 Conveyance on and inside garments

**Rovables (MIT and Stanford, UIST 2016).** Untethered robots that grip unmodified cloth between
magnetic wheels and climb vertically; 45 minutes of running; carry up to 1.5 N [37][93]. Speed is
at most about 50 mm/s by the Calico authors' estimate [36]. Trouble with seams and thick cloth.

**Calico (Univ. of Maryland, IMWUT 2022).** A two-wheel robot on a sewn-on flexible track with
magnets and Hall sensors for localisation. Robot 42 x 32 x 35 mm, 18 g; carries 20 g; 115 mm/s
worst case to 227 mm/s; positioning to about 4 mm; "turntables" switch between tracks so one
robot reaches arms, torso and legs [36][94]. A US quarter is under 6 g and a half dollar about
11 g (unverified from memory), so the payload is in range. *Concealment:* the track has a 3 mm
centre wall; it must live inside a lined jacket. *Noise:* geared micro-motors; not measured.

**Cord-loop shuttle (derived design, not a published system).** A closed loop of cord in a PTFE
tube or bonded fabric channel from one cuff, across the shoulders, to the other cuff, driven by
one N20 at the back of the collar. At 1 to 2 m/s line speed [63] a 1.4 m crossing takes about a
second. This is a clothesline; it is simpler, faster and quieter than a robot, and it reverses.

**Through-fabric magnetic shuttle.** A magnet on that loop, inside the lining, drags a
ferromagnetic object on the *outside* of the cloth. Many current UK and Canadian coins are
plated steel (unverified from memory), so in those countries a borrowed coin qualifies.

**Peristaltic transport.** Ring-shaped pneumatic modules that squeeze and shift an object along
a tube exist as fixed stations [47]. A wearable sleeve version is conceivable and silent but
slow (cm/s). No wearable instance found.

### 2.7 Extra digits and powered hands

**Third Thumb (Dani Clode; UCL then Cambridge).** Flexible printed digit (NinjaFlex, about Shore
85A) with resin hand and wrist mounts; two wrist motors pull Bowden cables; two pressure sensors
under the big toes send proportional commands by Bluetooth, one per degree of freedom
[49][50]. In a 596-person public test, 98% manipulated objects within the first minute [48].
Training with it changed the brain's hand representation [51] (five days, from memory,
unverified). Not sold; build details are
public enough to copy.

**Supernumerary fingers.** MIT's wrist-mounted pair follows the wearer's own grasp synergies
without explicit commands [52]. Siena's Sixth Finger is a forearm-worn opposing digit for stroke
patients, commanded from a ring switch on the other hand; the soft version weighs 140 g [53].

**Tendon gloves.** SNU's Exo-Glove Poly routes tendons through a polymer glove from a remote
actuation unit [54]. A glove is not deceptive at close range.

*Magic relevance:* (a) openly worn, an extra digit is a presentational premise, the lowest level
of use; (b) the *toe-proportional control scheme* transfers directly to reels and holdouts; (c) a
soft tendon-driven digit that lives in the cuff is a holdout that can grasp (section 4.4).

### 2.8 Adhesion and holding on the bare hand

- **Gecko-type directional dry adhesive.** Stanford's hand-sized pads carried a 70 kg climber on
  140 cm2 per hand, which is roughly 50 kPa of working shear (my calculation), on clean smooth
  glass only [55]. Grips when loaded in shear, releases when unloaded, no residue. Works on
  phone glass, gloss plastic cards; poorly on embossed playing cards and coin relief (my
  assessment). Retail availability not confirmed.
- **Octopus-type suction skins.** A Virginia Tech glove switches adhesion by more than 450 times
  in under 50 ms using pneumatically actuated membranes triggered by micro-LIDAR proximity
  sensors, above 60 kPa underwater [56]. Passive micro-patterned patches adhere to wet, dry and
  hairy skin [57]. Lab-level, but it shows sensor-triggered grip with no finger closure.
- **Electroadhesion pads.** A 10 x 10 mm interdigitated pad at 5 kV gave about 35 kPa shear and
  13 kPa pull-off, enough to lift paper flat ([58], from the search summary, unverified against
  the paper); robot "electroadhesive fingers" lift an egg or a sheet of paper [59]. At even a
  tenth of that, 1 cm2 holds a card. *Safety:* kilovolts on the hand; must be current-limited
  and fully insulated. Speculative for skin use.
- **Micro-blower suction port.** From 2.4: 0.25 N of hold per cm2 of sealed port with a silent
  blower. No high voltage, no residue, works on any smooth card or bill.
- **Magnets on the hand.** Ring magnets (the PK ring family), magnets under a nail overlay, and
  implanted magnets (2.11). Need a ferromagnetic or shimmed object.
- **Reusable tack.** Polyurethane gel pads, micro-suction tape, magician's wax, prosthetic
  adhesives (pointer: agent 15). Cheap, unglamorous, and the practical choice for most "hold
  with an open hand" needs.

### 2.9 How fast is fast enough (body-worn view; general treatment is agent 27's)

- Smooth pursuit keeps up to about 90 deg/s; above about 30 deg/s catch-up saccades are needed;
  pursuit starts 100 to 130 ms after motion onset and a voluntary saccade takes 200 to 250 ms
  [64]. Vision is further degraded during the saccade itself [65].
- A 35 cm palm-to-elbow path seen from 50 cm spans about 39 degrees. Done in 150 ms that is about
  260 deg/s and is over before a saccade can launch (my calculation). The task's 150 ms figure is
  the right target for the unaided eye.
- Requirements for that move with a 16 g load (coin plus carrier): 62 m/s2, 4.7 m/s peak, 1 N,
  0.17 J, 4.7 W peak (my calculation).
- At 240 fps the same move occupies 36 frames. A 3 cm uncovered gap at 4.7 m/s lasts 6 ms, under
  two frames.
- Belief and expectation matter as much as speed: in Kuhn and Land's vanishing-ball study the
  ball never left the hand, and half the viewers saw it fly [66].

### 2.10 Performer senses

**Magnet as a sense organ.** A small magnet under the skin moves in external fields and the
surrounding touch receptors feel it. A Reading University pilot found implanted magnets beat
surface-attached ones on absolute intensity threshold but not on frequency discrimination
[68][69], so a nail-mounted magnet is a weaker but real substitute. Strohmeier and McIntosh
drove a 2 x 4 mm Parylene-coated magnet in the palm from a coil in a watch-like device and
mapped perceived strength from 16 to 640 Hz; they also tracked the magnet's position as an input
[67]. *Relevance:* a private receiver with no battery, no wire and nothing to find on the hand;
and a way to feel an alternating field from a prop.

**Vibrotactile belts and compass devices.** The feelSpace belt (north always vibrates) changes
spatial behaviour after weeks of wear but does not produce a "felt field" [86]. The North Sense
was a chest-pierced compass buzzer released in 2017; current availability unknown [87]. A
performer who always knows north, blindfolded, is a level-1 stunt.

**Hearing aids as covert superhuman hearing** (pointer: agents 10 and 15). Directional
microphones give about 3 dB of signal-to-noise gain; binaural beamformers 6 to 7 dB, with
manufacturer claims of 9 to 10 dB for recent AI processing [88]. A remote microphone near the
talker beats all of them [88]. Receiver-in-canal aids are near-invisible and socially
unremarkable.

### 2.11 Body modification (capability report; not a recommendation)

**What performers have done.**

- Anastasia Synn: 26 implants in 2019, 52 by 2023 (a Guinness record). Magnets for coin work and
  for holding anything ferrous; chips for doors and data; a planned leg computer relaying
  through a hairpiece to vibrate a magnet near her ear as a private cue [76][77][78]. More than
  half were self-implanted; she reports quarterly liver and kidney blood tests because the
  coatings are not medically approved [76].
- Patrick Kramer performed a card trick with an xNT NFC implant in the web of the thumb at CeBIT
  2016 [79].
- Zi Teng Wang's RFID implant became unusable after he lost its password, and the trick was
  reportedly unreliable because reads depended on exact hand placement ([80], seen in search
  results only; page returned 403).

**Hardware.** Dangerous Things xSIID: 13.56 MHz NTAG I2C chip with an LED that lights from the
reader field, 888 bytes user memory, injectable glass capsule, about $177 on one listing (unverified which seller) [73]. Biomagnets: the
Titan (4.5 x 2.5 mm, N52, about 2.9 kG at the faces; under redesign) [70]; the xG3 injectable
(3 mm by 13 to 15 mm, $129) shown lifting a chain of paperclips [71][72]. No lift ratings in
grams are published; forum users rank the xG3 above the Titan for lifting [95].

**Risks, plainly.**

- These are unregulated devices implanted outside medicine. Infection, migration, rejection and
  nerve damage are possible; removal is a minor surgical procedure.
- Magnets: coating breach leads to corrosion and tissue reaction; sensation can fade through
  tissue changes [70]. A magnet in the body is a serious problem for MRI and must always be
  disclosed. Synn's public claim that this is a myth is her opinion, not evidence [78].
- NFC glass capsules: one independent paper found an NFC device MR-conditional at 1.5 and 3 T
  with under 2 C heating, device unnamed [75]; the vendor claims compatibility [74].
- Battery-powered implants add leakage and fire risk; Synn herself rates these the most
  worrying [76].
- Lock-out and obsolescence: see Wang [80].

**Non-invasive substitutes that give most of the capability.**

| Implant capability | Substitute |
|---|---|
| NFC chip in hand | NFC nail sticker under gel polish [81][84]; 5 x 5 mm flexible tags [83]; LED nail stickers that light in a reader field [82]; NFC ring; tag inside a thumb tip |
| Fingertip magnet for lifting | Magnet under a nail overlay or in a ring (pointer: agent 15 for nails) |
| Fingertip magnet for sensing | Magnet on the nail; weaker intensity threshold, same frequency discrimination [68] |
| Sub-dermal LED | LED nail sticker [82] |
| Fingernail electronics | NailO showed a full capacitive trackpad, radio and battery on a thumbnail in 2015 [85] |

### 2.12 Clothing as apparatus

- **Channels and pockets.** Heat-bonded seam tape and TPU film make flat, airtight, snag-free
  channels in a lining with a household iron or heat press; whole-garment knitting can knit
  tubes in (trade detail: agent 15). The same seal that makes a channel makes a pouch motor [44].
- **Power to a hand-held prop.** Embroidered and printed textile coils at 6.78 MHz deliver 3 W
  (all-textile receiver, over 20% end to end) to 15 W (printed receiver), and a glove with two
  embroidered receivers has been shown [89]. A coil in the cuff or forearm can power a prop that
  contains no battery and no switch, which makes the prop thinner and more examinable (pointer:
  agent 14).
- **Thermal zones.** Carbon-fibre heating pads and small Peltier modules hold a pocket at a set
  temperature, keeping a thermally triggered gimmick armed or safe (pointer: agent 7).
- **Shoes.** The largest hidden rigid volume on the body. Proportional toe sensors [48][49];
  insole on/off switches already sold for reels and flash devices [18][19]; one reviewer notes
  the switch shifts while walking and is a weak point [20]. An insole duress switch appears in a
  1980s patent [92]. Heels take battery packs; soles take magnets and readers ("Sole Snatcher" is a
  non-electronic card-to-shoe [21]).
- **Watch and strap.** Coil for magnet haptics [67], reel, suction port, blower, clutch
  electronics. The only bare-arm housing near the hand.
- **Collar, hat, hair, glasses, mask.** Housings for the far end of a cross-body route, for
  cameras and for bone-conduction audio (pointer: agents 10 and 11). Synn's planned hairpiece
  relay is a real example [76].

### 2.13 Training technology

- **Hand tracking.** MediaPipe Hands gives 21 3D keypoints per hand in real time on a phone
  [90]. Finger-on-finger occlusion is its known weakness, and sleights are mostly occlusion.
- **What skilled deception looks like in data.** Motion capture shows magicians' pantomimed
  grasps match real grasps when a real object is visible nearby, and are no better than
  laypeople's when it is not [91]. Naturalness is measurable, and it is calibrated from vision of
  a real object.
- **High-speed phone video** (240 fps) and the toe-control learning curves in [48][51] suggest
  short, instrumented practice loops.
- **Automatic angle checking.** No existing tool was found before the search budget ran out
  (unverified absence). Two buildable versions: (a) three or more cameras at audience eye
  positions with a detector that flags frames where the hidden object's colour is visible; (b) a
  tracked hand model and a ray-cast from each seat. See 4.10.

### 2.14 What survives short sleeves

| Location | What can live there | Reach to the hand |
|---|---|---|
| Nail | Magnet, NFC tag, LED, thin electrode | Zero |
| Ring | Magnet, tag, switch, tiny reel | Zero |
| Watch and strap | Blower, suction port, coil, reel, MCU, battery | 3 to 8 cm |
| Waistband and pockets | Motors, bellows, batteries | Thread only |
| Collar and neckline | End of a thread or cord route | Thread only |
| Shoes | Controls, power, magnets | Floor |

## 3. Capability primitives

1. *Now possible:* hold 20 N on a 1 cm2 flat strip and release it in under 15 ms with no moving
   part and no sound, for about 1 mW. *Because:* textile electrostatic clutches [31][34].
   *Before:* mechanical catches that click, or the performer's own grip. *Primitives:* hold /
   release, erase evidence (no click).
2. *Now possible:* stop a moving line or shuttle quietly by ramping clutch voltage, or with a
   magnet in a copper tube. *Because:* variable-friction clutches [33]; eddy-current braking.
   *Before:* a pull hit the end of its elastic. *Primitives:* move, conceal (sound).
3. *Now possible:* re-arm a spring pull in 1 to 2 s without touching it. *Because:* 10 x 12 mm
   gearmotors with 0.45 kg cm at 30:1 [63]. *Before:* one shot per routine, reset by hand.
   *Primitives:* move, hold.
4. *Now possible:* put motor, battery and electronics at the waist or back and deliver the pull
   at the wrist through a 2 mm sheath. *Because:* Bowden tendons as in exosuits and the Third
   Thumb [30][49]. *Before:* the whole machine sat on the forearm. *Primitives:* conceal, move.
5. *Now possible:* a 5 to 7 cm pull of tens of newtons from a pencil-thin, gearbox-free
   actuator. *Because:* twisted-string actuators [26][27][29]. *Before:* strong pulls needed the
   performer's limbs. *Primitives:* move, hold.
6. *Now possible:* carry 20 g to any pre-laid point on a garment at up to 227 mm/s, with
   branching routes and 4 mm positioning. *Because:* Calico track robots [36]. *Before:* a second
   duplicate object, or the hands. *Primitives:* move, delay, swap.
7. *Now possible:* cross from cuff to cuff or cuff to collar in about a second on a motor-driven
   cord loop in a bonded channel. *Because:* micro-winch speeds of 1 to 3 m/s [63] plus cheap
   PTFE tube. *Before:* cross-body elastic pulls went one way, once. *Primitives:* move, swap.
8. *Now possible:* 2.5 kPa of silent air from a 20 x 20 x 1.85 mm part. *Because:* piezo
   microblowers at 26 kHz [43]. *Before:* squeeze bulbs and audible diaphragm pumps.
   *Primitives:* hold / release, move.
9. *Now possible:* flat actuators in a lining that give 28% stroke and up to 100 N, made with an
   iron. *Because:* pouch motors [44]. *Before:* none. *Primitives:* move, release, conceal
   (zero thickness at rest).
10. *Now possible:* hold a card or banknote against a 1 cm2 port with about fourteen times its
    weight and no grip, magnet, wax or clip. *Because:* microblower static pressure [43] (my
    calculation). *Before:* palms, clips, wax. *Primitives:* hold / release, prove ordinariness
    (object unprepared).
11. *Now possible (speculative):* draw an unprepared flat object 35 cm up a lay-flat duct in
    under 100 ms. *Because:* a spring bellows gives 2 to 10 kPa across the duct section (my
    calculation, section 4.1). *Before:* the object had to be clipped to a pull. *Primitives:*
    move, prove ordinariness.
12. *Now possible:* two proportional, invisible control channels with a one-minute learning
    curve. *Because:* toe pressure sensors as validated on 596 people [48]. *Before:* on/off toe
    switches [18][19]. *Primitives:* control, tell.
13. *Now possible:* a grasping, releasing extra digit with two degrees of freedom, printed in
    flexible filament. *Because:* Third Thumb architecture [49][50]. *Before:* steel jaws on a
    slide (Kepplinger). *Primitives:* hold, move, steal.
14. *Now possible:* trigger hardware from a finger snap within a few milliseconds, with the snap
    covering the hardware's own sound. *Because:* the snap is a 7 ms, high-acceleration,
    high-level acoustic event [60]; MEMS microphones and accelerometers cost cents (pointer:
    agent 14). *Before:* triggers were hidden switches. *Primitives:* tell, conceal (sound),
    control.
15. *Now possible:* a private haptic receiver with no battery or electronics on the hand.
    *Because:* a coil can vibrate a small magnet at 16 to 640 Hz [67]; nail-mounted magnets
    retain frequency discrimination [68]. *Before:* thumpers with batteries strapped to the body.
    *Primitives:* tell, prove ordinariness (hands empty).
16. *Now possible:* feel an alternating magnetic field through a fingertip. *Because:* same
    magnet [68][69]. *Before:* could not. *Primitives:* know.
17. *Now possible:* carry an NFC identity or a field-lit LED on a fingernail under ordinary
    polish. *Because:* nail tags and stickers [81][82][83]. *Before:* palmed tags or implants.
    *Primitives:* tell, know, prove ordinariness.
18. *Now possible:* deliver 3 to 15 W across a few centimetres from a sleeve to a battery-free
    prop. *Because:* textile coils at 6.78 MHz [89]. *Before:* props carried batteries and
    switches. *Primitives:* prove ordinariness, tell.
19. *Now possible:* move a ferrous object on the outside of cloth from inside the lining, along a
    programmed path. *Because:* cord-loop or Calico shuttle carrying a magnet [36]. *Before:* a
    hand under the cloth. *Primitives:* move, animate.
20. *Now possible:* 6 to 10 dB better speech pickup in noise from near-invisible ear devices.
    *Because:* binaural beamforming hearing aids [88]. *Before:* cupped ears and stooges.
    *Primitives:* know.
21. *Now possible:* measure how natural a sleight looks, frame by frame. *Because:* 21-keypoint
    hand tracking on a phone [90] plus the finding that naturalness is a measurable kinematic
    property [91]. *Before:* a mirror and a mentor. *Primitives:* (training) conceal.
22. *Now possible:* keep an exposed transit under two frames of 240 fps video by confining it to
    a 3 cm gap at about 5 m/s. *Because:* spring release with a low-mass shuttle (my
    calculation). *Before:* relied on the eye's limits only [64]. *Primitives:* move, conceal.
23. *Now possible:* a pocket or pouch that is sealed shut except during a commanded 300 ms
    window. *Because:* pouch motors, TSA or SMA on a bistable mouth [44][26][45]. *Before:* a
    topit was always open and could be found. *Primitives:* conceal, prove ordinariness.
24. *Now possible:* locate the heavy parts in the shoe. *Because:* heel volume plus trouser-leg
    cable routes; insole products already exist [18][20]. *Before:* everything on the torso.
    *Primitives:* conceal.

## 4. Effect concepts

Level refers to the brief's three levels of use. Seven of the ten are level 2 or 3.

### 4.1 The air pull: a pull with nothing attached to the object (level 3, speculative)

*Effect.* A borrowed banknote, signed and held at the fingertips of an otherwise empty hand, is
gone. It is later found somewhere impossible, or returns to the fingertips.

*Method sketch.* A lay-flat duct of bonded TPU-coated fabric, about 70 mm wide and 2 mm open,
runs inside the sleeve from the cuff to a spring-loaded bellows of 200 to 300 mL at the upper arm
or back. A latch (clutch strip or electropermanent magnet) releases the bellows; pressure in the
duct drops by a few kPa; the note or card, presented edge-on to the duct mouth under the cover of
the fingers, is drawn in. A playing card in a 65 x 2 mm duct presents 1.3 cm2: at 2 kPa that is
0.26 N on 1.8 g, about 140 m/s2, and 35 cm in roughly 70 ms (my calculation). A 30:1 N20 re-cocks
the bellows in about 2 s. Reversing the bellows returns the object. An eddy or felt section at
the top stops it quietly.

*BOM and cost.* TPU fabric and seam tape, printed bellows frame and spring, N20, latch, small
MCU and cell: about $40 to $80 (unverified estimate).

*Difficulty.* Medium to hard. The physics is simple; leakage around a loose card, duct collapse
under suction (needs ribs or spacer mesh), and the sound of the air pulse are unknowns.

*Risks.* Paper flutter at entry; a hiss; the cuff must sit close to the fingers. Long sleeve
required.

*Novelty.* I found no pneumatic sleeve vanisher in the sources reached; the classical pull always
grips the object [14][15]. Believed new, pending a proper prior-art check.

### 4.2 The re-arming silent pull (level 2)

*Effect.* As a classical pull or Raven vanish, but repeatable several times in one routine, with
the arm still, and silent.

*Method sketch.* Elastic or constant-force spring drives a 3 to 5 g shuttle on a line inside the
sleeve. A 1 cm2 electrostatic clutch strip on the line holds it armed (20 N available against 1
to 3 N needed [31]). Release is a voltage drop. The shuttle enters a 6 cm copper tube and stops
without a click. A back-mounted N20 rewinds through a Bowden sheath in about 1 s. Trigger: toe
pressure or a snap (4.9). A simpler first build replaces the clutch with a micro-servo latch and
accepts a faint click.

*BOM and cost.* N20, PTFE sheath, elastic, copper tube, clutch film and HV module or servo,
MCU: $30 to $90 (unverified).

*Difficulty.* Easy with a servo latch; hard with a home-made clutch.

*Risks.* High voltage on the body with the clutch version. Line tangles.

*Novelty.* Incremental but real: it removes three of the six failure modes in 2.1.

### 4.3 Cross-body shuttle: a borrowed ring travels with the hands apart (level 3)

*Effect.* A borrowed finger ring is closed in the left fist. Both arms are spread. It is gone
from the left hand and drops from the right sleeve into the right hand, or is found hanging at
the performer's collar, or in a back pocket.

*Method sketch.* A cord loop in a bonded channel from left cuff across the shoulders to right
cuff, with a small spring clip or magnet cup as carrier, driven by one motor at the nape. The
ring is loaded into the carrier at the left cuff under cover of closing the fist, transits 1.4 m
in one to two seconds, and is released at the far cuff by a cam at the end of travel. A branch
(Calico-style turntable or a simple Y with a second loop) ends at the collar. A Calico-type
robot is the slower, track-based alternative [36].

*BOM and cost.* Jacket, PTFE tube or seam-taped channel, Dyneema loop, N20, MCU, cell: about $30
plus the jacket.

*Difficulty.* Medium. Mostly tailoring and friction management around the shoulder bend.

*Risks.* Motor whine in a quiet room; the carrier jamming at a bend; jacket required.

*Novelty.* Cross-body elastic pulls are old [14], but they are one-way and end in a ditch. A
powered, reversible conveyor that *delivers* a unique borrowed object at the far side removes the
duplicate and the hand-to-hand contact. Believed new in this form.

### 4.4 The prehensile holdout (level 3)

*Effect.* The performer's hands are shown empty, front and back, fingers spread, slowly. A
moment later a selected card, coin or small object is at the fingertips. Or the reverse.

*Method sketch.* Replace the Kepplinger slide and steel jaws with a soft printed digit that
lives inside the cuff and is driven by two Bowden tendons from motors at the upper arm or back,
exactly as the Third Thumb is built [49]. One tendon extends and curls the digit; the second
closes a compliant two-pad gripper at its tip. Proportional toe pressure controls both [48]. The
digit reaches about 8 cm past the cuff on the palm side, takes or presents the object under the
cover of the hand's back, and withdraws. Unlike a slide, it can pick an object off the palm
rather than needing it fed into jaws, and it can hand it back at a chosen angle.

*BOM and cost.* TPU print, PTFE tube, line, two N20s or small servos, two force-sensing
resistors, two MCUs with radio: about $60 to $120 (unverified).

*Difficulty.* Medium. Published Third Thumb descriptions give the architecture.

*Risks.* Seen from below or the side. Slow (0.5 to 1 s). Long sleeve.

*Novelty.* High. Supernumerary digits have not appeared in the magic sources reached except as
open display.

### 4.5 The pocket that is not there (level 2)

*Effect.* An object is tossed and vanishes, topit-style. Afterwards a spectator is invited to
open the performer's jacket, pat it and look.

*Method sketch.* The topit mouth is a bistable sprung lip held flat and shut against the lining
by magnets, opening only when a pouch motor or twisted-string actuator [44][26] pulls it for 300
ms, timed by a snap or toe trigger. A second pouch, inflated by a microblower [43], then pushes
the load down a channel to the back hem, away from the chest, so that the front of the jacket is
empty. Knitted SMA [45] can cinch the channel closed behind it.

*BOM and cost.* Film, seam tape, microblower and driver, N20, MCU: about $60 to $100
(unverified).

*Difficulty.* Medium; mostly sewing.

*Risks.* Timing; the open window must coincide with the throw.

*Novelty.* The Topit 180 changed what a topit can do by hand [13]; an actively gated, self-
emptying one was not found.

### 4.6 The coin that walks (level 2, with a level-1 surface)

*Effect.* A borrowed coin laid on the performer's forearm crawls up the sleeve to the shoulder,
or vanishes under one hand at the wrist and is found already sitting at the shoulder.

*Method sketch.* The cord-loop shuttle of 4.3 carries a 10 x 3 mm neodymium disc inside the
lining. The borrowed coin must be ferromagnetic: many UK and Canadian coins are plated steel
(unverified). Elsewhere the performer switches in a steel-cored duplicate by sleight, which is
exactly the pairing the brief asks for: the sleight explains away "switched", and the travel
explains away "sleight".

*BOM and cost.* As 4.3 plus a magnet: about $30.

*Difficulty.* Easy to medium.

*Risks.* Reads as "magnet" if the coin is not examined before and after; cloth drag.

*Novelty.* Low to medium. Magnetic animation is old; a programmable path on the body is not.

### 4.7 The empty-handed receiver (level 2)

*Effect.* A mentalism or identification effect with the performer's hands and wrists visibly
bare and examinable: which hand holds the coin, which cup, what card.

*Method sketch.* The information is sensed elsewhere (agents 10 and 22). The *tell* channel is a
1 to 2 mm magnet under a nail overlay or a clear polish dome. A coil under the close-up mat, in
the table edge or in a watch drives it at around 200 to 250 Hz in coded bursts [67]. The
performer feels a buzz in the nail. There is no battery, wire or electronics on the hand, and a
magnet that small passes inspection. The same magnet lets the performer feel an alternating
field from a hidden source [68].

*BOM and cost.* Magnet, coil, H-bridge, MCU: under $20.

*Difficulty.* Easy. Range and felt strength with a nail-mounted (not implanted) magnet need
testing; [68] says intensity threshold is worse than an implant.

*Risks.* Field strength needed at a distance; do not bring strong coils near anyone with an
implanted medical device.

*Novelty.* Medium. Implant-based cueing is discussed by Synn [76]; a nail magnet with a table
coil as a deliberate method was not found.

### 4.8 Foot-flown animation (level 2)

*Effect.* A borrowed light object rises, pauses, drifts and settles with both of the performer's
hands far from it and motionless.

*Method sketch.* A body-worn motorised thread reel (Tarantula or Gravity Reel class [16][18])
whose speed and direction follow proportional pressure under the two big toes, the control
scheme validated for the Third Thumb [48]. Today's toe switches start a canned program [18];
proportional control lets the performer respond to the room and removes the hand and body
motions that currently work the thread.

*BOM and cost.* Two force-sensing resistors in an insole, a small radio MCU, an N20 with a
thread spool: about $30.

*Difficulty.* Easy.

*Risks.* Thread visibility and lighting, as always (agent 9's territory).

*Novelty.* Low as an effect; a clear improvement as a method.

### 4.9 The snap as trigger and mask (level 2)

*Effect.* None by itself. Any release, launch or change on the performer's body happens exactly
on a finger snap, with no visible or audible actuation.

*Method sketch.* A MEMS accelerometer or microphone at the wrist detects the snap impulse and
fires the actuator within a few milliseconds. The snap completes in about 7 ms and is loud and
broadband [60]; an actuator click that follows within about 10 ms should be hidden by auditory
masking (window not verified here). The trigger is a gesture audiences already read as "the
magic moment", so it needs no cover.

*BOM and cost.* Under $10.

*Difficulty.* Easy.

*Risks.* False triggers from claps or table knocks; solve with a two-snap arming pattern.

*Novelty.* Sound triggers certainly exist in props; pairing with masking as a design rule is the
contribution.

### 4.10 The angle and naturalness auditor (training tool; supports every level-2 pairing)

*Effect.* None. A hobbyist learns a classic palm or a pull's handling in weeks instead of months
and knows exactly which seats can see it.

*Method sketch.* Three phones or webcams at left, centre and right audience eye positions. The
hidden object is a saturated colour for practice. Software flags every frame in which that
colour is visible (a "flash"), and MediaPipe hand keypoints [90] are compared with the same
performer's empty-hand baseline to score how far the concealing hand departs from natural
[91]. Add 240 fps capture for speed work.

*BOM and cost.* Phones already owned; software only.

*Difficulty.* Easy for an LLM-assisted build.

*Risks.* Hand tracking degrades in exactly the occluded poses that matter.

*Novelty.* Not found in the sources reached (search incomplete).

## 5. Dead ends and overhyped items

- **A secret extra thumb on a bare hand.** The Third Thumb is as large as a thumb and needs a
  wrist unit [49]. It is a premise, not a method, unless it lives in a sleeve (4.4).
- **Exo-gloves to "hold a palm without tension".** Any glove ends the deception [54]. Adhesion
  or suction solves the same problem with nothing worn.
- **HASEL and dielectric-elastomer muscles in clothing.** Kilovolt drive and lab fabrication
  (pointer: agent 7). The clutch gives the useful part at a tenth of the voltage [34].
- **SMA garments for fast moves.** 10 mmHg and seconds [45].
- **Stretchable electrohydrodynamic pumps.** Silent and elegant, 10 kPa per gram [42], but not
  buildable at home; the Murata blower is a catalogue part [43].
- **Free-roaming cloth robots on visible clothing.** About 50 mm/s, 45 minutes, defeated by
  seams [36][37], and plainly visible.
- **Motor-only winches for sub-150 ms travel.** Power-limited to about 1.5 W in the N20 class
  [63] (my calculation).
- **Speed as the whole method.** Sufficient for the eye [64], not for slow-motion video.
- **Electroadhesion on embossed playing cards or skin-mounted kilovolt pads.** The numbers work
  on smooth or conductive targets [58]; the safety and visibility problems on a palm do not
  justify it when a silent suction port exists.
- **Gecko adhesive for cards and coins.** Needs clean, smooth, flat surfaces [55].
- **Implants as a shortcut.** Real, used, and mostly replaceable by a nail sticker or a nail
  magnet (2.11). Wang's locked chip [80] and Synn's quarterly blood tests [76] are the fair
  summary of the cost side.
- **Compass senses.** feelSpace and North Sense change navigation, not perception of a field
  [86][87]; little method value.
- **Peristaltic sleeves.** Slow, and no wearable version exists [47].
- **Magnetic tattoos, sub-dermal battery LEDs.** Nothing usable confirmed in this search.

## 6. Open leads

- **Build and measure the air pull (4.1).** Leak rate around a loose card, required bellows
  volume, sound level, and whether a banknote enters cleanly are all unknown.
- **Measure noise.** No decibel figures were found for N20 gearmotors, coreless direct drive,
  twisted strings or clutch release at 30 cm. This decides most of section 4.
- **Twisted-string primary numbers.** The force, stroke and speed tables in [27] and the
  patent's 200 ms claim [28] were not opened.
- **Hobby route to an electrostatic clutch.** Which off-the-shelf films reach even 2 N per cm2 at
  300 V; safe miniature supplies (pointer: agent 14).
- **Nail-magnet sensitivity.** Range at which a 2 mm nail magnet can be felt from a 20 mm coil;
  [68] and [69] should have thresholds.
- **Maskelyne's "Sharps and Flats" (1894)** for the original holdout specifications and failure
  reports [5]; the Gutenberg page was unavailable.
- **Magic-forum evidence** on what fails with reels, pulls and holdouts; the search budget ended
  before this was done, so 2.1 rests on retailer reviews.
- **Retail gecko and micro-suction materials**, and which coins by country are steel-cored.
- **Prior art checks** for a pneumatic sleeve vanisher, powered cross-body conveyors and
  automatic angle-checking software.
- **Auditory masking window** after a finger snap, to confirm 4.9.
- **The Wang implant story** [80] and current Dangerous Things pricing, from the primary pages.
- **Octopus-style sensor-triggered grip** [56] reduced to one suction cell under a watch strap.

## 7. Sources

1. https://en.wikipedia.org/wiki/Holdout_(gambling) - holdout types; Kepplinger 1888; skill still required.
2. https://www.ripleys.com/stories/kepplinger-style-card-holdout-device - Kepplinger mechanism, knee cable, $100 price (via search summary).
3. https://www.casino.org/blog/stealing-machines/ - R. Paul Wilson on holdout machines (seen in results, not opened).
4. https://vault.si.com/vault/1974/05/27/how-to-win-at-poker-always - Sports Illustrated account of holdouts (seen in results).
5. https://www.gutenberg.org/ebooks/41169 - Maskelyne, Sharps and Flats (1894); fetch failed, not read.
6. https://www.vanishingincmagic.com/holdouts/ - retailer overview of holdouts.
7. https://vanishingincmagic.com/holdouts/the-invisible-hand - Vernet Invisible Hand, $55, Jack Miller lineage.
8. https://www.tannens.com/products/the-invisible-hand-device-onl - object types it handles.
9. https://cupsandballsmagic.com/Vernet-Invisible-Hand.php - review: rugged; practice and adjustment.
10. https://www.penguinmagic.com/p/86 - The Raven, $39.95, buyer complaints (via search summary; page returned 403).
11. https://penguinmagic.com/reviewcomments.php?rid=80178 - Blackbird reviews: narrow sleeves.
12. https://en.wikipedia.org/wiki/Topit - topit history: Comden, Page 1966, Ammar 1983 and 2014.
13. https://vanishingincmagic.com/close-up-magic/topit-180-gimmick-by-david-penn - Topit 180: vanish, steal, ditch.
14. https://www.conjuringarchive.com/list/category/86 - 504 indexed pull and holdout items; De Kolta bare-armed pull.
15. https://wiki.geniimagazine.com/index.php?title=Pull - pull definition; De Kolta 1875.
16. https://www.tannens.com/collections/all/products/tarantula-2 - Tarantula II, $75.
17. https://www.theory11.com/forums/threads/tarantula-2-by-yigal-mesika.52221 - user report on battery life.
18. https://vanishingincmagic.com/close-up-magic/gravity-reel-toe-switch - Gravity Reel toe switch (via search summary; 403 on fetch).
19. https://www.tannens.com/collections/magic-accessories/products/spectro-touch-toe-switch - Spectro Touch toe switch.
20. https://mylovelyassistant.com/19993 - Flash Burst review: toe switch weaknesses.
21. https://vanishingincmagic.com/stage-and-parlor-magic/sole-snatcher - card-to-shoe gimmick.
22. https://wikipedia.com/wiki/Thumb_tip - thumb tip (seen in results, not opened).
23. https://www.first4magnets.com/product/stitch-in-pvc-coated-quick-change-textile-magnets-magic-illusions-pair-19503 - stitch-in quick-change magnets.
24. https://www.apexmagnets.com/news-how-tos/wardrobe-quick-rigging/ - magnets versus hook-and-loop noise.
25. https://www.backstage.com/magazine/article/quick-change-artist-advice-14580/ - quick-change practice.
26. https://arxiv.org/abs/2410.12097 - Poon, Padia, Hunter (2024), twisted-winching string actuator (PDF read).
27. https://usiena-air.unisi.it/retrieve/623a958c-e5d5-4a21-bc88-141faf46a3f0/1-s2.0-S0263224125021839-main.pdf - 2025 TSA review (abstract only).
28. https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/9950422 - "Twisted string actuators for an exosuit system" patent (via search summary).
29. https://cris.unibo.it/handle/11585/133708 - Bologna twisted-string actuation papers (via search summary).
30. https://biodesign.seas.harvard.edu/resource/pdf-73 - Harvard soft exosuit, Bowden actuation, 300 N hip assistance (via search summary).
31. https://www.epfl.ch/labs/lmts/lmts-research/haptics/textile-clutch - textile electrostatic clutch figures (page read).
32. https://www.epfl.ch/labs/lmts/wp-content/uploads/2019/02/DextrES_final.pdf - DextrES, UIST 2018 (PDF read).
33. https://doaj.org/article/6eb034e3195c40f28564d7c04bdd7893 - Hinchet and Shea 2022, glove and sleeve clutches.
34. https://www.mccormick.northwestern.edu/news/articles/2025/02/redesigning-electroadhesive-clutches-for-robotics-and-wearable-devices/ - 22 N at 100 V (page read).
35. https://www.andrew.cmu.edu/user/shc17/Diller_2016_ICRA.pdf - Diller et al. 2016 electroadhesive clutch (seen in results).
36. https://arxiv.org/abs/2208.08491 - Calico, IMWUT 2022 (PDF read).
37. https://dspace.mit.edu/handle/1721.1/126836 - Rovables, UIST 2016 (abstract read).
38. https://www.media.mit.edu/projects/omnifiber-millifluidic-muscle-fibers/overview/ - OmniFiber figures.
39. https://news.mit.edu/2021/fibers-breath-regulating-1015 - OmniFiber news release.
40. https://www.frontiersin.org/articles/10.3389/frobt.2019.00146/pdf - EHD pump with thin McKibben muscle.
41. https://www.nature.com/articles/s41586-019-1479-6 - Cacucciolo et al. 2019, stretchable pumps.
42. https://www.epfl.ch/labs/lmts/lmts-research/stretchable-pumps-for-soft-machine/ - pump lab page: silent, 0.1 bar per gram.
43. https://www.murata.com/en-global/products/mechatronics/fluid/microblower_mzb1001t02 - microblower specifications.
44. https://dspace.mit.edu/handle/1721.1/107946 - Niiyama et al., Pouch Motors (abstract figures).
45. https://pmc.ncbi.nlm.nih.gov/articles/PMC7032068 - self-fitting SMA knitted garment.
46. https://www.hybridbody.human.cornell.edu/s/KnitDema_CHI2023.pdf - KnitDema, CHI 2023.
47. https://arxiv.org/abs/2412.06823v1 - modular pneumatic peristaltic transport.
48. https://www.cam.ac.uk/stories/third-thumb - Third Thumb 596-person study (page read).
49. https://3dprintingindustry.com/news/3d-printed-third-thumb-prosthesis-gives-superhuman-abilities-117602/ - Third Thumb construction.
50. https://blog.hackster.io/adding-a-third-thumb-cb198ecec73e - Third Thumb build details.
51. https://www.ucl.ac.uk/news/2021/may/robotic-third-thumb-use-can-alter-brain-representation-hand - training study.
52. https://news.mit.edu/2014/getting-grip-robotic-grasp-0718 - MIT supernumerary fingers.
53. https://thesixthfinger.diism.unisi.it/ - Siena Robotic Sixth Finger.
54. https://www.biorobotics.snu.ac.kr/egp - Exo-Glove Poly.
55. https://pmc.ncbi.nlm.nih.gov/articles/PMC4277072 - Stanford gecko-adhesive human climbing.
56. https://smr.unl.edu/papers/frey_et_al-2022-SA.pdf - octopus-inspired switchable adhesive glove (PDF read in part).
57. https://pmc.ncbi.nlm.nih.gov/articles/PMC6097001 - octopus-like patches for wet and hairy skin.
58. https://core.ac.uk/download/196597437.pdf - electroadhesive pad paper (figures via search summary; attribution between this and core.ac.uk/download/288369482.pdf not confirmed).
59. https://makezine.com/?p=504567 - electroadhesive robot fingers.
60. https://pmc.ncbi.nlm.nih.gov/articles/PMC8596009 - Acharya et al. 2021, finger snap (page read).
61. https://par.nsf.gov/servlets/purl/10434945 - Patek, LaMSA review (PDF read in part).
62. https://par.nsf.gov/servlets/purl/10424943 - Hyun et al. 2023, engineered LaMSA (not opened).
63. https://www.pololu.com/category/60/micro-metal-gearmotors - N20 gearmotor table (page read).
64. https://pmc.ncbi.nlm.nih.gov/articles/PMC2277072 - pursuit and catch-up saccades (via search summary, with https://pmc.ncbi.nlm.nih.gov/articles/PMC4534514).
65. https://en.wikipedia.org/wiki/Saccadic_masking - saccadic suppression.
66. https://www.scientificamerican.com/article/abracadabra-a-classic-mag/ - Kuhn and Land vanishing ball.
67. https://hci.cs.uni-saarland.de/wp-content/uploads/publications/strohmeier_ahs2020_magnet_implant.pdf - implanted magnet input and output (PDF read in part).
68. https://centaur.reading.ac.uk/40664/ - Harrison thesis, implanted versus surface magnets.
69. https://informahealthcare.com/doi/full/10.1080/01969722.2018.1448223 - Harrison, Warwick, Ruiz 2018.
70. https://dangerousthings.com/product/titan - Titan biomagnet.
71. https://dangerousthings.com/product/xG3 - xG3 injectable magnet.
72. https://dangerousthings.com/biomagnets - biomagnet prices (page read).
73. https://dangerousthings.com/product/xsiid - xSIID NFC and LED implant.
74. https://store.dangerousthings.com/x-faq - vendor MRI and capsule statements.
75. https://pubmed.ncbi.nlm.nih.gov/35688399/ - NFC device MRI evaluation.
76. https://www.statnews.com/2019/09/06/a-cyborg-magician-explains-why-she-implanted-26-microchips-and-magnets-in-her-body/ - Synn interview (page read).
77. https://www.guinnessworldrecords.com/news/2023/11/woman-inserts-technological-implants-into-her-body-to-become-human-cyborg-759815 - 52 implants.
78. https://en.wikipedia.org/wiki/Anastasia_Synn - biography; MRI remark via insidemagic.com.
79. https://www.computerworld.com/article/1659794/your-old-dog-may-already-know-this-digiwell-nfc-trick.html - Patrick Kramer's xNT card trick.
80. https://www.techspot.com/news/110458-magician-implanted-rfid-chip-becomes-useless-after-forgets.html - Zi Teng Wang (403 on fetch).
81. https://learn.adafruit.com/unlock-android-with-wearable-nfc.md?view=all - NFC tag under gel nail polish.
82. https://magazine.raspberrypi.com/articles/pimoroni-nfc-nail-stickers-review - LED nail stickers.
83. https://www.tindie.com/products/questwise-ventures/ultra-thin-flexible-1356mhz-nfc-rfid-tag-5x5mm - 5 x 5 mm flexible tag.
84. https://www.dazeddigital.com/beauty/article/70707/1/biohack-your-body-microchips-manicures-nails-nfc-wearable-tech - NFC manicures.
85. https://nailo.media.mit.edu - NailO thumbnail trackpad.
86. https://pmc.ncbi.nlm.nih.gov/articles/PMC4154453 - feelSpace belt study.
87. https://en.wikipedia.org/wiki/CyborgNest - North Sense.
88. https://hearingreview.com/hearing-products/hearing-aids/directionality-in-single-microphone-hearing-aids - directional gain; with https://pubs.asha.org/doi/10.1044/2024_AJA-24-00027 and Phonak field study PDF (via search summary).
89. https://eprints.soton.ac.uk/456797/1/Wagih_APS22_SAR_NearField.pdf - all-textile 3 W receiver; with https://eprints.gla.ac.uk/298139/2/298139.pdf (15 W) and https://eprints.soton.ac.uk/437634/ (glove).
90. https://research.google/blog/on-device-real-time-hand-tracking-with-mediapipe/ - MediaPipe Hands.
91. https://research.gold.ac.uk/id/eprint/8256 - Cavina-Pratesi et al. 2011, The Magic Grasp.
92. https://patents.google.com/patent/US4350853 - insole toe switch patent.
93. https://www.media.mit.edu/projects/rovables/overview/ - Rovables project page.
94. https://smartlab.cs.umd.edu/publication/calico - Calico project page.
95. https://forum.dangerousthings.com/t/titan-biomagnet-neodymium-core-weight-comparison-to-different-magnets/15564 - forum lift comparison (via search summary).
