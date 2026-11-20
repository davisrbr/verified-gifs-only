# 03 - Prior art: makers, open source, academia, patents, technology-forward performers

Scope: where engineering and conjuring already meet outside the mainstream magic dealers, and what
that says about how much of the thesis is still open. Dealer products (agent 2), classical taxonomy
(agent 1), psychology (agent 4) and the individual engineering domains (agents 5 to 14) get one-line
pointers only.

**Access note.** The shared web-search budget ran out after my first ten searches. Everything after
that came from direct fetches of primary pages: Google Patents (class and assignee queries plus
individual patent pages), arXiv listings, Frontiers, Hackaday, Wikipedia, lab and performer pages.
Thingiverse, Printables, MakerWorld, Cults3D, Kickstarter, Hackster, SparkFun, Justia and ACM DL
pages returned 403 or could not be queried, so download rankings on those sites and the CHI/UIST/TEI
literature are thinner than I wanted. Anything written from memory is marked **(unverified)**.
Prices are rough late-2026 estimates and were not checked against supplier pages.

---

## 1. Summary

- **3D-printed magic is plentiful but shallow.** What gets downloaded is re-modelled 19th and 20th
  century mechanical apparatus: coin slides and drawer boxes, thumb tips, pencil-through-bill
  guides, money-printing frames. The most-downloaded item I could confirm is a 2012 coin-piercing
  box with "almost 14,000" downloads; most others sit in the hundreds to low thousands. None use
  electronics, and none address examinability (layer lines and seams announce "printed gimmick").
- **DIY electronic magic has converged on one architecture**: a sensor hidden in a prop, a radio
  (BLE advertisement or ESP-NOW), and a vibration or peek for the performer. Published builds (a
  gyro die, a capacitive coin box, a free-fall deck) are mostly proofs of concept that stop before
  the performer-side feedback is finished. It is the same architecture the dealers sell, and it now
  appears in patents (Penguin Magic's tuck-box scale; Nathan Buzza's multi-vendor "Notifier").
- **The most honest maker write-up reports a failure of effect, not of engineering.** James
  Stanley's CNC-milled Bluetooth coin box worked and was fully examinable, and friends still
  shrugged it off as "rigged". A flawless hidden sensor does not by itself beat the "it's
  electronic" theory.
- **Academia has one sustained "computers design magic" programme** (Williams and McOwan, Queen
  Mary University of London, 2014 to 2016): genetic-algorithm and simulated-annealing design of a
  vanishing-area jigsaw and a stacked-deck phone trick, both sold in a London magic shop. Since
  then the literature I could reach is mostly magic as a *test* for machines (a 2019
  DeepLabCut-as-spectator study; a NeurIPS 2026 video benchmark) and logic formalisations of
  tricks. I found no paper in which software designs a physical gimmick, and none in which an LLM
  designs a performable trick.
- **Magic-industry patents are few and low-tech.** Google Patents returns only 109
  English-language families in CPC A63J 21/00 with priority after 1 January 2014, and many of those
  are toys, wands and Pepper's-ghost foils. The filings that are really for conjurers are small:
  magnets in half-balls and shoelaces, a thread-spool wand, a vibrating ring, a watch set by phone.
- **The sophisticated illusion engineering is in theme-park filings**, mostly Universal (Akiva
  Krauthamer and colleagues) and Disney (Lanny Smoot, Quinn Smithwick and colleagues): a sliding
  mirror-to-glass gradient that makes the guest vanish from their own reflection; mirrors that
  change angle while a camera waits for the guest to blink; an addressable electromagnet array that
  puppeteers a battery-less plush toy; props powered by a tracked near-infrared beam; an invisible
  UV stamp on the guest's hand used as a tracking marker; an infrared camera boresighted with a
  projector so beams of light appear to leave an audience member's badge.
- **None of that has been miniaturised for close-up or parlor magic.** Sensing the spectator
  (position, gaze, blink) and adapting the method to them in real time is the largest unclaimed
  area I found.
- **Technology-forward performers mostly make technology the subject**: screens, drones, robots,
  holograms, and now "AI". The best-documented case, Marco Tempest's 24-drone piece, turns out to
  rest on a classical method: the drones flew pre-programmed routes and the performer acted the
  interaction.
- **Theatre is the quiet success story.** Jamie Harrison and Chris Fisher's illusions for *Stranger
  Things: The First Shadow* earned a Special Tony Award in 2025, and *Harry Potter and the Cursed
  Child* runs a "#KeepTheSecrets" campaign. Methods are not public; the lesson available from
  outside is that technology is kept invisible and subordinate to story.
- **Adjacent consumer hardware already ships magic methods openly**: maglev lamps, chessboards
  whose pieces move by hidden magnets, sand tables, 3D-printed Sugihara ambiguous objects. The
  escape-room community has a mature free stack for hidden sensors (Playful Technology's
  Node-REDscape and RFID libraries) that magic builders appear not to use.

---

## 2. Catalog

### 2.1 3D-printed and DIY mechanical magic

**What exists.** The model sites carry a long tail of "magic trick" prints. All3DP's roundup of ten
gives a fair cross-section with counts: Coin Piercing by dnewman on Thingiverse (almost 14,000
downloads, 28 makes), Picture Frame money printer by daveab (over 7,300), Disappearing Coin slide
by AZDawg (almost 4,400), a fan-driven "levitating ball" (almost 2,000), a printed thumb tip (over
1,300), a pencil-through-bill guide (542), and several MyMiniFactory models with 13 to 500
downloads. On MakerWorld, a remodelled "magic coin box" showed 220 boosts and 294 makes in a
search snippet (the page itself was blocked).

- References: https://all3dp.com/2/3d-printed-magic-tricks-3d-models/ ;
  https://www.thingiverse.com/thing:24719 ; https://www.thingiverse.com/thing:3157749 ;
  https://www.thingiverse.com/thing:1764501 ; https://makerworld.com/en/models/251925
- Accessibility: free files, cents of filament.
- Quality level: toy-shop mechanics in visibly printed plastic. Tolerances are loose, nothing is
  weighted, finished or disguised as a real object, and nothing survives handling by a suspicious
  adult. Designers copy apparatus they already know; I saw nothing that uses what printing is
  uniquely good at (internal channels, embedded magnets or electronics added mid-print, one-off
  personalisation, living hinges, multi-material transparency).
- Magic relevance: vanish, penetration, transformation for children's and beginner magic. The gap
  is the interesting part: print-in-place mechanisms inside objects that look injection-moulded or
  turned from wood, and printed *duplicates of real objects* rather than printed boxes.
- Prior use: one patent (US11288910B1, section 2.7) explicitly claims 3D-printed PLA spheres and a
  printed cage with a "ferromagnetic appearance" as a way to hide a magnet trap, which shows
  printing used for disguise rather than for the visible apparatus.

**Puzzle boxes and impossible objects.** Printable puzzle boxes, impossible dovetails and
"impossible bottle" jigs overlap with magic in mechanism (hidden magnets, gravity pins, centrifugal
locks) but are presented as puzzles. Chris Ramsay's YouTube channel popularised high-end mechanical
puzzles to a magic audience **(unverified, from memory)**. These are a reservoir of compact locking
and release mechanisms rather than effects.

### 2.2 DIY electronic magic (Hackaday, Instructables, Adafruit, Hackster)

**Wireless gyro die (Naufil Metkar, 2022).** A 3D-printed die holding an MPU6050 and a small ESP
module sends its orientation by ESP-NOW to an ESP8266, which only prints coordinates to a serial
port. A reed switch and magnet power it down. Commenters asked whether the die is balanced and
suggested a Seeed Xiao BLE Sense for lower standby current; one pointed to a commercial LED gaming
die as the nearest product.
- Reference: https://hackaday.com/2022/09/23/for-the-esps-next-esp-trick/
- Accessibility: hobbyist, about $10 to $20 in parts.
- Relevance: identification, prediction. This duplicates long-standing dealer products (agent 2)
  at lower quality: oversized, unbalanced, short battery life, no finished peek.

**Egyptian coin box (James Stanley, 2023).** A coin placed in one of five slots is located by
capacitive sensing: a copper plate under each slot, a grounded copper sheet in the lid, a 1 megohm
resistor per channel, and charge-time counting on a Seeed Xiao ESP32C3. Readings go out in the
manufacturer-data field of BLE advertisements (connections to the watch were unreliable) to a
Bangle.js smartwatch that vibrates. The electronics sit in a CNC-milled pocket between two
half-thickness plywood sheets glued with crossed grain and cut to shape afterwards, so there is no
visible seam; charging is through a USB-C port hidden behind a removable hinge.
- References: https://incoherency.co.uk/blog/stories/egyptian-coin-box.html ;
  https://hackaday.com/2023/08/07/the-egyptian-coin-box-trick
- Accessibility: hobbyist with CNC or laser access; roughly $30 to $60.
- Relevance: identification, ESP. Deception properties are good (examinable, silent, no moving
  parts). The reported weakness is conceptual: spectators assumed a rigged box. The author's own
  conclusion, following The Jerx, was to use it for unannounced moments rather than as a
  presented trick.
- Safety: a lithium cell glued inside wood has no vent path; the author fitted a 1 A polyfuse.

**Arduino Psychic (Hari Wiguna, 2020).** Two Arduinos that share no wire or radio: a "randomizer"
and a "psychic" that names the chosen number. The channel is the audience. The randomizer computes
a sentinel digit (nine minus the larger digit of a throwaway number) and shows the real choice
immediately after a number containing that sentinel; the psychic runs the same arithmetic on the
"guesses" typed into it.
- References: https://hackaday.com/2020/11/24/bet-you-didnt-know-arduinos-are-psychic/ ;
  https://www.instructables.com/Arduino-Psychic/
- Relevance: thought transmission. It is the classical two-person code moved into firmware. It is
  the only DIY build I found whose method survives the "they must be talking by radio" theory,
  because they are not.

**Mystery Box: The Freefall Deck (John Park, Adafruit, 2017).** A sealed-looking Bicycle deck
contains a Circuit Playground whose LIS3DH accelerometer raises a free-fall interrupt; tossing the
deck makes it beep a Morse message. Extra cards restore thickness and weight and the cellophane is
re-closed with hot glue.
- Reference: https://www.digikey.com/en/maker/projects/mystery-box-the-freefall-deck/64b85f9fcdad46399151e5f98493db29
- Relevance: an escape-room prop, but it documents the "factory-sealed object that is secretly a
  computer" construction, including weight matching.

**Other items seen but not opened.** A Bluetooth thumb-tip controller, "MATT+", reported by
Hackster as hiding inside a standard thumb tip
(https://www.hackster.io/news/the-microcontroller-powered-matt-puts-magic-at-the-tip-of-your-thumb-8007c7829e12);
an electronic cheating die
(https://hackster.io/news/cheat-your-friends-with-this-electronic-trick-die-0c8bef4291af); an
Arduino card-trick project on hackaday.io (https://hackaday.io/project/164418-arduino-magic-trick/).
Hackaday's own "magic-trick" tag holds a single post, and GitHub's "magic-trick" topic holds four
small software repositories and no firmware (https://github.com/topics/magic-trick). The open-source
magic-hardware scene is close to empty.

**Pattern.** DIY Pepper's ghost pyramids, fan levitators and "PK" magnet rigs exist in volume
**(unverified beyond the All3DP fan example)**, and they show a phenomenon rather than hide a
method. The builds with a hidden method all reduce to "know and tell", and they stop at the bench
demo.

### 2.3 Maker-magicians and YouTube

**Mario "the Maker Magician" Marchese.** A touring family show billed as "all-ages robot magic".
A 2013 Make profile describes a vaudeville suitcase with about 18 Arduino-driven servos that pop
epaulets, drop banners and spin lapel ribbons; he taught himself electronics because "to advance
his act he had to build it himself".
- References: https://makezine.com/2013/02/18/making-magic-with-arduino ;
  https://www.mariothemagician.com/ ; https://news.sparkfun.com/2482 (blocked)
- Relevance: animation and comedy sight gags. The electronics are visible and charming rather than
  deceptive; the robots are characters. This is the most successful "maker aesthetic" act and it
  deliberately does not hide its technology.

**YouTube exposure and gimmick channels** (Mismag822, Magic Wagon, Rick Lax-style viral clips,
Craig Petty's reviews of electronic props) **(all unverified, from memory)**: they spread
awareness of dealer technology to lay audiences, which raises the baseline suspicion of anything
that could contain electronics. Agent 2 covers the products.

### 2.4 Technology-forward performers

**Marco Tempest.** Swiss "cyber illusionist", MIT Media Lab Director's Fellow alumnus, creative
technologist at NASA JPL since 2018. Works named on Wikipedia include a 32-screen video-wall show
(1991), "phonecam" single-take tricks from 2006, and "Magic Projection", imagery that tracks a
moving canvas. At TED2014 he performed with a robot called EDI (3.5 million plays). In February
2016 his MagicLab and Rhizomatiks Research released "24 Drone Flight": 24 small drones swarming
around him using what Rhizomatiks calls "a cutting-edge proprietary indoor localization and control
system", reported as three years in development. A 2020 MIT Media Lab article about his SIGGRAPH
talk states the method plainly: the drones "followed preprogrammed routes", partly guided by lines
on the carpet, and "didn't pay any attention" to his gestures or voice.
- References: https://en.wikipedia.org/wiki/Marco_Tempest ;
  https://www.media.mit.edu/articles/what-magic-can-teach-us-about-the-future-of-technology-according-to-an-mit-magician/ ;
  https://research.rhizomatiks.com/en/works/marco_tempest_magic.html ;
  https://rhizomatiks.com/en/work/24-drone-flight ;
  https://www.vice.com/en/article/cyber-illusionist-drone-performance/ ;
  https://www.ted.com/talks/marco_tempest_and_for_my_next_trick_a_robot
- Accessibility: lab-scale then; a handful of Crazyflie-class drones with optical positioning is
  now a four-figure hobby project **(unverified estimate)**.
- Relevance: animation, sympathetic reaction. The useful lesson is that the apparent interactivity
  was the illusion. Choreography plus acting was cheaper and more reliable than real gesture
  control, and the audience credited the technology with more than it did.
- Safety: propellers near faces; indoor swarm failures.

**Simon Pierro ("the iPad magician").** Since about 2008: objects appear to pass in and out of a
tablet, including a beer tap attached to the screen that pours real beer. Two videos had over 80
million views by 2015. Wikipedia gives no technical detail. Keelan Leyser sells the same genre as
"Tech Magic" with iPads, LED screens, drones, robots, holograms and "AI Magic", and a Las Vegas
show, *HACKED*, themed on deepfakes.
- References: https://en.wikipedia.org/wiki/Simon_Pierro ; https://www.keelanleyser.com/
- Relevance: production, transposition between screen and world. The methods are classical loads
  and steals with video synchronisation **(unverified)**; the screen supplies motivation and
  misdirection. It is the genre the brief rates as weak, and it shows the too-perfect problem
  inverted: nobody asks how, because "it's the tablet" is the accepted answer.
- Jamie Allan ("iMagician"), Tom London, Kevin Li, Moulla and Xavier Mortimer work the same seam
  with tablets, apps, AR headsets, projection and video walls **(all unverified, from memory; I
  could not open sources)**.

**Zach King.** "Digital sleight of hand": edited short videos; about 87 million TikTok followers;
"Magic Broomstick" (2019) holds a Guinness record at 2.2 billion views. Video-only context.
- Reference: https://en.wikipedia.org/wiki/Zach_King

**Shin Lim.** Silent close-up card act set to music; won *America's Got Talent* in 2018 and its
*Champions* edition in 2019. Wikipedia notes special decks and slow-motion self-review but nothing
about his smoke devices; the small vapour gimmicks associated with his act are dealer territory
**(unverified)**.
- Reference: https://en.wikipedia.org/wiki/Shin_Lim

**Derek DelGaudio and Glenn Kaino (A.BANDIT).** A performance-art collective that staged
interventions at Art Basel Miami, LA><ART and The Kitchen, and ran "The [Space] Between", a
"conceptual magic shop". *In & Of Itself* (directed by Frank Oz, filmed for Hulu in 2021) is known
for effects built on information about each audience member **(effect details unverified)**. The
relevance here is architectural: the strongest reported moments depend on logistics and information
handling before and during the show, not on apparatus.
- Reference: https://en.wikipedia.org/wiki/Derek_DelGaudio

**Adrien M & Claire B, teamLab.** Projection and real-time physics installations where the
phenomenon is the piece **(Adrien M & Claire B unverified; the Wikipedia page did not resolve)**.
teamLab holds a patent for strobing light onto intermittently released water droplets so they
appear frozen or rising (US12539470B2).

### 2.5 Theatre and theme-park illusion engineering

**Stage plays.** *Harry Potter and the Cursed Child* credits Jamie Harrison for illusions and
magic, with a standing "#KeepTheSecrets" campaign (slogan on tickets, badges at the interval).
*Stranger Things: The First Shadow* credits Harrison and Chris Fisher for "illusion design and
visual effects" and 59 Productions for video; in 2025 Harrison, Fisher, Gary Beestone and Edward
Pierce received a Special Tony Award "for illusions and technical effects".
- References: https://en.wikipedia.org/wiki/Harry_Potter_and_the_Cursed_Child ;
  https://en.wikipedia.org/wiki/Stranger_Things:_The_First_Shadow
- Public knowledge of method is close to nil, by design. What can be said from outside is that
  both shows blend classical stage principles with tightly cued lighting, sound and video so that
  no single technology is identifiable **(interpretation, unverified)**.

**Disney.** The Haunted Mansion's Hatbox Ghost is the canonical case of an effect waiting for
technology: the 1969 figure, whose head was meant to vanish and reappear in the hatbox, was pulled
within days because ambient light kept the face visible. The 2015 replacement is an animatronic
with a projected face. Disney Research's "Magic Bench" (SIGGRAPH 2017) gives a walk-up group a
shared third-person mixed-reality view with haptics in the bench. Disney patents since 2014 lean
heavily to floating-image displays (retroreflector aerial images, mirror displays without viewer
reflection, spinning displays), plus a few mechanisms detailed in section 2.7.
- References: https://en.wikipedia.org/wiki/Hatbox_Ghost ;
  https://la.disneyresearch.com/publication/magic-bench/ ;
  https://en.wikipedia.org/wiki/Pepper%27s_ghost
- Recent filings reported by fan press: a projection surface that deploys into a scene and
  retracts (filed December 2024) and a forced-perspective "elevation change" set with no moving
  parts or projection (filed February 2025).
  https://www.wdwmagic.com/other/walt-disney-imagineering/gallery/04jun2026-disneys-latest-patent-drawings-reveal-a-new-kind-of-theme-park-illusion.htm ;
  https://blogmickey.com/2026/08/disney-patent-reveals-new-elevation-change-illusion-for-theme-park-attractions/

**Universal.** The richest vein I found; see the patent table. The recurring ideas are: track the
guest invisibly (retroreflective wand tips since a 2013 priority, UV stamps, RFID wearables), use
that data to aim or time the effect at one person, and update Pepper's ghost with sensing so real
and virtual scenes stay consistent.

### 2.6 Academic work that targets magic

**Williams and McOwan, "Magic in the machine" (Frontiers in Psychology, 2014).** A three-part
framework: a constrained trick domain, measured perceptual data, and a search engine.
- *Magic jigsaw.* A two-dimensional version of the DeLand concealed-distribution paradox: 12
  rectangles become 10 on reassembly. NSGA-II with a rectangle packer searched designs under
  measured constraints: people miss a length increase of 9.5% to 21.1% depending on orientation,
  counting costs about 160 to 470 ms per rectangle, and assembly becomes erratic above eight
  pieces. The search converged in under 50 generations, about two minutes on a desktop. It was
  made as a laser-cut printed wooden puzzle; two runs totalling 30 units sold out at a London
  magic shop.
- *Probabilistic card trick.* Simulated annealing arranged a cyclic 52-card stack so that naming
  the colours of four dealt cards, plus knowledge of which cards people prefer, identifies a
  mentally chosen card in up to four guesses. A phone app holds the lookup, with input through a
  fake passcode screen. It averaged 3.85 questions against 4.04 for Aronson's Simon-Eyes. At a
  science festival (N=116) it scored 3.28 out of 4. It was released as the Android app "Phoney".
- Finding worth keeping: McOwan reported that "we suspected that audiences would be suspicious of
  the involvement of technology" and found they were not.
- References: https://www.frontiersin.org/articles/10.3389/fpsyg.2014.01283/full ;
  https://pmc.ncbi.nlm.nih.gov/articles/PMC4233310 ;
  https://www.sciencedaily.com/releases/2014/11/141116211014.htm ;
  https://qmro.qmul.ac.uk/xmlui/handle/123456789/12788?show=full
- Follow-up: "Manufacturing Magic and Computational Creativity" (2016) concedes that "humans remain
  the main creative force", notes there is no shared annotated dataset of performances, and
  proposes optimising close-up magic from gaze and timing data. I found no sign that was done.
  https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2016.00855/full
- Accessibility: trivially reproducible today; the optimisation would run in a browser.

**Formal models of tricks.** Smith, Dignum and Sonenberg (2016) model a trick as parallel "effect"
and "method" event sequences in propositional dynamic logic and name two apparatus properties that
make impossibility possible: substitutable elements and stable occlusion. Icard and Fervari (2024)
give a dynamic epistemic logic of misdirection using the French Drop; Zhu (2024) model-checks a
card routine. These could become the fitness function for automated trick search; nobody appears
to have closed that loop.
- References: https://www.frontiersin.org/articles/10.3389/fpsyg.2016.00748/full ;
  arXiv:2401.14516 ; arXiv:2402.13802 (both seen in https://arxiv.org/search/?query=%22magic+trick%22&searchtype=all)

**Machines as spectators.** Zaghi-Lara, Gea, Camí, Martínez and Gomez-Marin (2019) trained
DeepLabCut to follow coins through a professional magician's vanishes "as a human spectator would";
some sleights fooled people and not the network, and some the reverse. "The Prestige" (Wen et al.,
NeurIPS 2026 datasets track) is a video benchmark of professional magic performances and reports a
"substantial gap" between the best vision-language model and humans in explaining what happened.
- References: https://arxiv.org/abs/1908.07446 ; https://arxiv.org/abs/2610.38103
- Relevance: a network that tracks where a spectator *believes* the coin is, is a ready-made
  rehearsal critic. Nobody has packaged it as one.

**Mathematics of tricks.** Diaconis and Graham's *Magical Mathematics* (Princeton, 2011) is the
foundation: de Bruijn sequences, Gilbreath principle, shuffles **(publisher page blocked; details
from memory)**. arXiv keeps adding small results: the Kruskal count (math/0110143), a
generalisation of the Hummer principle to odd packets (2308.02684), Gozinta box geometry
(2508.18277), Fibonacci sum tricks (2409.01296), the 21-card trick (1809.04072), a string "proof"
that knots are trivial (2604.13799), and the elastic mechanics of the coin-through-rubber trick
(1509.06232).
- Reference: https://arxiv.org/search/?query=magician&searchtype=abstract

**Magic as a lens for interface design.** Tognazzini's INTERCHI '93 paper is still the reference:
the "user illusion", simulation versus dissimulation, manipulation of perceived time (do the work
before the user looks for it, or after they think it is finished), and a "threshold of
believability" to be exceeded with margin. Later HCI and game-design work in this line (Marshall,
Benford and Pridmore, CHI 2010; Kumari, Deterding and Kuhn, 2018) exists **(unverified, from
memory)**. The direction of transfer is always magic into HCI. I found no HCI or fabrication paper
that builds conjuring apparatus.
- Reference: https://www.asktog.com/papers/magic.html

**Robot magicians.** A 2015 Japanese paper on a high-speed robot performing card manipulation and
later humanoid "robot magic" shows exist **(unverified; the URL I tried returned 404)**. Patents
record a Korean "magic robot" that moves real props in step with a monitor (KR101659400B1) and a
Chinese cabinet with two robot arms and two cameras (CN107970625A). The robot is the spectacle in
every case, never the secret.

**LLMs and magic.** Performers market "AI magic" (Leyser), and the 2026 benchmark shows models
still explain tricks poorly. I found no published LLM-designed trick or LLM-driven mentalism
system; given the search limits this absence is **unverified**.

### 2.7 Patents, 2014 to 2026

Counts from Google Patents: A63J 21/00 with priority after 2014-01-01, English: 109 results.
A63J 5/02 after 2016: 2,018 results, dominated by stage lighting, bubble and fog machines and K-pop
light sticks. "Illusion" with assignee Disney Enterprises after 2014 (US): 115. A similar query for
Universal City Studios after 2016: 122. All entries below were read on Google Patents
(https://patents.google.com/patent/NUMBER/en) unless marked "listing only".

**Conjuring apparatus (magic industry and individuals)**

| Patent | Who, priority | Effect | Mechanism |
|---|---|---|---|
| US11898896B2 (family US11448545B1, US11788878B2) | Acar Altinsel, Penguin Magic, 2022 | Name the card at which a spectator cut | Scale about 3.5 x 2.5 x 0.7 in hidden in a tuck box on 1 to 1.5 mm legs; microcontroller sends a weight only after two matching samples; "protected" Bluetooth to a phone, which converts weight change to card count and looks up a stored stack |
| US11941475B2 | Nathan Buzza, 2021 | Performer covertly reads any electronic prop | Pocket "Notifier" hub: several radios, RFID/NFC reader, IR camera for card barcodes, magnetometer, colour LCD, vibration codes (suit as 1 to 4 pulses, long pulse = 5), "stability time" so it stays quiet while a prop is moving |
| US10632394B2 | Christopher Mitchell and Rory Adams, Nobody Knows LLC, 2018 (lapsed 2024) | A named time is found on a watch | Micro-motors drive the hands; Bluetooth from a phone whose input is disguised as a passcode screen, calculator, swipes or voice |
| US10421029B2 | Milanesi and Mezadri, 2017 (lapsed 2023) | "Telekinesis": nuts unscrew, rings move | Finger ring with vibration motor, reversible driver, lithium cell, charge board; stone held by four neodymium magnets |
| WO2024129149A1 | Yigal Mesika, 2022 (ceased) | Feather rises to a wand | Motor and thread spool inside a hollow wand, wax tip, button or tilt switch, optional microcontroller "dance" patterns |
| US20240416255A1, US10183780B2 | Yigal Mesika | Thread and elastic-loop accessories | Retractable keychain spool; ridged container for elastic bands (listing only) |
| US11288910B1 | G. de Azevedo Silveira, 2021 (lapsed 2026) | Bingo cage "randomly" selects the forced ball | No electronics: 59 printed plain spheres plus one with a magnet, and a hidden-magnet trap in a printed cage painted to look like steel; the performer checks the trap when it is upside down |
| US12691388B2 | Jeffrey Prace, 2024 | Tossed tabs eliminate themselves until two forced symbols remain | Two perforated cards glued so that only the force tabs lack an opaque face |
| US20180154245A1 | Ondrej Psenicka, 2016 (abandoned) | Read a whole deck from its edge | Back design carries binary value and suit marks near the long edges, readable when the deck is bevelled; a reversed card shows on the opposite edge |
| WO2025093524A1 | Christian Campanella, 2023 | Find a signed blank card by touch | Chiral card outline: short edges slanted by at most 0.5 to 0.7 mm (89.3 to 89.5 degrees) with 0.7 mm recesses, so the stripper effect survives turning the card end for end |
| US10960321B1, US11904255B1 | Kranzo; Nanda, Penguin Magic, 2020 and 2023 | Half-ball and coin transformations | Half sphere with a coin on the flat face and embedded magnet |
| US11850534B1, US12004599B1, US12251647B1, US11752445B1 | Penguin Magic, 2023 to 2024 | Levitation kit; self-tying shoelaces; coin in bottle cap; hole-pattern cards | Two look-alike objects of different weight; magnet-tipped laces; grooved cap; aligned holes (listing only) |
| US10492583B1 | Anthony Potter, 2018 | Stored items look half vanished | Mirror on the symmetry plane of a rack, deliberately asymmetric top frame, tilted base |
| US11794125B2, US20230285872A1 | Joya Lyons, 2020 and 2022 | Handheld vanish | Rotating floor drops the object into a pouch; sliding holder (listing only) |
| US9017177B1 | David Copperfield, 2014 (lapsed) | Souvenir photo in which a cut-out figure lifts the guest | Concealed foot platform through the wall; cut-out mounted at 90 degrees for a rotated photograph |
| US9586158B2, US10398993B1 | William Mark Forti, 2015 and 2017 | Toy "telekinesis" wand, floating phantom | Near-invisible tether; removable hidden support (listing only) |
| DE202021001549U1 | Alfred Rutz, 2021 | Vanishing smartphone | Lockable fabric joint and bar for a phone dummy (listing only) |

**Theme-park and attraction illusions**

| Patent | Who, priority | Effect | Mechanism |
|---|---|---|---|
| US20210291071A1 / EP4121185B1 | Brister, Universal, 2020 | A guest looking in a mirror watches themselves fade away | Second room built as a mirror image behind the wall; a pane with mirrored, graded (alternating mirror and clear strips, or frosted) and clear zones slides on linear actuators in 1 to 120 s; no lighting change needed |
| US20250010220A1 | Krauthamer and others, Universal, 2023 | A guest's reflection vanishes while the room behind stays | Two mirrors with a disguised seam rotate by about 10 degrees at 10 to 15 ft or 25 degrees at 1 to 5 ft; props on the opposite wall shift to match; sensors track the guest's position and sightline, and **blink detection times the move** |
| US11090574B2 | Jeromin, Krauthamer, Hertzler, Universal, 2019 | A battery-less plush toy walks and waves on a table | Addressable electromagnet array under the surface sets polarity and strength per node; magnets in limbs; Hall sensors or pressure plates close the loop; RFID identifies the figure |
| US12061351B2 | Yeh, Rodgers, Cossairt, Universal, 2020 | A sword glows only for its "chosen" owner | Prop has no battery; a tracked 750 to 1200 nm beam aimed at a retroreflective marker powers a photovoltaic harvester; effect differs by user identity |
| US12505557B2 | Freedman and others, Universal, 2022 | Gestures with a bare hand cast "spells" | Invisible UV powder or liquid stamped on the hand, or delivered from a sanitiser dispenser or lap bar; UV camera tracks the mark and filters out smudges |
| US12100292B2 | Kawash, Universal, 2013 priority | Wand gestures trigger shop-window effects | Retroreflective tip, IR illumination, camera path recognition |
| US11836868B2 | Krauthamer, Universal, 2020 | Ghost flame sits in a real lantern and casts matching shadows | Pepper's ghost with cameras tracking props; controller correlates projector, lighting and reflector tilt |
| US20250196019A1 | Garnier and Krauthamer, Universal, 2023 | A glass fills by itself while a ghost bartender pours | Bottom-fill valve opened magnetically by the base, Hall sensors, flow meter; display behind a semi-reflective bar mirror timed to fill level |
| WO2025250288A1 | Eck, Universal, 2024 | A huge object plunges toward riders | Real object free-falls in a hidden shaft and is seen in a 45 degree reflector; eddy-current brakes |
| US12539470B2 | teamLab, 2021 | Hanging or rising water drops | Light pulsed onto intermittent droplets (listing only) |
| US9843744B2 | Ackley, Smoot, Ayala, Disney, 2015 | Light beams shoot from audience members' badges; a drone "fires" at a toy saber | IR flood plus retroreflectors; IR camera boresighted with a visible projector through a hot mirror; haze makes the beam visible, and viewers cannot tell which end emits it |
| US10065127B1 | Honeck, Smoot, Smithwick and others, Disney, 2017 | A rigid glowing blade extends from a hilt in under a second | Two semi-cylindrical diffuser tapes wound flat on motorised spools form a tube as they exit; a flexible LED strip on a third spool runs up the centre |
| US10627079B2 | Joseph, Disney, 2016 | Mid-air "laser blast" | Light element moved along a support rod (listing only) |
| US11099403B2, US10739613B2 | Smithwick; Joseph, Disney, 2016 to 2018 | Mirror display without the viewer's reflection; floating images | Half-mirror and retroreflector optics (listing only) |
| US12695400B2 | Kauffmann and Banfield, Google, 2020 | A toy wand bobs in its stand to signal events | Solenoid cradle modulates current to hold, release or wobble a magnet in the wand; BLE triggers |
| US20220371875A1 | The Cauldron London, 2019 | Wand pours drinks | Wand reads RFID/NFC tags to trigger preset behaviours (listing only) |

Also in the class and best left alone: gas mixtures for voice change including sulphur
hexafluoride (CN107349607A and siblings) and a flammable bubble tube (CN108837539A). Both are
inhalation or fire hazards.

Reading across the table: the magic-industry filings protect a product shape (ring, watch, scale).
The attraction filings protect system ideas: measure the spectator, then move the method to suit.
Those ideas are public, disclosed in detail, and aimed at rooms rather than tables.

### 2.8 Maker and crowdfunding crossovers; escape-room technology

**Hidden-magnet motion.** Self-moving chessboards (Square Off, later Phantom), sand-drawing tables
(Sisyphus) and maglev lamps and planters (Flyte, Lyfe) put an XY magnet gantry or a levitation
coil under a wooden surface and sell the result as decor **(all unverified, from memory;
Kickstarter and Wikipedia pages were blocked or missing)**. Animation and levitation of a passive
object over a tabletop is therefore a solved consumer problem, including noise reduction in the
later boards. The effect is public knowledge, which helps a magician only if the object and
surface are things nobody associates with those products.

**Ambiguous and impossible objects (Kokichi Sugihara, Meiji University).** A series of Best
Illusion of the Year winners: "Impossible Motion: Magnet Slopes" (first, 2010), "Ambiguous Garage
Roof" (second, 2015), "Ambiguous Cylinder" (second, 2016), "Triply Ambiguous Object" (first,
2018), "3D Schroeder Staircase" (first, 2020). The mathematics came from his 1986 work on machine
interpretation of line drawings: a drawing of an impossible object usually has a real, unexpected
solid that projects to it from one viewpoint. Printable copies circulate widely **(unverified)**.
- Reference: https://en.wikipedia.org/wiki/Kokichi_Sugihara
- Relevance: physical anomaly, transformation. Strictly viewpoint-locked and one-eyed (camera or a
  viewer about a metre away), which is why it lives on video.

**Escape rooms.** Over 50,000 rooms worldwide by late 2019, and a move from padlocks to
"automation technology". The open-source side is well organised: Playful Technology (UK, 97
repositories) publishes Node-REDscape (162 stars), a Node-RED layer for monitoring, solving and
resetting props built on Arduino, ESP32, ESP8266, Teensy or Raspberry Pi over Ethernet, Wi-Fi or
serial with DMX, MIDI and Hue hooks, plus Arduino libraries for PN5180 ISO15693 readers (56 stars)
and the R200 long-range UHF RFID module (138 stars).
- References: https://en.wikipedia.org/wiki/Escape_room ; https://github.com/playfultechnology ;
  https://github.com/playfultechnology/node-redscape
- Accessibility: all hobbyist. Typical parts are 12 V maglocks, reed and Hall switches, MFRC522
  readers, relays and MP3 modules at a few dollars each **(prices unverified)**.
- Relevance: these builders solve the magician's problems daily (sensors behind wood, props that
  must survive rough handling by the public, silent latches, remote reset, operator dashboards),
  with one difference: their players expect technology, so nothing has to be denied.
- Dealer cross-reference for agent 2: RFID card readers such as Wings Magic's "Bat System",
  PITATA's accelerometer props and Electricks' e-paper "Teleport" ($499 at 52Kards) are the
  commercial equivalents.
  https://vanishingincmagic.com/stage-and-parlor-magic/the-bat-system ;
  https://shop.52kards.com/products/teleport-by-electricks

---

## 3. Effect concepts: the strongest existing crossovers and the step nobody has taken

Costs are rough parts estimates, late 2026, unverified against supplier pages.

**1. From Universal's blink-timed mirror vanish to a blink-timed close-up change.**
*Existing:* US20250010220A1 moves mirrors while a camera waits for the guest to blink.
*Next step:* a small IR camera in a card box, pen pot or the performer's glasses frame watches one
spectator's eyes; on blink or saccade onset it fires a fast mechanical change in a prop the
spectator is looking at (a flap under a card, a shutter over a coin, a colour panel).
*Audience view:* "I was staring straight at it and it changed. I never looked away."
*Method sketch:* ESP32-S3 camera or OpenMV board at 60 to 120 frames per second with IR LEDs;
eyelid-closure detector; solenoid or voice-coil flap completing in under 60 ms inside a blink of
roughly 100 to 150 ms.
*BOM and cost:* camera board $25 to $70, actuator and driver $10, battery, printed housing; under
$120.
*Difficulty:* high (latency budget, one eye tracked reliably at 0.5 to 1 m, silent actuator).
*Risks:* works on one spectator at a time, and others see the move, so it needs a one-on-one frame
or a prop only the helper can see into; glasses and lighting.
*Novelty:* high. I found nothing like it outside the attraction patent. Related to psychology
(agent 4).

**2. From the electromagnet-array plush to a "haunted" close-up surface.**
*Existing:* US11090574B2; consumer boards with moving magnets.
*Next step:* a thin coil-array PCB under a leather close-up pad, a book cover or a bar mat moves
small passive objects with closed-loop Hall sensing: a finger ring crawls toward its owner, a
bottle cap turns over, a matchbox shuffles to a named position.
*Method sketch:* 8 x 8 planar coils on a four-layer board with MOSFET drivers; target objects need
a small magnet or steel insert, so pair it with a switch of a borrowed object for a prepared
duplicate, or use objects that are steel anyway (caps, paper clips, keys, some coins).
*BOM and cost:* PCB $30 to $60 assembled, drivers and microcontroller $15, 2S battery $15.
*Difficulty:* medium to high (heat, force falls off quickly with pad thickness, coil whine).
*Risks:* "magnets" is the first lay theory, so the convincer has to cancel it: let a spectator
slide their own compass or steel key over the pad while the coils are off. Safety: keep away from
pacemakers and magnetic-stripe cards.
*Novelty:* medium. The parts exist in products; a portable, examinable close-up version does not
seem to.

**3. From the invisible UV hand stamp to a live-applied invisible fiducial.**
*Existing:* US12505557B2 marks guests with UV-fluorescent powder from an innocent dispenser.
*Next step:* the spectator marks their own object. The pen they sign with also lays down an
IR-absorbing or UV-fluorescent trace, or the performer's fingertip transfers a dab. A filtered
camera then finds that one card in a shuffled, spread or boxed deck by its edge, or follows that
coin among five identical ones under cups.
*Audience view:* "I signed it, shuffled it myself, and he found it without touching the deck."
*Method sketch:* IR-pass or UV camera hidden in a phone case or lamp; fluorescent or IR ink;
simple blob detection; result by vibration.
*BOM and cost:* camera module and filter $20 to $40, UV-A or IR LEDs $5, ink $10, microcontroller
$10.
*Difficulty:* medium.
*Risks:* ink visibility under venue lighting; UV-A LEDs aimed toward eyes (keep power low,
indirect). Marked-deck reading is agent 2's territory; marking a borrowed or just-signed object at
the moment of use is the new part.
*Novelty:* medium to high.

**4. From beam-powered swords to sealed props with nothing inside to find.**
*Existing:* US12061351B2 powers a battery-less prop from a tracked near-infrared beam.
*Next step:* drop the laser (eye hazard at useful power) and harvest from NFC or Qi-style
induction instead. A solid resin die, chess piece or ring box has no battery, no port, no switch
and nothing that rattles. It wakes only on the performer's pad or near a phone, and then reports
its orientation, lights a faint internal glow or shifts an e-paper face.
*BOM and cost:* NFC energy-harvesting tag chip with I2C $3 to $6, accelerometer $2, small flex
PCB $20, casting resin; about $40 a unit.
*Difficulty:* medium (antenna tuning in a small volume, cast-in electronics).
*Risks:* power is a few tens of milliwatts and range a few centimetres; e-paper needs a believable
reason to be on the object.
*Novelty:* medium. NFC props exist at the dealers; battery-less sealed sensing objects made to be
examined seem rare.

**5. From the tuck-box scale to weighing the whole table.**
*Existing:* Penguin's patent weighs a deck to count cards cut.
*Next step:* four load cells in the feet of a side table, tray or drinks coaster give total weight
and centre of pressure. The performer, back turned, knows which of several objects was lifted,
where a coin was put down, which hand left the table holding something and how many cards were
taken.
*Method sketch:* four 1 kg cells and HX711 amplifiers, ESP32, BLE advertisement to a watch.
Centre-of-pressure maths locates an event to about a centimetre; weight resolution near 0.1 g
separates most coin denominations.
*BOM and cost:* $25 to $40 plus the furniture.
*Difficulty:* low to medium.
*Risks:* drift, people leaning on the table, air conditioning; needs a settling filter like the
patent's "two matching readings".
*Novelty:* medium. The sensor is in the furniture, so every object in play is ordinary and can be
borrowed. That answers the "rigged box" reaction in section 2.2.

**6. From the Egyptian coin box to sensing through borrowed props.**
*Existing:* Stanley's capacitive plates in a custom box.
*Next step:* put an inductive sensing array (inductance-to-digital converter chips with printed
spiral coils) under a close-up pad. It reads metal through cups, cards and hands: which borrowed
cup covers the coin, heads or tails for bimetallic coins, the denomination, whether a ring is on a
finger passing overhead.
*BOM and cost:* converter chips $5 to $8 each, coil PCB $20, microcontroller; about $50.
*Difficulty:* medium.
*Risks:* metal table frames, calibration per venue. Agents covering sensing may detail this.
*Novelty:* medium.

**7. From the genetically designed jigsaw to machine-designed solid vanishes.**
*Existing:* Williams and McOwan optimised a flat concealed-distribution puzzle against measured
perception thresholds.
*Next step:* run the same loop on three-dimensional printable objects and let an LLM write the
parametric CAD: a block puzzle that packs into its tray with one piece left over, a chain with one
link too many after re-linking, a nest of boxes whose total changes. Add the logic models of
section 2.6 as constraints and the published length and counting thresholds as the fitness
function.
*BOM and cost:* software plus filament; a few dollars per candidate.
*Difficulty:* medium (the search is easy; judging which outputs are deceptive still takes people).
*Risks:* the 2014 result needed a story for anyone to notice a vanish at all.
*Novelty:* medium to high for the solid versions; I found no follow-up in ten years.

**8. From Sugihara's ambiguous cylinder to a two-witness disagreement.**
*Existing:* an object that is round from one viewpoint and square from another, shown with a
mirror on video.
*Next step:* optimise the shape for two specific seated viewpoints at 60 to 80 cm instead of
object-and-mirror, so two spectators handed the "same view" of one object on a stand sincerely
disagree about its shape, then swap seats.
*Method sketch:* Sugihara's construction solved for two eye positions; a printed stand that fixes
orientation; a peephole card or "look through the ring" business to enforce one-eyed viewing.
*BOM and cost:* under $5.
*Difficulty:* low to medium.
*Risks:* binocular viewing breaks it at close range; it is an optical curiosity more than a
mystery, so it works best as an opener or a prop inside a larger routine.
*Novelty:* low to medium.

**9. From Arduino Psychic to sealed objects that agree with no channel at all.**
*Existing:* Wiguna's two devices communicate through a coded sequence the audience relays.
*Next step:* two sealed objects that share only time. Each holds a temperature-compensated clock
and the same seeded pseudo-random generator and shows a symbol on a small e-paper window. Sealed in
separate foil-lined boxes, in different rooms, phones collected, they always match.
*Method sketch:* a real-time clock drifting about a minute a year; the display changes every N
seconds; a third copy of the algorithm on the performer's watch gives a prediction.
*BOM and cost:* clock module $4, e-paper $8, microcontroller $3, coin cell; about $25 each.
*Difficulty:* low.
*Risks:* "they're synchronised clocks" is guessable by engineers, so let spectators choose when to
look, or key the output to something they supply. Displays have the screen problem; flip-dot or
mechanical indicators would be better.
*Novelty:* medium.

**10. From Mesika's motor-spool wand to closed-loop thread.**
*Existing:* a motor and spool in a wand, open-loop button control.
*Next step:* add tension sensing (motor current or a strain gauge on the thread guide) and an IMU
in the performer's anchor so the reel pays out and takes in automatically as the hands move. The
floating object holds position in space instead of bobbing with the performer's hands, and the
thread never goes slack or snaps.
*BOM and cost:* coreless gearmotor $8, driver $3, IMU $3, microcontroller, 40 mAh cell; under $30.
*Difficulty:* medium (control tuning at gram-level tension).
*Risks:* motor noise at close range; thread visibility is unchanged. Dealer reels are agent 2's
subject; I saw no closed-loop version in patents.
*Novelty:* medium.

**11. From Disney's tape-spring blade to rigid productions from the pocket.**
*Existing:* US10065127B1 forms a one-metre rigid tube in under a second from two flat tapes on
spools.
*Next step:* the same paired tape-spring mast, unpowered or spring-driven, as an appearing staff,
tripod leg or two-metre pole produced from a hand-sized housing, strong enough to lean on.
*BOM and cost:* two steel measuring-tape blades, printed former and spools, constant-force
spring; under $30.
*Difficulty:* medium.
*Risks:* pinch and whip hazards from spring steel; retraction is slower than deployment; the
appearing cane already owns the light-duty version of this effect.
*Novelty:* low to medium.

**12. From Tempest's scripted drones to objects that respond without sensing.**
*Existing:* 24 drones that appeared to obey gestures while flying fixed routes.
*Next step:* use the same economy at table scale. A pre-timed sequence in a self-moving object
(the pad in concept 2, a rolling ball with an internal pendulum) cued by a silent vibration timing
track lets the performer "command" it. This costs nothing in sensing and fails less often than
gesture recognition.
*BOM and cost:* adds a $5 vibration motor and a script to any animated prop.
*Difficulty:* low. *Risks:* rehearsal burden; spectators cannot be given control. *Novelty:* low;
the value is that it removes hardware.

---

## 4. Dead ends and overhyped items

- **DIY Pepper's ghost and "hologram" pyramids or fans.** Everyone has seen them; they need
  controlled darkness and a fixed sightline; they read as a display. The attraction patents show
  how much sensing and lighting control it takes to make the effect hold even in a built room.
- **Tablet and phone magic as a genre.** Proven on television and in corporate work, but the
  device absorbs the credit. Consistent with the brief's view.
- **Drones indoors near an audience.** Loud and hazardous, and the best-known piece was scripted.
- **Robot magicians.** The robot is the attraction and there is no hidden method to speak of.
- **"AI designs magic" as marketed.** The peer-reviewed systems produced incremental variants of
  two mathematical tricks and their authors say humans did the creative work. The 2026 benchmark
  suggests models still cannot reliably explain a trick, let alone invent one unaided.
- **Sensor-in-a-custom-box builds.** Sound engineering, weak effect, by the builder's own report.
  The custom object is the tell.
- **Raw FDM prints handed out as props.** Layer lines, low weight and the wrong sound identify
  them at once. Fine for hidden parts and jigs.
- **Maglev and self-moving chess as effects.** These are catalogue products; as visible phenomena
  they are recognised.
- **Viewpoint-locked anamorphic objects** for a live group: only one seat sees the effect.
- **Patent-office "disappearance systems"** from individuals (for example US20200195898A1) and
  novelty filings that restate Pepper's ghost or a mirror box.
- **Near-infrared power beaming at hobby level.** Useful power means a hazardous laser; induction
  achieves the same end safely.

## 5. Open leads

- **Direct statistics from Printables, MakerWorld, Thingiverse, Cults3D and Thangs** (all blocked
  here): the true top ten by downloads, and whether MakerWorld's newer multi-colour prints have
  raised finish quality.
- **ACM Digital Library sweep** (CHI, UIST, TEI, DIS, 2015 to 2026) for "magic", "conjuring",
  "illusion" plus "fabrication". I could not run it. My statement that no fabrication paper builds
  conjuring apparatus is provisional.
- **The Krauthamer, Yeh, Cossairt, Garnier and Jeromin patent families at Universal**, and
  Smoot, Smithwick, Joseph and Haseltine at Disney. I read about fifteen of more than 200. The
  remaining results in both assignee queries (pages past the first 40) are unread.
- **Chinese, Korean and Japanese utility models** in A63J 21/00, which the English filter hid;
  Tenyo's filings in particular.
- **Jamie Harrison and Chris Fisher interviews**, and trade coverage (Lighting & Sound America,
  TPi) of the Tony-recognised effects, for whatever has been said publicly about approach.
- **Disney Research papers** relevant to props: projector-based face augmentation, printed
  optics, electrostatic haptics **(titles unverified, from memory)**.
- **Performers I could not source**: Jamie Allan, Tom London, Kevin Li, Moulla, Xavier Mortimer;
  Marco Tempest's own technical talks and any software he released.
- **Illusioneering (QMUL)**, McOwan's outreach project mixing science demonstrations and magic:
  www.illusioneering.org did not resolve from this session and would need allowing in the network
  settings.
- **The Jerx** on unannounced, non-presentational use of electronic props, cited by Stanley; this
  bears directly on the "rigged" problem and belongs with agent 4.
- **An open "magic bus"**: Buzza's Notifier patent and Node-REDscape both exist because every prop
  speaks its own protocol. An open BLE-advertisement format plus a Bangle.js receiver app would
  let hobby props interoperate. I found no such project.
- **Rehearsal critic from pose tracking**: repackaging the 2019 DeepLabCut "artificial spectator"
  as a tool that flags the frames where a sleight is detectable.

## 6. Sources

Academic
- https://www.frontiersin.org/articles/10.3389/fpsyg.2014.01283/full - Williams and McOwan 2014, "Magic in the machine"
- https://pmc.ncbi.nlm.nih.gov/articles/PMC4233310 - PMC copy of the same paper
- https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2016.00855/full - Williams and McOwan 2016, "Manufacturing Magic and Computational Creativity"
- https://qmro.qmul.ac.uk/xmlui/handle/123456789/12788?show=full - QMUL repository record for the 2014 paper
- https://www.sciencedaily.com/releases/2014/11/141116211014.htm - press coverage, names the Phoney app and quotes McOwan
- https://www.frontiersin.org/articles/10.3389/fpsyg.2016.00748/full - Smith, Dignum, Sonenberg 2016, logic of impossibility
- https://arxiv.org/abs/1908.07446 - Zaghi-Lara et al. 2019, DeepLabCut as artificial spectator
- https://arxiv.org/abs/2610.38103 - Wen et al. 2026, "The Prestige" video benchmark
- https://arxiv.org/search/?query=%22magic+trick%22&searchtype=all - arXiv listing (2401.14516, 2402.13802, 2308.02684, 2508.18277, 2409.01296, 2604.13799)
- https://arxiv.org/search/?query=magician&searchtype=abstract - arXiv listing (1809.04072, 1509.06232, math/0110143, 2609.27416)
- https://www.asktog.com/papers/magic.html - Tognazzini, INTERCHI '93
- https://en.wikipedia.org/wiki/Kokichi_Sugihara - Sugihara's illusions and contest results

Makers and DIY
- https://all3dp.com/2/3d-printed-magic-tricks-3d-models/ - roundup of ten printed tricks with download counts
- https://www.thingiverse.com/thing:24719 - Coin Piercing (page blocked; count via All3DP)
- https://www.thingiverse.com/thing:3157749 - Picture Frame money printer (via All3DP)
- https://www.thingiverse.com/thing:1764501 - Disappearing Coin (via All3DP)
- https://makerworld.com/en/models/251925 - magic coin box (seen in search results; page blocked)
- https://hackaday.com/2022/09/23/for-the-esps-next-esp-trick/ - wireless gyro die
- https://hackaday.com/tag/magic-trick/ - Hackaday tag page, one post
- https://hackaday.com/2023/08/07/the-egyptian-coin-box-trick - Hackaday summary of the coin box
- https://incoherency.co.uk/blog/stories/egyptian-coin-box.html - James Stanley's build log
- https://hackaday.com/2020/11/24/bet-you-didnt-know-arduinos-are-psychic/ - Arduino Psychic
- https://www.instructables.com/Arduino-Psychic/ - maker's write-up (title only retrievable)
- https://www.digikey.com/en/maker/projects/mystery-box-the-freefall-deck/64b85f9fcdad46399151e5f98493db29 - Adafruit free-fall deck
- https://www.hackster.io/news/the-microcontroller-powered-matt-puts-magic-at-the-tip-of-your-thumb-8007c7829e12 - MATT+ thumb-tip controller (seen in search results; blocked)
- https://hackster.io/news/cheat-your-friends-with-this-electronic-trick-die-0c8bef4291af - electronic trick die (seen in search results; blocked)
- https://hackaday.io/project/164418-arduino-magic-trick/ - Arduino card trick (seen in search results)
- https://github.com/topics/magic-trick - GitHub topic, four software repositories
- https://github.com/playfultechnology - escape-room electronics organisation
- https://github.com/playfultechnology/node-redscape - Node-REDscape
- https://makezine.com/2013/02/18/making-magic-with-arduino - Mario the Maker Magician profile
- https://www.mariothemagician.com/ - performer site
- https://news.sparkfun.com/2482 - "Sleight of Servo" (seen in search results; blocked)
- https://en.wikipedia.org/wiki/Escape_room - history and room counts

Performers, theatre, parks
- https://en.wikipedia.org/wiki/Marco_Tempest
- https://www.media.mit.edu/articles/what-magic-can-teach-us-about-the-future-of-technology-according-to-an-mit-magician/ - how the drone piece worked
- https://research.rhizomatiks.com/en/works/marco_tempest_magic.html - 24 Drone Flight credits
- https://rhizomatiks.com/en/work/24-drone-flight - project page
- https://www.vice.com/en/article/cyber-illusionist-drone-performance/ - press coverage
- https://www.ted.com/talks/marco_tempest_and_for_my_next_trick_a_robot - TED2014 talk with EDI
- https://en.wikipedia.org/wiki/Simon_Pierro
- https://www.keelanleyser.com/ - "Tech Magic", "AI Magic", HACKED
- https://en.wikipedia.org/wiki/Zach_King
- https://en.wikipedia.org/wiki/Shin_Lim
- https://en.wikipedia.org/wiki/Derek_DelGaudio
- https://en.wikipedia.org/wiki/Harry_Potter_and_the_Cursed_Child
- https://en.wikipedia.org/wiki/Stranger_Things:_The_First_Shadow
- https://en.wikipedia.org/wiki/Hatbox_Ghost
- https://en.wikipedia.org/wiki/Pepper%27s_ghost
- https://la.disneyresearch.com/publication/magic-bench/ - Magic Bench, SIGGRAPH 2017
- https://www.wdwmagic.com/other/walt-disney-imagineering/gallery/04jun2026-disneys-latest-patent-drawings-reveal-a-new-kind-of-theme-park-illusion.htm - Disney deployable projection surface filing
- https://blogmickey.com/2026/08/disney-patent-reveals-new-elevation-change-illusion-for-theme-park-attractions/ - Disney forced-perspective filing
- https://vanishingincmagic.com/stage-and-parlor-magic/the-bat-system - RFID card system (dealer pointer)
- https://shop.52kards.com/products/teleport-by-electricks - e-paper prediction device, $499 (dealer pointer)

Patents (Google Patents; each at https://patents.google.com/patent/NUMBER/en)
- https://patents.google.com/?q=(A63J21%2f00)&after=priority:20140101 - class query, 109 English-language results
- US11898896B2 - Penguin Magic tuck-box scale
- US11941475B2 (US20230063812A1) - Buzza electronic peek device
- US10632394B2 - timepiece illusion device
- US10421029B2 - vibrating finger ring
- WO2024129149A1 - Mesika motorised spool wand
- US11288910B1 - magnet-trap bingo cage
- US12691388B2 - Prace forcing tabs
- US20180154245A1 - Psenicka edge-marking system
- WO2025093524A1 - Campanella chiral playing card
- US10492583B1 - Potter mirror container
- US9017177B1 - Copperfield photo illusion
- US10960321B1, US11904255B1, US11850534B1, US12004599B1, US12251647B1, US11752445B1 - Penguin Magic (listing)
- US11794125B2, US20230285872A1, US9586158B2, US10398993B1, DE202021001549U1, US20200195898A1, KR101659400B1, CN107970625A - listing only
- US20210291071A1 / EP4121185A1 - Universal vanishing illusion system
- US20250010220A1 - Universal mirror illusion with blink detection
- US11090574B2 - Universal electromagnetic animated figure
- US12061351B2 - Universal beam-powered interactive object
- US12505557B2 - Universal UV detectable marker
- US12100292B2 - Universal passive wand tracking
- US11836868B2 - Universal correlative-effect AR
- US20250196019A1 - Universal vessel-filling illusion
- WO2025250288A1 - Universal gravity-assisted show effect
- US10614271B2 - Universal RFID interactive systems
- US9843744B2 - Disney audience interaction projection
- US10065127B1 - Disney retractable illuminated blade
- US10627079B2, US11099403B2, US10739613B2 - Disney (listing)
- US12695400B2 - Google levitating wand cradle
- US12539470B2 - teamLab water droplets (listing)
- US20220371875A1 - The Cauldron wand (listing)
