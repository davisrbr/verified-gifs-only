# 16 - Chance, choice and control

Slice: making an apparently random or free outcome secretly determined, predicted or known,
treated as an engineering problem (mechanics, control, statistics, behavioural data).

Scope note: everything here is for entertainment with the performer's own props and consenting
volunteers. Where a source comes from casino security or advantage play, only the physics or
statistics are extracted. Nothing here is guidance for cheating at real gambling or rigging real
draws.

Method note: about 55 web searches and 35 page fetches were run before the shared search budget
ran out. Several primary PDFs were downloaded and read locally (Olson et al. 2012, Kubovy & Psotka
1976, Lagarias et al. on the Kruskal count, Diaconis-Holmes-Montgomery 2007, Diaconis-Fulman-Holmes
2013, Small & Tse 2012, Wang et al. 2014, Labby 2009), so numbers from those are verbatim. Numbers
marked "my simulation" or "my calculation" were computed for this report and are not from a
source. Anything marked "(unverified)" is recalled and was not confirmed.

## 1. Summary

- **Randomisers are deterministic machines whose trustworthiness comes from sensitivity, not
  from physics.** A spring coin-flipper lands the starting side up 100% of the time (Diaconis,
  Holmes & Montgomery 2007). Human flips are 50.8% same-side over 350,757 flips (Bartoš et al.),
  which is useless on stage, but a penny *spun* on its edge can land tails about 80% of the time
  and a coin with an invisibly shaved edge "always" lands one way. The useful design rule: pick
  the randomiser whose mechanism has the fewest bounces and the lowest energy, because that is
  where small hidden inputs dominate.
- **The size of bias needed is surprisingly small and usually below perception.** A roulette
  wheel tilted 0.2° already creates a large arc of the rim from which the ball never drops (Small
  & Tse 2012, confirming Thorp). 0.2° is 1 mm of rise across a 300 mm table and moves a freely
  rolling ball about 5 cm in 2 s (my calculation). Ordinary dice whose 1-6 axis is 0.1 to 0.2 mm
  short on 16 mm show a statistically certain bias (Labby 2009, 315,672 die-rolls), but that bias
  is under 0.3 percentage points: geometric and mass biases need to be large (centre of mass
  moved about 40% of the half-width) before one face reaches even 40%.
- **So passive bias is a weak tool and closed-loop control is the strong one.** A servo-shifted
  weight in a 3D-printed die reaches only about 40% on the target face (James Stanley, 2021). By
  contrast, hobbyists have closed loops around thrown objects with 200 to 600 ms of flight (Mark
  Rober's dartboard, Shane Wighton's hoop), and the Ishikawa lab's janken robot wins 100% of
  rock-paper-scissors rounds by recognising the hand in 1 ms. Magic has barely used "sense the
  honest randomiser late and nudge once".
- **The cheapest certainty is to replace the randomiser's output, not bias its motion.** A $200
  hobbyist card shuffler with a Pi Zero camera and bins (3DprintedLife) reads every card and can
  deal any planned order while looking like a randomiser; a commercial casino shuffler already
  contains a camera that knows the full deck order (IOActive 2023).
- **Human "free" choices are heavily concentrated and the numbers are published.** "Name a
  card": Ace of Spades 24.6%, Queen of Hearts 13.7% (Olson, Amlani & Rensink 2012, n=423 valid).
  "First digit that comes to mind": 7 at 28.4% (Kubovy & Psotka 1976, pooled n=1,770). Four cards
  in a row: 52 to 60% take the third from the left (Pailhès & Kuhn). Four shelf rows: 71% take
  the middle two (Christenfeld 1995).
- **Outs are an engineering variable.** Using Olson's table, k outs covering the top-k named
  cards give 24.6% (k=1), 38.5% (2), 50.6% (4), 63.9% (8), 72.2% (12), 84.4% (20), 90.2% (26)
  (my calculation). Asking several people multiplies it: the chance that at least one of 10
  people names the Ace of Spades is 94%.
- **People cannot generate random sequences, and a trivial model exploits it.** Aaronson's
  n-gram key-press predictor is right about 70% of the time (70 to 80% in his class); at 70% per
  round a best-of-15 game is won 95% of the time (my calculation). Rock-paper-scissors play shows
  win-stay and lose-shift conditional responses (Wang, Xu & Zhou 2014, 360 players, 300 rounds).
- **Mathematical procedures can be tuned from "likely" to "near certain".** The Kruskal count
  succeeds 85.4% with one deck, face cards = 5, performer starting on card 1 (Lagarias, Rains &
  Vanderbei; reproduced). Counting the letters of each card's name instead gives 95.8%; two decks
  with face = 5 give 97.9%; two decks with letter-counting give 99.8% (my simulation, 100,000 to
  200,000 trials). A computer-searched text or stack can make it exactly 100%.
- **Priming is the weak member of the family.** The best-documented "conversational prime"
  force reaches 17.8% for the exact card (Pailhès & Kuhn 2020, n=90). It is an out-multiplier,
  not a method.
- **Whole-audience statistics plus one-off printing is an under-used architecture.** With 256
  seats each holding a different printed chain of predictions, 8 people are certain to hold a
  perfect record after 5 honest coin flips and 1 after 8 (the tipster scheme as theatre; Derren
  Brown's "The System" used 6^5 = 7,776 people). This must be framed honestly.

## 2. Catalog

### 2.1 Physics of randomisers

**Coin tossing.**
A caught coin toss is rigid-body motion fixed by initial upward speed, spin rate and the angle
between the angular momentum vector and the coin's normal. Diaconis, Holmes & Montgomery built a
spring-and-ratchet tossing machine in which a coin started heads up "always lands heads up - one
hundred percent of the time", and showed that natural flips precess enough to give about .51
same-side probability. They also note that a flip with the angular momentum along the normal
(a "pizza" wobble with no turnover) is a controlled flip that magicians and gamblers already
use. Bartoš et al. confirmed the prediction with 350,757 flips: Pr(same side) = 0.508 (95% CI
0.506 to 0.509), Pr(heads) = 0.500, with the bias varying between people and shrinking with
practice.
- References: Diaconis, Holmes & Montgomery, SIAM Review 49 (2007),
  https://www.stat.berkeley.edu/~aldous/157/Papers/diaconis_coinbias.pdf ; Bartoš et al., JASA
  2025, https://arxiv.org/abs/2310.04153
- Accessibility: a deterministic launcher is a spring, a ratchet and a printed cradle, under $10.
- Magic relevance: the 0.8% human bias is worthless live (it needs about 10,000 flips to show).
  The valuable facts are (a) a mechanical launcher is 100% deterministic, and changing flight
  time by half a revolution flips the result, and (b) the audience believes a tossed coin is the
  fairest object in the room. A "fair launcher" with two detents that differ by half a turn of
  flight is a control-of-chance device that looks like a fairness device.
- Prior use: controlled tosses and double-sided coins are classical; a launcher as a hidden
  selector appears not to be marketed (unverified).

**Spun coins and edge geometry.**
Spinning a coin on its edge is far more biased than tossing. Diaconis is quoted that a spun
penny lands tails about 80% of the time; DHM report data from 103 Berkeley students who each
tossed and spun a penny 100 times: tosses clustered at 50 heads, spins showed "a pronounced
proportion of tails", several coins under 10% heads. DHM state that the result "depends in a
delicate way on the shape of the coin's edge and the exact center of gravity" and that magicians
use coins with slightly shaved edges, invisible to the eye, that always come up heads.
- References: DHM 2007 (above); Science News item, https://sciencenews.org/?p=36382
- Accessibility: a bevelled edge of a few tenths of a millimetre can be turned on a hobby lathe
  or printed into a token/poker chip; cost near zero.
- Magic relevance: outcome of a spun token can be made close to certain with an edge bevel that
  cannot be seen. Works on any disc the performer supplies (casino chip, bottle cap, custom
  token). Fully examinable in the casual sense. The spectator does the spinning. Level 2.

**Dice: how initial conditions map to outcomes.**
Kapitaniak et al. (Chaos, 2012) modelled the die throw in 3D with high-speed video. The die is
more likely to land on the face that started lowest; the face probabilities approach equality
only with high initial rotational energy and many bounces. A high-friction table produces more
bounces and less predictability; a soft or sticky surface produces fewer. Prediction is possible
in principle but needs initial-condition accuracy no hand can supply.
- References: phys.org summary, https://phys.org/news/2012-09-die.pdf ; AIP Inside Science,
  https://www.aip.org/inside-science/dice-rolls-are-not-completely-random
- Magic relevance: the *surface* is a control parameter the performer owns. A soft, grippy
  close-up pad and a short drop turn a die into a nearly predictable object; a hard bouncy
  surface is the honest condition. A pad whose stiffness or friction differs by region (or is
  switchable) changes how random the same die is, with nothing in the die.

**Dice: ordinary versus precision, and how big a bias must be.**
Labby (2009) built a machine that rolled 12 ordinary drilled-pip dice 26,306 times. Face
probabilities were 0.1686, 0.1651, 0.1662, 0.1658, 0.1655, 0.1688 for faces 1 to 6 (chi-square
25.0, p = 0.00014). The cause was not pip weight but geometry: the 1-6 axis was consistently
shorter than the other two (differences of the order of 0.1 to 0.2 mm on 16 mm dice). So
manufacturing error that is easily measurable with calipers shifts a face by under 0.3
percentage points. Pender & Uhrin (2014) logged 16,300 throws of deliberately non-square "2D
dice", matched a Markov-chain formula and a million simulated throws, and found the main
discrepancy came from the landing surface. A quasi-static solid-angle model gives the scale for
mass loading (my calculation): moving the centre of mass toward one face by 10% of the edge
length gives 20.9% for that face down; 20% gives 26.3%; 30% gives 33.1%; 40% gives 41.1%.
- References: Labby, CHANCE 22(4), https://www.Gwern.net/doc/statistics/probability/2009-labby.pdf ;
  UCL release, https://www.ucl.ac.uk/mathematical-physical-sciences/news/2014/jun/formula-cheating-dice ;
  arXiv 1407.6307, https://ar5iv.labs.arxiv.org/html/1407.6307 ; cuboid tossing data,
  https://web3.arxiv.org/pdf/1302.3925
- Magic relevance: passive loading cannot reach 90% without becoming obvious (a die that is
  40% offset will not roll naturally and fails the water or spin test). Passive loads are an
  "edge", not a force. This is the main negative result of the slice.

**Dice with moving mass inside.**
James Stanley (2021) 3D-printed a hollow d6 in two halves with a tiny linear servo that moves a
steel weight toward a chosen face, with brass pips doubling as charging/control contacts via
pogo pins in a cradle. With the weight at one extreme the die rolled the target about 40% of the
time over 200 rolls, "more than twice as often as any other number", matching the solid-angle
estimate above. He notes a slight rattle and that it has to sit in the cradle to change state.
- Reference: https://incoherency.co.uk/blog/stories/loaded-dice.html
- Accessibility: hobbyist, roughly $20 to $40.
- Magic relevance: historical "tappers" (variable-load dice with a shifting slug) did the same
  thing mechanically. The modern gain is remote selection of *which* face, not a higher hit
  rate. 40% is not a force; it is a 2.4x multiplier to combine with outs.

**Dice that sense (and could act).**
Commercial connected dice already contain motion sensing and radio in a standard-size die:
GoDice use a Nordic nRF52805 SoC, supercapacitors charged in about 10 s through contacts on the
5 face, about 2 hours of play, and classify moved / rolled / tilted / free fall / tapped. Pixels
dice use an accelerometer and Bluetooth with LEDs. Reaction-wheel cubes that jump up and balance
exist at hobby scale (Cubli at 15 cm; ESP32 + SimpleFOC + small brushless motor builds; a 2026
ESP32 build that springs into the air, reorients in flight with a reaction wheel and lands on a
chosen edge).
- References: https://www.nordicsemi.com/News/2022/08/Particulas-GoDice-employs-Nordics-nRF52805-SoC ;
  https://hackaday.com/2019/10/09/these-dice-know-if-youre-cheating ;
  https://robohub.org/swiss-robots-cubli-a-cube-that-can-jump-up-balance-and-walk-across-your-desk ;
  https://github.com/willem-pennings/balancing-cube ;
  https://hackaday.com/2024/10/13/diy-3d-printed-arduino-self-balancing-cube ;
  https://circuitdigest.com/news/this-esp32-powered-self-balancing-cube-jumps-with-a-spring-and-uses-a-reaction-wheel-to-land-on-its-edge
- Magic relevance: "know the roll" is solved and sold to magicians (electronic dice sets that
  transmit the up face exist; product names not verified here). "Choose the face after the
  throw" is not solved at 16 mm. It is plausible at 40 to 60 mm (a novelty "giant die"), where a
  single-axis reaction wheel or a solenoid-thrown slug could add one extra quarter-turn during
  the final rock. See concept 3.1.

**Roulette-style wheels and spinners.**
Small & Tse (Chaos 2012) predicted the half of the wheel where the ball lands from timings of
ball and rotor, for an expected return of at least 18% against -2.7%. The physics that matters
here: prediction needs only position, velocity and deceleration at one moment, and "a tilt of
0.2° was apparently sufficient - we verified that this is indeed more than sufficient" to create
a large region of the rim from which the ball will not fall.
- Reference: https://arxiv.org/abs/1204.6412
- Magic relevance: for a performer-owned wheel, spinner, or ball-in-bowl prop, a levelling error
  of 0.2° (three sheets of paper under one foot of a 300 mm base) produces a strongly preferred
  arc. Combined with releasing at a chosen phase, this gives sector-level control with no
  mechanism in the prop. Hidden eddy-current brakes and magnets belong to agents 7 and 14.

**Cards: how random real shuffles are.**
Bayer & Diaconis: in the Gilbert-Shannon-Reeds model, after 7 riffles of 52 cards the total
variation distance from uniform is still 0.334, and 5 riffles are far from uniform. The overhand
shuffle mixes in order n² log n steps (Pemantle; Jonasson), which is thousands of shuffles for
52 cards. So a spectator's "thorough" shuffle of two or three riffles plus some overhand
shuffling leaves most of the original order's structure (rising sequences, clumps) intact.
- References: https://www.stat.berkeley.edu/~aldous/157/Papers/bayer_diaconis.pdf ;
  https://math.hmc.edu/funfacts/seven-shuffles/ ; https://arxiv.org/abs/math/0501401
- Magic relevance: after one honest riffle a known stack is two interleaved known sequences;
  identifying a removed or moved card is a decoding problem (classical magic uses this). With a
  camera or marked deck (agents 10, 12) the full order after real shuffles is recoverable.
  Measured data on how real human riffles deviate from GSR was not retrieved (open lead).

**Cards: machines.**
(a) Diaconis, Fulman & Holmes (2013) analysed a 10-shelf casino shuffler: after one pass the
total variation distance to uniform is 1.000 to three decimals, and a knowledgeable guesser gets
about 9.5 cards right through the deck against 4.5 for a well-shuffled deck. (b) IOActive (2023)
showed that the Deckmate 2 casino shuffler has an internal camera (there to verify the deck is
complete) and that the machine can therefore know the full order. (c) Hobbyists have built
shufflers that are openly sorters: 3DprintedLife's machine (Pi Zero, OpenCV, three steppers, an
eight-bin organiser, about $200) has a "planned shuffle" mode where each card is read and placed
deliberately; a Purdue student shuffler can bring chosen cards to the top; a UIUC student sorter
handles one card in 4 s (about 3 minutes per deck).
- References: https://arxiv.org/pdf/1107.2961 ;
  https://ioactive.com/article/internal-camera-hacked-casino-card-shuffler-lets-you-look-at-the-cards/ ;
  https://www.hackster.io/news/rig-the-deck-so-you-always-win-with-this-card-shuffler-5db782b1b15f ;
  https://engineering.purdue.edu/477grp10 ;
  https://courses.physics.illinois.edu/ece445/project.asp?id=12014
- Accessibility: hobbyist, $100 to $300, medium-hard mechanically (card feeding is the hard part).
- Magic relevance: "know the full order of a shuffled deck" and "produce any order while
  appearing to randomise" for about $200. Too-perfect risk is high (a machine is the obvious
  suspect); it must be cancelled by a real spectator shuffle afterwards whose effect on the
  structure is controlled mathematically (Gilbreath: one honest riffle preserves the invariant).
  Faro-shuffling machines as such were not found (open lead).

**Balls, blowers, cages.**
Lottery machine makers state that "the key to randomness is having ball sets with very tight
weight tolerance" and test every ball set and run 100 simulated draws. Gravity-pick machines
with visible paddles are used because visibility builds trust. The best-known historical fix
(Pennsylvania 1980) used added paint weight on all balls except two digits; this is cited only
to show that a few percent of mass decides an air-mix draw.
- Reference: https://www.lotteryusa.com/news/science-lottery-machines-how-random-is-random
- Magic relevance: an air-mix blower is a mass sorter. A performer-owned blower or bingo cage
  with one ball a few percent lighter (or with a different surface drag) favours that ball
  strongly. No quantified study was found (open lead); treat reliability as unknown.

**Chaotic toys: magnetic pendulum, Galton board, Plinko.**
A pendulum over three magnets has fractal basin boundaries; outside a few large basins the
release position cannot be measured accurately enough to predict the result (HMC and Yale lab
notes). A Galton board is a sum of near-independent left/right bounces, so the outcome variance
shrinks only as the square root of the number of rows. To put a single ball in the chosen half
with 90% reliability the per-peg probability must be about 0.76 (8 rows), 0.71 (12 rows), 0.68
(16 rows), 0.63 (30 rows) (my calculation, binomial). Per-peg bias from tilt was not found
quantified (a simulation write-up reports that tilted pegs shift the distribution significantly;
an NJIT thesis varies board tilt).
- References: https://gauss.math.yale.edu/fractals/Labs/MagPendulumLab/MagPendulumLab.html ;
  https://math.hmc.edu/~dyong/math164/2006/win/finalreport.pdf ; https://en.wikipedia.org/wiki/Galton_board ;
  https://core.ac.uk/download/232275551.pdf (not read)
- Magic relevance: chaotic toys are trusted because they visibly amplify. That same property
  means tiny late inputs decide the outcome, so they are good hosts for closed-loop control
  (one electromagnet pulsed at the right phase captures the pendulum) and poor hosts for
  open-loop bias (a Galton board needs each peg biased to 70%).

**Drawing lots.**
Bags, straws and tickets are controlled through touch and temperature, not physics. Thermal and
tactile marking are covered by sensing/materials agents; the statistics point is that a draw of
one from N with a mark the drawer cannot perceive is a 100% force with zero apparatus.

**Electronic randomisers in the performer's props.**
A rigged app or LED die is trivial and nearly worthless: the audience's first theory is correct.
Convincing uses are narrow: the randomiser is the spectator's own device, or the electronic
output only *triggers* an honest-looking physical process. No peer-reviewed HCI study comparing
trust in physical and digital dice was found (open lead). The working design rule, from lottery
practice and from the DHM/Kapitaniak results: audiences trust randomisers that are
spectator-operated, transparent, mechanically simple and visibly chaotic (tossed coin, thrown
dice, tumbling balls). Those are exactly the ones whose final state is decided by millijoules.

### 2.2 Small hidden influences with large determinate effects

**Micro-tilt.**
A solid ball rolling without slipping accelerates at (5/7)·g·sin(θ). At 0.2° that is 0.024 m/s²:
5 cm of drift in 2 s. At 0.5°, 12 cm in 2 s. Rolling resistance for a steel ball on glass or
hard metal is 10^-5 to 10^-3, so a ball starts to move at tilts of 0.001° to 0.06°. The rise
needed across a 300 mm surface is 1.0 mm for 0.2° and 2.6 mm for 0.5° (my calculations; rolling
coefficients from the precision-engineering literature).
- Reference: https://www.jstage.jst.go.jp/article/jjspe1933/45/533/45_533_573/_article/-char/en ;
  https://arxiv.org/pdf/2111.06258
- Accessibility: three small linear actuators or cams in table feet; an IMU with 0.01° noise
  closes the loop. $30 to $80.
- Deception: a 1 mm change in a table's stance is not visible and cannot be felt through the
  props. Human slope-detection thresholds were not retrieved; liquid in a glass on the table is
  the tell to avoid.
- Magic relevance: ball-and-cups-as-roulette, marble "choosing" a cup, a spun top or coin
  drifting toward a chosen person, a rolled pencil stopping pointing at a word. Level 2.

**Vibration that walks objects.**
Reznik & Canny's Universal Planar Manipulator moves several parts independently along chosen
paths on one rigid plate that only vibrates horizontally, using an asymmetric ("pump-like")
vibration so that sliding friction has a non-zero average. Northwestern's surface-haptics
patents describe switching ultrasonic friction reduction in sync with lateral motion to give a
net time-averaged force on "a part".
- References: https://people.eecs.berkeley.edu/~jfc/dreznik/UPM2000/ ;
  https://people.eecs.berkeley.edu/~jfc/dreznik/Pubs/wafr98.pdf ;
  https://patents.google.com/patent/US8791902
- Accessibility: voice-coil or eccentric actuators under a thin rigid tabletop; hobbyist but
  needs tuning. No numbers for speed or audibility were retrieved; assume millimetres per second
  and an audible hum unless the frequency is kept low or masked.
- Magic relevance: a die that has landed can be "walked" off an edge it is rocking on; a coin
  on its edge can be biased as it settles; objects on a tray can migrate. Speculative for
  outcome control, since it acts after the visible motion has ended.

**Timing-based control.**
Because the outcome of a spinner, wheel or launcher is a deterministic function of release
phase and energy, a mechanism that only controls *when* an honest release happens (a detent, a
latch, a hidden "go" cue to the performer) controls the result without changing the motion.
This is the DHM machine generalised. The audience checks the object, not the timing.

**Surface engineering.**
CNC or printed surfaces can carry slopes of 0.1 to 0.5° and textures that are invisible under a
close-up mat or felt. Kapitaniak's result says a softer, higher-damping landing zone makes dice
outcomes follow the initial orientation; a harder zone randomises. A mat with two zones lets the
performer choose between "fair" and "what I dropped is what you get" by where the roll happens.

### 2.3 Closed-loop control hidden in an object

**Existence proofs.**
- Mark Rober's dartboard: six Vicon infrared cameras track a retroreflective dart, MATLAB fits
  the parabola, six steppers move the board on an XY gantry within about 200 ms. It took three
  years. https://hackaday.com/2017/03/22/dartboard-watches-your-throw-catches-perfect-bullseyes
- Shane Wighton's hoop: a ceiling Kinect tracks the ball, three steppers tilt the backboard,
  with about 600 ms of flight to work in; lag causes misses.
  https://www.hackster.io/news/a-basketball-hoop-that-won-t-let-you-miss-998c5721485e
- Ishikawa lab janken robot: recognises the human hand shape in about 1 ms with high-speed
  vision and completes the winning shape before the human finishes; 100% win rate.
  https://www.therobotreport.com/this-rock-paper-scissors-robot-has-never-lost-to-a-human/
- Ball-on-plate tables: an Arduino Due with a resistive touchscreen as the plate and three hobby
  servos; typical loop rates 50 to 100 Hz.
  https://blog.arduino.cc/2017/07/14/ball-on-plate-machine-uses-touchscreen-position-sensing
- What an ESP32-class controller can close a loop around (typical figures, unverified here): IMU
  data at 1 kHz or more, brushless motor field-oriented control at several kHz, Bluetooth LE
  round trips of 10 to 30 ms, camera pipelines at 60 to 120 frames per second.

**Magic relevance.**
The receiver moving to meet the projectile is the general pattern: the cup, slot, or target is
the actuated part, and it moves a few millimetres under cover of being "just a cup". A ball
tossed into one of three cups has 300 to 500 ms of flight; a cup rim that shifts 15 mm, or a
funnel under the table surface, makes the chosen cup certain while the throw is honest. A top
that "falls toward" a person is the micro-tilt table with an IMU. A balance that tips the wrong
way is a reaction mass in the beam. None of these need the lab hardware above, because the
performer controls the geometry and can sense with one photogate or a short-range time-of-flight
sensor instead of motion capture.
Deception properties: the sensing is the tell (cameras, emitters), so prefer sensors inside the
prop. Lag shows as a visible late correction; design so that the correction happens out of
sight (below the rim, under the cloth).

### 2.4 Human choice is not random: the numbers

| Prompt | Top responses and rates | Sample and caveats |
|---|---|---|
| "Name a playing card" | AS 24.6%, QH 13.7%, AH 6.1%, KH 5.9%, JS 4.3%, AD 3.8% | Olson, Amlani & Rensink 2012; 667 asked, 423 valid; Canadian students and science-centre visitors; first-card-to-mind only |
| "Visualise a card" | AS 17.3%, AH 11.1%, QH 10.0%, KH 5.1%, 3D 2.9% | same paper; 700 asked, 450 valid |
| Card values, suits | Threes and sevens most named among number cards, sixes least; spades and hearts over clubs and diamonds; men named QH more than women did | same paper |
| "First digit that comes to mind" | 7 at 28.4% (SE 1.9%) | Kubovy & Psotka 1976, 13 pooled clusters, n=1,770, US students. Drops to about 17% when the range is 6 to 15 or when 7 is mentioned first |
| "A number in the 20s / 70s" | 27 at 27.7%; 77 only 15.5% | same paper, small groups |
| Number 1 to 100 | 37 and 73 lead once 1, 100, 42, 69 are set aside; 7 and 77 next | Veritasium survey, about 200,000 online respondents; Reddit polls of 1,380 and 6,750 put 69 first. No per-number percentages retrieved |
| Colour and number together | "close to one in three" 7, "more than two in five" blue | Simon 1971, via secondary source |
| Four cards in a row | 52% (two experiments) to 60% take the third from the left | Pailhès & Kuhn 2021; Kuhn, Pailhès & Lan 2020. Telling people it is a decision reduces it |
| Four identical rows or stalls | 71% choose the middle two | Christenfeld 1995 |
| Card after gesture and word primes for 3 of diamonds | 17.8% name 3D; 38.9% any three; diamonds not above control | Pailhès & Kuhn, PNAS 2020, n=90; 0 of 23 controls named it |
| Rock-paper-scissors | Marginals 0.36 / 0.33 / 0.32 (R/P/S); repeat after a win, shift after a loss | Wang, Xu & Zhou 2014; 360 students, 60 groups, 300 rounds. Tournament first-throw data: rock 35.4%, paper 35.0%, scissors 29.6% (World RPS Society via press) |
| "Random" binary key presses | next press predicted about 70%; 70 to 80% in class | Aaronson's lecture demo; Shannon's 1953 relay machine reportedly won 59% of 8,517 games (secondary source) |
| 4-digit codes (aggregate, breached data) | 1234 is 10.7%; top 20 are 26.8%; every 19xx value is in the top fifth | DataGenetics 2012, 3.4 million PINs. Aggregate statistics only |
| First word that comes to mind | per-cue response distributions | Small World of Words: 12,000+ cues, 90,000+ participants, three responses each; downloadable |
| Category exemplars (a tool, a vegetable, a flower) | hammer, carrot, rose are the folklore answers | Van Overschelde, Rawson & Dunlosky 2004 give first-response proportions for 70 categories, 700+ US participants; values not retrieved (open lead) |

References: https://www.cs.ubc.ca/~rensink/publications/download/Cards-OAR.pdf ;
https://gwern.net/doc/psychology/cognitive-bias/1976-kubovy.pdf ;
https://www.veritasium.com/videos/2024/6/19/why-is-this-number-everywhere ;
https://telescoper.blog/2018/04/11/what-happens-if-you-ask-people-to-pick-a-number-at-random-between-1-and-100/ ;
https://link.springer.com/article/10.1007/s00426-020-01350-z ;
https://www.psychologicalscience.org/journals/psychological-science/j.1467-9280.1995.tb00304.x/ ;
https://pmc.ncbi.nlm.nih.gov/articles/PMC7395500 ; https://arxiv.org/pdf/1404.5199 ;
https://www.scottaaronson.com/democritus/lec18.html ;
https://www.slate.com/blogs/future_tense/2012/09/19/how_to_choose_a_pin_code_avoid_birth_date_1234_or_8068.html ;
https://www.doi.org/10.3758/s13428-018-1115-7 ; https://smallworldofwords.org

Items commonly stated in the magic literature for which no dataset was retrieved (all
unverified): the "odd two-digit number under 50 with different digits" force on 37 at roughly a
third; 3 for "1 to 4"; 17 for "1 to 20"; triangle-in-circle for "two simple shapes"; house, tree,
sun, cat, flower, stick figure for "a simple drawing". The Kubovy result is a warning for all of
these: the modal answer is context-sensitive, and merely mentioning it as an example halves it.

**Population caveats.** Nearly all samples are WEIRD students or self-selected internet users.
Olson's rates hold for "first card that comes to mind" asked quickly; 87 of 667 people said
their answer was not their first thought and were excluded, so live rates where people
deliberately avoid the obvious will be lower. Card and number preferences vary with local card
games and lucky-number cultures. Magicians and people who have seen these forces answer
differently.

**The engineering of outs.** Treat a psychological force as a probability distribution and
choose k outs to cover the head of it (my calculations from Olson's Table B1):

| Outs k (top-k named cards) | 1 | 2 | 4 | 6 | 8 | 12 | 20 | 26 |
|---|---|---|---|---|---|---|---|---|
| Coverage, "name a card" | 24.6% | 38.5% | 50.6% | 58.7% | 63.9% | 72.2% | 84.4% | 90.2% |
| Coverage, "visualise a card" | 17.3% | 28.4% | 43.5% | 48.8% | 53.7% | 61.9% | 75.5% | 83.9% |

The tail is long: half the mass sits in 4 cards and the last 10% needs 26 more. So the
efficient design is tiered: one spectacular out for the top answer (hit 1 time in 4), a small
set of strong outs for the next 10 or so (another 45 to 50%), and a different *method* (not
more outs) for the remaining quarter. Asking more than one person multiplies the head: the
chance that at least one of n people names a top-2 card is 62% (n=2), 77% (3), 91% (5); a top-4
card, 76%, 88%, 97%. Priming multiplies it again by a modest factor.

### 2.5 Real-time prediction and adaptation

**Sequence predictors.** Aaronson's program builds a table of what followed each recent
pattern of presses and predicts the more frequent continuation; "even a very crude" model is
right about 70% of the time. Shannon's 1953 "mind-reading machine" did the same with an 8-state
memory in relays. People over-alternate (alternation rates near 0.6 rather than 0.5 in
generation and perception studies: Wagenaar; Falk & Konold). At a per-round hit rate p, the
chance of winning the majority of n rounds is (my calculation): p=0.6: 73% (n=9), 83% (21);
p=0.7: 90% (9), 95% (15), 97% (21); p=0.75: 95% (9), 98% (15).
- References: lecture above; https://literateprograms.org/mind_reading_machine__awk_.html ;
  https://srri.umass.edu/sites/srri/files/FalkKonold1997/index.pdf
- Magic relevance: any repeated binary or ternary game with one spectator (which hand, odd or
  even, rock-paper-scissors) can be won reliably over 15 rounds by a phone-in-pocket model fed
  by the performer's own record of results, with no sensing of the spectator at all. A few
  "practice rounds" are the training data. Level 3: the method is statistics only, and each
  individual round looks, and is, fair.

**Behavioural leakage measurable by the performer's props.**
- Response time carries preference strength: Konovalov & Krajbich (2019) rank people's
  preferences and predict later choices from response times alone.
  https://dlab.sauder.ubc.ca/sjdm/journal/18/181101/jdm181101.html
- Gaze shifts toward the item about to be chosen before the response (Shimojo et al. 2003,
  https://www.nature.com/articles/nn1150); the effect is weaker or absent for some stimulus
  types, and one small system reported 81% choice classification on seven subjects.
- Arm movements leak confidence: observers judged poker hand quality from arm motion better
  than from faces (Slepian et al. 2013,
  https://www.psychologicalscience.org/journals/psychological-science/0956797613487384/).
- No study was retrieved giving accuracy for hand-hover dwell time, first-touched item, grip
  force or weight shift as predictors of a *secretly thought-of* item. These are plausible and
  cheap to instrument (agent 10 covers the sensors), but the hit rates are unknown: an open lead
  that the commissioning hobbyist could measure directly with 30 volunteers.

**Question design as information theory.**
A progressive anagram is a decision tree over letters in which the performer states letters and
continues only while hearing "yes". If the tree may contain at most m "no" answers and at most
L questions, it can separate at most the sum of C(L, i) for i = 0..m items (my derivation): for
one allowed miss, L+1 items (7 items with 6 letters); for two misses, 22 items with 6 letters,
37 with 8; for three misses, 42 with 6. An unconstrained yes/no tree separates 2^L (64 for 6).
So each permitted "no" is worth far more than an extra question, and the design problem is to
spend misses where they sound like hits ("there's no E... that's what threw me"). Weighting the
tree by the response frequencies in section 2.4 (Huffman-style) puts the popular answers at
zero or one question. Tools: Glen S.'s progressive anagram tool (https://snelg.github.io/jta/),
which can cap guesses and misses, and the generator at https://www.cavemanchemistry.com/anagram ;
the Jerx write-up is at https://thejerx.squarespace.com/blog/2025/6/1/progressive-anagram-tool .
The technique dates to Stanley Collins, 1920. Williams & McOwan (2014) used simulated annealing
to order a 52-card de Bruijn-style stack so that fewer fishing questions identify a card (mean
4.04 down to 3.85), using card-likeability data to order guesses; details belong to agent 12.
https://pmc.ncbi.nlm.nih.gov/articles/PMC4233310

### 2.6 Procedures that feel free but are constrained

**Equivoque as a decision tree.** Magician's choice is a tree in which every spectator action
maps to the same leaf because the meaning of each action ("take", "eliminate", "hand me") is
assigned after it is made. Pailhès, Kumari & Kuhn (2021) report across three experiments that
it gave participants an illusory sense of agency over the outcome, that this survived two
repetitions, that it worked with items people have preferences about, and that participants did
not notice the inconsistencies. Exact rates were not retrieved (repository host unreachable).
https://research.gold.ac.uk/29234 . Related: in the criss-cross cut force only 4 to 6% of
participants realised their cut had no effect (Pailhès & Kuhn 2020, n=60 and n=90),
https://pmc.ncbi.nlm.nih.gov/articles/PMC7583451 ; in the position force, choosers of the forced
card reported high freedom and underestimated how many others would choose the same.
Engineering reading: a formally enumerated tree can be checked for the two failure modes
(a branch that needs a contradictory instruction on repetition; a branch longer than the
others) before it is ever performed.

**Kruskal count.** Two walkers on the same sequence of step sizes merge with high probability.
Lagarias, Rains & Vanderbei (10^6 Monte Carlo trials per point): failure 14.6% with face cards
= 5 and the performer starting at card 1 (success 85.4%); failure 27.8% with faces = 10. The
performer should always start on the first card. Smaller mean step size and longer sequences
are the levers. My simulation (spectator start uniform on 1 to 10, performer on card 1):
faces = 5: 85.4%; faces = 1: 94.3%; step = number of letters in the card's name (3 to 5):
95.8%; two decks, faces = 5: 97.9%; two decks, letters: 99.8%. Dynkin's version on 100 digits
has error about 2.6%. The clock version used by David Copperfield is deterministic after three
moves.
- References: https://arxiv.org/abs/math/0110143 ; https://en.wikipedia.org/wiki/Kruskal_count ;
  https://faculty.uml.edu/rmontenegro/research/kruskal_count/index.html ;
  https://rss.org.uk/RSS/media/Membership/Volunteering/Education/Sociable_cards_vP1.pdf
- New lever: because a custom deck or a printed text costs a few dollars, the sequence need not
  be random. A computer can search for an ordering (or write a paragraph) in which *every*
  permitted starting point converges, giving 100% with a procedure that is known in the
  literature as merely probable. The spectator can still cut (a cyclic search handles cuts).

**Invariants under cut and shuffle.** Cyclic stacks survive any number of cuts. The Gilbreath
principle: after one riffle of a deck prepared by reversing part of a repeating pattern, every
consecutive block of m cards contains one of each of m labels (Gilbreath 1958; Diaconis &
Graham's "ultimate" version). Hummer/CATO operations preserve face-up/face-down parity; down-
under (Australian) deals are fixed Josephus permutations; the 9-principle and clock forces are
arithmetic invariants. De Bruijn sequences let k consecutive binary observations locate a
position among 2^k (five red/black cards locate one of 32).
- References: https://mathworld.wolfram.com/GilbreathPrinciple.html ;
  https://en.wikipedia.com/wiki/Gilbreath_shuffle ; https://www.ams.org/featurecolumn/archive/mulcahy6.html
- Level-3 opportunity: these were found by people, one at a time. Exhaustive or SAT-style search
  over small procedure grammars (deal, cut, spell, reverse, riffle-once) for sequences whose
  output distribution is a single point or is extremely non-uniform is tractable on a laptop.
  Agent 12 owns the software; the probability target to give it is "find procedures with at
  least three spectator decisions and outcome entropy under 0.1 bit".

**Audience-wide procedures.** Kruskal-type coupling and parity walks on a grid let every
audience member follow their own path and end on the same item (RSS "Sociable Cards": "most,
usually all" participants land on the same card). With a searched layout it is all, always.

### 2.7 Whole-audience statistics

- Birthday coincidences (my calculation): some pair shares a birthday with probability 50.7%
  (23 people), 89% (40), 97% (50), 99.4% (60). Someone has one *specific* birthday: 24% (100
  people), 42% (200), 75% (500); within one day either side: 56%, 81%, 98%.
- "At least one of you is thinking of X": if X has per-person probability 3.5%, a room of 100
  contains it with probability 97%; at 2%, 87%.
- Predicting a show of hands is predicting a mean; with 200 people the standard error of a
  proportion near 30% is about 3 points, so "between a quarter and a third of you" is safe.
- Mass personalisation: give each of N people a different printed prediction. With r binary
  events, N/2^r people hold a perfect record: 256 seats give 8 perfect after 5 events and 1 after
  8. Derren Brown's "The System" (2008) ran this on horse races with six runners over five races,
  hence 6^5 = 7,776 starting participants. Variable-data digital printing makes every piece
  different at no extra set-up cost; per-piece prices were not retrieved (open lead), but the
  marginal cost is that of an ordinary printed card.
  https://derrenbrown.co.uk/shows/the-system/ ; https://botherer.org/?p=851
- Ethics: these are honest statistics that feel like destiny to the one person who experiences
  the hit. Presenting them as psychic ability, or letting the "survivor" believe they were
  singled out, is the mechanism of real investment fraud. The defensible framings are an
  explicit demonstration ("here is how tipsters fool you"), or a reveal at the end as Brown did.

## 3. Capability primitives

1. *Now possible:* A tossed coin's result can be made 100% certain with a spring launcher
   whose flight time differs by half a revolution between two detents. *Because:* DHM 2007
   machine; printed parts. *Before:* controlled tosses needing skill. *Primitives:* control chance.
2. *Now possible:* A spun disc can be made to fall one way about 80% (plain penny) to nearly
   100% (edge bevel of tenths of a millimetre), with the spectator spinning. *Because:* edge
   geometry dominates spun coins; lathe or resin print. *Before:* shaved coins, known to few.
   *Primitives:* control chance, prove ordinariness.
3. *Now possible:* A ball's resting place on a table can be made over 90% certain with a hidden
   tilt of 0.2 to 0.5° (1 to 2.6 mm over 300 mm). *Because:* rolling resistance under 0.001;
   cheap linear actuators and IMUs. *Before:* fixed crooked tables. *Primitives:* move, control chance.
4. *Now possible:* A wheel or bowl can be given a strongly preferred arc with 0.2° of tilt and
   no internal mechanism. *Because:* Small & Tse / Thorp. *Before:* brakes and magnets.
   *Primitives:* control chance, prove ordinariness.
5. *Now possible:* A die face can be favoured to about 40% (2.4 times chance) by remote choice
   of which face, in a sealed printed die. *Because:* micro servo and printed shell (Stanley).
   *Before:* fixed loads, tappers. *Primitives:* control chance. Not a force on its own.
6. *Now possible:* The up face of a thrown die can be known within about 1 s at 100% by the die
   itself. *Because:* nRF52-class SoC, MEMS accelerometer, supercapacitor in a 16 mm die.
   *Before:* peeks, marked dice. *Primitives:* know, tell.
7. *Now possible:* The full order of a spectator-shuffled deck can be known, or replaced by any
   chosen order, in 1 to 3 minutes by a $200 machine that looks like a shuffler. *Because:* Pi
   Zero, OpenCV, steppers, printed bins. *Before:* deck switches, memorised stacks, false
   shuffles. *Primitives:* know, swap, control chance.
8. *Now possible:* A thrown object can be made to land in the chosen receptacle near 100% with
   200 to 600 ms of flight and a receiver that moves 10 to 30 mm. *Because:* cheap fast sensing
   and steppers (Rober, Wighton at larger scale). *Before:* impossible. *Primitives:* move, know.
9. *Now possible:* A hand gesture can be recognised and answered within tens of milliseconds, so
   a "simultaneous" reveal always wins. *Because:* high-speed vision (1 ms at lab grade).
   *Before:* impossible. *Primitives:* know, control choice. Lab-grade for 1 ms; 8 to 16 ms on
   hobby cameras is still below what people perceive as late (unverified).
10. *Now possible:* A dice outcome can be shifted from random toward "lands as dropped" by
    changing only the landing surface's damping and friction. *Because:* Kapitaniak 2012.
    *Before:* dice cups and switches. *Primitives:* control chance.
11. *Now possible:* A named playing card can be covered at 25% with 1 out, 51% with 4, 72% with
    12, 90% with 26. *Because:* Olson et al. frequency table. *Before:* folklore lists.
    *Primitives:* control choice.
12. *Now possible:* Among any 5 people asked to name a card, at least one names a top-2 card
    91% of the time and a top-4 card 97%. *Because:* same data. *Before:* not quantified.
    *Primitives:* control choice.
13. *Now possible:* A free choice among 4 objects in a row can be predicted at 52 to 60% with
    no outs and at about 71%+ with 2 outs (the middle pair). *Because:* position-force and
    Christenfeld data. *Before:* intuition. *Primitives:* control choice.
14. *Now possible:* A first-digit choice can be predicted at 28% with 1 out; saying the number
    aloud beforehand cuts that to 17%. *Because:* Kubovy & Psotka. *Before:* folklore.
    *Primitives:* control choice.
15. *Now possible:* A spectator's next left/right or rock/paper/scissors choice can be predicted
    at about 70% after a short warm-up, and a best-of-15 won 95%. *Because:* n-gram predictor in
    a pocket microcontroller. *Before:* cold reading. *Primitives:* know, control choice.
16. *Now possible:* One item of 22 can be identified with at most 6 stated letters and at most 2
    apparent misses; one of 7 with at most 1 miss. *Because:* tree-generating software and the
    counting bound. *Before:* hand-built anagrams. *Primitives:* know.
17. *Now possible:* A counting procedure with a free secret starting point can end on a
    predicted card 85% (standard), 96% (letter-count), 99.8% (two decks, letter-count), or 100%
    (computer-searched order). *Because:* simulation and search; custom printing. *Before:* 85%
    and a prayer. *Primitives:* control chance, control choice.
18. *Now possible:* A deck can be genuinely riffle-shuffled once by a spectator and still obey a
    known block invariant at 100%. *Because:* Gilbreath principle; any stack can be machine-set
    in minutes. *Before:* same principle, set by hand. *Primitives:* control chance, prove
    ordinariness.
19. *Now possible:* In a room of 60, a shared birthday is 99.4% certain; in a room of 100, a
    3.5%-popular thought is present 97%. *Because:* arithmetic. *Before:* known, rarely
    engineered. *Primitives:* control chance.
20. *Now possible:* Exactly N/2^r audience members can be guaranteed a perfect r-event printed
    prediction at 100%. *Because:* variable-data printing, one unique sheet per seat. *Before:*
    needed thousands of mailings. *Primitives:* duplicate, control chance, delay.
21. *Now possible:* A magician's-choice script for N objects can be exhaustively verified for
    consistency on first and repeated use. *Because:* enumeration by software. *Before:* scripts
    tested on audiences. *Primitives:* control choice.
22. *Now possible:* Preference strength between items can be ranked from response time alone.
    *Because:* drift-diffusion regularities; a microcontroller timestamps a touch or a spoken
    answer. *Before:* reading tells by eye. *Primitives:* know. Hit rate for thought-of items
    not established.
23. *Now possible:* A chaotic pendulum or settling object can be captured by one timed pulse of
    millijoules at the end of its motion. *Because:* fractal basins mean the last decision is
    tiny; hall sensor plus coil. *Before:* constant magnets that give visible pull.
    *Primitives:* control chance. Speculative.
24. *Now possible:* A per-peg bias of 0.71 puts one Galton ball in the chosen half 90% of the
    time over 12 rows. *Because:* binomial arithmetic. *Before:* not quantified. *Primitives:*
    control chance. Says open-loop Galton control is hard.

## 4. Effect concepts

### 4.1 The late nudge (level 3)
*Effect:* A spectator throws an oversized die (45 to 60 mm) into a wooden tray. It tumbles,
rocks, and settles on the number written in an envelope they have held all along.
*Method:* The die is honest in mass distribution and contains only an IMU and radio (like a
connected die). The tray holds a voice-coil actuator under a floating floor. The controller
watches the die's orientation and angular rate; in the last rock, when the die is balanced on an
edge between the wanted face and a neighbour, a single 1 to 2 mm lateral floor pulse of the
right sign tips it. If the die is about to settle on a face not adjacent to the target, a
slightly larger pulse buys one more quarter-turn. The pulse hides in the die's own clatter.
*BOM:* nRF52 or ESP32-C3 module, IMU, small cell, printed die shell; tray with voice coil or
solenoid, driver, ESP32. $60 to $120.
*Difficulty:* hard (timing model, 5 to 10 ms radio latency, tuning on one surface).
*Risks:* opposite face up needs two corrections; visible tray twitch; expect perhaps 60 to 80%,
not 100% (speculative), so pair with a two-way out (target face or its total with the bottom).
*Novelty:* high. Stanley's servo die and tappers bias the mass; nothing found that acts once,
externally, at the decision instant.

### 4.2 The shuffler that is a typesetter (level 3)
*Effect:* A spectator shuffles, a desktop "casino shuffler" re-shuffles "so nobody can accuse
me", the spectator then riffles once more by hand and deals. Every pair is a red and a black;
every four cards has one of each suit; a later prediction matches.
*Method:* The machine reads all 52 cards and outputs a Gilbreath-ready stack. The honest hand
riffle afterwards preserves the block invariant and cancels the "the machine set it" theory,
because the audience knows a riffle destroys order.
*BOM:* 3DprintedLife-style sorter (Pi Zero, camera, three steppers, bins), about $200.
*Difficulty:* hard mechanically, easy mathematically.
*Risks:* jams; 1 to 3 minute run time needs covering; machine noise pattern differs between
"random" and "planned" modes unless the planned mode is the only mode.
*Novelty:* medium-high. The sorter exists as a maker joke; pairing it with a shuffle-proof
invariant so the last shuffle is real appears new.

### 4.3 The searched sentence (level 3)
*Effect:* The audience reads a paragraph on a banner or in their programme. Each person
secretly picks any word in the first sentence, counts its letters, jumps that many words, and
repeats to the end. Everyone is on the same word, which has been printed on the back of the
banner all evening.
*Method:* Kruskal coupling, but the text is generated and then exhaustively verified by software
so that all starting words converge (100%, not 85 to 97%). The text can be about that night's
event or company. Different programmes can carry different verified texts ending on the same
word.
*BOM:* a script and a print order. Under $30.
*Difficulty:* easy.
*Risks:* miscounting by audience members (keep it under 60 words; my simulation logic suggests
short words speed convergence).
*Novelty:* medium. The principle is classical; guaranteed convergence by search and overnight
personalisation is the new part.

### 4.4 Graded outs (level 2)
*Effect:* "Name any card." The named card is the only one reversed, or the only one missing, or
is sealed in a block of resin on the table.
*Method:* Three tiers designed from the frequency table. Tier 1 (Ace of Spades, 25%): the
impossible, permanent out, in view from the start. Tier 2 (the next 11 cards, 47 to 48%):
eleven strong outs spread over the performing space, each a single object. Tier 3 (28%): a
conventional any-card method (index or secret writing). Ask two people and choose whom to
continue with and tier 1 or 2 is hit 92% of the time (my calculation: 1 - 0.278²).
*BOM:* props only; cheap one-off fabrication makes eleven different permanent outs affordable.
*Difficulty:* easy to medium.
*Risks:* population differs from Olson's sample; rates fall when people deliberately avoid the
obvious. Log results per show and re-rank.
*Novelty:* low to medium; the contribution is the quantified tiering and the logging loop.

### 4.5 Fifteen rounds (level 3)
*Effect:* The performer plays "which hand holds the coin" or rock-paper-scissors against a
spectator for 15 rounds and wins nearly all the later ones, having sealed the final score.
*Method:* A pocket microcontroller runs an order-4 context predictor. The performer keys in each
result with a toe or finger switch and receives the predicted next move as a tap. The first 5
rounds are "practice" and train the model. The lose-shift and win-stay regularities add a prior.
*BOM:* ESP32 or nRF52 board, vibration motor, two switches. $20.
*Difficulty:* easy electronics, moderate performance load.
*Risks:* per-round accuracy 60 to 75% depending on the person; some people are near 50%
(Aaronson's one student). Sealing "I win the match" is safe at 90 to 95%; sealing an exact score
is not.
*Novelty:* medium. The algorithm is 70 years old; hidden use in a live physical game with a
committed prediction was not found.

### 4.6 The level table (level 2)
*Effect:* Five borrowed cups on a small table, a marble dropped in the centre by a spectator.
It wanders and comes to rest against the cup covering the chosen object. Later a spun coin
drifts to a named person.
*Method:* Three feet of the table are cam or lead-screw actuators with 2 mm travel; an IMU in
the top closes the loop to 0.02°. The table sets a 0.3° slope in the commanded direction
(7 cm of drift in 2 s for a rolling ball) and returns to level while attention is on the
result. A camera is not needed.
*BOM:* three micro linear actuators or geared steppers, IMU, ESP32, battery. $60 to $100.
*Difficulty:* medium.
*Risks:* liquids and hanging objects reveal tilt; actuator noise (move slowly, 2 to 3 s); rough
cloth raises rolling resistance, so use a hard top.
*Novelty:* medium. Self-levelling hardware is common; using it as an invisible selector is not
marketed as far as found.

### 4.7 The fair launcher (level 2)
*Effect:* A glass-fronted brass "coin launcher" is introduced as the fairest possible toss: no
hands. A spectator loads their own coin either way up, pulls the lever, and the coin lands in a
cup. The performer has committed to the result of each of five launches.
*Method:* DHM's deterministic machine. A hidden detent or a 5% change in spring preload changes
the flight by half a revolution, so the performer chooses "same side" or "other side" per launch
after seeing how the spectator loaded it. The coin lands in a felt-lined cup (no bounce).
*BOM:* printed frame, spring, ratchet, felt. $15.
*Difficulty:* medium (repeatability needs a stiff frame and a consistent coin seat).
*Risks:* different coins need different settings: restrict to one denomination; bounce ruins it.
*Novelty:* medium-high as a presented prop.

### 4.8 The surviving row (level 3, statistical theatre)
*Effect:* Every seat has a sealed card. Five audience members flip their own coins. After each
flip, those whose card got it wrong sit down. Eight people remain with five-for-five; three more
flips leave one person whose card also names the row they are sitting in.
*Method:* Each of 256 cards carries a different 8-flip sequence, printed by variable-data
printing and placed by seat map. Nothing else. The reveal explains the scheme.
*BOM:* 256 printed cards and envelopes. $40 to $80 (estimate).
*Difficulty:* easy; logistics only.
*Risks:* people in the wrong seats (print the seat-independent version and drop the row line);
empty seats (use only filled rows, or hand out at the door in sequence).
*Novelty:* medium. Brown did it on film over weeks; a live, same-evening, printed version is
enabled by cheap one-off print.

### 4.9 The patient spinner (level 2)
*Effect:* A plain wooden arrow on a needle pivot is spun hard by a spectator and stops pointing
at the chosen person or object. It can be lifted off and examined.
*Method:* No brake and nothing in the arrow except a steel pin or the needle seat. Control is by
0.2 to 0.3° of base tilt (preferred arc, as in the roulette result) plus, if needed, a stepper-
turned magnet under the base that couples only when the arrow is below about one revolution per
second, sensed by a hall sensor. Open-loop tilt alone will give an arc, not a point.
*BOM:* stepper, magnet, hall sensor, ESP32, tilt feet from 4.6. $50.
*Difficulty:* medium.
*Risks:* visible deceleration that looks "caught"; keep coupling weak and late.
*Novelty:* low to medium; rigged wheels are old, tilt-only bias with an examinable pointer is
the cleaner version.

### 4.10 Two-zone dice pad (level 2)
*Effect:* Dice are rolled repeatedly and fairly by spectators; on the one roll that matters the
total is the predicted one.
*Method:* A close-up pad with a high-damping, high-friction zone (sorbothane-like layer under
the cloth) beside a hard zone. On the critical roll the performer rolls, or has the spectator
"drop them from the cup", into the dead zone from a low height with the dice pre-oriented by
the cup's printed internal ribs. Kapitaniak: few bounces means the starting orientation
survives.
*BOM:* damping sheet, cloth, printed dice cup. $25.
*Difficulty:* easy to medium; needs measurement of hit rate.
*Risks:* dead-zone rolls look and sound different (short, quiet); hit rate unknown until tested.
*Novelty:* medium.

### 4.11 Compiled equivoque (level 2)
*Effect:* A spectator freely eliminates objects until one remains; it matches. Repeated with a
second spectator, it works again with different choices.
*Method:* Software enumerates every branch for N objects and a vocabulary of instructions,
rejects trees where any branch would need an instruction that contradicts an earlier one on a
repeat performance, equalises branch lengths, and weights the first step by the position bias
(third of four chosen 52 to 60%) so the most direct branch is the most common. Output is a
one-page script.
*BOM:* software only.
*Difficulty:* easy.
*Risks:* the performer must deliver every branch identically; the tree is only as good as the
wording.
*Novelty:* medium; the research shows repetition is survivable, and formal verification of
scripts was not found.

## 5. Dead ends and overhyped items

- **The 50.8% same-side coin bias.** Real, but 0.8 points needs thousands of flips to matter.
- **Predicting or controlling a hard-thrown 16 mm die.** Kapitaniak: deterministic but
  practically random with bounces. Internal reaction wheels do not fit, and a mass offset large
  enough to reach 90% makes the die roll visibly wrong.
- **Passive loaded dice as forces.** 40% at best in a realistic build. Good only as an out-
  multiplier.
- **Open-loop Galton or Plinko control by tilt.** Needs about 70% bias at every peg over 12
  rows. Tilt large enough for that is visible. Use closed-loop capture at the bottom or
  redesign the pegs.
- **Predicting a magnetic pendulum from its release.** Fractal basins; not measurable outside
  the big basins.
- **Priming forces.** 17.8% exact hit in the best-documented case; the suit component did not
  beat control. Do not build a routine on one.
- **Gaze cascade as mind reading.** Weak or absent for some stimuli; the 81% figure is seven
  subjects.
- **Number forces quoted without context.** Kubovy shows the modal answer halves when the
  context changes. Internet polls are skewed by joke answers (69, 42).
- **Rigged apps and LED dice.** The audience's first guess is right. Only useful as a hidden
  trigger for a physical process.
- **Lab-grade closed loops.** Rober's dartboard needed six motion-capture cameras and three
  years. The lesson is the architecture, at tabletop scale with in-prop sensors, not the rig.
- **Vibration "walking" as outcome control.** It works for parts feeding, but acts after the
  visible motion and is likely audible; unproven for this use.

## 6. Open leads

- First-response proportions from the Van Overschelde et al. (2004) category norms (tool,
  vegetable, flower, colour, country) and per-cue distributions from Small World of Words, to
  build top-k coverage tables like the one for cards.
- Per-number percentages from the Veritasium 200,000-response survey and any dataset for the
  "odd two-digit number under 50" force; magic-community test data (the Jerx's focus-group
  testing of psychological forces was searched for and not found).
- Exact rates from the equivoque paper (Pailhès, Kumari & Kuhn 2021) and the position-force
  paper; the Goldsmiths repository host (eprints-gro.gold.ac.uk) was not reachable from this
  session and would need to be allowed.
- Measured data on real human riffle and overhand shuffles versus the GSR model, and how many
  cards of a known stack can be tracked through two or three real shuffles.
- Hit rates for hover time, first touch, grip and weight shift as predictors of a thought-of
  object. Probably unmeasured; a 30-person experiment with a sensing tabletop would settle it.
- Kapitaniak's numerical tables (probability of the initially lowest face versus drop height
  and surface), to design concept 4.10 properly. The core.ac.uk copy returned 403.
- Human thresholds for seeing or feeling a table tilt of 0.2 to 0.5°.
- Quantified mass or drag bias in air-mix ball machines and bingo cages.
- Whether any hobbyist has built a faro-shuffling machine, and the cycle time of the fastest
  hobby card sorters.
- HCI evidence on trust in physical versus electronic randomisers (none found; one PubMed item,
  "An illusion of unfairness in random coin flips", could not be opened).
- Current per-piece prices for variable-data printed cards and one-off custom decks.
- Latency of hobby high-speed vision (global-shutter cameras at 120+ frames per second on a
  Pi or ESP32-S3) for a tabletop janken-style "always wins" reveal.

## 7. Sources

Randomiser physics
- https://www.stat.berkeley.edu/~aldous/157/Papers/diaconis_coinbias.pdf - Diaconis, Holmes & Montgomery 2007, coin toss dynamics, machine, spun coins.
- https://arxiv.org/abs/2310.04153 - Bartoš et al., 350,757 flips, same-side 0.508.
- https://sciencenews.org/?p=36382 - Science News, spun penny about 80% tails.
- https://www.stat.berkeley.edu/~aldous/Real-World/coin_tosses.html - 40,000 tosses, ambiguous evidence.
- https://phys.org/news/2012-09-die.pdf - Kapitaniak et al. die throw summary.
- https://www.aip.org/inside-science/dice-rolls-are-not-completely-random - Kapitaniak interview, bounces and friction.
- https://www.Gwern.net/doc/statistics/probability/2009-labby.pdf - Labby, Weldon's dice automated.
- https://www.ucl.ac.uk/mathematical-physical-sciences/news/2014/jun/formula-cheating-dice - Pender & Uhrin, 16,300 throws.
- https://ar5iv.labs.arxiv.org/html/1407.6307 - Predicting non-square 2D dice probabilities.
- https://web3.arxiv.org/pdf/1302.3925 - cuboid tossing, technique dependence.
- https://cooperrc.github.io/engineering-dynamics/module_04/dice.html - weighted die worked example.
- https://incoherency.co.uk/blog/stories/loaded-dice.html - James Stanley, servo-loaded printed die.
- https://www.nordicsemi.com/News/2022/08/Particulas-GoDice-employs-Nordics-nRF52805-SoC - GoDice internals.
- https://hackaday.com/2019/10/09/these-dice-know-if-youre-cheating - Pixels dice.
- https://arxiv.org/abs/1204.6412 - Small & Tse, predicting roulette, 0.2° tilt.
- https://www.lotteryusa.com/news/science-lottery-machines-how-random-is-random - lottery machine design and testing.
- https://gauss.math.yale.edu/fractals/Labs/MagPendulumLab/MagPendulumLab.html - magnetic pendulum basins.
- https://math.hmc.edu/~dyong/math164/2006/win/finalreport.pdf - magnetic pendulum student report.
- https://en.wikipedia.org/wiki/Galton_board - Galton board.
- https://core.ac.uk/download/232275551.pdf - NJIT thesis on Galton board with tilt (not read).

Cards and shuffling
- https://www.stat.berkeley.edu/~aldous/157/Papers/bayer_diaconis.pdf - Bayer & Diaconis 1992.
- https://math.hmc.edu/funfacts/seven-shuffles/ - seven shuffles, overhand figure.
- https://arxiv.org/abs/math/0501401 - Jonasson, overhand shuffle mixing time.
- https://arxiv.org/pdf/1107.2961 - Diaconis, Fulman & Holmes, shelf shufflers.
- https://ioactive.com/article/internal-camera-hacked-casino-card-shuffler-lets-you-look-at-the-cards/ - Deckmate 2 camera.
- https://www.hackster.io/news/rig-the-deck-so-you-always-win-with-this-card-shuffler-5db782b1b15f - 3DprintedLife planned-shuffle machine (seen in search results; page returned 403).
- https://engineering.purdue.edu/477grp10 - Purdue smart card shuffler.
- https://courses.physics.illinois.edu/ece445/project.asp?id=12014 - UIUC card sorter.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC4233310 - Williams & McOwan, Magic in the machine.
- https://mathworld.wolfram.com/GilbreathPrinciple.html - Gilbreath principle.
- https://en.wikipedia.com/wiki/Gilbreath_shuffle - Gilbreath shuffle, ultimate principle.
- https://www.ams.org/featurecolumn/archive/mulcahy6.html - Mulcahy, mathematical card tricks.
- https://arxiv.org/abs/math/0110143 - Lagarias, Rains & Vanderbei, The Kruskal Count.
- https://en.wikipedia.org/wiki/Kruskal_count - variants, Dynkin, clock version.
- https://faculty.uml.edu/rmontenegro/research/kruskal_count/index.html - Kruskal count and kangaroo method.
- https://rss.org.uk/RSS/media/Membership/Volunteering/Education/Sociable_cards_vP1.pdf - group version.

Control and actuation
- https://hackaday.com/2017/03/22/dartboard-watches-your-throw-catches-perfect-bullseyes - Rober dartboard.
- https://www.hackster.io/news/hit-the-bullseye-every-time-on-this-self-adjusting-dartboard-343b1b74e57 - dartboard timing.
- https://www.hackster.io/news/a-basketball-hoop-that-won-t-let-you-miss-998c5721485e - Wighton hoop (seen in search results).
- https://www.windowscentral.com/man-uses-kinect-and-windows-make-basketball-hoop-you-cant-miss - hoop, Kinect and lag.
- https://www.therobotreport.com/this-rock-paper-scissors-robot-has-never-lost-to-a-human/ - janken robot.
- https://robohub.org/swiss-robots-cubli-a-cube-that-can-jump-up-balance-and-walk-across-your-desk - Cubli.
- https://github.com/willem-pennings/balancing-cube - hobby balancing cube.
- https://hackaday.com/2024/10/13/diy-3d-printed-arduino-self-balancing-cube - Arduino balancing cube.
- https://circuitdigest.com/news/this-esp32-powered-self-balancing-cube-jumps-with-a-spring-and-uses-a-reaction-wheel-to-land-on-its-edge - jumping ESP32 cube.
- https://blog.arduino.cc/2017/07/14/ball-on-plate-machine-uses-touchscreen-position-sensing - ball on plate.
- https://people.eecs.berkeley.edu/~jfc/dreznik/UPM2000/ - Universal Planar Manipulator.
- https://people.eecs.berkeley.edu/~jfc/dreznik/Pubs/wafr98.pdf - Reznik & Canny 1998.
- https://patents.google.com/patent/US8791902 - haptic device with controlled traction forces.
- https://www.jstage.jst.go.jp/article/jjspe1933/45/533/45_533_573/_article/-char/en - rolling friction of steel balls.
- https://arxiv.org/pdf/2111.06258 - rolling friction torque analysis.

Human choice and prediction
- https://www.cs.ubc.ca/~rensink/publications/download/Cards-OAR.pdf - Olson, Amlani & Rensink 2012.
- https://gwern.net/doc/psychology/cognitive-bias/1976-kubovy.pdf - Kubovy & Psotka 1976.
- https://www.veritasium.com/videos/2024/6/19/why-is-this-number-everywhere - 37 survey.
- https://telescoper.blog/2018/04/11/what-happens-if-you-ask-people-to-pick-a-number-at-random-between-1-and-100/ - 6,750-person tally.
- https://iflscience.com//is-the-blue-seven-phenomenon-real-yes-kind-of-77553 - blue-seven summary.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC7395500 - Pailhès & Kuhn 2020, conversational primes.
- https://link.springer.com/article/10.1007/s00426-020-01350-z - Pailhès & Kuhn, position force.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC7583451 - Pailhès & Kuhn, criss-cross force.
- https://research.gold.ac.uk/29234 - Pailhès, Kumari & Kuhn, equivoque.
- https://www.psychologicalscience.org/journals/psychological-science/j.1467-9280.1995.tb00304.x/ - Christenfeld 1995.
- https://ratio.huji.ac.il/node/3129126 - Bar-Hillel, position effects.
- https://arxiv.org/pdf/1404.5199 - Wang, Xu & Zhou 2014, rock-paper-scissors.
- https://www.scottaaronson.com/democritus/lec18.html - Aaronson, key-press predictor.
- https://literateprograms.org/mind_reading_machine__awk_.html - Shannon's mind-reading machine.
- https://magazines.ulbsibiu.ro/ijasitels/index.php/IJASITELS/article/view/49/46 - software reproduction of Shannon and Hagelbarger machines.
- https://srri.umass.edu/sites/srri/files/FalkKonold1997/index.pdf - Falk & Konold 1997.
- https://www.slate.com/blogs/future_tense/2012/09/19/how_to_choose_a_pin_code_avoid_birth_date_1234_or_8068.html - PIN statistics.
- https://www.doi.org/10.3758/s13428-018-1115-7 - Small World of Words norms.
- https://link.springer.com/10.3758/s13428-021-01787-z - category production norms overview.
- https://dlab.sauder.ubc.ca/sjdm/journal/18/181101/jdm181101.html - Konovalov & Krajbich 2019.
- https://www.nature.com/articles/nn1150 - Shimojo et al. 2003, gaze cascade.
- https://www.psychologicalscience.org/journals/psychological-science/0956797613487384/ - Slepian et al. 2013.
- https://snelg.github.io/jta/ - progressive anagram tool.
- https://www.cavemanchemistry.com/anagram - progressive anagram generator.
- https://thejerx.squarespace.com/blog/2025/6/1/progressive-anagram-tool - write-up of the tool.

Whole-audience
- https://derrenbrown.co.uk/shows/the-system/ - The System.
- https://botherer.org/?p=851 - description of the scheme and the 7,776 figure.
