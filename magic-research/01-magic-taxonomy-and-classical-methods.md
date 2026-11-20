# 01 - The structure of magic: effect taxonomies, classical method principles, and the demand side of a capability match

Scope: the textbook and historical literature of conjuring, read as a requirements document. This
report is the "demand side": what secret operations magic needs, how well classical methods deliver
them, and where they fall short. Other strands supply the technology.

**Research note.** The shared web-search budget ran out after 9 searches, so most of this was built
from direct fetches of known pages (53 pages opened) plus my own knowledge of the conjuring
literature. Convention used throughout: a claim followed by a source number in square brackets was
confirmed on a page I opened; **(unverified)** means recalled from memory and not confirmed this
session. The "weakness" columns in section 2 are largely practitioner lore that is rarely written
down on citable pages; treat them as unverified unless a source is given. All numeric tolerances in
sections 2.3 and 2.7 are my own engineering estimates, offered as design targets, not measurements.

---

## 1. Summary

- **No taxonomy of effects is canonical, and the best scholars say none can be.** Fitzkee lists 19
  [1], Sharpe six (Britannica, seen in search only), Wikipedia 10 [5], a retailer 13 [8]. Lamont
  argues effects do not slot into natural categories because one trick can be framed several ways
  [2]. Use Fitzkee's 19 as tags, not as truth.
- **The more useful split for engineers is "happening" versus "spectacle"** (Smith, Dignum and
  Sonenberg 2016 [31]): an impossible *transition* seen for an instant, versus an impossible *state*
  held up for inspection. Sleight of hand is already excellent at happenings. Classical methods are
  weakest at spectacles (floating, sustained animation, an object that stays impossible in the
  spectator's hands), and that is where technology has most to give.
- **Classical methods reduce to about twelve secret operations**: hold/release, move, swap,
  duplicate, conceal, transform, know, tell, delay, control chance or choice, erase the evidence,
  prove ordinariness. Section 2.3 writes each as a spec with numbers.
- **The most common single complaint across all physics families is non-examinability.** Shells,
  key rings, gaffed decks, flap props, magnets in coins and thread hook-ups all work, and nearly
  all must be switched out before anything is handed over. "Prove ordinariness" and "erase the
  evidence" are the two operations classical magic does worst.
- **The second most common is the environment**: light (thread, black art, Pepper's ghost), angle
  (mirrors, palms, Balducci [13]), wardrobe (pulls and topits need a jacket [48][49]), seating
  (lapping), noise ("talking" shells, snapping pulls).
- **Information methods are the cheapest place to add technology and the least visible.** "Know"
  and "tell" have been done with verbal codes that took years to learn [24], confederates, and
  peeks that require the performer to touch the billet [29]. Any sensing-plus-covert-channel system
  replaces years of skill, and the audience never sees an object that could be electronic.
- **Every historical technology transfer that worked hid the technology in the building or the
  procedure, not in the prop, and wrapped it in a non-technical story.** Robert-Houdin's magnet was
  under the floor [3]; Pepper's glass was the proscenium [9]; Psycho's "proof of isolation" (a
  clear glass cylinder) was probably the control channel itself [47].
- **Audiences suspecting the technology is not new.** Robert-Houdin's Paris audience guessed
  electromagnetism in the 1840s, and he responded by adding a rope-and-pulley phase that a magnet
  could not explain [3][4]. That is the first documented "cancel the electronic theory" move and
  the model for today.
- **Mathematical principles are a huge under-used reservoir.** Their classical weakness is
  procedure (dealing, counting, a set-up that an honest shuffle destroys). A hidden computation
  that knows the state of an honestly shuffled deck removes the procedure and makes dozens of stack
  and parity principles usable under fair conditions.
- **New technology can enable new architectures, not just better parts**: hundreds of outs instead
  of four, methods that act before the performer arrives or after they leave, gimmicks that remove
  themselves, and remote "secret assistants" (the Mechanical Turk architecture [25] with software
  in the box).

---

## 2. Catalog

### 2.1 Effect taxonomies compared

| Source | Categories | Organising idea | Use to us |
|---|---|---|---|
| **Fitzkee, *The Trick Brain*** (1944, date unverified) | 19: production, vanish, transposition, transformation, penetration, restoration, animation, anti-gravity, attraction, sympathetic reaction, invulnerability, physical anomaly, spectator failure, control, identification, thought reading, thought transmission, prediction, ESP [1] | Runs from physical feats to mental ones [1]; the book is a brainstorming system that recombines effects, objects and methods | The project's tag set. Fine-grained on mentalism, coarse on physical magic. |
| **S.H. Sharpe, *Neo-Magic*** (1932, rev. 1946 [18]) | Six: productions, disappearances, transformations, transpositions, natural science defied (e.g. levitation), mental phenomena (list per Britannica snippet, partly confirmed; first four confirmed in [31]) | "Magical plots"; Sharpe cares about conjuring as art, with a chapter on "Systematic Invention of Effects" and "The Legitimate Use of Apparatus" [18] | The four state-transition plots plus two "impossible state" classes. Closest to the happening/spectacle split. |
| **Tarbell Course** (1928 onward [38]) | Organised by prop and genre: coins, cards, silks, rope, mind reading, illusions, apparatus [38] | Pedagogical | Shows how hobbyists actually meet magic: by object, not by effect. |
| **Lamont and Wiseman, *Magic in Theory*** (1999) | Nine: appearance, vanish, transposition, transformation, penetration, restoration, extraordinary feats, telekinesis, ESP (list unverified; pages 7-27 confirmed as the effects chapter [2]) | Written for psychologists; also splits misdirection into physical (attention) and psychological (suspicion) [7] | Clean modern list; treats prediction as one presentation of ESP [2]. |
| **Wikipedia "Magic (illusion)"** | 10: production, vanish, transformation, restoration, transposition, teleportation, escape, levitation, penetration, prediction [5] | Folk consensus | Adds escape; notes Hollingworth and Tom Stone reject fixed categories [5]. |
| **52Kards blog** | 13: vanish, production, penetration, transformation, transposition, prediction, restoration, telekinesis, hypnosis, levitation, mind reading, metal bending, teleportation [8] | Retail navigation | What a new hobbyist is told. |
| **Ortiz, *Strong Magic* / *Designing Miracles*** (1994 / 2006, unverified) | Not a list of effects. Classifies what makes an effect strong and where the method sits relative to the effect: temporal, spatial and conceptual distance; the "critical interval" during which the audience believes the magic must have happened (unverified summary) | Causality | The best design language for technology methods: put the work outside the critical interval. |
| **Tamariz, *The Magic Way*** (1988) | Not a list of effects. The "method of false solutions": lead the spectator down each plausible explanation and close it, so nothing is left [search result: Hermetic Press sample; magicref] | Spectator's reasoning | Directly applicable to "it's electronic": that theory is one more false path that must be closed. |
| **Kuhn, Caffaratti, Teszka, Rensink (2014)** | Misdirection by mechanism: perception (attentional focus, timing, resources; non-attentional masking, grouping), memory (forgetting, misremembering), reasoning (ruse, feigned actions, wrong assumptions: dual reality, multiple outs, effort, pre-show) [7] | Cognitive mechanism | A checklist of the psychological "parts bin". Agent 4 owns this. |
| **Rensink and Kuhn (2015)** | Effect-centred versus method-centred inventories; calls existing lists "folk taxonomies" [6] | Research programme | Justifies building a *method-centred* inventory, which is what section 2.2 is. |
| **Smith, Dignum, Sonenberg (2016)** | Happenings versus spectacles; evidence relationships (similarity, perceptual equivalence, structural equivalence, congruence); apparatus features "substitutable elements" and "stable occlusion" [31] | Formal logic of belief | "Substitutable elements" = duplicates; "stable occlusion" = cover. Technology can attack both. |
| **Lamont (2015)** | Argues a complete taxonomy is infeasible: effects overlap, methods are endless, boundaries are arbitrary [2] | Critique | Keeps us honest. |

**Working list adopted.** Fitzkee's 19 as tags, grouped into six families, plus three axes that
matter more than the class for choosing a method:

1. *Existence*: production, vanish. 2. *Location*: transposition, penetration.
3. *Identity and integrity*: transformation, restoration. 4. *Physics defied*: animation,
anti-gravity, attraction, invulnerability, physical anomaly, sympathetic reaction.
5. *Mind over matter and people*: control, spectator failure.
6. *Information*: identification, thought reading, thought transmission, prediction, ESP.

Axes: (a) **happening or spectacle** [31]; (b) **who holds the object at the moment of magic**
(performer, table, spectator's closed hand, sealed and isolated); (c) **examinable before, after,
both, or never**. An effect that is a spectacle, in the spectator's hand, examinable both sides, is
the hardest classical target and the best technology target.

### 2.2 Classical method principles by physics

Each row: principle; representative classics; weaknesses performers complain about; what kind of
technology would remove the weakness (pointers only; other agents own the technologies).

#### Optical

| Principle | Classics | Weaknesses | Technology that would remove it |
|---|---|---|---|
| **Plane mirrors (Sphinx principle: two mirrors at 90 degrees, apex to audience, reflecting side walls [11])**; Proteus cabinet; mirror box; mirror glass | Sphinx (Stodare and Tobin, 1865, unverified); head on table; square-circle-type productions | Visible mirror edge; fingerprints and dust; anything crossing the reflected zone doubles; needs identical surroundings on both sides; fixed sight lines; glass weight and fragility. Wikipedia notes mirrors are now seldom used [5]. | Thin first-surface film mirrors; edge-free laminated optics; switchable mirror/clear films; small-scale versions made to 0.1 mm by cheap laser cutting. |
| **Partial reflection (Pepper's ghost)** | Dircks/Pepper 1862 [9][45][52]; Metempsychosis; modern "hologram" concerts [9] | Requires dimmed main space and a bright hidden one; glass edge must be hidden in scenery; glass reflects far less than a mirror so the hidden figure must be intensely lit and others in matte black; actors cannot see the ghost [9]; originally needed theatre rebuilding until Pepper used the orchestra pit [45] | Bright LED sources, thin beam-splitter film, table-top scale. Mostly a level-1 use; the audience now names it. |
| **Black art (black on black under controlled light)** [11] | Black-art tables and wells; appearing/vanishing objects; "invisible" assistants | Lighting must be controlled; fails in daylight, under a phone flash, at close range; velvet shows dust and sheen | Ultra-black coatings (agent on materials); structured light that blinds cameras less than eyes. |
| **Shells and nesting** [11] | Expanded shell coin; multiplying billiard balls; shell in cups and balls; half-shell wands | "Talking" (clink), visible rim, thickness and weight difference, wear; cannot be handed out; expensive precision work | Precision CNC/EDM/electroforming at hobby prices; shells that lock (magnetic or bistable) so the nested unit passes handling; matched acoustic ring. |
| **Camouflage and matching surfaces** (flaps matching a background, pocketed close-up mats) | Card frames, slates with flaps, flap cards | Seam lines; texture or gloss mismatch under raking light; flap noise | Colour-accurate on-demand printing; laser-cut seams hidden in printed pattern lines. |
| **Selective light: polarisers, one-way film, lenticular, UV/IR** | Polarised "solid" walls; luminous readers and infrared marked cards read by camera [33] | Needs special glasses or a camera; riffle test and solvent sheen expose marks [33]; UV lamps are conspicuous | Cheap NIR cameras and filters; inks visible only in narrow bands; edge codes read by a hidden camera. |
| **Perceptual geometry** (angle-only illusions) | Balducci and King levitations: work from one side, last seconds, a few inches [13]; depth illusion in card work | One viewing angle; fails on video from a second phone | Mostly not a technology problem; see agent 4. |

#### Mechanical (including the hand as a mechanism)

| Principle | Classics | Weaknesses | Technology that would remove it |
|---|---|---|---|
| **Invisible thread, loops, reels** [11] | Floating bill, floating ring, haunted deck, rising card, Hummer card, floating cigarette [13], dancing handkerchief | Breaks (carries about a banknote of 1 g up to a light ring; unverified); visible in bright or back light and against pale clothing; tangles and static; hook-up and wax anchoring take time; wind; nothing can be handed out mid-effect; hoop "proofs" are choreography | Stronger, finer fibres; motorised micro-reels with tension control; non-contact force (magnetic, electrostatic, airflow, acoustic) at close range; anchors that attach and release without wax. |
| **Rigid hidden support** | Zombie ball (Karson, 1940s, unverified): gimmick behind a cloth; Asrah wire form; Kellar's S-shaped bar that lets a hoop pass [13]; computer-controlled wire rigs [13] | Cloth cover is mandatory; one-sided; stage machinery | Thin high-stiffness supports (carbon, UHMWPE); supports disguised as legitimate structure. |
| **Pulls, reels, holdouts** [11] | Vanishing bird cage (De Kolta: collapsing cage on elastic up the sleeve [48]); vanishing cigarette or silk; gamblers' holdouts | Needs jacket and sleeves; snap and rustle; big arm motion as cover; limited object size; slow reset; cage could injure a live bird [48] | Silent motorised or spring-damped retraction; short-sleeve architectures; self-resetting. |
| **Body loads and ditches** | Topit (Comden 1920s, Page 1966, Ammar 1983 [49]); servante [11]; sleeving, lapping [11][35] | Jacket required [49]; lapping needs a seat at a table; angles; the hand must still get there | A "ditch" that needs no travel (object leaves the hand by itself). |
| **Secret compartments, flaps, false bottoms, double walls** | Change bag, egg bag [11], card box, drawer box, dove pan, Lota and funnel-type double walls [51], Himber wallet | Prop looks like a magic prop; thickness; click; cannot be examined; "tin painted to look like glass" [51] | Fabrication precise enough to hide the compartment inside a recognisable retail object; latches with no moving exterior part. |
| **Springs and collapsibles** | Spring flowers [37], appearing cane, De Kolta's expanding die (200 mm to 800 mm [37]) | One-shot; reset is slow and fiddly; edges look fake up close | Bistable and deployable structures (origami, tape springs); shape-memory reset. |
| **Gravity, shifting weights, balance, gyroscopic** (all unverified, from memory) | Sand frame (sand falling between glass sheets hides or reveals a card); obedient ball that stops on a cord on command (friction in a bent channel); counterweight-driven rising cards; loaded dice; off-centre weights for "impossible" balances; spinning props that stay upright | The prop is too heavy or its balance point is wrong when handled; shot or sand can be heard shifting; needs a deliberate tilt to trigger; loaded dice are always biased and fail a float or repeated-roll test; one-shot | A small internal mass that can be moved or locked on command (so the object is fair when checked); reaction wheels and motion sensors in thin props; silent damping fills. |
| **Stage machinery: traps, lifts, hidden assistants** | Sawing (Selbit 1921; Goldin's patent mentions false feet moved by electric motors [20]); Metamorphosis/sub trunk [28]; Mechanical Turk's sliding seat and dummy clockwork [25] | Venue, crew, transport, cost | Out of hobby scope except in miniature. |
| **Gimmicked decks and gaff cards** | Svengali (Hull, 1909: short duplicate cards [40]); stripper; rough-and-smooth "invisible deck" [11]; marked decks [33] | Not examinable; riffle sound gives Svengali away; widely sold so laypeople know it [40]; roughing fluid wears; gaffs need factory print runs to match | Short-run factory-quality card printing; decks that are gaffed only when triggered. |
| **Sleight of hand** | Palms, passes, double lift, false counts and shuffles [11]; French drop, muscle pass [35] | Years of practice; angle-sensitive; "dirty" hands [11]; a spectator who "burns" the hands [11] | Not to be replaced: it is the best canceller of "it's electronic". Technology should shrink the hardest moves, not remove the performer's hands. |

#### Magnetic

| Principle | Classics | Weaknesses | Technology that would remove it |
|---|---|---|---|
| **Permanent magnets in props** | Chop cup (Wheatley, c. 1954 [17]); magnetic and shimmed coins; shimmed cards; PK ring effects; magnetic ramrod in the bullet catch [43] | Always on: the prop grabs keys, the table edge, another gimmick; steel-cored coins sound and weigh wrong; force falls off steeply so working range is centimetres; spectators now test with phones; strong magnets pinch, wipe hotel key cards and are a hazard near implanted devices | Magnets that switch with zero holding power (electropermanent, rotating-pair); field-shaped arrays; sensing the magnet instead of pulling with it. |
| **Magnet as information** | The Turk tracked chess pieces with a magnet under each piece and indicators under the board, and Kempelen invited spectators to test the cabinet with their own magnets [25] | Gimmick must be inside the object; classic reed-switch detectors (unverified) are on/off only, work at a few centimetres and cannot tell direction or which of several magnets | Multi-axis magnetometers at coin-cell power; sensing ordinary objects without a magnet. |
| **Electromagnets** | Light and Heavy Chest: magnet under the stage ramp, iron plate in the box, assistant on the switch [3] | Power, heat, size; must be built into the venue or table; batteries in 1856 filled a room [3] | Pulse-switched magnets, modern cells; portable table-top versions. |
| **Induction** | Lamp lit in the hand; induction-loop cueing (unverified history) | Coil size, alignment, heat | Off-the-shelf wireless power and NFC harvesting. |

#### Chemical and thermal

| Principle | Classics | Weaknesses | Technology that would remove it |
|---|---|---|---|
| **Nitrocellulose (flash paper, cotton, string)** | Flash productions, vanish of a billet, misdirection [11][36] | Fire; decomposes in storage and can self-ignite if impure; flash point about 4 C; postal restrictions [36]; banned in many venues | Electrically triggered, enclosed, or non-pyrotechnic flashes. **Hazard: fire.** |
| **Colour-change chemistry** | Wine and water (indicator plus acid/base, unverified); "any drink called for" with essences in glasses [51]; iodine-clock delays | Usually undrinkable or toxic; one-shot; timing drifts with temperature; smell; staining | Food-safe indicators; metered micro-dosing; encapsulated reagents. **Hazard: do not let spectators drink lab reagents.** |
| **Superabsorbent "slush powder"** | Water vanishes in a cup or newspaper | Gel is visible if the cup is inspected; residue; wrong weight | Absorbers bonded invisibly into the vessel wall. |
| **Reactive and fugitive inks** | Spirit writing, heat-revealed messages, vanishing ink | Uncontrolled timing; needs a flame or lamp; ghosting | Thermochromic/photochromic inks with embedded micro-heaters or light triggers. |
| **Metals that misbehave** | Shape-memory "self-bending" spoons that bend in warm liquid or from body heat [21]; pre-fatigued cutlery [21]; low-melting alloys (unverified) | Fixed transition temperature; wrong colour, feel and ring; gallium-type alloys stain and some classic fusible alloys contain lead or cadmium | Alloys tuned to a chosen temperature; local electrical heating; bending that happens after the object leaves the performer. |
| **Smell and smoke as convincers** | Robert-Houdin poured real ether on a hot shovel so the theatre smelled of it; the ether did nothing [14] | None; this is a model, not a weakness | Any cheap sensory "proof" that supports the false cause. |

#### Pneumatic and hydraulic

| Principle | Classics | Weaknesses | Technology that would remove it |
|---|---|---|---|
| **Finger-valved compartments (hydrostatics)** | Inexhaustible bottle: compartments with air holes under the fingers, tin painted as glass [51]; magic funnel [51]; Lota bowl (unverified) | Opaque vessel; limited volume; leaks; messy reset | Micro-valves and micro-pumps; transparent vessels with hidden channels. |
| **Air as actuator** | Psycho (1875): probably bellows forcing air up through the clear glass cylinder that "proved" isolation [47] | Tubes, hiss, a hidden operator | Silent micro-pumps; pouch actuators inside thin flat props. |
| **Suction and adhesion** | Suction-cup thumb tip [30]; "magnetised" wands and adhesion stunts (attraction class) | Marks, moisture dependence | Dry reversible adhesives. |

#### Acoustic

| Principle | Classics | Weaknesses | Technology that would remove it |
|---|---|---|---|
| **Sound as proof** | Coin clink as a "convincer" for a false transfer [7]; rings that ring when struck are preferred [19]; the Turk's clockwork noises during moves [25] | The same channel betrays gimmicks (talking shells, flap clicks, the Svengali riffle [40]) | Gimmicks tuned to sound right; sound produced where the object is supposed to be. |
| **Sound as secret channel** | Spoken codes (Zancigs [24]); spirit raps; speaking tubes (unverified) | Years to learn a code [24]; audible to anyone listening for it | Private audio or vibration channels. |

#### Electrical and electronic

| Principle | Classics | Weaknesses | Technology that would remove it |
|---|---|---|---|
| **Remote signalling** | Second-sight acts with silent electrical cueing (Heller, unverified; his Wikipedia page does not cover it [53]); Dunninger photographed with a portable wireless set on his back for duplicating mediums' tricks [39]; Popoff's earpiece, fed by his wife from prayer cards and intercepted with a scanner in 1986 [16]; "thumper" devices [11] | Earpiece visible; interceptable [16]; pulse-count codes are slow; pairing failures; a hand has to go to a pocket; batteries | Short-range encrypted links; richer haptic alphabets; receivers with no wearable part visible. |
| **Electronic sensing props** | Electronic dice, "which hand" detectors, impression pads (agent 2 owns products) | Proprietary, costly, the spectator must use the performer's object; audience default theory is "electronics" | Sensing ordinary or borrowed objects; putting the sensor in the room, not the prop. |
| **Light sources** | Lamp that lights in the hand; Blackstone's floating bulb [13] | Battery bulk | Trivial now. |

#### Mathematical and self-working

| Principle | Classics | Weaknesses | Technology that would remove it |
|---|---|---|---|
| **Stacks and memorised orders** [11] | Si Stebbins, memorised deck; Out of This World (Curry, 1942: colour-separated stack plus one covert move while the spectator does all the handling [50]) | An honest shuffle destroys the set-up; false shuffles needed; memory load | Know the order *after* a real shuffle; then the stack is virtual. |
| **Shuffle invariants** | Gilbreath principle: a riffle of a reversed packet preserves local structure [41]; faro; parity (Hummer) | Specific procedure must be followed; feels procedural | Computer search for new invariants and for the least procedural handling. |
| **Probabilistic coupling** | Kruskal count: independent starting points converge; "more than 90%" for a 52-card deck in one quoted source [34] | Fails sometimes; slow counting | Simulation to tune decks and rules toward certainty; an out when it fails. |
| **Arithmetic forces** | Book tests forcing a page and word by sums; now less used because widely known [22] | "It's just maths" | Hide the arithmetic in something that does not look like arithmetic. |

#### Psychological

| Principle | Classics | Weaknesses | Technology that would remove it |
|---|---|---|---|
| **Forces** [11][32] | Classic force, riffle force, cross-cut; equivoque ("magician's choice") | Physical forces miss sometimes; equivoque cannot be repeated for the same people because each repeat narrows the information gap [32] | Replace the force with coverage (many outs) or with knowledge (let them choose freely, then find out). |
| **Wrong-assumption structures** [7] | Dual reality, pre-show, multiple outs, instant stooge | Collapse if spectators compare notes or the show is filmed; pre-show needs access and time | See architectures, 2.4. |
| **Cold and hot reading** [42] | Readings, Q&A acts | Depends on a co-operative sitter; weak evidence in large rooms; ethical problems when presented as real [15][42] | Out of scope for building; flag ethics. |
| **Suggestion** | Wiseman and Greening: verbal suggestion alone made viewers report a key continuing to bend [21] | Works on a fraction of people | Pair a small real physical change with suggestion. |

#### Stooges and information leakage

| Principle | Classics | Weaknesses | Technology that would remove it |
|---|---|---|---|
| **Confederates and hidden operators** [11] | Mechanical Turk: a chess master inside for 84 years, exposed once in 1827 and not believed [25] | Payroll, trust, exposure | Software or a remote human as the hidden operator. |
| **Two-person codes** | Zancigs' verbal code, "Two minds with but a single thought"; Julius sold the secret to a newspaper in 1924 [24] | Years of rehearsal; the partner | One-person versions via a covert channel. |
| **Peeks and steals of written information** | Billet reading: one-ahead, switches, palmed billets [29]; dictionary peek, memorised force book, flashback books [22] | The performer must handle the billet or supply the pad or book; restricted word choice in gimmicked books [22]; magicians love catching billet readers with trap questions [29] | Sense the writing act, not the paper. |
| **Unconscious cueing** | Contact mind reading (Brown, Bishop, 1870s-80s): find a hidden pin by reading the subject's muscles [44] | Skill takes years; needs a "good" subject | Instrumented sensing of the same ideomotor signals. **Flag: anything worn by or aimed at a spectator's body.** |

### 2.3 The twelve secret operations, written as specifications

Decomposing the catalog above. Tolerances are my estimates. Reference masses: US quarter 5.7 g,
half dollar 11.3 g, playing card about 1.8 g, banknote about 1 g, finger ring 3-8 g, deck about
95 g (all approximate, unverified).

1. **Hold / release** (palms, wax, magnets, holdouts, clips).
   - Hold a 6-12 g coin against a palm-down, relaxed, open-looking hand; no visible grip from any
     angle beyond 30 cm; release in under 50 ms, under 25 dBA, with no finger movement; hand passes
     inspection afterwards.
   - Hold a 20-60 mm "final load" (lemon, 100 g) under a jacket edge or table lip for 10 minutes and
     deliver it to a hand or cup on cue in under 300 ms, silently.
   - A latch of under 8 mm cube that holds 2-5 N with zero standby power and releases on a timed or
     remote pulse with no click.
2. **Move** (thread, pulls, hidden assistants, under-table magnets).
   - A thread substitute invisible at 50 cm under 500 lux, against a pale shirt and under a phone
     flash, carrying 5 g (stretch goal 100 g), surviving 50 performances, attachable and detachable
     in under 2 s without wax.
   - Move a 2 g card or 6 g coin 20-50 cm across a table that spectators may look under, under
     30 dBA, nothing above the table.
   - Remove a 10-100 g object from the fingertips to out of sight in under 150 ms in short sleeves,
     silently, with reset under 10 s.
3. **Swap** (billet switch, deck switch, change bag, Himber wallet).
   - Swap two envelopes, billets or cards in under 0.5 s with both hands in view and under 1 mm
     added thickness; or remove the need by rewriting the contents in place.
   - Exchange a 52-card deck in under 1 s during a natural action.
4. **Duplicate** (duplicates, "substitutable elements" [31]).
   - Reproduce a spectator's signature or drawing on a second object within 10 s at pen quality.
     Classical magic cannot do this at all, which is why "sign it" is the standard proof.
   - Produce a visually exact double of a borrowed ring, key or banknote serial within 30 minutes
     of pre-show access.
5. **Conceal** (shells, black art, mirrors, flaps, thumb tip [30]).
   - Hide a 25 mm by 2 mm object in a prop under 3 mm thick or visibly transparent, surviving
     handling.
   - Concealment that works through 360 degrees, under arbitrary light, on phone video with flash.
6. **Transform** (flap cards, colour changes, chemistry, shape-memory).
   - Change the printed face or colour of a card-sized surface in under 0.3 s with no glow, no
     more than 0.1 mm over a 0.3 mm card, stable afterwards, safe to hand out.
   - Bend, soften, break or fuse an object that passed inspection a minute earlier, on cue, at
     room temperature, in the spectator's hand.
7. **Know** (peeks, marks, stacks, magnets, muscle reading).
   - Know the full order of an honestly shuffled, borrowed-looking deck within 1-2 s, at 99.5% or
     better, with no visible scan.
   - Know what was written or drawn on a 5 by 8 cm slip the performer never touches, within 5 s,
     after it is folded.
   - Know which of N hands, cups or boxes holds an ungimmicked object at 0.5-1 m.
   - Know a spoken word and have it in usable form within 1 s.
8. **Tell** (codes, thumpers, earpieces, cue cards).
   - Deliver 6 bits (one card of 52) to the performer in under 2 s with nothing visible in ear or
     hand, in a noisy room, not readable by a spectator's phone.
   - Deliver a message to exactly one spectator at 1 m that neighbours cannot perceive (the dual
     reality and instant-stooge channel).
9. **Delay** (wax, ice, slow chemistry, fuses, clockwork).
   - A self-contained trigger under 5 mm thick that acts 1 minute to 24 hours later, within 1 s of
     the set time, silent in standby, with a one-year shelf life.
10. **Control chance or choice** (forces, loaded dice, double-faced coins, equivoque).
    - A die, coin or spinner that gives a commanded outcome 99% of the time and yet is fair by
      roll, balance and float tests when not commanded.
    - Or replace control by coverage: N outs at under $0.50 each, any one retrievable in under 2 s
      without fumbling (today's pocket indexes manage this badly).
11. **Erase the evidence** (ditches, flash paper, switching back).
    - A gimmick, thread, adhesive or ink that removes itself within 5-60 s or on a trigger, at
      ambient temperature, leaving no visible or tactile residue, so the final object is honest.
12. **Prove ordinariness** (examination, signing, sealing, borrowing).
    - A gimmicked prop within 2% of the genuine weight, 0.05 mm of its dimensions, with the same
      ring, riffle sound, flex and magnetic response, and no seam visible to the eye at 15 cm.
    - Retail packaging (cellophane, tax seal, blister) opened, altered and re-closed so that it
      passes as factory sealed.

### 2.4 Method architectures

| Architecture | What it is | Classical cost or limit | What cheap technology changes |
|---|---|---|---|
| **Multiple outs** [7][11] | Several endings prepared; audience assumes one | 2 to 6 outs before pockets and memory give up | Hundreds of outs by brute-force fabrication, indexed mechanically; or one out written late. |
| **One-ahead** [11][29] | Learn item n while apparently revealing item n-1 | Needs one known item (a plant or a stolen envelope) and a final clean-up | Any covert "know" seeds the chain with no plant. |
| **Pre-show** [7] | Work done before the audience thinks the trick has begun | Needs access to spectators; fragile on video | Methods that run in the room hours earlier with no performer; personalised props made overnight. |
| **Time misdirection** [7] | Separate method and effect in time so the method is forgotten | The performer must still do the move, just earlier | "Delay" hardware does the move when nobody is near it. This is Ortiz's temporal distance made literal. |
| **Cancelling methods** (Tamariz's false solutions; Ortiz) | Repeat an effect with different methods so each disproves the theory raised by the other | Requires several complete methods for one effect | A technology method and a sleight method cancel each other unusually well: one works hands-off, the other works with borrowed objects. Robert-Houdin did exactly this with magnet and pulley [3]. |
| **Too-perfect theory** (Johnsson, 1970-71, unverified) | If conditions exclude every explanation but one, the audience lands on that one | With technology the surviving explanation is "electronics", "magnets" or "camera" | Deliberately leave a wrong, checkable explanation open and then close it; never let the prop be the only suspect. |
| **Instant stooge** | A spectator is secretly cued to play along | Risky; depends on the person | A private one-spectator channel (operation 8) makes cueing deniable and precise. Ethical limits apply. |
| **Dual reality** [7] | Volunteer and audience experience different events | Collapses when they talk afterwards | Private sensory channels; per-person printed material. |
| **Hidden operator** [25][47] | A person inside or behind the apparatus | Space, heat, exposure (the Turk's operator once had to climb out [25]) | Remote operator or software; the "automaton that is secretly a person" becomes "the ordinary object that is secretly a networked sensor". |
| **Proof-as-channel** [47][25] | The feature offered as proof of fairness carries the method: Psycho's glass cylinder; the Turk's open doors | Needs ingenuity per prop | Transparent, sealed or "isolated" presentations that are the conduit (light, air, field, sound). |
| **Sensory convincer for a false cause** [14][7] | Ether smell, coin clink, clockwork noise | None | Cheap synthetic sound, smell, heat or vibration to sell a cause that is not the real one. |

### 2.5 History of technology transfer into magic

- **Mechanical Turk (Kempelen, 1770; Maelzel to 1838; destroyed 1854)** [25]. A human hidden by a
  sliding seat and dummy machinery, with magnets under the pieces as the sensing layer. What worked:
  the display of clockwork matched what the public expected machines to be; doors were opened in a
  sequence that proved emptiness; clockwork sounds; an invitation to bring your own magnet.
- **Robert-Houdin (theatre opened 3 July 1845)** [14]. A clockmaker who built automata and used
  the new electromagnetism. Light and Heavy Chest: electromagnet under the floor, iron plate in the
  box, assistant on the switch [3]. Steinmeyer's corrections matter for our thesis: it was Paris
  repertoire from the 1840s, not built for Algeria; Parisians suspected electromagnetism and
  Robert-Houdin admitted it; he added a pulley-and-rope phase to defeat that theory; in Algiers he
  changed only the story (not "the box is heavy" but "you are weak"); the electric-shock ending is
  probably a later literary addition because an induction coil and battery were too large [3][4].
- **Pepper's ghost (Dircks 1858; Pepper, Christmas Eve 1862; patent 1863)** [9][45][52]. Dircks
  had the optics but needed theatres rebuilt; Pepper's contribution was packaging: use the existing
  orchestra pit [45]. It earned about 12,000 pounds [52]. Pepper meant to explain it and held back
  after seeing the reaction [52]. Lesson: the winning step was an integration that fitted existing
  venues, not the physics, which della Porta had described in 1589 [9].
- **Tobin's mirror illusions (Sphinx, Proteus cabinet, 1865, unverified)**. Plane mirrors at
  90 degrees [11]. Plate glass and silvering had just become cheap and large (unverified): a
  materials-cost story much like today's.
- **Maskelyne (Egyptian Hall, 1873-1905)** [12]. A watchmaker; also invented a coin-operated lock
  and a typewriter [12]. Psycho (1875) played whist on a clear glass cylinder; the method is still
  not certain, but air through the cylinder is the leading account [47]. His son Nevil worked in
  wireless telegraphy and in 1903 broke into Marconi's demonstration of "secure" wireless [23]:
  a magician as red-team engineer.
- **Hopkins, *Magic: Stage Illusions and Scientific Diversions, Including Trick Photography***
  (1897), compiled by a Scientific American editor with Henry Ridgely Evans, reviewed by the
  psychologist Jastrow in *Science* [46]. It documents the period when magic and popular science
  shared a stage. (Contents not re-read this session; archive.org link listed in sources.)
- **Electrical and radio mentalism.** Second-sight acts moved from spoken codes (Robert-Houdin's
  son, 1846 [14]; the Zancigs [24]) toward silent electrical cueing (unverified). Dunninger used
  portable wireless equipment to duplicate mediums [39]. Popoff's 39.17 MHz earpiece (frequency
  from a citation title [16]) was defeated by an off-the-shelf scanner in 1986 [16].
- **Steinmeyer, *Hiding the Elephant*** (2003/2004 [10]). The standard history of the optical era
  from Pepper to Houdini's vanishing elephant (contents unverified this session). Its thesis, as I
  recall it: the great illusions were engineering solutions to sight-line problems, guarded as
  trade secrets, and usually beaten by presentation rather than by technology.

**What made the transfers work.**

1. *Scale mismatch, not ignorance.* The public knew magnets; they did not expect one strong enough
   to pin a box, switchable, and under a floor. They knew mirrors; not mirrors used as "empty
   space". The gap was between the principle people knew and the scale or place it was used.
2. *The technology lived in the architecture.* Floor, pit, proscenium, cabinet. The object the
   audience looked at was simple.
3. *A non-technical cause was supplied*, with sensory support (ether smell [14]).
4. *The theory was cancelled when it arose* (pulley [3]; bring-your-own-magnet [25]).
5. *Integration beat invention* (Pepper's pit [45]).

**Implications for an audience that assumes electronics.** (a) Put the technology where the scale
mismatch still exists: inside a single card thickness, inside a borrowed object, in the room the
day before, in the logistics of how a prop was made. (b) Prefer technology that only *knows* or
*tells*; the visible miracle is then done by a hand with an ordinary object. (c) Any prop that
moves, lights up or changes by itself must survive "prove ordinariness" or be destroyed, eaten,
burned or given away. (d) Plan a canceller: one phase that electronics could not do (a borrowed
object, the spectator's own hands) and one that sleight could not do (hands-off, at a distance).
(e) Assume the spectator has a magnetometer, an RF scanner, a torch and a slow-motion camera in
their pocket, because they do.

### 2.6 Classic plots a hobbyist will meet

| Plot | Effect class | Usual method principle | Main weakness to attack |
|---|---|---|---|
| Ambitious Card [26] | Transposition (repeated) | Sleights (double lift), sometimes stripper or Svengali [26][40]; signature rules out duplicates | Needs a climax under test conditions (bent card, card to wallet). |
| Cups and Balls [17] | Vanish, production, penetration, transposition | Extra ball, palming, misdirection, final loads | Final-load steals from pockets; skill; clear-cup versions are rare (Latimer 2003 [17]). |
| Chop Cup [17] | Same, one cup | Magnet in cup, magnetic ball plus duplicate (unverified here) | Cup and ball not examinable together. |
| Linking Rings [19] | Penetration | Key ring with gap, permanently linked sets (unverified here) | Key ring must be hidden or switched; sound matters [19]. |
| Coins Across, Three Fly, Matrix, Spellbound [35] | Transposition, transformation | Palms, shells, extra coin | Angles; shell cannot be handed out. |
| Miser's Dream [27] | Production | Palming, droppers; bucket for sound | Stamina and angles; the bucket's sound is the proof. |
| Torn and restored card, newspaper, cut and restored rope | Restoration | Duplicate piece, switch, concealed extra | Signed pieces; a real restoration does not exist classically. |
| Floating bill or ring; haunted deck; rising card | Anti-gravity, animation | Thread, loops [11], reels | Light, breakage, no hand-out. |
| Zombie ball | Anti-gravity | Rod behind foulard (unverified) | Cloth cover; front angle only. |
| Balducci / King Rising [13] | Anti-gravity | Angle | One viewpoint, seconds, inches. |
| Book test [22] | Thought reading | Force book, gimmicked book, peek | Performer's own books; restricted words. |
| Billet work, Q&A [29] | Thought reading, ESP | One-ahead, switch, centre tear | Handling the paper. |
| Spoon and key bending [21] | Control (mind over matter), physical anomaly | Manual bend under misdirection, pre-fatigue, optical reveal, shape-memory | Bend never happens visibly, hands-off, in the spectator's grip. |
| Card to wallet, bill to lemon, ring flight | Transposition | Palm and load, pull, duplicate | The load. |
| ACAAN (any card at any number) | Prediction, identification | Stack plus force, or secret arithmetic | Fair shuffle and free number together. |
| Out of This World [50] | ESP (spectator succeeds) | Stack plus one move | Cannot start from a shuffled deck. |
| Headline or lottery prediction | Prediction | Late loading, switch, nail writer | The envelope is touched at the end. |
| Second sight / two-person telepathy [24] | Thought transmission | Code | Partner and years of practice. |
| Inexhaustible bottle / Think-a-Drink [51] | Production, transformation | Compartments, essences | Opaque vessel. |
| Sawing; Metamorphosis; levitations [20][28][13] | Restoration, transposition, anti-gravity | Hidden space, false limbs, speed, wires | Stage scale; not a hobby target except as miniatures. |
| Bullet catch [43] | Invulnerability | Switch, wax bullet, blank | **Lethal history (Chung Ling Soo, 1918). Do not build.** |
| Light and Heavy Chest [3] | Anti-gravity (weight), spectator failure | Electromagnet | Portable, examinable version. |
| Spirit bell, rapping hand, haunted key, pendulum | Animation, sympathetic reaction | Thread, magnet, ideomotor, balance | Isolation that can be believed. |

---

### 2.7 Capability primitives (demand side)

Supplementary to the original brief (written in response to a mid-project request that was later
withdrawn; kept because it restates the weakness lists above as specifications).

Form: *Wanted* (capability with numbers). *Today* (how magic does it and what is wrong).
*Primitives*. Numbers are design targets, my estimates.

1. *Wanted:* hold a 6-12 g coin to a flat, palm-down hand with no visible grip at 30 cm from any
   side, release in under 50 ms at under 25 dBA. *Today:* classic palm (months of practice, cramped
   hand, angle-bound), shimmed coin and magnet (coin is fake, clings to things). *Primitives:* hold/release, prove ordinariness.
2. *Wanted:* an 8 mm latch holding 2-5 N at zero power, silent release on a timed or remote pulse.
   *Today:* a thread pulled by hand; spring catches that click; solenoids that buzz and drain cells.
   *Primitives:* hold/release, delay.
3. *Wanted:* a line or non-contact force invisible at 50 cm under 500 lux and phone flash that
   lifts 5 g (stretch 100 g) for 50 shows. *Today:* invisible thread and loops [11]: about 1 g
   reliably, dim light, dark shirt, breakage, wax. *Primitives:* move, conceal.
4. *Wanted:* attach and detach that line to a borrowed object in under 2 s with no residue.
   *Today:* a pellet of wax; fumbling; residue on the borrowed ring. *Primitives:* hold/release, erase.
5. *Wanted:* take a 10-100 g object from fingertips to nowhere in under 150 ms, short sleeves,
   silent, reset under 10 s. *Today:* elastic pulls and reels (snap, jacket), topit (jacket [49]),
   sleeving, lapping (seated). *Primitives:* move, conceal.
6. *Wanted:* slide a card or coin 20-50 cm on a table that can be looked under, under 30 dBA.
   *Today:* thread; a magnet moved by hand or by an assistant under the table. *Primitives:* move.
7. *Wanted:* swap two flat paper items in under 0.5 s, hands in view, or rewrite one in place in
   under 5 s. *Today:* billet switch (hard sleight), flap clipboards and wallets (thick, odd).
   *Primitives:* swap, transform.
8. *Wanted:* copy a signature or sketch onto a second object in under 10 s at pen quality.
   *Today:* impossible; signing is therefore the trusted proof, and breaking it would be a new
   class of method. *Primitives:* duplicate.
9. *Wanted:* a same-day double of a borrowed or local object (ring, key, ticket, banknote number).
   *Today:* only mass-produced objects can be duplicated; otherwise a force is needed.
   *Primitives:* duplicate, prove ordinariness.
10. *Wanted:* hide a coin-sized object in something under 3 mm thick or see-through, through
    handling. *Today:* shells, flaps, double walls, black-art wells; all thick or opaque.
    *Primitives:* conceal.
11. *Wanted:* concealment independent of light and angle, safe on phone video. *Today:* black art
    and mirrors, both lighting- and sight-line-bound [9][11]. *Primitives:* conceal.
12. *Wanted:* change a card face or a surface colour in under 0.3 s, no glow, under 0.1 mm added,
    then hand it out. *Today:* sleight colour changes; flap cards with visible seams and two
    states. *Primitives:* transform, prove ordinariness.
13. *Wanted:* an inspected metal object that bends or parts 10-60 s later in the spectator's fist.
    *Today:* bend by hand under misdirection; shape-memory at a fixed temperature; suggestion [21].
    *Primitives:* transform, delay.
14. *Wanted:* full order of an honestly shuffled deck in 1-2 s at 99.5%. *Today:* memorised stack
    plus false shuffles; marked decks read card by card [33]; commercial camera systems (agent 2).
    *Primitives:* know.
15. *Wanted:* contents of a folded slip the performer never touches, within 5 s. *Today:* centre
    tear, one-ahead, impression pads; the performer handles the paper or supplies the pad [29].
    *Primitives:* know.
16. *Wanted:* which hand, cup or box holds an ungimmicked object, from 0.5-1 m. *Today:* a magnet
    in the object plus a sensor; psychological tells with a real failure rate. *Primitives:* know.
17. *Wanted:* a word spoken on stage, in the performer's possession silently within 1 s, with a
    looked-up fact attached. *Today:* a human assistant listening and cueing; pre-show research.
    *Primitives:* know, tell.
18. *Wanted:* 6 bits to the performer in under 2 s, nothing visible, not interceptable by a
    phone. *Today:* thumpers [11] (slow pulse counts), earpieces (visible, intercepted in the
    Popoff case [16]), verbal codes (years [24]). *Primitives:* tell.
19. *Wanted:* a message one spectator perceives and their neighbour at 0.5 m does not.
    *Today:* whispers, a card shown to one person, pre-show; all visible as an interaction.
    *Primitives:* tell (dual reality, instant stooge).
20. *Wanted:* a self-contained trigger under 5 mm thick, accurate to 1 s over 1 minute to 24 hours,
    silent. *Today:* melting wax or ice, dissolving salt, slow chemistry (temperature-sensitive,
    minutes of error), clockwork (ticks). *Primitives:* delay.
21. *Wanted:* a die or coin that obeys 99% on command and tests fair otherwise. *Today:* loaded
    dice (always biased), magnetic dice with a table magnet, double-faced coins, a switch.
    *Primitives:* control chance, prove ordinariness.
22. *Wanted:* 50-1000 outs at under $0.50 each, the right one in hand within 2 s. *Today:* 2-6
    outs; pocket indexes that are slow and error-prone. *Primitives:* control choice (by coverage).
23. *Wanted:* thread, adhesive, ink or gimmick that removes itself in 5-60 s with no residue.
    *Today:* ditching by sleight; flash paper [36]; scraping wax. *Primitives:* erase.
24. *Wanted:* a gimmicked prop within 2% weight and 0.05 mm of the real one, same sound and flex,
    no seam at 15 cm. *Today:* machined shells that talk; tin "glass" bottles [51]; decks that
    cannot be examined [40]. *Primitives:* prove ordinariness.
25. *Wanted:* factory-sealed appearance after tampering (cellophane, seals, blister packs).
    *Today:* hand re-wrapping; or custom print runs with large minimums. *Primitives:* prove ordinariness.
26. *Wanted:* genuine restoration of a torn, cut or broken marked object in under 5 s. *Today:*
    duplicates and switches; the signed piece trick restores only one corner's worth of proof.
    *Primitives:* transform, duplicate, erase.

---

## 3. Effect concepts: ranked classic method weaknesses most worth attacking with new technology

As the task for this slice specifies, this section is a ranked list of weaknesses and the classic
effects each would unlock, in place of built effect concepts.

Ranked by (number of classics unlocked) x (how badly classical methods handle it) x (how invisible
a fix can be). Level 2 = hidden input to a traditional method; level 3 = new architecture.

1. **Non-examinability of the working object (prove ordinariness; erase).** Level 2-3. Unlocks:
   Linking Rings with every ring handed out, Chop Cup with cup and ball left with the spectator,
   shell-coin routines, Svengali-type miracles with a deck that is then honest, Zombie, flap
   props. Directions: gimmicks that lock into an ordinary state, gimmicks that self-remove,
   fabrication good enough that the gimmicked object *is* within tolerance of ordinary.
2. **Knowing the state of an honestly mixed set (know).** Level 2. Unlocks: ACAAN under fair
   conditions, Out of This World from a shuffled deck, identification of any card, every
   memorised-deck and Gilbreath effect without false shuffles, poker deals. One sensing capability
   upgrades a whole shelf of the literature.
3. **Knowing a thought-of item without touching the paper (know).** Level 2. Unlocks: billet
   reading, Q&A, drawing duplications, book tests with borrowed books, PIN and name revelations.
4. **Silent, invisible, rich cueing (tell).** Level 2. Unlocks: one-person second sight, any
   "know" device, one-ahead without a plant, instant-stooge and dual-reality structures.
5. **Invisible support that survives light and handling (move).** Level 2. Unlocks: floating bill
   and ring in daylight, haunted deck on the spectator's palm, rising card from a borrowed deck,
   animated handkerchief, spirit bell and pendulum effects in isolation.
6. **Hold and release with no grip and an off switch (hold/release).** Level 2. Unlocks: Miser's
   Dream with open hands, coins across in a spectator's hand, cups-and-balls final loads without a
   pocket trip, chop cup without a permanent magnet, PK-style adhesion that vanishes on inspection.
7. **Coverage instead of forcing (control choice).** Level 3. Unlocks: headline and lottery
   predictions with a free choice, "the object you named is the one in the sealed box", chair
   tests, confabulation. Hundreds of cheap outs, or one out created late, replaces the force and
   so cannot fail and can be repeated.
8. **Methods displaced in time (delay).** Level 3. Unlocks: an object that changes after it has
   been in the spectator's pocket for ten minutes; sealed predictions that become correct after
   sealing; haunted objects with no performer in the room; spoon bending in the spectator's fist.
9. **Switching flat objects in the open (swap), or avoiding the switch by rewriting (transform).**
   Level 2. Unlocks: prediction envelopes never touched at the end, signed card to impossible
   location, bill serial-number effects, torn-and-restored with the signed original.
10. **True restoration (transform, erase).** Level 2-3. Unlocks: torn and restored card or note,
    cut and restored rope, broken and restored thread or rubber band, each with the marked piece.
11. **Vanish without wardrobe or a lap (move, conceal).** Level 2. Unlocks: coin or ring vanish in
    a T-shirt, ring flight, vanishing silk and cigarette-type effects for street conditions.
12. **Visible change of a surface under scrutiny (transform).** Level 2. Unlocks: colour-changing
    deck, card colour change in the spectator's hand, writing that appears on a signed card,
    Spellbound. High too-perfect risk if it looks like a display; must end examinable.
13. **Chance devices that are fair on inspection (control chance).** Level 2. Unlocks: dice
    predictions, coin-flip sequences, spinner and bottle forces, Russian-roulette-style choices
    made safe.
14. **Light- and camera-independence for optical concealment (conceal).** Level 2. Unlocks:
    black-art productions at a lit table, mirror-box and Sphinx-type miniatures on a desk,
    installation pieces viewed from all sides.
15. **Safe replacements for fire and reagents (transform, erase).** Level 2. Unlocks: flash
    vanishes in venues that ban nitrocellulose, drinkable water-to-wine, any-drink routines in a
    clear vessel.

---

## 4. Dead ends and overhyped items

- **Building a complete, "correct" taxonomy.** Lamont's objections hold [2]. Tag and move on.
- **Rebuilding the Victorian optical illusions as the effect.** Pepper's ghost is now the name the
  public gives to any floating image [9]. Useful only as a hidden component.
- **Bigger permanent magnets.** They make the tell worse (clinging, phone compasses, wallets) and
  add a real hazard. The need is switchability and field shaping, not strength.
- **Replacing sleight of hand wholesale.** A fully automatic prop leaves "it's a gadget" as the
  only theory. Gimmick-only coin magic is already noted as unimpressive [35].
- **Mathematical principles shown as procedures.** Arithmetic book tests fell out of use once
  known [22]. The principle is valuable only when the procedure disappears.
- **Earpiece-style cueing as is.** Visible, and defeated with a consumer scanner forty years ago
  [16].
- **Angle-only levitations** (Balducci, King Rising [13]). No technology fixes a one-viewpoint
  method in a room full of phones.
- **The bullet catch and anything "invulnerability" with real stored energy** [43]. Not a
  hobby project.
- **Cold and hot reading as engineering targets** [42]. Automated research on audience members is
  feasible and ethically and legally fraught; out of scope.

---

## 5. Open leads

- Fitzkee's own lists of *methods* per effect in *The Trick Brain* (he enumerates basic ways to
  vanish, levitate and so on; unverified). They would be a ready-made requirements table.
- Sharpe's "Systematic Invention of Effects" and "The Legitimate Use of Apparatus" chapters [18],
  and his later four-volume *Conjurers' Optical / Mechanical / Hydraulic and Pneumatic / Psychological
  Secrets* (titles unverified): the closest existing "methods by physics" encyclopaedia.
- Hopkins (1897) [46] and Hoffmann's *Modern Magic* (1876, unverified) should be read page by page
  for forgotten principles; many were abandoned for cost or bulk reasons that no longer apply.
- Robert-Houdin's *Secrets of Stage Conjuring* (Project Gutenberg 77917, server unavailable this
  session) for his own description of the chest and electrical cueing.
- Ortiz's *Designing Miracles* and Tamariz's *The Magic Way*: confirm my summaries; they are the
  design theory any technology method should be checked against.
- Johnsson's "Too Perfect Theory" essay and the replies to it (unverified citation).
- Measured data on thread visibility and breaking loads, classic-force failure rates, and
  audience explanations of gimmicked-prop effects (agent 4 may have the last).
- The Hooker Rising Cards (a century-old mechanical method still not public; unverified) as a case
  study of an over-engineered hidden mechanism that survived expert scrutiny.

---

## 6. Sources

Opened this session:

1. https://notes.elie.net/zdata/kindle/Fitzkee-The+Trick+Brain - Fitzkee's 19 basic effects, verbatim list.
2. https://pmc.ncbi.nlm.nih.gov/articles/PMC4477052/ - Lamont (2015), "Problems with the mapping of magic tricks", Frontiers in Psychology.
3. https://jimsteinmeyer.com/2022/04/14/what-we-hide-problems-in-algeria-part-two/ - Steinmeyer on the Light and Heavy Chest.
4. https://jimsteinmeyer.com/?p=956 - same essay, alternative URL; Algeria mission and audience knowledge.
5. https://en.wikipedia.org/wiki/Magic_(illusion) - categories of effects, genres, history.
6. https://www.frontiersin.org/articles/10.3389/fpsyg.2014.01508/full - Rensink and Kuhn (2015), "A framework for using magic to study the mind".
7. https://pmc.ncbi.nlm.nih.gov/articles/PMC4260479 - Kuhn, Caffaratti, Teszka, Rensink (2014), taxonomy of misdirection.
8. https://shop.52kards.com/blogs/posts/the-13-effects-behind-every-magic-trick - retail "13 effects" list.
9. https://en.wikipedia.org/wiki/Pepper%27s_ghost - principle, history, constraints, modern uses.
10. https://en.wikipedia.org/wiki/Hiding_the_Elephant - resolves to the Steinmeyer article; publication details only.
11. https://en.wikipedia.org/wiki/Glossary_of_magic_(illusion) - definitions: angles, black art, shell, pull, topit, servante, loop, thumper, Sphinx principle, etc. (also reached via /wiki/Black_art_(theatre)).
12. https://en.wikipedia.org/wiki/John_Nevil_Maskelyne - Egyptian Hall, Psycho, inventions.
13. https://en.wikipedia.org/wiki/Levitation_(illusion) - Asrah, Balducci, King, Kellar, Copperfield methods and limits.
14. https://en.wikipedia.org/wiki/Jean-Eug%C3%A8ne_Robert-Houdin - theatre, second sight, ethereal suspension, chest, Algeria.
15. https://en.wikipedia.org/wiki/Mentalism - methods overview.
16. https://en.wikipedia.org/wiki/Peter_Popoff - 1986 radio earpiece exposure.
17. https://en.wikipedia.org/wiki/Cups_and_balls - history, variants, chop cup date.
18. https://magicref.net/magicbooks/bookssz/sharpeshneomagic.htm - contents of Sharpe's Neo-Magic, 2nd ed.
19. https://en.wikipedia.org/wiki/Chinese_linking_rings - history, sets, sizes.
20. https://en.wikipedia.org/wiki/Sawing_a_woman_in_half - Selbit, Goldin patent, variants.
21. https://en.wikipedia.org/wiki/Spoon_bending - methods, shape-memory spoons, Wiseman and Greening.
22. https://en.wikipedia.org/wiki/Book_test - method families and limitations.
23. https://en.wikipedia.org/wiki/Nevil_Maskelyne_(magician) - wireless work, 1903 Marconi incident.
24. https://en.wikipedia.org/wiki/The_Zancigs - two-person code act and its exposure.
25. https://en.wikipedia.org/wiki/Mechanical_Turk - method, deception of examiners, history.
26. https://en.wikipedia.org/wiki/Ambitious_Card - effect, history, methods.
27. https://en.wikipedia.org/wiki/Miser%27s_Dream - effect and history.
28. https://en.wikipedia.org/wiki/Metamorphosis_(illusion) - substitution trunk.
29. https://en.wikipedia.org/wiki/Billet_reading - one-ahead, history, exposures.
30. https://en.wikipedia.org/wiki/Thumb_tip - uses and variants.
31. https://www.frontiersin.org/articles/10.3389/fpsyg.2016.00748/full - Smith, Dignum, Sonenberg (2016), "The Construction of Impossibility".
32. https://en.wikipedia.org/wiki/Equivocation_(magic) - forces, equivoque and its repetition weakness (also /wiki/Forcing_(magic)).
33. https://en.wikipedia.org/wiki/Card_marking - marking methods and detection.
34. https://en.wikipedia.org/wiki/Kruskal_count - principle and probabilities.
35. https://en.wikipedia.org/wiki/Coin_magic - plots, sleights, remarks on gimmicks.
36. https://en.wikipedia.org/wiki/Flash_paper - resolves to nitrocellulose; hazards and storage.
37. https://en.wikipedia.org/wiki/Buatier_de_Kolta - expanding die, vanishing lady, spring flowers.
38. https://en.wikipedia.org/wiki/Tarbell_Course_in_Magic - structure and dates.
39. https://en.wikipedia.org/wiki/Joseph_Dunninger - radio career, wireless set photograph.
40. https://en.wikipedia.org/wiki/Svengali_deck - construction, date, limitations.
41. https://en.wikipedia.org/wiki/Gilbreath_shuffle - principle.
42. https://en.wikipedia.org/wiki/Cold_reading - techniques and limits.
43. https://en.wikipedia.org/wiki/Bullet_catch - methods and deaths.
44. https://en.wikipedia.org/wiki/Washington_Irving_Bishop - muscle reading.
45. https://www.lindahall.org/about/news/scientist-of-the-day/john-henry-pepper/ - Pepper and Dircks; the orchestra-pit adaptation.
46. https://en.wikipedia.org/wiki/Henry_Ridgely_Evans - Hopkins 1897 book, Jastrow review.
47. https://en.wikipedia.org/wiki/Psycho_(automaton) - 1875 debut, glass cylinder, surviving copies.
48. https://en.wikipedia.org/wiki/Vanishing_bird_cage - collapsing cage on a pull.
49. https://en.wikipedia.org/wiki/Topit - history and use.
50. https://en.wikipedia.org/wiki/Out_of_This_World_(card_trick) - Curry 1942.
51. https://en.wikipedia.org/wiki/Inexhaustible_bottle - hydrostatic method, variants.
52. https://www.mentalfloss.com/article/631857/peppers-ghost-optical-illusion-the-toast-of-victorian-london - debut, earnings, Dircks dispute.
53. https://en.wikipedia.org/wiki/Robert_Heller_(magician) - biography only; does not confirm the second-sight method.

Seen in search results or as links, not opened (or blocked):

54. https://www.britannica.com/art/conjuring - Sharpe's six-effect classification (HTTP 403 on fetch).
55. https://issuu.com/hermeticpress/docs/magicwaysamplepages - Tamariz, The Magic Way, sample pages.
56. https://magicref.net/magicbooks/bookssz/tamarizjuanmagicway.htm - contents of The Magic Way.
57. https://www.vanishingincmagic.com/magic-book-reviews/neo-magic-artistry/ - review of Sharpe's Neo-Magic Artistry (HTTP 403).
58. https://www.gutenberg.org/ebooks/77917 - Robert-Houdin, The Secrets of Stage Conjuring (HTTP 503).
59. https://gutenberg.org/files/72672/72672-h/72672-h.htm - Pepper, The True History of the Ghost (HTTP 503).
60. https://archive.org/stream/magicstageillusi00hopk#page/n7/mode/2up - Hopkins (1897), linked from [46].
61. https://www.jstor.org/stable/1623294 - Jastrow's review of Hopkins in Science, linked from [46].
62. https://cosmosmagazine.com/technology/the-magic-of-magnets - popular account of the chest.
63. https://fringearts.com/?p=1284 - summary of Fitzkee's effects.
64. https://tricksupply.com/?p=45174 - The Trick Brain product description.
65. https://www.theory11.com/forums/goto/post?id=332589 - forum thread on categories of effects (HTTP 403).
66. https://peerj.com/articles/9712 - "On the cognitive bases of illusionism" (HTTP 403).
67. https://research.gold.ac.uk/11632 - repository copy of Kuhn et al. (2014).
68. https://en.wikipedia.org/wiki/Henry_Dircks - Dircks biography.
69. https://www.scientificamerican.com/article/how-ghostbusting-became-a-victorian-pastime/ - Pepper's ghost and spiritualism.
