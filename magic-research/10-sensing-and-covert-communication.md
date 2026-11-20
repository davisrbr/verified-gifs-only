# 10. Sensing, recognition and covert communication as magic methods (2015 to 2026)

Slice: how a performer (or a prop, or the room) secretly comes to *know* something and how that knowledge is secretly *told* to whoever needs it. Scope is live entertainment with the performer's own props and volunteers who agreed to take part. Where a source is a security side-channel paper, only the sensing principle is reported. Nothing here is guidance for use at a gaming table, for watching people who have not agreed to take part, or for capturing credentials.

Research note: the shared web-search quota for the project ran out after about 15 of my searches. The rest of the evidence comes from pages opened directly. Anything recalled from memory and not re-checked is marked "(unverified)". Prices are as seen on the cited pages in November 2026.

## 1. Summary

- **The market already sells "read one thing, buzz the performer".** RFID decks read at 11 cm (Insight Pro, $550), magnet detectors at 12 to 18 cm (Sixth Sense 3, $300), electronic impression pads ($999 for ThoughtCast Pro), smart dice and vibrating receivers all exist [11][15][53][47]. Rebuilding those is cheap but not new. The gap is elsewhere.
- **The real opening is complete, continuous state knowledge of every prop**, held by a controller rather than the performer's head. With the full state known, forces, controls, stooges and pre-show become unnecessary, and the spectator's choice can be truly free.
- **Fully passive sensing is now cheap**: the object the audience handles can contain nothing at all. A $6 24-bit load-cell ADC [27], a 4-channel 28-bit inductive converter that ignores magnets [26], a $75 thermal array [44], a $27 60 GHz radar [30] and a $19 camera-plus-microphone board the size of a postage stamp [56] all sit in the table, the room or the performer's clothing.
- **Battery-free tags became sensors, not just IDs.** IDSense (Disney Research, CHI 2015) classifies touch and movement of 20 objects at about 93% from changes in the RFID radio link alone [10]. A hobby UHF reader reads up to 300 tags per second at up to 4.9 m [9]. Tags now come as small as 1.2 x 1.2 x 0.55 mm [1].
- **Magnet sensing moved from "is a magnet near" to "where is it and which way is it facing".** MagX tracks passive magnets in 5 degrees of freedom with 8 magnetometers, about 0.76 cm error at 11 cm [20][22]. This is the genuinely new thing relative to existing "which hand" devices.
- **Writing capture through paper is mature.** Wacom's EMR smartpads read a pen through about 80 sheets (8 mm) [48]. Recognising writing from pen motion alone (IMU pens) works in research but is weak across writers [54]; restrict it to small symbol sets.
- **Reading people is mostly a dead end as a method, and useful as theatre.** Voice stress analysis performed at chance in a US field study [62]; micro-expressions are rare and unreliable [63]; pupil dilation gives an AUC of about 0.70 on a single trial [58]; a consumer EEG headband needs averaged trials and reduced guessing entropy by only 15 to 40% in the best-known study [59][60]. None of these can carry an effect alone.
- **What can be read from people reliably is coarse and behavioural**: where heads are pointing (real-time head pose for a whole room on a phone [73]), presence and breathing by radar [30], and what was said aloud (on-device Whisper in about 273 MB of memory with half-second updates [67]). Head pose opens a new architecture: secret moves timed by measured attention.
- **Output channels are no longer the bottleneck.** Display glasses that let a presenter keep eye contact are a retail product [71][69], and an EMG wristband for silent input ships with one of them at $799 [69]. Contact-lens displays do not exist as products [72].
- **Radio is the main reliability risk in a room full of phones.** Prefer links that are quiet until needed (NFC, IR, wired), or connectionless short frames on a fixed channel (ESP-NOW, 250-byte frames [74]), and design every routine so that a missing packet leads to an "out", not a failure.

## 2. Catalog

### A. Knowing the state of your own props

**A1. HF RFID / NFC tags and readers.**
*What:* 13.56 MHz tags powered by the reader's field. Read range scales with antenna size. Murata lists a 3.2 x 3.2 mm NTAG210 module at about 17 mm and a 6.4 x 6.4 mm NTAG213 module at about 30 mm ("reference" values, test reader not stated) [2]. A vendor blog reports only about 2 mm from a phone for its tiniest NTAG213 tag [8]. ISO 15693 (NFC-V) tags read further than ISO 14443 tags with the same antenna; NXP's NTAG 5 boost adds active load modulation for tiny antennas [4].
*Multi-tag:* anticollision is in the standards, but hobby libraries are patchy. Users of the popular PN5180 library report the 16-slot inventory failing, with a workaround that addresses known UIDs one at a time [5][6]. ST's ST25R3911 stack returns multiple UIDs [7]. Stacked tags detune each other; the commercial Insight Pro deck claims a stack of at most three cards [11].
*Access:* off the shelf. Sticker tags cost cents each (unverified); reader boards $5 to $40 (unverified).
*Magic relevance:* identification, prediction, control. The new capability is not "read a card". It is that every prop in a show can carry a unique, unpowered, sub-millimetre-thin identity, so a controller can verify which object is where. A tag can be dropped into a 3D print mid-layer and leave no seam.
*Prior use:* Insight / Insight Pro (11 cm, coded vibration, optional iPhone relay to 10 m) [11]; The Bat System (claimed 3 m, discontinued) [12]; Illuminati Magic Second Sight (110 mm, programmable tags that can be hidden on cups, postcards and so on, $446) [13]; a DIY Arduino reader under a table [77]. Televised poker uses RFID cards and table antennas for broadcast graphics [14], which shows the principle is production-grade.

**A2. UHF RFID (860 to 928 MHz), including tags used as sensors.**
*What:* longer range and fast inventory. The SparkFun M7E Hecto reader reads up to 300 tags per second, roughly 30 to 60 cm with its PCB antenna and up to 4.9 m with an external antenna, at 0 to 27 dBm, for $309.95 [9]. Murata's smallest tag is 1.2 x 1.2 x 0.55 mm with about 24 mm range from a dedicated loop antenna; a 2.0 x 1.2 mm part that uses the host PCB as its antenna is listed at 14 m [1][3].
*Tags as sensors:* IDSense watches RSSI, phase and read rate of ordinary passive tags and classifies four movement classes plus "swipe touch" and "cover touch" at about 93% while tracking 20 objects [10]. A hand covering a tag, a foil-lined lid closing over it, or liquid behind it all change or kill the response.
*Access:* hobbyist, $310 to $400 with antenna. Transmit power and band are regulated per region; set the reader to the local band.
*Magic relevance:* a backdrop antenna can inventory a whole table several times a second. "Which objects are present, which was just touched, which box is open" becomes a continuous data stream with nothing powered in any object. The weakness is multipath: people moving in the room change the link, so per-venue calibration is needed.
*Prior use:* none found for the touch-sensing use. The Bat System's 3 m claim suggests UHF [12] (unverified).

**A3. Magnetometer arrays: position and orientation of passive magnets.**
*What:* existing magic devices detect field strength and sometimes polarity. Sixth Sense 3 is 17 x 34 mm and detects a magnetic coin at 12 to 18 cm, 30 cm+ with its app [15]; version 2.5 signals heads or tails by polarity [16]; reviewers complain about inconsistency and the need for strong magnets with weaker devices [19]. Research systems solve the inverse problem for full pose. MagX (MobiCom 2021) tracks two magnets independently in 5 DoF with millimetre accuracy close up, 2.6 cm at 27 cm with a 9.8 cm square array, on 0.38 W [20]; a later paper summarises it as 0.76 cm error within 11 cm using 8 magnetometers [22]. Accuracy falls off past 30 cm [23]. AuraRing (IMWUT 2019) uses an active coil ring and wrist coils for 4.4 mm dynamic accuracy at 2.3 mW [24]. µTouch (PerCom 2026) adds an ambient-field rejection module and classifies gestures at about 93 to 95% with three seconds of calibration per gesture [22]. A hobby write-up claims usable 3D tracking from three magnetometers and a fingertip magnet [25].
*Access:* hobbyist. Eight I2C magnetometer breakouts and a microcontroller, roughly $30 to $60 (unverified). The solver is a published least-squares fit.
*Magic relevance:* a pad can know which face of a die is up, which of nine zones a coin is in, whether it was flipped, and the path it took, for two objects at once. A magnet on the performer's own ring becomes an invisible six-axis controller with no electronics on the body. Stage steel and speakers disturb the field; calibrate on site. Safety: neodymium magnets pinch, and must be kept away from pacemakers and from children's mouths.
*Prior use:* threshold and polarity detection only [15][16][17][18].

**A4. Inductive sensing of unprepared metal.**
*What:* an inductance-to-digital converter measures the shift in an LC tank when conductive metal comes near a flat PCB coil. TI's LDC1614 has 4 channels at 28-bit resolution, I2C, a 4 mm package, and explicit immunity to DC magnetic fields [26]. Useful range is about one coil diameter (unverified rule of thumb); response differs with alloy and size.
*Access:* hobbyist, a few dollars per chip (unverified) plus coils drawn as PCB traces.
*Magic relevance:* the coin, ring or key can be genuinely borrowed. No magnetic shell, no switch. A coil array under veneer or a close-up pad knows which cover hides the metal and can tell a large coin from a small one. Fails with metal cups, metal table frames and foil.
*Prior use:* not found. Buyers of magnet detectors are told they are "not a metal detector" [19].

**A5. Weight and centre of pressure.**
*What:* four load cells under a tray give total weight and, from the ratio between cells, the position of whatever was added or removed. The NAU7802 is a 24-bit bridge ADC on a $5.95 board [27]. Hobby scales built this way resolve around 0.1 g on a 1 kg range in still air (unverified).
*Access:* hobbyist, $30 to $60.
*Magic relevance:* nothing electronic is in any object. The system can identify which object left by its mass, where an object was put down, how many coins were taken, and plausibly how many cards were cut from a deck (a card is under 2 g, so this needs about 1% accuracy; speculative, weigh your own deck). Leaning hands, draughts and vibration corrupt readings, so sample only in quiet moments and report confidence.
*Prior use:* not found.

**A6. Capacitive sensing through covers.**
*What:* electrodes under wood, leather or a book cover sense a hand at centimetres and a finger at millimetres, and respond strongly to water because of its permittivity. Parts such as the MPR121 and FDC2214 are standard (unverified, pages not opened). Capacitivo (UIST 2020) recognised 20 objects on a fabric electrode grid at about 94.5% (unverified).
*Magic relevance:* which book was touched, which envelope is being held, which opaque cup is full, whether a hand is hovering. Cheap enough to tile a whole table.

**A7. mmWave radar.**
*What:* FMCW radar at 24, 60 or 77 GHz senses micro-motion and penetrates cloth, paper, cardboard and thin plastic [35]. RadarCat (Yeo et al., UIST 2016) put objects directly on a Google Soli sensor and classified 26 materials and objects at 96.0% across sessions and 17 transparent materials at 98.67%. Filled and empty glasses were never confused. Training and testing were in the same quiet lab, drift and clutter degraded it, and it could not tell single sticky notes of different colours apart. The authors list "counting the number of poker cards" as an observed but unvalidated ability [28][29]. For contents of sealed boxes, 77 GHz work classifies fill material from range profiles [33]; ACCOR (2025) classifies occluded objects from raw IQ data [34]; the MITO dataset has 580+ mmWave images of 76 objects inside and outside boxes, made with a robot-arm synthetic aperture [35].
*Vital signs:* Seeed's MR60BHA2 claims breathing and heartbeat to 1.5 m and presence to 6 m for $26.90 [30][31]. A hobbyist test of the earlier model found heart rate 10 to 20 bpm off a chest strap and poorly correlated [32].
*Access:* presence and breathing modules are off the shelf. Raw-data boards built on Infineon's BGT60TR13C, the commercial descendant of Soli, cost roughly $100 to $300 (unverified; Infineon's page could not be opened). Imaging through boxes is lab-only.
*Magic relevance:* treat radar as a through-cloth motion and presence sensor (someone sat down, a hand entered a covered box, breathing paused), and as a contact material classifier in a fixed fixture. Do not expect to image an object in an envelope with a hobby module.

**A8. UWB ranging, BLE direction finding, Wi-Fi CSI.**
*What:* DW3000-class UWB gives two-way ranging at a vendor-claimed 10 cm [37]. Modules cost $17 to $44 [36][37][38], and Qorvo states interoperability with Apple's U1 chip, though the hobby board vendor provides no demo of it [38]. BLE 5.1 angle-of-arrival kits exist (unverified). Espressif's esp-csi turns ESP32 boards into Wi-Fi motion and presence sensors; its own notes say other people moving in the room disturb it [39].
*Magic relevance:* UWB is the practical one. A tag about 23 x 13 mm plus a cell fits in a matchbox-sized object, and a single anchor on the performer gives live distance to within a hand-width, through pockets and bags. Bodies in the path add error. Wi-Fi CSI is too crowd-sensitive for a show.

**A9. Acoustic and vibration sensing.**
*What:* piezo discs or contact microphones on a hard table localise taps by time difference of arrival. Toffee (MobileHCI 2014) reports 4.3 degrees mean bearing error [40]. Related foundations include Acoustic Barcodes (notched strips that encode an ID in the sound of a fingernail swipe) and EM-Sense (identifying powered objects by their electromagnetic noise), both cited in [28]. Knocker (IMWUT 2019) identified objects by knock sound with a phone (unverified).
*Access:* trivial. Piezo discs cost cents and an ESP32 samples them.
*Magic relevance:* which box was knocked on, where on the table a coin was put down, how many coins dropped into a cup, counting cards dealt by their snap. The object is ordinary. Fails in loud rooms unless the pickup is structure-borne.

**A10. Thermal imaging of residual heat.**
*What:* a touch leaves a heat trace that a long-wave IR camera sees after the hand is gone. HeatWave (CHI 2011) used this for touch interfaces [42]; a 2014 demo paired thermal and visible cameras to locate touches on arbitrary objects [43]; MIDAS (2022) used the decay curve to classify materials at up to 83% and detected heat through objects up to 2 mm thick [41]; a recent patent describes extraction by subtracting a pre-touch frame [78]. Hardware: MLX90640, 32 x 24 pixels, 55 x 35 degree view, 16 Hz practical, plus or minus 2 C, $74.95 [44]; 256 x 192 phone-dongle cameras cost about $200 (unverified).
*Limits:* polished metal has low emissivity and mostly reflects, so shiny coins are poor targets; paper, card, wood, plastic, leather and painted surfaces work. Ordinary glass and acrylic block long-wave IR, so the camera needs an open aperture or an IR-transparent film (thin polyethylene is the hobbyist's choice, unverified).
*Magic relevance:* the only method here that works on borrowed, unprepared, non-metallic objects with nothing added: which of five envelopes was held, which chair was sat in, which book was handled. The time window is seconds to a couple of minutes.

**A11. Cameras, invisible marks and machine-readable decks.**
*What:* a 21 x 17.8 mm board with camera, microphone, Wi-Fi and BLE costs $18.90 [56]. Marks that are invisible to the eye and readable by a filtered camera (IR-absorbing or fluorescing inks, embedded markers such as InfraredTags, BrightMarker and AirCode) belong to agent 6. Hyperspectral and polarisation cameras exist but cost four figures (unverified) and offer nothing a marked prop does not.
*Magic relevance:* the capability worth naming is whole-state capture: one frame of a squared deck with machine-readable edges, or one riffle past a fast camera, yields the complete order. The same principle is sold for cheating at card games; that use is illegal and out of scope here. For a performer's own deck in a show, it turns "locate one card" into "know all 52 positions after a genuine spectator shuffle".
*Prior use:* marked decks are old; whole-order capture is not something I found sold to magicians (unverified).

**A12. IMUs inside props.**
*What:* Pixels dice pack an accelerometer, Bluetooth, LEDs and wireless charging into a slightly oversized die [45]; GoDice are about $100 to $120 for five with roughly two hours of play per charge [46]. ProMystic sells magic-specific electronic dice and colour-choice sensing (Real Die, MD Mini, ColorMatch) [47]. UID has a movement-detection mode that hides in a card case [18]. Smart Rubik's cubes report every turn over BLE (unverified).
*Magic relevance:* beyond dice, an IMU with wake-on-motion can sit in a pen, book, box lid, chair or ball and report "picked up, tilted, opened, turned over, shaken, set down" for months per charge (unverified). It is the cheapest way to make timing cues fire by themselves.

**A13. Optical and ultrasonic ranging.**
*What:* single-chip time-of-flight sensors measure distance to millimetres over tens of centimetres to a few metres, and multizone versions return a coarse depth grid (8 x 8 zones in ST's VL53L5CX class) from a 6 mm package for roughly $10 to $25 (unverified). Structured-light and stereo depth cameras give full depth maps for $100 to $400 (unverified). Ultrasonic rangers cost a dollar or two but have wide beams and a visible pair of transducers.
*Magic relevance:* a ToF sensor behind a 3 mm IR-pass window (looks like black plastic) knows which of several positions a hand reached into, how high a stack of cards or coins is, whether a box lid is up, and how far away a spectator is standing. It is the easiest "which of N places" sensor when the performer owns the furniture. Sunlight and hot stage lamps add IR noise. Ultrasonic sensing is rarely worth its visibility.
*Prior use:* not found as a named product (unverified).

### B. Reading what someone wrote or drew

**B1. EMR digitiser under ordinary paper.**
Wacom's Bamboo Slate and Folio read a ballpoint containing a passive resonant circuit through about 80 sheets (8 mm), including pressure [48][49]. The spectator writes on real paper, tears the sheet off and keeps it. Electronic impression devices sold to magicians follow this pattern: PITATA's Smart Memo Pad and Smart Clipboard [51][52] and ThoughtCast Pro (from $999) [53]. The non-electronic ParaPad costs about $70 to $75 [50]. A hobbyist gets most of the capability from a used smartpad. The pen must be the system's pen.

**B2. Dot-pattern camera pens.** Neo and Livescribe pens read a printed micro-dot pattern with a camera in the tip and stream strokes over Bluetooth (unverified; the vendor site gave no specifications [76]). They need special paper and a fat pen, so they are weaker than B1 for deception.

**B3. Pen-motion recognition.** Ott et al. (2022) benchmark handwriting recognition from a ballpoint with accelerometer, gyroscope, magnetometer and force sensor at 100 Hz [54][55]. Writer-dependent results are good; writer-independent results are clearly worse (exact figures not confirmed). For magic this means: classify among few alternatives (ten digits, five ESP symbols, tick or cross), not free text. The pad and paper can then be borrowed. Recognition of handwriting from the scratch sound has been shown in security research (WritingHacker, UbiComp 2016, unverified) with accuracy too low to rely on.

**B4. Pressure films and touch layers.** Resistive matrices under a pad capture any pen's strokes at low resolution (unverified). A classic carbon or wax impression plus a camera is still simpler.

**B4b. E-ink notepads and LCD writing tablets.** E-ink tablets with EMR pens (reMarkable class) capture and sync strokes, and pressure-sensitive LCD "boogie board" slates are cheap and familiar, but both are visibly electronic writing surfaces, so the audience's first theory is the right one (details unverified). Useful only when a second, non-electronic explanation is planted, or when the device is the spectator's own and the method is elsewhere.

**B5. Camera peek plus recognition.** A hidden camera sends an image of the writing to a model that transcribes it. Handwriting recognition is now good enough that the performer need not look at an image at all; the word can arrive as audio or haptics. The pipeline belongs to agent 12.

### C. Reading people (consenting volunteers)

**C1. Head pose and gaze.** MediaPipe Face Landmarker returns 478 landmarks, 52 expression blendshapes and a head-pose matrix per face, in real time, on phones, browsers and Python [73]. Head direction for many people at parlor distance is reliable. Eye gaze at distance is not, and gaze is not the same as attention.

**C2. Speech.** Whisper was trained on 680,000 hours and approaches human robustness [66]. whisper.cpp runs on phones and a Raspberry Pi, the tiny model needs about 273 MB, and the streaming example updates every half second [67]. Spoken words in a show can be captured without a human listener. Whispered or distant speech degrades sharply (unverified). Lip reading: the best open visual-only models have about 20 to 36% word error on clean frontal broadcast video, after training on 438 to 3,291 hours [65][64]; useless across a room.

**C3. Physiology.** Camera pulse measurement (rPPG) works on still, well-lit faces and has an open toolbox [57]; accuracy under stage light and movement is poor (unverified). Radar heart rate is unreliable at hobby level [32]. Skin conductance needs electrodes and reacts to everything.

**C4. Pupil.** When observers covertly picked one of five digits shown in sequence, the time of peak dilation discriminated first from last position with AUC 0.70; the authors call single-trial reliability low [58].

**C5. EEG.** A Muse headband records the P300 and related components in group averages over 120 trials, with about 40 ms Bluetooth lag and awkward electrode positions [59]. The best-known consumer-headset "which item do you recognise" study reduced guessing entropy by 15 to 40% compared with random guessing [60]. Open experiment code for Muse and OpenBCI exists [61]. Nothing about the content of thoughts is decoded.

**C6. EMG and silent speech.** Meta's wristband decodes pinches and thumb swipes for anyone without per-user training and ships with display glasses at $799; handwriting decoding was promised for the "near future" at launch [69]. The Nature 2025 paper reports about 20 words per minute of handwriting (unverified; the page was paywalled to my fetch) [70]. MIT's AlterEgo reads neuromuscular signals during silent articulation and answers by bone conduction; it became a company in 2025 [68], reported about 92% accuracy on small vocabularies in 2018 (unverified), and is not a purchasable product as far as I could confirm.

**C7. Voice stress and micro-expressions.** Pseudoscience for practical purposes; see section 5.

**C8. Ideomotor movement.** Contact mind reading (muscle reading) relies on unconscious pushes and pulls. No recent engineering paper was found; a force sensor or IMU in a shared object could amplify these for the performer. Speculative.

### D. Telling the performer

**D1. Vibration.** The standard channel: receivers built into the sensor (Insight, Sixth Sense) [11][15] or worn separately, with coded pulses. Newer parts (coin LRAs, piezo benders, smartwatch haptic APIs) give crisper, quieter pulses (unverified). One of 52 takes two symbols and about 2 to 3 seconds.

**D2. Audio.** Second Sight can speak the result into a hidden Bluetooth earpiece [13]. Bone conduction keeps the ear canal open [68]. Synthesised speech delivers "seven of clubs" in under a second, and whole sentences if a script is being fed. In-ear devices are visible at close-up distance.

**D3. Glanceable displays.** Small peek displays and modified watches are sold to magicians (Electricks PeekSmith and SB Watch; their pages refused my fetch). Even Realities G2 glasses with the R1 control ring ($179) are marketed with testimonials about presenting while keeping eye contact [71]. Meta Ray-Ban Display has a full-colour display in one lens, 6 hours of mixed use and an 18-hour band [69]. Detectability is now mostly social: the frames are recognisable products, and a downward glance reads as a glance. A display in a watch face, pen clip or card box is easier to justify.

**D3b. Displays and lights hidden in ordinary objects.** A 0.4 to 1 inch OLED or a small e-ink panel fits behind a watch crystal, inside a card-box flap, a pen clip, a ring-box lid or a notebook spine; e-ink holds its image with no power and no glow. A single LED in peripheral vision (inside a glasses temple, a cuff, a table edge) can carry a colour or blink code with no head or eye movement at all, at the cost of a low symbol rate much like vibration. Haptic smart rings and smartwatch haptic APIs do the thumper's job in an object nobody questions (parts and prices unverified; agent 14 has the catalogue).

**D4. Not available.** Contact-lens displays: Mojo Vision shelved its lens in January 2023 to work on micro-LEDs [72]. Thermal and electro-tactile cueing are slow or uncomfortable and sit in agent 11's slice.

**D5. Latency budget.** Sensor read 10 to 100 ms; BLE or ESP-NOW hop 10 to 100 ms; haptic code 1 to 3 s or audio 0.5 to 1 s; speech recognition adds 0.5 to 2 s [67]. Human decoding of a haptic code is the slowest step, which argues for sending decisions ("go left pocket") rather than data.

### E. Telling the system

Toe and heel switches, palmed remotes and pocket keypads typed by touch are existing practice; a one-handed chording keyboard in a pocket reaches full text at a few words per minute with practice (unverified). Tongue and in-mouth switches exist in assistive technology but are awkward while speaking, and subvocal input is not purchasable (C6). New options: an EMG wristband that reads pinches with the hand hanging at the side [69]; smart rings as input devices, a field with 206 surveyed papers [23]; a plain magnet ring read by a magnetometer in the prop (A3); and room speech recognition that picks out cue words so the performer's patter is the input (pipeline in agent 12's slice).

### F. Radio and power practicalities

- **BLE:** universal and phone-friendly, but 2.4 GHz is saturated in a full venue and phone operating systems delay background notifications (unverified). Keep connections open and payloads tiny.
- **ESP-NOW:** connectionless frames up to 250 bytes (1,470 in v2), 1 Mbps by default, AES-CCMP optional, up to 20 peers, MAC-level acknowledgement only [74]. Good for prop-to-prop links without pairing rituals. XIAO-class boards claim over 100 m with an external antenna [56].
- **Sub-GHz (433 / 868 / 915 MHz, LoRa):** penetrates bodies better and avoids phone bands; low data rate is fine for a few bytes (unverified).
- **NFC as a link:** nothing radiates until the prop is on the reader, so it cannot be interfered with or detected at range, and energy-harvesting tags can run a tiny circuit with no battery [4].
- **Infrared:** line-of-sight, immune to RF congestion, parts cost cents.
- **Sound:** ggwave sends 8 to 16 bytes per second with error correction and runs on ESP32 and RP2040; its "ultrasonic" modes start at 15 kHz [75], which many younger spectators can hear.
- **Power:** wake-on-motion or wake-on-field designs turn hours into months. LiPo cells in props need protection circuits and must not be crushed or punctured.
- **Rule:** acknowledge every message (a haptic "got it"), and script an out for silence.

## 3. Capability primitives

1. *Now possible:* give each of 500 props a unique unpowered identity in a chip 1.2 to 6.4 mm across, read at 17 to 30 mm. *Because:* micro NFC/UHF modules [1][2]. *Before:* marks the performer had to see. *Primitives:* know, prove ordinariness.
2. *Now possible:* inventory every tagged object on a stage 5+ times a second from up to 4.9 m. *Because:* 300 tags/s hobby UHF reader [9]. *Before:* one object, one reader, centimetres. *Primitives:* know, control choice.
3. *Now possible:* detect that a spectator touched, covered or moved one of 20 objects, with only a paper label in each. *Because:* RFID link-quality sensing, about 93% [10]. *Before:* a stooge or a peek. *Primitives:* know.
4. *Now possible:* read open/closed or sealed/opened state of a container with no battery, by a lid that shields a tag. *Because:* tags vanish behind foil or detune near liquid [10] (design speculative). *Before:* secret marks, hairs, wax. *Primitives:* know, delay.
5. *Now possible:* know 3D position and facing of a magnet to under 1 cm at 11 cm, two magnets at once. *Because:* magnetometer arrays and solvers [20][22]. *Before:* near or not near. *Primitives:* know.
6. *Now possible:* control a prop with a gesture of a plain magnetic ring, no electronics on the performer. *Because:* same arrays used as input (speculative). *Before:* palmed remotes, toe switches. *Primitives:* tell.
7. *Now possible:* locate a borrowed, unprepared coin, key or ring under one of several covers. *Because:* 28-bit inductive sensing that ignores magnets [26]. *Before:* magnetic or shell coins. *Primitives:* know, prove ordinariness.
8. *Now possible:* identify which ordinary object left a tray, and where a new one was placed, to about 0.1 g and about a centimetre. *Because:* $6 24-bit bridge ADC [27] (resolution unverified). *Before:* not done. *Primitives:* know.
9. *Now possible:* count cards cut from an unprepared deck to within one card (speculative). *Because:* same. *Before:* estimation by eye, breather crimps. *Primitives:* know, control choice.
10. *Now possible:* tell a full opaque cup from an empty one from below, without contact. *Because:* capacitive sensing; radar never confused filled and empty glasses [28]. *Before:* marked cups, weight in the hand. *Primitives:* know.
11. *Now possible:* see which non-metallic object was held, for a minute afterwards, with nothing added to the object. *Because:* $75 to $200 thermal cameras [44][41]. *Before:* impossible without marking. *Primitives:* know, prove ordinariness.
12. *Now possible:* sense a hand entering a cloth-covered box, someone sitting down, or breathing, from behind fabric. *Because:* $27 60 GHz radar [30]. *Before:* a watching assistant. *Primitives:* know, delay.
13. *Now possible:* know the distance to a matchbox-sized hidden object to about 10 cm anywhere in a room. *Because:* $17 to $44 UWB modules [37][38]. *Before:* contact mind reading skill. *Primitives:* know.
14. *Now possible:* locate a tap on a table to about 4 degrees of bearing with a few piezo discs. *Because:* TDOA processing on a microcontroller [40]. *Before:* watching. *Primitives:* know.
15. *Now possible:* capture every pen stroke through 80 sheets of ordinary paper. *Because:* EMR digitisers [48]. *Before:* carbon impressions needing a look. *Primitives:* know, duplicate.
16. *Now possible:* classify a written digit or symbol from the pen's motion alone, on borrowed paper (small sets only). *Because:* IMU pens and sequence models [54]. *Before:* pencil reading by eye. *Primitives:* know.
17. *Now possible:* capture the complete order of the performer's own deck in about a second after a genuine shuffle. *Because:* $19 camera boards and machine-readable marks [56]. *Before:* memorised stacks destroyed by any shuffle. *Primitives:* know, control choice.
18. *Now possible:* measure where each head in a room is pointing, 30 times a second, on a phone. *Because:* MediaPipe [73]. *Before:* the performer's intuition. *Primitives:* conceal, delay.
19. *Now possible:* transcribe what is said on stage within about a second, offline. *Because:* whisper.cpp [67]. *Before:* an assistant listening. *Primitives:* know, tell.
20. *Now possible:* a prop that wakes on being lifted, tilted or opened and reports it, for months per charge (battery figure unverified). *Because:* IMUs with motion interrupts [18][45]. *Before:* the performer had to watch. *Primitives:* know, delay.
21. *Now possible:* read text hands-free while holding eye contact. *Because:* retail display glasses [71][69]. *Before:* cue cards, earpieces. *Primitives:* tell.
22. *Now possible:* give multi-way silent commands with the hand hanging naturally. *Because:* EMG band [69], smart rings [23]. *Before:* one-bit toe switch. *Primitives:* tell.
23. *Now possible:* link props with zero pairing and frames that arrive in milliseconds. *Because:* ESP-NOW [74]. *Before:* bespoke RF remotes. *Primitives:* tell.
24. *Now possible:* a link that cannot be jammed or noticed, because it only exists within 3 cm. *Because:* NFC with energy harvesting [4]. *Before:* always-on radios. *Primitives:* tell, prove ordinariness.
25. *Now possible:* confirm that a secret load, switch or steal actually happened before the reveal is committed. *Because:* any of 1, 5, 7, 8 on the performer's own holders. *Before:* hope. *Primitives:* know, control chance.
26. *Now possible:* log every performance (timings, choices, attention, misses) and mine it. *Because:* all of the above are digital. *Before:* memory and video review. *Primitives:* know.

## 4. Effect concepts

Levels: 1 = the phenomenon is the effect; 2 = hidden input to a traditional method; 3 = new method architecture.

**4.1 The weighing table (level 3).**
*Effect:* a spectator cuts a deck anywhere while the performer is across the room, back turned. The performer names the card cut to. Later the spectator secretly removes some coins from a bowl; the performer says how many, and which coin.
*Method:* the "table" is a tray on four load cells. Total weight change gives the number of cards lifted; a memorised stack converts that count to a card. A false shuffle is the only classical skill needed. Centre of pressure says which pile or object changed.
*BOM:* 4 load cells, 1 to 4 NAU7802 boards [27], ESP32, haptic or audio out; $40 to $70.
*Difficulty:* moderate; the mechanical design (stiff tray, no rubbing) matters more than the electronics.
*Risks:* plus or minus one card. Design the reveal for that: name the card, and if wrong, the neighbour is "the one above it". Draughts and hands on the table.
*Novelty:* high as far as I could find; nothing electronic touches the deck, which can be handed out.

**4.2 Free shuffle, any card named, never touched (level 3).**
*Effect:* a spectator shuffles the performer's deck and boxes it. Anyone names a card. The performer, who has not touched the deck, says "twenty-third from the top". It is.
*Method:* whole-order capture (A11): a camera in the case reads machine-readable edges, or the deck is read one card at a time as it is dealt across a concealed NFC antenna. A controller holds the full order and sends only the number.
*BOM:* camera board [56] or NFC reader, marked or tagged deck; $40 to $150.
*Difficulty:* high. The marking chemistry and optics are agent 6's topic.
*Risks:* a misread is fatal, so the system must verify all 52 are present and unique before signalling "ready"; the too-perfect problem, eased by having the performer do something classical-looking (riffle to the ear, weigh in the hand) first.
*Novelty:* the component principle is known; using full order to remove every force and control from a routine is where the value is. For performance with the performer's own deck only.

**4.3 The shelf that feels touch (level 3).**
*Effect:* with the performer out of the room, a volunteer walks along a shelf of twenty ordinary objects, picks some up, puts them back, lingers over one and finally just thinks of one. The performer returns and narrates the whole walk, including the hesitation.
*Method:* a UHF label inside each object; an antenna behind the backdrop; IDSense-style classification of touch, cover and movement from link changes [10]. A log with timestamps becomes the script.
*BOM:* M7E Hecto $310 [9], antenna $50, tags, small computer; about $400.
*Difficulty:* high; needs per-venue calibration and a few hundred training events.
*Risks:* multipath from other people; keep the audience back. The final "thought of" object must be supported by a classical out, since only handled objects are sensed.
*Novelty:* high. It replaces a hidden assistant with no line of sight.

**4.4 Attention-gated secret moves (level 3).**
*Effect:* invisible to the audience; the effects are whatever the performer does. Loads, switches and steals happen only in moments when measurement says almost nobody is looking at the hand.
*Method:* a camera at the back of the performing area runs head-pose estimation on the audience [73]. When the share of heads turned towards the performer's face or the "bright" hand passes a threshold, a single haptic pulse says "now". Every show is logged, so the performer learns which lines and gestures actually move heads.
*BOM:* phone or Raspberry Pi with camera, haptic receiver; $80 to $150.
*Difficulty:* software only; moderate.
*Risks:* head direction is not attention; one off-axis spectator is enough to be caught; reacting to a cue costs concentration. Start as a rehearsal and review tool. Consent and privacy: process on the device, store angles rather than video, and tell the venue.
*Novelty:* high; I found no live system of this kind (unverified).

**4.5 Verified method state (level 2 to 3).**
*Effect:* none visible. Reliability rises, and the "outs" are chosen by the system.
*Method:* every secret holder gets a cheap sensor: an NFC reader in the wallet that confirms the duplicate has arrived, a Hall sensor in a pocket holder, a load cell under a servante. A controller runs the routine as a state machine. It refuses to arm a reveal (does not update a hidden e-ink prediction, does not release a hold-out) until the previous secret step is confirmed, and tells the performer which ending is live.
*BOM:* a few dollars per station; $50 total.
*Difficulty:* low to moderate.
*Risks:* complexity; a sensor failure must degrade to manual.
*Novelty:* the idea is standard in theatre show control and largely absent from close-up and parlor magic.

**4.6 Borrowed-coin cups (level 2).**
*Effect:* a borrowed, signed coin goes under one of four leather cups, mixed by spectators with the performer's back turned. The performer finds it every time, then tells whether the hidden object is now the coin or the spectator's ring.
*Method:* PCB coils under the mat, LDC1614 [26]. Signal size and alloy separate coin from ring.
*BOM:* $25 to $40.
*Difficulty:* low. *Risks:* metal in the table; coins from different countries need a calibration table.
*Novelty:* moderate; removes the gimmicked coin from a known plot.

**4.7 Warm hands (level 2).**
*Effect:* five sealed envelopes, each signed by a different spectator. One spectator holds theirs to their chest while concentrating; all are mixed on a tray. The performer picks the one that was held, by "reading" the spectators.
*Method:* a thermal camera above or beside the tray, behind an IR-transparent window, compares each envelope with a frame taken before [78]. Paper holds a usable contrast for tens of seconds (speculative; test).
*BOM:* MLX90640 $75 [44] or a 256 x 192 dongle (about $200, unverified), microcontroller, haptic out.
*Difficulty:* low. *Risks:* the window must be justified (a speaker grille, a lamp shade vent); hot stage lights wash out contrast; not for bare metal objects.
*Novelty:* moderate to high; the objects are completely unprepared and can be borrowed.

**4.8 Pencil reading, automated (level 2).**
*Effect:* a spectator draws one of the five ESP symbols, or writes a two-digit number, on their own notepad held against their chest. The performer names it.
*Method:* the marker contains an IMU and radio; a classifier trained on many writers picks among few alternatives [54].
*BOM:* custom 8 mm wide PCB with IMU, BLE system-on-chip and 40 mAh cell in a fat marker barrel; $30 to $60 via PCBA.
*Difficulty:* moderate hardware, moderate machine learning (collect data from 30+ people).
*Risks:* writer independence; use the top-two outputs and a classical fishing line to settle between them.
*Novelty:* I found no product doing this (unverified).

**4.9 Warmer, colder (level 2).**
*Effect:* while the performer is offstage, the audience hides a small box anywhere in the room, even in someone's bag. The performer returns, holds a volunteer's wrist as in the classic contact mind-reading act, and walks to it.
*Method:* a UWB tag in the box, one anchor on the performer, distance sent as a haptic pulse rate [37][38]. Walking provides the gradient. The wrist-holding is cover and tradition.
*BOM:* two DW3000 modules, two microcontrollers, cells; $60 to $100.
*Difficulty:* low to moderate. *Risks:* bodies between tag and anchor add tens of centimetres; the last half metre still needs observation or genuine muscle reading.
*Novelty:* moderate. It makes a notoriously difficult act learnable.

**4.10 Self-running sympathetic object (level 3, installation).**
*Effect:* a sealed glass case in a foyer holds an old bell. A sign invites visitors to place any object from their pocket on a small tray. The bell rings once for keys, twice for coins, stays silent for paper. No performer is present.
*Method:* tray with inductive coils, load cells and a capacitive plate (A4 to A6) classifies the object; an actuator rings the bell (actuation belongs to other agents). The sensing is entirely under the tray.
*BOM:* $80 to $150. *Difficulty:* moderate. *Risks:* classification of mixed objects; needs a "refuse" state.
*Novelty:* moderate; shows the closed-loop, performer-absent architecture.

**4.11 Decoy technology (level 2, presentational).**
*Effect:* the performer openly puts an EEG headband on a volunteer and "reads" a thought-of card from a brain-wave display. Then the headband comes off, the laptop is closed, and it works again.
*Method:* the visible technology decodes nothing useful [59][60]. The information comes from a hidden channel elsewhere in this report or from a classical method. The device absorbs the audience's "it's electronic" theory, and removing it then cancels that theory.
*BOM:* a used Muse (about $100 to $200, unverified). *Difficulty:* low.
*Novelty:* the structure (false explanation, then its removal) is classical; the prop is new.

**4.12 Pulse on a lamp (level 1).** A volunteer's heartbeat, measured from a fingertip clip, pulses a filament lamp across the room and falters when they think of the chosen card. Pure theatre, honest sensing, good as dressing for another method.

## 5. Dead ends and overhyped items

- **Voice stress analysis.** A US National Institute of Justice field study found two commercial systems detected about 15% of lies, overall around chance [62]. Use only as a prop.
- **Micro-expressions as a tell.** About 2% of high-stakes expressions in one study; poor classification in others [63]. Not a method.
- **Consumer EEG "mind reading".** Averaged-trial recognition effects exist [59][60]; a single live trial is noise. Minutes of flashing images is also poor theatre.
- **Pupil dilation.** Real but weak (AUC about 0.70) and it needs an eye tracker close to the face [58].
- **Camera or radar heart rate as a lie detector.** Heart rate is not deception, and hobby radar is 10 to 20 bpm off [32].
- **Lip reading at a distance.** 20%+ word error on ideal broadcast video [65].
- **Imaging an object in an envelope with hobby radar.** The published results need synthetic-aperture scans on a robot arm or contact with the sensor in a fixed lab setup [35][28].
- **Wi-Fi CSI sensing in a venue.** The vendor's own notes say bystanders break it [39].
- **Chipless RFID, hyperspectral cameras, contact-lens displays, silent-speech wearables.** Lab-only, four-figure, shelved [72] and not purchasable [68] respectively.
- **"Ultrasonic" data links at 15 kHz.** Audible to younger spectators [75].
- **Reading a full stacked RFID deck in one go.** Stacked HF tags detune; the commercial state of the art is three cards [11].
- **Thermal sensing of shiny coins.** Low emissivity; the camera sees reflections.

## 6. Open leads

- Whether hobby 60 GHz radar can count cards in a packet placed on it, as RadarCat's authors suspected [28].
- Measured load-cell accuracy for counting cards and for per-denomination coin identification on a real table.
- NFC tags with tamper-loop inputs (NTAG 213 TT class, unverified) as battery-free seal sensors.
- IDSense replication on the M7E reader: does the hobby reader expose phase and RSSI at a useful rate?
- A pen-IMU dataset limited to digits and ESP symbols across many writers; the public OnHW data [55] is a starting point.
- Open-source tools for live stroke streaming from Wacom smartpads (a Linux project named "tuhi" exists, unverified).
- BLE 5.1 direction finding and whether AirTag-class Precision Finding can be used through third-party UWB boards [38].
- Current products from Electricks, PITATA and Illuminati Magic (several pages refused automated access) so that agent 2's survey and this one agree on what is already sold.
- Ideomotor sensing: instrumented pendulum or planchette to measure, rather than assume, unconscious steering.
- Audience-attention logging validated against eye-tracking studies of misdirection (Kuhn and colleagues, unverified).

## 7. Sources

1. https://www.murata.com/en-us/products/rfid/rfid/overview/lineup/uhf - Murata UHF RFID tag line-up, sizes and reference read ranges.
2. https://www.murata.com/en-us/products/rfid/rfid/overview/lineup/hf/single - Murata HF/NFC module line-up (3.2 mm and 6.4 mm tags).
3. https://www.digikey.ca/en/products/detail/murata-electronics/LXMSJZNCMH-225/18876277 - DigiKey listing, 1.25 mm UHF tag.
4. https://www.nxp.com/products/rfid-nfc/nfc-hf/connected-nfc-tags/ntag-5-boost-nfc-forum-compliant-ic-bridge-for-tiny-devices:NTAG5-BOOST - NXP NTAG 5 boost.
5. https://community.nxp.com/t5/NFC/PN5180-read-3-5-tags-ISO15693/td-p/1201348 - NXP forum, reading several ISO 15693 tags with PN5180.
6. https://github.com/ATrappmann/PN5180-Library/issues/15 - PN5180 Arduino library, anticollision issue and workaround.
7. https://community.st.com/st25-nfc-rfid-tags-and-readers-54/how-do-i-read-multiple-nfc-tags-at-the-same-time-46641 - ST forum on multi-tag reads.
8. https://serialio.com/serialio-news/blog/iphone-read-tiny-nfc-tag/ - vendor blog on tiny NFC tag range (search snippet only; page refused fetch).
9. https://www.sparkfun.com/sparkfun-simultaneous-rfid-reader-m7e-hecto.html - SparkFun UHF reader, 300 tags/s, $309.95.
10. https://la.disneyresearch.com/publication/idsense/ - IDSense, Li, Ye and Sample, CHI 2015.
11. https://shop.52kards.com/products/insight-pro-by-hugo-shelley-trick - Insight Pro RFID deck, specifications and price.
12. https://vanishingincmagic.com/stage-and-parlor-magic/the-bat-system - The Bat System (search result).
13. https://thegadgetflow.com/portfolio/illuminati-magic-second-sight-rfid-system-for-mentalists-detect-cards-4point5inches-away/ - Second Sight description.
14. https://www.pokergfx.io/ - RFID card tables for poker broadcast graphics.
15. https://shop.52kards.com/products/sixth-sense-3-by-hugo-shelley-trick - Sixth Sense 3 specifications.
16. https://vanishingincmagic.com/close-up-magic/sixth-sense-25 - Sixth Sense 2.5, polarity signalling (search result).
17. https://vanishingincmagic.com/close-up-magic/espionage-iarvel - Espionage magnet detector (search result).
18. https://vanishingincmagic.com/stage-and-parlor-magic/uid-with-coin - UID, magnet and movement modes (search result).
19. https://penguinmagic.com/p/2499 - customer reviews of a magnet detector (search result).
20. https://meilu.jpshuntong.com/url-68747470733a2f2f7468656973636c61622e636f6d/projects/MagX/MagX.html - MagX project page (mirror URL as returned by search).
21. https://rtcl.eecs.umich.edu/rtclweb/assets/publications/2022/mobicom22-chen.pdf - University of Michigan PDF returned for the MagX query (not opened).
22. https://arxiv.org/abs/2601.22864 - µTouch, Wang et al., PerCom 2026.
23. https://arxiv.org/abs/2502.02459 - Computing with Smart Rings, systematic review, 2025.
24. https://ubicomplab.cs.washington.edu/publications/auraRing - AuraRing, IMWUT 2019.
25. https://www.hackster.io/news/three-magnetometers-a-fingertip-magnet-and-clever-mathematics-offer-cheap-accurate-3d-tracking-bb06ea25a787 - hobby-scale magnet tracking (search result; page refused fetch).
26. https://www.ti.com/product/LDC1614 - TI LDC1614 inductance-to-digital converter.
27. https://www.sparkfun.com/sparkfun-qwiic-scale-nau7802.html - NAU7802 24-bit load-cell ADC board, $5.95.
28. https://cse.buffalo.edu/faculty/dimitrio/courses/cse709_s17/material/papers/p833-yeo.pdf - RadarCat, Yeo, Flamich, Schrempf, Harris-Birtill and Quigley, UIST 2016 (full paper read).
29. https://sachi.cs.st-andrews.ac.uk/?p=6038 - St Andrews page on radar object recognition.
30. https://files.seeedstudio.com/Bazaar/product_pdf/114993387.pdf - Seeed MR60BHA2 datasheet and price (search result); also https://thepihut.com/products/60ghz-mmwave-breathing-and-heartbeat-detection-sensor-mr60bha2
31. https://smarthomescene.com/reviews/seeed-studio-60ghz-mmwave-sensors-review/ - independent review of Seeed 60 GHz sensors.
32. https://neurotechhub.wustl.edu/evaluating-a-60ghz-mmwave-radar-system - hobbyist evaluation of radar heart rate against a chest strap.
33. https://www.mdpi.com/2076-3417/12/20/10243 - 77 GHz FMCW classification of sealed box contents (search result; page refused fetch).
34. https://arxiv.org/abs/2512.11556 - ACCOR, occluded object classification from mmWave IQ (search result).
35. https://arxiv.org/abs/2502.10259 - MITO mmWave dataset and simulator, Boroushaki et al., 2025.
36. https://store.qorvo.com/products/detail/dwm3000-qorvo/681949/ - Qorvo DWM3000 module price.
37. https://www.robotshop.com/products/botstore-ai-thinker-dw3000-scheme-uwb-indoor-centimeter-level-high-precision-positioning-module-bu03-bidirectional-ranging-positioning - Ai-Thinker BU03 UWB module.
38. https://www.makerfabs.com/esp32-uwb-dw3000.html - Makerfabs ESP32 UWB DW3000 board, $43.80.
39. https://github.com/espressif/esp-csi - Espressif Wi-Fi CSI sensing examples.
40. https://www.robertxiao.ca/research/toffee/ - Toffee, Xiao et al., MobileHCI 2014.
41. https://arxiv.org/abs/2212.02918 - MIDAS thermal dissipation sensing, 2022.
42. https://rse-lab.cs.washington.edu/postscripts/HeatWave-CHI-11.pdf - HeatWave, CHI 2011 (search result; 404 when fetched).
43. https://www.technologyreview.com/2014/06/13/172534/thermal-camera-turns-many-things-into-interactive-surfaces/amp/ - thermal touch demo, 2014 (search result).
44. https://www.adafruit.com/product/4407 - MLX90640 thermal camera breakout, $74.95.
45. https://gamewithpixels.com/ - Pixels electronic dice.
46. https://appleinsider.com/articles/22/05/26/godice-review-make-game-night-more-fun-with-these-bluetooth-enabled-dice - GoDice review and price.
47. https://promystic.com/ - ProMystic product list.
48. https://support.wacom.com/hc/en-us/articles/1500006261081-Can-I-use-any-size-paper-with-my-Bamboo-Slate-or-Bamboo-Folio - Wacom, paper thickness limit.
49. https://www.wacom.com/en-us/for-business/technologies/emr - Wacom EMR technology.
50. https://www.tannens.com/products/parapad - ParaPad impression pad.
51. https://vanishingincmagic.com/mentalism/smart-memo-pad - PITATA Smart Memo Pad (search result; page refused fetch).
52. https://vanishingincmagic.com/mentalism/smart-clipboard - PITATA Smart Clipboard (search result).
53. https://thoughtcastmagic.com/ - ThoughtCast electronic impression pad system.
54. https://arxiv.org/abs/2202.07036 - Ott et al., handwriting recognition from IMU pens, IJDAR 2022.
55. https://stabilodigital.com/onhw-dataset/ - OnHW dataset page.
56. https://www.seeedstudio.com/XIAO-ESP32S3-Sense-p-5639.html - XIAO ESP32S3 Sense, $18.90.
57. https://arxiv.org/abs/2210.00716 - rPPG-Toolbox, Liu et al.
58. https://www.frontiersin.org/articles/10.3389/fnhum.2010.00018/full - Einhäuser, Koch and Carter, pupil dilation and decisions, 2010.
59. https://www.frontiersin.org/articles/10.3389/fnins.2017.00109/full - Krigolson et al., Muse validation for ERPs, 2017.
60. https://www.usenix.org/conference/usenixsecurity12/technical-sessions/presentation/martinovic - Martinovic et al., 2012 (sensing principle only).
61. https://github.com/NeuroTechX/eeg-notebooks - open EEG experiments for Muse and OpenBCI.
62. https://nij.ojp.gov/topics/articles/voice-stress-analysis-only-15-percent-lies-about-drug-use-detected-field-test - NIJ voice stress field test.
63. https://www.frontiersin.org/articles/10.3389/fpsyg.2018.01672/full - Burgoon, microexpressions, 2018.
64. https://arxiv.org/abs/2303.14307 - Auto-AVSR, Ma et al., ICASSP 2023.
65. https://github.com/mpc001/auto_avsr - Auto-AVSR model zoo with lip-reading word error rates.
66. https://arxiv.org/abs/2212.04356 - Whisper, Radford et al.
67. https://github.com/ggerganov/whisper.cpp - whisper.cpp, memory use and streaming.
68. https://www.media.mit.edu/projects/alterego/overview/ - MIT AlterEgo.
69. https://about.fb.com/news/2025/09/meta-ray-ban-display-ai-glasses-emg-wristband/ - Meta Ray-Ban Display and Neural Band.
70. https://www.nature.com/articles/s41586-025-09255-w - Meta sEMG interface paper, Nature 2025 (paywall redirect; not read).
71. https://www.evenrealities.com/ - Even Realities G2 and R1 ring.
72. https://www.mojo.vision/news/a-new-direction - Mojo Vision pivot away from the contact lens, January 2023.
73. https://developers.google.com/edge/mediapipe/solutions/vision/face_landmarker - MediaPipe Face Landmarker.
74. https://docs.espressif.com/projects/esp-idf/en/stable/esp32/api-reference/network/esp_now.html - ESP-NOW documentation.
75. https://github.com/ggerganov/ggwave - ggwave data-over-sound.
76. https://neolab.net/en/ - Neolab (Neo smartpen) site.
77. https://hackernoon.com/how-i-hacked-a-news-channel-to-report-fake-news-aa2f4b4f5b95 - maker write-up with an Arduino RFID reader under a table (search result).
78. https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/12159414 - US patent on heat-trace region extraction (search result).
