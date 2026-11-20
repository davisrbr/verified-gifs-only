# 27. Speed and compaction

Slice: two physical quantities that bound productions, vanishes and transformations. (A) How fast
something must move or change before vision stops following it. (B) How small something can be
stowed relative to its deployed size, and how fast and quietly it deploys or collapses.

Conventions. "Derived" means I computed the figure from sourced inputs; the arithmetic is shown.
"(unverified)" means recalled from memory and not confirmed on a page this session. Prices are as
of late 2026. The shared web-search budget ran out about two thirds of the way through, so several
prior-art and noise figures could not be checked; they are marked.

## 1. Summary

- **Speed is cheap; the latch, the stop and the timing are what cost.** A 6 g coin needs only 10 g
  of acceleration (0.6 N, 0.3 J) to cover 500 mm in about 100 ms, which is inside the 90 to 150 ms
  it takes the eye to start pursuit. Classical elastic already delivers this. What engineering adds
  is a release with no pre-motion, a stop with no click, and a trigger timed better than a person
  can time it.
- **Contrast, not velocity, sets the speed requirement.** Vision integrates over roughly 100 to
  120 ms. A moving object smears into a streak whose contrast is the object's contrast times
  (time it dwells at a point / integration time). A bright coin on black must clear its own width
  in about 3 ms (8 m/s) to streak below threshold; the same coin within 10% of the background
  luminance needs under 1 m/s. Background matching buys a tenfold cut in required speed (derived).
- **There are three "instant" thresholds, and they differ for eyes and cameras.** About 100 ms
  (cannot be tracked), about 30 to 40 ms (no intermediate state seen; one frame of ordinary video),
  and about 4 ms (one frame of 240 fps phone slow motion). Mechanical props can reach the first two.
  Only electro-optic changes, shutter blades and elastic membrane retraction reach the third.
- **Latch-mediated spring actuation (LaMSA) is the right design vocabulary for fast props.** The
  biology and robotics literature since 2018 treats motor, spring and latch as one coupled system.
  Hobby-scale results: a 30 g device going 0 to 28 m/s in 9 ms; a 1.5 g striker reaching 26 m/s;
  a toy popper snapping in under 5 ms. The latch geometry, not the spring, decides how clean the
  release is.
- **Audiences blink together, and they do it just after an effect lands.** Wiseman and Nakano
  (2016) found blink onsets synchronised within plus or minus 150 ms across viewers, with
  synchronised blinks right after each climax and on 4 of 7 secret actions. VR researchers have
  since built systems that detect one person's saccades and blinks and change the scene during
  them. Nobody appears to have pointed that at a physical prop.
- **Deployable-structure engineering beats every classical compaction benchmark on paper.** The
  appearing cane is about 17:1 in length. A coilable lattice mast stows in under 1% of its length
  (100:1) at under 35 g per metre and deploys on its own strain energy. Bistable reeled composite
  tubes (RolaTube and NASA booms) give a load-bearing pole from a hand-sized coil. Rigid-chain
  actuators give 10:1 at 1 m/s.
- **Collapse on a trigger now has several non-classical routes.** Layer jamming (a stack of
  sheets held rigid by vacuum, limp when air is let in), multistable inflatable origami (rigid
  without pressure, snaps flat), drop-stitch panels (board-stiff at about 1 bar, cloth when
  vented) and vacuum-driven origami (90% contraction).
- **Thinner sheet is the least glamorous and largest compaction gain.** Magicians' silk is about
  22 g/m2. Ultralight 7-denier nylon is 19 g/m2 at $18.50 per yard. Indoor-model film is
  1.4 g/m2: sixteen times the area of silk in the same packed volume. Four square metres of
  metallised film is about 4 cm3 of solid material.
- **Slow things to rule out early:** shape-memory alloy, electrochromics, e-paper (120 to 250 ms
  and it flashes), memory foam (hours to recover from tight packing), mechanical flip-dots (60 to
  70 ms and a loud click).
- **Safety scales with speed squared.** Anything above 10 m/s near a face, spring-steel edges,
  CO2 cartridges (frost, noise), capacitor-driven launchers (high voltage) and nitrocellulose need
  explicit hazard controls. Several of the best ideas below avoid all of these by moving nothing
  further than a fraction of a millimetre.

## 2. Catalog

### Part A. Speed

#### A1. The target: what vision can and cannot follow

What the sources give:

- **Smooth pursuit** starts 90 to 150 ms after a target begins to move; the first 100 ms or so
  is open-loop. Targets faster than about 30 deg/s tend to need catch-up saccades. One study
  cited in the literature found linear tracking up to 75 deg/s with gain about 0.9. A 1985 paper
  titled "The upper limit of human smooth pursuit velocity" exists; I recall its figure as about
  100 deg/s but could not open it (unverified).
  Sources: https://en.wikipedia.org/wiki/Smooth_pursuit ,
  https://scilit.com/publications/8e0b8b93c644e759c750f6d1ed6d7e1a
- **Saccades** take about 200 ms to launch at an unexpected target. Peak velocity is about
  300 deg/s for a 10 degree jump and 500 deg/s for 30 degrees, up to about 700 deg/s. Duration is
  roughly 2.2 ms per degree plus 21 ms, so a 10 degree saccade lasts about 43 ms. People make 2 to
  3 per second. Sources: https://en.wikipedia.org/wiki/Saccade , https://arxiv.org/pdf/1906.07183
- **Saccadic suppression** reduces sensitivity from about 40 to 50 ms before saccade onset to 50
  to 80 ms after it ends. The stationary images before and after the saccade mask the smear; even
  a 10 ms post-saccadic image abolished motion perception in one study.
  Sources: https://pmc.ncbi.nlm.nih.gov/articles/PMC3704127 ,
  https://elifesciences.org/articles/49700
- **Blinks.** The pupil is fully covered for about 100 ms; whole blinks run 100 to 300 ms and
  suppression extends beyond the lid closure. Large picture changes made during blinks are often
  missed even at the point of fixation (O'Regan, Deubel, Clark and Rensink 2000). People are
  functionally blind about 10% of the time.
  Sources: https://www2.psych.ubc.ca/~rensink/publications/abs.00.9.html ,
  https://www.inf.uni-hamburg.de/en/inst/ab/hci/projects/in-the-blink-of-an-eye.html
- **Temporal integration and smear.** Daylight vision sums over about 120 ms (Burr 1980).
  Perceived smear grows with exposure up to about 40 ms and then shrinks, because the visual
  system "deblurs" objects it has had time to register as moving. Blur thresholds are raised for
  moving targets at both 40 and 150 ms exposures. So a brief motion (under 40 ms) smears; a longer
  one is seen as an object in motion.
  Sources: https://www.nature.com/articles/284164a0.pdf ,
  https://pmc.ncbi.nlm.nih.gov/articles/PMC1688277
- **Flicker fusion** is typically 30 Hz or higher depending on brightness; the critical duration
  for luminance summation is about 35 to 100 ms. Source: https://webvision.med.utah.edu/?p=159
- **"The hand is quicker than the eye" is false as an account of sleight of hand.** Kuhn, Amlani
  and Rensink state that most manipulations are done at normal pace and work through attention.
  This matters here: speed is a property worth engineering into *mechanisms*, where it is cheap,
  not into hands. Source: https://philarchive.org/archive/RENTAS

**Design table 1: linear speed that gives a stated angular speed (derived, v = d x angular rate).**

| Angular speed | Meaning | At 0.5 m (close-up) | At 3 m (parlor) |
|---|---|---|---|
| 30 deg/s | pursuit starts to need catch-up saccades | 0.26 m/s | 1.6 m/s |
| 100 deg/s | approximate pursuit ceiling | 0.87 m/s | 5.2 m/s |
| 300 deg/s | peak of a 10 degree saccade | 2.6 m/s | 15.7 m/s |
| 700 deg/s | fastest human saccade | 6.1 m/s | 37 m/s |

Angular speed matters less than it looks, because pursuit cannot start for 90 to 150 ms. The
practical rule is about *duration*: if the object leaves and is hidden within about 100 ms, no eye
movement can follow it, whatever its speed. What remains is whether the streak is seen.

**Design table 2: streak visibility (derived; an estimate, not a measured threshold).** Model: if
the whole transit fits inside one integration window T of about 100 ms, the streak at any point has
contrast C0 x (w / v) / T, where C0 is the object's contrast against the background, w its length
along the direction of travel and v its speed. Take 3% as the contrast below which a brief streak
is not noticed (real thresholds vary from about 1% to 5% with size and lighting).

| Object (length along travel) | v for invisible streak, bright on dark (C0 about 0.9) | v if matched to background within 10% (C0 about 0.1) | Time to cover 150 mm / 500 mm at the first speed |
|---|---|---|---|
| Coin, 24 mm | 7 to 8 m/s | 0.8 m/s | 20 ms / 65 ms |
| Ball, 50 mm | 15 m/s | 1.7 m/s | 10 ms / 33 ms |
| Card, short axis 63 mm | 19 m/s | 2.1 m/s | 8 ms / 26 ms |
| Bunched silk, 60 mm | 18 m/s | 2 m/s | 8 ms / 28 ms |

Readings: (1) under black-art conditions (C0 of a few percent) nearly any speed works, which is
why black art works; (2) for ordinary lighting, a matched or mid-grey object and background
lets a 1 to 2 m/s pull vanish cleanly; (3) the numbers are almost independent of viewing distance,
because the streak model is about time, not angle; (4) a larger simultaneous motion elsewhere
(kinematic masking) and a clean stationary end state both raise the tolerance further, by the same
mechanism that hides saccadic smear.

**Design table 3: how short must a surface change be?**

| Threshold | Eyes | Cameras |
|---|---|---|
| 100 ms | Reads as "a quick change"; the transition can be glimpsed | 3 frames at 30 fps: plainly visible on replay |
| 30 to 40 ms | No intermediate state seen; reads as a cut | 1 frame at 30 fps |
| 16 ms | Below fusion for most conditions | 1 frame at 60 fps |
| 4 ms | Far below any visual threshold | 1 frame at 240 fps slow motion |
| 1 ms | - | 1 frame at about 1000 fps |

Camera notes (unverified, from general knowledge): phone sensors read out row by row over
roughly 5 to 30 ms, so a change faster than the readout shows as a horizontal tear line in one
frame, which a frame-stepping viewer will find. Indoor exposure times of 1/50 to 1/120 s add motion
blur that helps a mechanical move. PWM-driven shutters and LEDs can produce banding. If the trick
will be filmed, a change that completes behind a 100 ms natural occlusion is safer than a 4 ms
change in the open.

#### A2. Latch-mediated spring actuation (LaMSA)

*What it is.* A slow motor loads a spring; a latch holds it; release delivers the energy far
faster than the motor could. Ilton et al. (Science 2018) set out the trade-offs: springs have
their own force-velocity limits, latch removal takes finite time and shapes the launch, and the
best design depends on load mass. Longo et al. (J. Exp. Biol. 2019) named the framework. Hawkes
et al. (Nature 2022) showed that a ratcheted motor can "multiply work" over many strokes into a
hybrid tension-compression spring (rubber bands plus carbon-fibre bows): a 30 g, 30 cm device
winds for about 2 minutes, then accelerates 0 to 28 m/s in about 9 ms (about 320 g, derived) and
jumps over 30 m, at over 1,000 J/kg for the whole device. Steinhardt et al. (PNAS 2021) built a
1.5 g mantis-shrimp striker reaching 26 m/s in air and showed a two-stage latch: a contact latch
releases first, then the linkage geometry itself holds until it passes over-centre.

*References.* https://ri.cmu.edu/publications/the-principles-of-cascading-power-limits-in-small-fast-biological-and-engineered-systems ,
https://scholars.duke.edu/publication/1404324 ,
https://pateklab.biology.duke.edu/research/mechanics-of-ultrafast-movement/latch-mediated-spring-actuation-lamsa/ ,
https://www.nature.com/articles/s41586-022-04606-3 , https://spectrum.ieee.org/record-breaking-jumping-robot ,
https://pmc.ncbi.nlm.nih.gov/articles/PMC8379920

*Accessibility.* Hobbyist. Rubber, carbon strip or printed flexures, a micro gearmotor, a printed
over-centre latch. Under $20.

**Design table 4: constant acceleration over a prop-scale stroke (derived).** For a 6 g coin.

| Acceleration | 50 mm | 150 mm | 500 mm | Force on 6 g | Energy over 500 mm |
|---|---|---|---|---|---|
| 10 g | 32 ms, 3.1 m/s | 55 ms, 5.4 m/s | 101 ms, 9.9 m/s | 0.6 N | 0.3 J |
| 100 g | 10 ms, 9.9 m/s | 17 ms, 17 m/s | 32 ms, 31 m/s | 5.9 N | 2.9 J |
| 1000 g | 3.2 ms, 31 m/s | 5.5 ms, 54 m/s | 10 ms, 99 m/s | 59 N | 29 J |

*Magic relevance.* Hold/release, move. The useful ideas are not the headline speeds but: the
over-centre geometric latch (release force near zero, no solenoid click, no pre-motion); work
multiplication (a silent 2-minute wind-up in the pocket before the show instead of a strong spring
cocked by hand); and matching spring to load so the payload is not shaken at launch. The 10 g row
is enough for nearly all vanishes. The 100 g row gives single-video-frame exits over 150 mm and is
already hazardous near eyes.

*Prior use in magic.* Reels, pulls and spring gimmicks are ad hoc LaMSA devices (agent 21). I
found no magic source that uses the latch-design literature.

#### A3. Springs compared: elastic, steel, snap-through shells, tape springs

- **Rubber versus steel.** Natural rubber stores more energy per unit mass than steel springs
  (Perry and Rathod 2019), with higher hysteresis that falls with pre-strain. An informal
  calculation gives about 0.7 kJ/kg as the ceiling for a steel bar, with stretched polymers tens
  of times higher. Rubber creeps and perishes; steel does not. Silicone and polyurethane bands
  have less energy but far better ageing (unverified as to numbers).
  Sources: https://scienceportal.tecnalia.com/en/publications/energy-density-and-hysteresis-comparison-in-natural-rubber-tube-s/ ,
  https://dercuano.github.io/notes/spring-energy-density.html
- **Snap-through shells.** A toy rubber popper sits inverted for about 70 ms, then snaps in under
  5 ms. Snap time scales as L squared over (sound speed times thickness), so a 30 mm, 1 mm thick
  polymer cap snaps in a few milliseconds. The Venus flytrap closes in about 100 ms by the same
  instability. Shells are their own latch: bistable, no parts, printable in TPU or cut from a ball.
  Sources: https://www.bu.edu/moss/files/2014/10/EPL_2014_Pandey.pdf , https://arxiv.org/pdf/1807.05978
- **Stretched membranes.** A crack in an inflated latex balloon runs at about 570 m/s; a
  stretched membrane therefore uncovers a 10 cm object in well under 1 ms and retracts over the
  next few milliseconds. Below a critical membrane stress a single crack runs; above it the crack
  tip splits and the balloon shreds into fragments (Moulinet and Adda-Bedia 2015).
  Sources: https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.115.184301 ,
  https://physicsworld.com/?p=15869
- **Tape springs.** See B2; a steel tape or bistable composite deploys on stored strain energy
  with no mechanism, and its speed is normally something to be damped, not increased.

*Magic relevance.* The popper and the membrane are the two cheapest sub-5 ms mechanical events
available. The membrane result gives a specific design rule (keep stress low to get one clean
tear instead of confetti).

#### A4. Electromagnetic and gas actuators

- **Solenoids** are slower than expected: a 12 V, 4 mm push-pull hobby unit took 33 to 133 ms from
  drive to full stroke in one measured write-up; 50 ms pull-in is typical. Overdriving helps.
  Source: https://cindyli-13.github.io/FYDP-design-log/jekyll/update/2023/11/16/solenoid-characterization.html
- **Voice coils** give over 20 g and move-and-settle under 15 ms over strokes of 1 to 76 mm; a
  miniature unit gives 5 N peak over 3 mm. $50 to $300 new; free from dead hard drives.
  Source: https://news.thomasnet.com/fullstory/linear-actuators-produce-more-than-20-g-acceleration-13419
- **Thomson coils** (pulsed repulsion of a conducting disc) move 30 mm in 5.4 ms at 300 V in a
  circuit-breaker prototype, with sub-millisecond contact opening as the design goal. High
  voltage, loud crack. Lab or advanced hobby. Source: https://mdpi.com/2076-0825/11/6/154
- **Reluctance coil launchers** at hobby scale manage 17 to 18 m/s on gram-scale slugs at 1 to
  3.5% efficiency. Poor fit: bulky capacitors, heat, hazard.
  Source: https://www.nature.com/articles/s41598-022-27022-z
- **Electropermanent magnets** hold with zero power and switch on a pulse; break-even times
  against an electromagnet are milliseconds at centimetre scale and microseconds at millimetre
  scale (Knaian thesis via Hizook). The on/off force ratio is four orders of magnitude in the
  reference design. This is the zero-latency, zero-standby release for LaMSA latches. Detail in
  agent 7. Sources: https://dspace.mit.edu/handle/1721.1/60151 ,
  https://en.wikipedia.org/wiki/Electropermanent_magnet
- **Compressed gas.** Wearable airbags fill in 20 to 100 ms from CO2 or helium cartridges
  (pyrotechnic car bags: 30 to 50 ms). An 8 g CO2 bulb yields about 4.4 L at room pressure, 16 g
  about 8.7 L (derived from 44 g/mol and 24 L/mol). Loud, and the bulb frosts.
  Sources: https://en.helite.com/?p=81196 , https://www.thedrive.com/reviews/30248/best-motorcycle-airbag-vest
- **Piezo micro-blowers.** Murata's MZB1001T02 is 20 x 20 x 1.85 mm, moves 0.7 to 1.2 L/min at
  1.4 to 2.5 kPa, and runs at 24 to 27 kHz, above hearing. A silent, flat, slow inflator: about a
  minute per litre. Source: https://www.murata.com/products/mechatronics/fluid/overview/lineup/microblower_mzb1001t02
- **Shape-memory alloy is slow.** Heating can take a few hundred milliseconds with overdrive but
  cooling takes seconds; use it to *trip a latch*, never as the fast element (agent 7).
- **Piezo stacks** are fast (microseconds) but move micrometres; useful only for the
  sub-millimetre shutters in A6.

#### A5. Fast shutters and covers

- **Focal-plane camera shutters.** Vertical-travel blades cross 24 mm in about 3 to 4 ms; a
  1/300 s sync camera implies about 7 m/s average blade speed, constant regardless of the set
  exposure. A complete unit is about 60 x 50 x 5 mm, is cocked by a spring and released by two
  small electromagnets. Used units cost roughly $10 to $30 (unverified). This is a ready-made
  "replace one 24 x 36 mm surface with another in 4 ms" component.
  Sources: https://en.wikipedia.org/wiki/Focal-plane_shutter , https://mhohner.de/newsitem2/myths/7
- **Liquid-crystal shutters.** Auto-darkening welding filters switch clear to dark in under 1 ms
  (patent literature; retail claims of 1/25,000 s are common but I could not verify one). A
  replacement filter is about 110 x 90 mm and $10 to $30 (unverified). They go dark, not opaque
  white, so they suit dark-on-dark concealment. Source: https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/5751258
- **PDLC "smart film".** Rise times from hundreds of microseconds to about 4 ms; decay about
  50 ms at room temperature and 300 to 600 ms at minus 10 C. A 2026 lab film saturates at 7 V with
  4.2 ms rise and 47 ms decay. So clear-on is instant and frost-return is one or two video frames.
  Sources: https://opticalengineering.spiedigitallibrary.org/conference-proceedings-of-spie/958/0000/Temperature-Dependent-Electro-Optic-Performance-Of-Polymer-Dispersed-Liquid-Crystal/10.1117/12.947723.full ,
  https://mdpi-res.com/d_attachment/molecules/molecules-31-01402/article_deploy/molecules-31-01402.pdf
- **Reflective displays.** E-paper takes 120 to 250 ms and flashes. Electrowetting pixels switch
  in under 10 to 20 ms (vendor and patent figures) but are hard to buy as bare panels. Detail in
  agent 5. Sources: https://displaydaily.com/?p=37324 , https://phys.org/news/2010-07-oil-based-pixels-videos-e-paper.html
- **Flip-dots.** Coil pulse 0.5 ms at 24 V, but the disc takes 60 to 70 ms to turn and clicks.
  Arrays reach 30 fps. Too slow and too loud for a hidden change; fine as an honest display.
  Source: https://hackaday.com/2023/03/03/a-close-look-at-how-flip-dot-displays-really-work
- **Rigid-chain "zip" actuators** push a rigid column out of a housing one tenth of the stroke
  at up to 1 m/s (industrial; see B3). Source: https://tsubakimoto.com/power-transmission/linear-actuator/zip-chain-actuator/
- **Combustion.** Flash paper and flash cotton burn out in well under a second with no ash. They
  are a cover and an "erase", not a mechanism; fire and storage hazards apply.
  Source: https://edu.rsc.org/exhibition-chemistry/the-production-and-combustion-of-nitrocellulose/4015917.article

#### A6. Surface change with sub-millimetre travel

Not a paper cluster but a principle the display literature implies: if two images are interleaved
at a pitch finer than the eye resolves, moving a mask by half a pitch swaps the whole surface.
Visual acuity is about 1 arcminute, which is 0.15 mm at 0.5 m and 0.9 mm at 3 m (derived). A
line screen of 0.1 mm stripes over an interlaced print is therefore unresolved at close-up range,
and the full change needs 0.1 mm of travel: within reach of a piezo bender, a voice coil, a
bimetal strip or a thumb on a flexure, in about a millisecond, silently. Lenticular sheet does the
same with a lens array (60 to 75 lines per inch means a half pitch of about 0.17 to 0.21 mm) and
no light loss, at the cost of a viewing-angle dependence and a ribbed surface. This is the
micro-scale descendant of the classical sliding-louvre and flap methods. I found no magic prior
art for a *translated* interlace (as opposed to tilt-to-flip lenticular novelty cards), but
searching was cut short (unverified novelty).

#### A7. Stopping quietly, and the sound of release

No sourced decibel figures were found for any of the mechanisms above; this is a measurement job.
Engineering options, from general knowledge (unverified numbers): an eddy-current brake (a magnet
entering a copper or aluminium tube) gives a force proportional to speed with no contact and no
sound, and from the familiar magnet-in-pipe terminal speed of about 0.1 m/s one can estimate a
stopping distance of roughly 10 mm per m/s of entry speed; viscoelastic pads (Sorbothane class)
absorb the last few millimetres; a crushable paper or foam stop is silent once. For release noise,
use over-centre or magnetic latches instead of sears, keep moving masses in the gram range, and
decouple the mechanism from any resonant panel.

#### A8. Timing aids

- **Audience blink synchrony.** Wiseman and Nakano (PeerJ 2016): 20 viewers of a Teller coin
  routine, mean 15.4 blinks per minute, blink onsets clustered within plus or minus 150 ms across
  viewers, 11 moments when 6 or more blinked together, 4 of 7 secret actions coinciding with a
  synchronised blink, and synchronised blinks "immediately after the conclusion of a magical
  effect". Barnhart et al. (2022) found magicians blink more during deceptive actions. Small
  samples, one video. Sources: https://peerj.com/articles/1873 ,
  https://resou.osaka-u.ac.jp/en/research/2016/20160404_1 ,
  https://www.psypost.org/study-suggests-magicians-unconsciously-blink-their-eyes-to-manipulate-the-audience-during-difficult-tricks/
- **Machine-timed changes during eye events.** Sun et al. (SIGGRAPH 2018) detect saccades with an
  eye tracker and rotate a VR scene during the suppression window. Langbehn et al. (2018) do the
  same in blinks: 4 to 9 cm of translation and 2 to 5 degrees of rotation go unnoticed per blink.
  Marwecki et al., "Mise-Unseen" (UIST 2019), model attention and spatial memory from gaze and
  inject scene changes inside the field of view; changes went unnoticed mainly when gaze was
  combined with ordinary masking. Zenner et al. (CHI 2024) combine saccades and blinks.
  Sources: https://research.nvidia.com/publication/2018-08_Towards-Virtual-Reality ,
  https://www.inf.uni-hamburg.de/en/inst/ab/hci/projects/in-the-blink-of-an-eye.html ,
  https://www.microsoft.com/en-us/research/?p=615969 ,
  https://www-live.dfki.de/fileadmin/user_upload/import/14956_zenner-saccadic-blink-suppressed-hand-redirection-chi-24-pre-print.pdf
- **Timing budget (derived).** A 10 degree saccade lasts about 43 ms and suppression persists
  about 50 ms after. A system that detects onset within 10 ms has 30 to 80 ms to finish. PDLC,
  LC shutters, shutter blades, snap shells and half-pitch masks fit. Flip-dots are marginal.
  E-paper does not fit. A blink gives 100 ms or more. Sensing hardware is agent 10's slice.

### Part B. Compaction

#### B1. Classical benchmarks, with numbers where found

| Prop | Stowed | Deployed | Ratio | Notes |
|---|---|---|---|---|
| Appearing wand (steel coil) | 2.5 in long | 14 in | 5.6:1 length | dealer listing |
| Appearing cane (plastic) | 6 cm | 100 to 110 cm | about 17:1 length | dealer listing; metal versions 110 to 150 cm |
| Vanishing birdcage (de Kolta) | tube about 18 in x 1 to 2 in | box cage (size not stated) | not stated | collapses when not held at both ends; elastic sleeve pull |
| Mouth coil | wafer-sized roll | 25 to 90 ft paper | - | one-shot |
| Thumb-tip streamer | thumb tip, about 10 cm3 | 1 in x 34 to 68 in, or 2 in x 4 ft silk | - | "king size" tip for the longest |
| 45 cm silk, about 5 momme | about 3.4 cm3 solid, 7 to 10 cm3 packed (derived) | 0.2 m2 | - | 4.5 g at about 22 g/m2 |
| Spring flowers | flat stack | 25 flowers, bouquet about 12 in round | - | shipping compressed weakens the spring |
| Zombie ball | - | - | - | 14 in gimmick, not a compaction prop |
| Hoberman sphere (toy) | 15 cm | 76 cm | 5.1:1 diameter | reference point outside magic |

Sources: https://www.desertcart.ni/products/13557530 ,
https://shop.52kards.com/products/appearing-cane-plastic-red-by-jl-magic ,
https://en.wikipedia.org/wiki/Vanishing_bird_cage , https://vanishingincmagic.com/mouth-coils/90ft-mouth-coil ,
https://vanishingincmagic.com/mouth-coils/thumb-tip-streamer-12-pack-1-68 ,
https://www.funinc.com/spring-flower-25/dr00150p/ ,
https://magicgizmo.com/home/articles-miscellaneous-topics/71-magic-workshop/314-how-to-restore-pop-and-spread-of-spring-flowers ,
https://en.wikipedia.org/wiki/Zombie_ball , https://en.wikipedia.org/wiki/Hoberman_sphere

Not verified this session: the history of the Walsh cane, deploy times of canes (commonly
described as a fraction of a second), the bowling-ball-from-sketch-pad method, appearing poles
and ladders, and why Tommy Wonder's birdcage is admired. On the last, a blog source says he used a
double-action pull and performed with rolled-up sleeves, and a bibliography lists his text "The
Well-Tempered Birdcage" as a detailed account of cage, lock and cloths; the admiration is, as far
as I recall, for removing every snag point and for the naturalness of the handling (unverified).
Sources: https://www.magicshow.tips/tag/wrist-to-wrist-pull ,
https://www.conjuringarchive.com/list/category/419

#### B2. Tape springs, bistable reeled composites and space booms

*What they are.* A tape spring is a thin curved strip, straight and stiff when extended, that
flattens and rolls. A carpenter's tape is the consumer version. Bistable reeled composites (BRC),
commercialised by RolaTube in the late 1990s, are slit tubes with a fibre layup that makes the
rolled state stable too, so the coil does not need a cassette to restrain it. RolaTube sells
tubes of 32 to 100 mm diameter in glass-reinforced polypropylene as field masts. NASA's small-sat
booms give scale: bistable shells with 28 mm natural coil diameter; four booms of at least 6.85 m
each stowing in 100 x 200 x 60 mm at under 0.25 kg per boom. Closed-section variants (lenticular
CTM, TRAC, SHEARLESS: two tape springs face to face in a sleeve) add torsional stiffness.
Deployment is self-driven by strain energy and has to be damped; an uncontrolled roll-out ends in
an impact.

*References.* https://www.rolatube.com/ ,
https://ntrs.nasa.gov/api/citations/20170001569/downloads/20170001569.pdf ,
https://technology.nasa.gov/patent/LAR-TOPS-268 ,
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10255148/

*Accessibility.* Steel tape blades: off the shelf, $5 to $30. Two blades in a sewn sleeve: an
afternoon. True bistable composite: hobbyist with care (thin plus/minus 45 degree glass or carbon
layup on a mandrel), or buy a RolaTube consumer product; no public prices.

*Magic relevance.* This is the engineered descendant of the appearing cane. Differences that
matter: the deployed tube is smooth and closed-looking, bears load, and can be handed out and
leaned on; it is not a sharp steel spiral; and bistable versions re-roll for a vanish. Weakness:
the slit, and re-rolling is a hand action, not an instant collapse.

*Prior use in magic.* None found (search incomplete).

#### B3. Masts, telescopes and rigid chains

- **Coilable lattice masts.** Three continuous longerons, battens and diagonals; twisting the
  mast coils the longerons flat. A carbon mast for solar sails stows in under 1% of its deployed
  length, weighs under 35 g/m and self-deploys on stored strain energy with a lanyard metering
  the rate. The design has flown since the 1970s. Hobby version: pultruded 1 mm glass or carbon
  rods, printed battens, thread diagonals.
  Sources: https://www.jpl.nasa.gov/nmp/st8/tech/sailmast_tech3.html ,
  https://roadmaps.mit.edu/en/roadmaps/Space_Booms
- **Computational telescoping.** Yu, Crane and Coros (SIGGRAPH 2017) showed that telescoping is
  not limited to straight tubes: any constant-curvature (helical) curve telescopes, so rings,
  spirals, claws and branching shapes can nest. Their tool converts a sketch or mesh into nested
  printable shells; code is public.
  Sources: https://www.cs.cmu.edu/~christoy/Projects/Telescopes.html ,
  https://github.com/icethrush/telescoping-structures
- **Rigid-chain (zip) actuators.** Two chains mesh into a rigid column; the housing is about one
  tenth of the stroke; up to 1 m/s; strokes to 5 m. Industrial and heavy, but printable in small
  form. Sources: https://tsubakimoto.com/power-transmission/linear-actuator/zip-chain-actuator/ ,
  https://en.wikipedia.org/wiki/Rigid_chain_actuator

*Magic relevance.* Production, animation (a column that grows at a metered rate), and furniture
that is not there until needed. A 100:1 mast is far beyond any magic prop I could find.

#### B4. Origami, scissor and elastic-grid deployables

- **Flasher pattern.** A rigid-panel prototype went from 0.136 m to 1.25 m diameter (9.2:1) with
  thickness accommodated (Zirbel, Lang et al. 2013); a 10 m version served as a starshade
  optical shield. Sources: https://langorigami.com/publication/accommodating-thickness-in-origami-based-deployable-arrays/ ,
  https://ntrs.nasa.gov/citations/20150008719
- **Miura-ori and Kresling.** A thesis comparison gives volume expansion ratios of 8.31 for
  Miura bellows and 2.56 for Kresling; Kresling tubes can be bistable and twist as they extend.
  Sources: https://research-information.bris.ac.uk/en/studentTheses/geometry-and-modelling-of-multi-stable-origami-bellows/ ,
  https://arxiv.org/pdf/2003.10411
- **Scissor linkages.** Hoberman's toy is 5.1:1 in diameter; ideal volume contraction to 12.5%,
  35% measured in one voxel design. One degree of freedom: push any joint and the whole moves.
  Source: https://www.eng.yale.edu/Faboratory/publications/conference/2024/Woodman%20-%202024%20-%20Deployable%20Cuboctahedrons%20for%20Adaptive%20Space%20Infrastructure.pdf
- **Elastic grids from computation.** Programmable auxetics (2018) deploy a flat laser-cut sheet
  to a chosen doubly curved surface by inflation or gravity. X-Shells (2019) are flat beam grids
  that pop to a designed 3D form. Umbrella meshes (2022) go from a compact block to a target
  surface as their beams swing from vertical to horizontal.
  Sources: https://www.ri.cmu.edu/publications/rapid-deployment-of-curved-surfaces-via-programmable-auxetics ,
  https://infoscience.epfl.ch/record/296487
- **Spring-steel hoops.** A flat-section steel loop folds into three stacked loops of one third
  the diameter, the pop-up tent and photo-reflector principle; the mechanics are analysed as ring
  "overcurvature". Sources: https://www.nature.com/articles/ncomms2311 ,
  https://groups.seas.harvard.edu/hutchinson/papers/2023-2T-SGPRingstability.pdf

*Magic relevance.* The computational grids matter most: they let a hobbyist specify the deployed
*shape* (a head, a vase, a hat) and get a flat or block-shaped load, where spring flowers and
spring animals were designed by trial. The fold lines and lattice look are the giveaway, so these
suit objects that are covered in fabric or film.

#### B5. Fluids, vacuum and jamming

- **Vacuum origami "muscles".** A folded skeleton in a sealed skin contracts when evacuated: over
  90% contraction, about 600 kPa stress, over 2 kW/kg, under $1 in materials (Li, Vogt, Rus and
  Wood, PNAS 2017). Read backwards, this is a rigid-looking form that shrinks to a tenth of its
  length on a puff of suction. Source: https://pmc.ncbi.nlm.nih.gov/articles/PMC5740677
- **Multistable inflatable origami.** Rigid-walled bistable units that deploy from one pressure
  input and then stay deployed with no pressure, demonstrated at metre scale as arches and
  shelters (Melancon et al., Nature 2021). Source: https://pubmed.ncbi.nlm.nih.gov/33883736/
- **Drop-stitch fabric.** Two skins tied by thousands of fixed-length threads become a flat,
  board-stiff panel when inflated: working pressures 15 to 25 psi, effective modulus about 75 MPa
  at 30 psi, thickness 2 to 6 in. Source: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10650755/
- **Laminar (layer) jamming.** A stack of sheets in a sealed envelope bends freely; under
  vacuum, friction couples the layers and bending stiffness rises sharply, tunable by layer count
  and pressure (Narang, Vlassak and Howe 2018). I could not retrieve the stiffness ratio; values
  of one to two orders of magnitude are commonly reported (unverified). Release is as fast as air
  can re-enter. Sources: https://softroboticstoolkit.com/publications/mechanically-versatile-soft-machines-through-laminar-jamming ,
  https://www.seas.harvard.edu/news/2018/05/robot-transitions-from-soft-to-rigid
- **Gas sources.** CO2 bulbs (A4); micro-blowers (silent, slow); citric acid plus bicarbonate
  (about 0.29 L of CO2 per gram of bicarbonate, derived; wet and slow, tens of seconds).

*Magic relevance.* Hold/release, transform, erase. Jamming and drop-stitch give "rigid until
triggered" with no hinges or locks to find, the property the Zombie gimmick, vanishing cane and
birdcage each achieve with one special mechanism.

#### B6. Sheets, foams and swelling materials

- **Fabrics and films.** 7-denier ripstop nylon: 19 g/m2, 58 in wide, $18.50 per yard, opaque
  enough to print. Silk at 5 momme: about 22 g/m2 (1 momme is 4.34 g/m2). Indoor free-flight
  films: 1.4 micron at 1.4 g/m2 and 0.68 micron at 0.7 g/m2, available aluminised with no weight
  penalty. Solid volume per square metre (derived): silk 17 cm3, 7D nylon 17 cm3, 1.4 micron film
  1 cm3. Sources: https://ripstopbytheroll.com/products/0-56-oz-membrane-7-ripstop-nylon ,
  https://en.wikipedia.org/wiki/Habutai ,
  https://prod-8babe12b-be845633-ssb7vc4z.app.devpanel.com/article/covering-materials-ff
- **Compressed towels.** A 4 cm tablet becomes a 28 x 25.5 cm viscose cloth in 5 to 10 s in
  water; a 7.5 cm tablet becomes a 70 x 140 cm towel. Sold through promotional-goods suppliers,
  where custom printing is the norm (printing not confirmed on the page I saw).
  Sources: https://en.wikipedia.org/wiki/Towel_tablet ,
  https://goodthings.com.au/products/giveaways/sports/towels-sports/compressed-towel-small
- **Superabsorbent polymer.** Sodium polyacrylate takes up about 300 times its weight in tap
  water (800 in distilled, 50 in saline), 30 to 60 times its volume. The cross-linked "instant
  snow" grade fluffs instead of gelling. Sources: https://www.cmu.edu/gelfand/k12-educational-resources/polymers/polymer-and-absorption/super-absorb-powder.html ,
  https://chemed.chem.purdue.edu/genchem/demosheets/25.5.html
- **Foams.** Fire-service high-expansion generators make 500 to 1000 volumes of foam per volume
  of solution, with a fan. Viscoelastic "memory" foam is deliberately slow: a roll-packed mattress
  takes 24 to 72 hours to recover fully, and long compression slows it further. Ordinary
  high-resilience polyurethane (the sponge-ball material) recovers in well under a second
  (unverified figure, common experience). Aerogel is brittle and sheds; not a production material.
  Sources: https://www.naffco.com/portable-high-expansion-generator ,
  https://www.tomsguide.com/wellness/mattresses/how-long-does-a-mattress-in-a-box-take-to-expand-and-when-can-you-sleep-on-it

#### B7. Mass as the give-away

A deployed object's mass is fixed by what was stowed. A 1 m pole from B2 or B3 weighs 30 to 150 g
where a wooden one weighs 300 g or more; a film or 7D fabric sheet weighs a tenth of the cloth it
imitates and falls slowly; a foam or shell "ball" weighs grams where a billiard ball weighs about
170 g. The audience mostly judges mass from how the performer moves it, so the performer must act
the weight, and the object should not be handed out unless a real duplicate is switched in.
Perceptual tolerances for weight are in agent 4's report (its section D and appendix).

## 3. Capability primitives

1. *Now possible:* release a spring load with near-zero trigger force and no pre-motion.
   *Because:* over-centre geometric latches from the LaMSA literature, tripped by an
   electropermanent magnet pulse. *Before:* sears, pins and thread pulls that click and twitch.
   *Primitives:* hold/release.
2. *Now possible:* charge a strong spring silently over 2 minutes from a coin cell and a micro
   gearmotor, so nothing has to be cocked by hand. *Because:* work multiplication (Hawkes 2022).
   *Before:* spring strength limited by what a hand could set without looking. *Primitives:* move,
   delay.
3. *Now possible:* choose the minimum speed for a vanish from a table instead of by feel: 1 to
   2 m/s if the object is within 10% of the background luminance, 8 to 20 m/s if it is bright on
   dark. *Because:* temporal-integration psychophysics. *Before:* trial and error; "use stronger
   elastic". *Primitives:* move, conceal.
4. *Now possible:* swap a 24 x 36 mm visible surface in 3 to 4 ms, inside one frame of 240 fps
   video. *Because:* salvaged focal-plane shutter units. *Before:* flaps and slides at 30 to
   100 ms. *Primitives:* swap, transform.
5. *Now possible:* change a whole printed surface with 0.1 to 0.2 mm of travel in about 1 ms,
   silently, in a 1 mm thick laminate. *Because:* 1200 dpi printing, line-screen film or
   lenticular sheet, piezo benders. *Before:* louvres and flaps with centimetre travel and visible
   slats. *Primitives:* transform, conceal.
6. *Now possible:* make a window clear in under 4 ms and frosted again in about 50 ms at 7 to
   60 V. *Because:* PDLC film. *Before:* a cloth, a door, a flap. *Primitives:* conceal.
7. *Now possible:* darken a 110 x 90 mm aperture in under 1 ms for about $20. *Because:* welding
   auto-darkening filters. *Before:* nothing comparable. *Primitives:* conceal.
8. *Now possible:* uncover an object in under 1 ms and clear the cover in a few more, with one
   clean tear and no fragments. *Because:* controlled-stress latex membranes (crack speed about
   570 m/s; fragmentation only above a stress threshold). *Before:* the colour-changing balloon,
   which shreds unpredictably. *Primitives:* transform, erase.
9. *Now possible:* a sub-5 ms mechanical event from a one-piece printed part with no latch.
   *Because:* snap-through shells. *Before:* multi-part spring catches. *Primitives:* release,
   move.
10. *Now possible:* stop a 5 to 10 m/s gram-scale load with no contact and no sound in 50 to
    100 mm (estimate). *Because:* eddy-current braking with small NdFeB magnets and copper tube.
    *Before:* the load hits cloth, a body or a stop. *Primitives:* move, conceal.
11. *Now possible:* time a secret action to within tens of milliseconds of one spectator's saccade
    or blink. *Because:* cheap IR eye tracking and the VR redirection literature. *Before:* the
    performer's feel for off-beats. *Primitives:* control attention, conceal, know.
12. *Now possible:* predict when a whole audience will blink (within plus or minus 150 ms, just
    after a climax) and schedule a machine action there. *Because:* blink-synchrony research.
    *Before:* intuition about "relaxation after the effect". *Primitives:* delay, conceal.
13. *Now possible:* a smooth, load-bearing 1.5 to 3 m pole from a 60 to 80 mm coil.
    *Because:* tape springs in a sleeve, bistable reeled composites. *Before:* the appearing cane,
    which is a sharp spiral that cannot be leaned on or closely handled. *Primitives:* produce,
    prove ordinariness.
14. *Now possible:* a self-erecting lattice column stowed at 1% of its height, under 35 g/m,
    rising at a metered rate. *Because:* coilable-mast design. *Before:* 17:1 at best, all at
    once. *Primitives:* produce, animate.
15. *Now possible:* telescoping objects that are curved, spiral or branched, generated from a
    sketch. *Because:* computational telescoping (code public) and FDM printing. *Before:*
    straight canes, straws and poles only. *Primitives:* produce, vanish.
16. *Now possible:* specify the deployed 3D shape and receive a flat or block-shaped load.
    *Because:* programmable auxetics, X-Shells, umbrella meshes. *Before:* hand-developed spring
    animals and flowers. *Primitives:* produce.
17. *Now possible:* an object that passes a knock-and-flex test, then goes cloth-limp in under
    0.2 s when air is admitted, with no hinge or lock to find. *Because:* layer jamming under
    stored vacuum. *Before:* one bespoke mechanism per prop (cane coil, cage joints). *Primitives:*
    hold/release, transform, prove ordinariness.
18. *Now possible:* a board-stiff panel from folded cloth in under 1 s, and back in about the
    same. *Because:* drop-stitch fabric plus a 16 g CO2 bulb (about 8.7 L). *Before:* hinged
    folding boards. *Primitives:* produce, vanish.
19. *Now possible:* a rigid form that stays up with no pressure and snaps flat when pushed.
    *Because:* multistable inflatable origami. *Before:* inflatables that sag. *Primitives:*
    produce, hold.
20. *Now possible:* a form that shrinks by 90% of its length on suction, for under $1.
    *Because:* vacuum-driven origami skeletons. *Before:* pulls that remove the object but do not
    shrink it. *Primitives:* vanish, move.
21. *Now possible:* 4 m2 of opaque metallised sheet from about 4 cm3. *Because:* 1.4 micron
    polyester film at 1.4 g/m2. *Before:* about 0.25 m2 of silk in the same space. *Primitives:*
    produce, conceal.
22. *Now possible:* a printable, opaque cloth at 19 g/m2 for $18.50 a yard. *Because:* 7-denier
    ripstop nylon. *Before:* silk at similar weight but higher cost and no rip resistance.
    *Primitives:* produce, duplicate.
23. *Now possible:* a 25 cm printed cloth hidden in a 2 to 4 cm tablet that looks like a mint,
    opening by itself in 5 to 10 s in water. *Because:* compressed viscose "coin tissue" and a
    shop press. *Before:* silks in hollow gimmicks. *Primitives:* conceal, delay, produce.
24. *Now possible:* silent inflation at about 1 L/min from a 20 x 20 x 1.85 mm part. *Because:*
    ultrasonic piezo micro-blowers. *Before:* squeeze bulbs, mouth, noisy diaphragm pumps.
    *Primitives:* move, delay, animate.
25. *Now possible:* a 3:1 diameter reduction of any hoop-framed flat object by a twist.
    *Because:* spring-steel band folding (known mechanics, cheap bandsaw-blade stock). *Before:*
    known to photographers; little used in magic beyond pop-up backdrops (unverified). *Primitives:*
    produce.

## 4. Effect concepts

Levels refer to the brief: 1 phenomenon is the effect, 2 hidden input to a classical method,
3 new method architecture. Novelty claims are limited by the truncated prior-art search.

### 4.1 The half-pitch card (level 3; uses a speed capability magic does not use)

*Effect.* A signed selection lies face up under the spectator's own finger, or under a glass.
Its back, or a printed prediction beside it, changes with no cover and nothing seen to move.

*Method.* The changing surface is a three-layer laminate: an interlaced print (image A and image
B in alternating 0.1 mm stripes), a clear line-screen film with 0.1 mm opaque stripes, and a
cover. The screen hides all B stripes. Shifting the screen 0.1 mm hides A and shows B. At 0.5 m
the eye resolves about 0.15 mm, so the stripes read as a slightly dim continuous image. The shift
comes from a flexure pressed at the card's edge, a bimetal strip warmed by the hand, or a piezo
bender in a close-up pad acting through a magnet. Travel time is about a millisecond. The dimming
(half the area is mask) is disguised by choosing dark designs and by printing the "normal" props
in the act at the same density.

*BOM and cost.* Line-screen film from a print bureau or a 1200 dpi laser on transparency; inkjet
photo print; 0.1 mm spring-steel flexure. Under $15.

*Difficulty.* Medium: registration to 20 microns over the card needs a jig.

*Risks.* Moire if the layers rotate; inspection under a loupe; a faint texture under raking light.
Not examinable at reading-glasses distance; switch out or keep under glass.

*Novelty.* I believe new as a translated (not tilted) interlace in a hand prop. Unverified.

### 4.2 Blink-gated installation (level 3; uses a timing capability magic does not use)

*Effect.* A single visitor studies an object in a display case: a chess position, a row of
objects, a painting. It is never seen to change, yet when they look back from the label, it has.
They can stare at it for a minute and nothing happens.

*Method.* An IR camera in the case frame tracks the visitor's eyes at 120 Hz or more. The
controller acts only inside a blink (100 ms or more of cover) or within a large saccade away from
the object (30 to 80 ms). The actuators are the fast ones from Part A: half-pitch masks, shutter
blades, snap shells, PDLC. Mise-Unseen's finding applies: gaze-gating works best combined with
ordinary masking, so the label text and a small light change give the visitor a reason to look
away. For a seated audience the same controller listens for the applause or laugh that follows a
climax and fires about 300 ms later, when synchronised blinking is most likely.

*BOM and cost.* Global-shutter IR camera module and IR LEDs ($40), single-board computer ($50),
open-source gaze code, actuators as above. $150 to $300.

*Difficulty.* High in software, low in mechanics.

*Risks.* Two viewers at once (gate on both or lock out); spectacles and IR reflections; a
bystander filming, since a camera does not blink (use changes that also sit under a physical
occlusion). Sensing detail is agent 10's.

*Novelty.* VR does this routinely; I found no physical-object version. Unverified.

### 4.3 The four-millisecond stamp (level 2 to 3; uses a speed capability magic does not use)

*Effect.* A small framed picture, a postage stamp on an envelope, or the dial of a pocket watch
changes at a finger snap. On slow-motion replay there is no in-between frame.

*Method.* A salvaged vertical focal-plane shutter sits behind the frame's mat. Its two blade sets
are printed or faced with thin film: the first curtain carries image A, and its travel reveals
image B fixed behind. Blade transit over 24 mm is 3 to 4 ms. The unit is cocked before the show
and held by its own electromagnet, released by a reed switch or radio. The finger snap covers the
shutter's click.

*BOM and cost.* Used SLR shutter module ($10 to $30, unverified), coin cell, reed switch, printed
frame. About $40.

*Difficulty.* Medium; blades are fragile and must stay light, so image A is a 10 to 20 micron
film or a direct print.

*Risks.* One shot per cocking; click volume is unmeasured; rolling-shutter cameras may record a
tear line in one frame.

*Novelty.* Using a camera shutter as a visible-surface changer: I know of no precedent. Unverified.

### 4.4 The quiet pull (level 2)

*Effect.* A coin, ring or folded note resting on the open palm is gone, with the hand still and
open and no sound.

*Method.* The classical sleeve pull, redesigned from the tables. Make the object and the
background (sleeve lining, palm shadow, table mat) match in luminance to within 10%, which drops
the required speed to about 1 to 2 m/s. Size the elastic for 10 g, not more: 0.6 N on a 6 g coin
clears 500 mm in 100 ms, inside pursuit latency. Hold with an over-centre latch on the wrist,
tripped by tendon movement, so there is no twitch. Stop the load in the sleeve with an
eddy-current brake: the coin carries a 6 x 1 mm NdFeB disc and enters a 100 mm copper tube sewn
along the forearm. Detail on worn rigs is agent 21's.

*BOM and cost.* Silicone cord, printed latch, 12 mm copper tube, magnets. Under $20.

*Difficulty.* Low to medium.

*Risks.* Magnet near a phone or pacemaker; copper tube stiffness in the sleeve; the brake's
stopping distance is my estimate and must be tested.

*Novelty.* Incremental; the specific numbers and the silent brake are the contribution.

### 4.5 Knock on wood, then fold it (level 3; uses a compaction capability magic does not use)

*Effect.* The performer raps a walking stick, a tray or a clipboard on the table and lets a
spectator flex it. A moment later it is rolled up, crumpled into the fist or pushed into a small
bag, where it is found to be a handkerchief.

*Method.* Layer jamming with stored vacuum. The "rigid" object is 15 to 30 sheets of paper or
polyester film inside a heat-sealed thin TPU-coated fabric skin printed as wood grain, evacuated
before the show through a valve and capped. Jammed, it bends like a solid laminate. Opening the
valve (a thumbnail on a duckbill) admits air in a fraction of a second and the stack becomes a
loose sheaf of films that rolls or folds. For the cane, the stack is rolled into a tube before
evacuation; after release it flattens and concertinas.

*BOM and cost.* Heat-sealable TPU nylon ($15 per metre), film or paper, a football valve, a hand
vacuum pump. About $30.

*Difficulty.* Medium: seals must hold for hours.

*Risks.* Slow leaks soften the prop before the cue; a jammed laminate is stiff but lighter than
wood and sounds papery when knocked, so add a hard skin patch where it is rapped; rustle on
collapse.

*Novelty.* High, as far as I can tell. The vanishing cane and Zombie gimmick solve one object
each; this is a general "rigid until triggered" material.

### 4.6 The side table that was not there (level 2 to 3; uses a compaction capability magic does not use)

*Effect.* The performer sets a tray or closed hat on the palm, lets go, and it stays at waist
height: a slender column has grown beneath it to the floor. The table is used for the rest of the
act and can be nudged by a spectator.

*Method.* A coilable lattice mast: three 1 mm pultruded rods as longerons, printed triangular
battens every 60 mm, thread diagonals. Twisted, a 0.9 m mast packs into a puck about 70 mm across
and 15 to 25 mm high in the tray base. Stored strain energy erects it; a thread wound on a small
rotary damper meters the rise to about 1 s so it does not snap out. A cloth sock pulled up with
it hides the lattice and makes it read as a turned pedestal.

*BOM and cost.* Carbon or glass rods ($8), printed parts, thread, toy rotary damper ($3), tray.
About $30.

*Difficulty.* High: many joints, and the mast needs tuning to deploy straight.

*Risks.* Low lateral stiffness (do not let anyone lean on it); the mast must be re-coiled by hand.

*Novelty.* Appearing tables exist as folding or telescopic props (unverified); a 40:1 or better
self-erecting leg is new to magic as far as I found.

### 4.7 The pole you can lean on (level 2; uses a compaction capability magic does not use)

*Effect.* From a closed fist or a small purse comes a smooth 2 m staff. The performer vaults on
it, hangs a coat from it, and hands it to a spectator to hold.

*Method.* Two 25 mm steel tape-measure blades face to face in a sewn fabric sleeve form a
lenticular closed-section boom that rolls onto a 60 mm hub. Unrolled, it has roughly the standout
of a tape measure but in both directions and with torsional stiffness. A constant-force spring on
the hub or the blades' own strain energy drives it out; a felt brake sets the speed. A bistable
composite slit tube does the same with one part and re-rolls for the vanish.

*BOM and cost.* Two 5 m tape measures ($20), ripstop sleeve, printed hub. About $30. Composite
version: glass or carbon braid and epoxy, $40, or a purchased bistable tube.

*Difficulty.* Low for the tape version, medium to high for composite.

*Risks.* Blade edges are sharp until sleeved; buckling if side-loaded near mid-span; coil mass
(about 300 g for steel) in the hand before production.

*Novelty.* The appearing cane and appearing pole are the benchmarks; a load-bearing, handable pole
is the improvement. No magic use of reeled booms found. Unverified.

### 4.8 A curved thing from a straight pocket (level 2)

*Effect.* A shepherd's crook, a spiral horn or a full-size umbrella handle with its curve is
produced from a flat envelope or a breast pocket.

*Method.* Yu, Crane and Coros showed that helical curves telescope. Their public tool turns a
drawn curve into nested shells; printed in PETG at 0.5 mm wall, ten shells nest into about one
tenth of the arc length. A pre-stretched silicone cord inside, or a puff of air, extends it; small
printed detents lock each stage.

*BOM and cost.* Filament ($2), silicone cord. Under $10.

*Difficulty.* Medium: print tolerances of 0.15 mm between shells.

*Risks.* Visible steps between shells (wrap in a spiral ribbon pattern that makes steps look
decorative); rattle.

*Novelty.* Curved telescoping is 2017 research and absent from magic catalogues as far as I
found. Unverified.

### 4.9 One clean tear (level 2)

*Effect.* A billiard ball, bottle or boxed deck visibly changes colour or label in the bare
hand, on camera, with no cloth and no shell to ditch. It is handed out.

*Method.* The object wears a printed latex or polyurethane skin, stretched to a moderate,
measured strain and anchored along one hidden line to a thread running into the palm or sleeve.
A pinprick on the far side starts a crack that runs at hundreds of metres per second; because the
stress is kept below the fragmentation threshold found by Moulinet and Adda-Bedia, it runs as one
tear, and the skin retracts in one piece toward its anchor in a few milliseconds, then leaves on a
gentle pull. The object underneath is ordinary.

*BOM and cost.* Printed balloons or dip-moulded latex, thread. Under $10 per dozen skins.

*Difficulty.* Medium: finding the strain that tears cleanly and silently enough.

*Risks.* The pop: lower strain means a quieter tear but slower retraction; latex allergy; a
visible flick of the skin if the anchor is badly placed.

*Novelty.* An engineered version of the colour-changing balloon principle applied to solid
objects; moderate.

### 4.10 Four square metres from a walnut (level 2)

*Effect.* From a borrowed ring box or a cracked walnut the performer draws a sheet of gold larger
than a bedsheet, which hangs in the air and sinks slowly.

*Method.* 1.4 micron aluminised polyester film weighs 1.4 g/m2. A 2 x 2 m sheet is 5.6 g and
about 4 cm3 of solid material; loosely accordion-pleated it fits in about 15 cm3. Its areal
density is so low that it falls at well under 1 m/s (estimate), which reads as floating. The same
film is a production cover for a larger load.

*BOM and cost.* Indoor free-flight film; price not checked, expected $10 to $30 per roll
(unverified).

*Difficulty.* Low to build, medium to handle: static cling and tearing.

*Risks.* One use per sheet; crinkle sound; draughts; near flames the film shrinks and melts.

*Novelty.* Mylar and holographic streamers are common in magic; sub-2-micron film is not, as far
as I found. Unverified.

### 4.11 The pill that was a prediction (level 2)

*Effect.* A white tablet has stood in a sealed bottle of water, or is dropped into the
spectator's own glass. It swells into a cloth printed with the card, word or drawing they have
just freely decided on.

*Method.* Compressed viscose tablets (4 cm tablet to a 28 x 25 cm cloth in 5 to 10 s). The
performer prints a set of cloths with a home dye-sublimation or pigment printer and compresses
them in a printed or turned die under a shop press. Outs are cheap: fifty-two tablets cost a few
dollars and index in a belt. Classical forcing or an index does the choosing; the tablet supplies
the delay, the sealed look and the transformation.

*BOM and cost.* Viscose nonwoven ($10), 6 tonne shop press ($60 to $80, unverified), die.

*Difficulty.* Low to medium; the pressure needed for a tablet that holds together is unknown to
me and needs testing.

*Risks.* A home-pressed tablet may open slowly or unevenly; ink bleed.

*Novelty.* Compressed towels are a known novelty; as a brute-force prediction medium, new as far
as I found. Unverified.

### 4.12 The board from the scarf (level 2)

*Effect.* A scarf is shaken out, held by two corners, and becomes a rigid board on which a glass
of water is placed. Afterwards it is a scarf again.

*Method.* A 40 x 50 cm drop-stitch panel 25 mm thick has a volume of 5 L. A 16 g CO2 bulb gives
about 8.7 L at room pressure, enough for about 0.7 bar gauge, where drop-stitch is board-stiff. A
pierce valve in one hem fires it in well under a second; a dump valve returns it to cloth. The
printed outer fabric and a square "hem" of foam cord disguise the rounded edge.

*BOM and cost.* Drop-stitch fabric offcut ($20 to $40, unverified), 16 g inflator head ($15),
bulbs ($1 each), valves.

*Difficulty.* Medium: seam welding.

*Risks.* Hiss and frost at the valve; 600 g or so of fabric is heavy for a scarf; edges look
inflatable up close. Stage or parlor only.

*Novelty.* Moderate.

Of the twelve, 4.1, 4.2, 4.3, 4.5, 4.6 and 4.7 rest on a speed or compaction capability that I
could not find in use in magic. All twelve are level 2 or 3.

## 5. Dead ends and overhyped items

(pending)

## 6. Open leads

(pending)

## 7. Sources

(pending)
