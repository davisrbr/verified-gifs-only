# 07 - Smart / active / programmable materials and small unconventional actuators as magic methods (2015 to 2026)

Research note. The shared web-search budget for the whole project ran out after my first 16 searches. Everything after that was done by opening primary pages directly (supplier pages, lab pages, papers, Wikipedia). Anything I could not open or confirm is marked **(unverified)**. Numbers marked **(calc)** are my own estimates from material properties, not quoted figures. Prices are as seen in late 2026 on the page cited.

## 1. Summary

- **The valuable use of this slice is not "a material that visibly moves" but "a hold, latch, clutch or bond with no motor, no noise and no standby power".** The practical toolbox is now: nitinol wire (silent pull), electropermanent magnets (pulse on, pulse off, zero holding power), programmable magnet sheets (selective sticking), fuses made of meltable, soluble or subliming solids (delays and self-erasing gimmicks), jamming (two stiffness states in one limp object), and electrostatic clutches (thin, silent, milliwatts).
- **Nitinol wire is the single most useful part.** Dynalloy's own table: a 0.10 mm wire pulls 143 g, needs about 200 mA, contracts in about 1 s, re-extends in about 1 s, and is rated for millions of cycles at 3 to 5% stroke. It is a hair-thin, silent "muscle" that fits inside a 1 mm cavity. Magic has used nitinol almost only as a visible self-bending spoon.
- **Electropermanent magnets (EPMs) fix the three weaknesses of magnets in magic**: a permanent magnet is always on (found by any steel object or phone compass), an electromagnet hums, heats and drains batteries. An EPM holds with zero power, switches with a pulse of tens of millijoules, and in the off state leaks almost nothing. A commercial drone unit holds 200 N. The mechanism also ships inside a Logitech MX Master 3 mouse.
- **Magnetism can now be a code, not just a force.** MIT's Mixels (UIST 2022) writes 3 mm north/south pixels onto $0.008/cm2 fridge-magnet sheet with a $62 printhead; two 25 mm squares stick with 1.09 N only to their coded partner. That is a new method primitive: objects that selectively attract one specific other object out of many.
- **Gadolinium is ferromagnetic below about 20 C and not above.** A chilled slug sticks to a magnet; warmed in a hand it lets go and afterwards passes any magnet test. This is a hold that releases on hand heat with no electronics and erases its own evidence. I found no magic use (unverified).
- **Material fuses give delays with nobody present and nothing left behind**: cyclododecane (a waxy solid used by art conservators) sublimes away in days to weeks with no residue; gallium melts at 29.76 C; polycaprolactone softens at 60 C; cold-water PVA dissolves; an electrically debonding adhesive (in the iPhone 16) releases with 9 to 30 V in 5 s to 6 min and zero force.
- **Jamming gives one object two mechanical states that look identical.** A stack of n thin sheets in an evacuated sleeve is up to n squared times stiffer than the same stack unevacuated (theory; 10 layers gives up to 100x). A hand-held syringe is enough vacuum. This removes the rigid insert that classic "stiff rope" and "stiff handkerchief" methods must hide or steal away.
- **Textile electrostatic clutches (EPFL, 2019 to 2022) hold 20 N/cm2 at 300 V, weigh 30 mg/cm2, switch in under 15 ms and draw 1 mW/cm2.** That is a lock thinner than a playing card. Nothing like it exists in magic.
- **Threads: the real gain is in what a thread can also do.** A single 12 um Kevlar filament holds about 35 g (calc), a 17 um UHMWPE filament about 75 g (calc), versus about 9 g (calc) for a 12 um nylon strand. A 10 um tungsten wire holds about 24 g (calc) and conducts current, so a thread can power, signal or cut itself free.
- **Weight is a cheap, strong, non-electronic anomaly.** A one-inch tungsten cube is 300 g (supplier figure); the same cube in aluminium is 44 g and in printed PLA about 20 g (calc). Identical-looking objects can differ 15-fold in weight.
- **Overhyped for live use:** HASEL and dielectric elastomers (10 to 22 kV), liquid crystal elastomers and azobenzene films (lab chemistry), self-healing polymers as "cut and restore" (hours, soft materials), electrowetting droplet tables, ferrofluid, aerogel, mu-metal as a "magnet blocker", ionic polymer actuators.

## 2. Catalog

Each entry: what it is, numbers, references, access and cost, what it does for a method, and prior magic use. Level tags follow the brief: L1 the phenomenon is the effect, L2 a hidden input to an old method, L3 a new method architecture.

### A. Shape memory and thermally driven solids

**A1. Nitinol actuator wire (Flexinol / Muscle Wire).**
Nickel-titanium wire that contracts when heated through its transition (70 C "LT" or 90 C "HT" grades) and is stretched back by a small bias force when cool. Dynalloy's table (opened):

| Diameter | Pull | Bias force to reset | Current for 1 s pull | Cool time (70 C grade) | Resistance |
|---|---|---|---|---|---|
| 0.025 mm | 8.9 g | 3.6 g | 45 mA | 0.18 s | 1425 ohm/m |
| 0.05 mm | 36 g | 14 g | 85 mA | 0.4 s | 500 ohm/m |
| 0.076 mm | 80 g | 32 g | 150 mA | 0.8 s | 232 ohm/m |
| 0.10 mm | 143 g | 57 g | 200 mA | 1.1 s | 126 ohm/m |
| 0.15 mm | 321 g | 128 g | 410 mA | 2.0 s | 55 ohm/m |
| 0.25 mm | 891 g | 356 g | 1050 mA | 5.4 s | 18.5 ohm/m |

Stroke is roughly 3 to 5% of length (Dynalloy says tens of millions of cycles inside its guidelines, hundreds to a few thousand if over-stressed). Worked example (calc): 100 mm of 0.10 mm wire is 12.6 ohm, runs from 2.5 V at 0.5 W, gives 3 to 5 mm of travel at 143 g, and costs about 0.5 J per pull, so a 40 mAh lithium cell gives several hundred actuations. It is completely silent and has no magnetic signature. Weaknesses: slow reset in still air for thick wire, needs a bias spring, gets to 70 to 90 C (keep off skin and paper edges), and stroke must be amplified with a lever for large motion.
- References: Dynalloy technical data https://www.dynalloy.com/tech_data_wire.php ; Wikipedia, Nickel titanium https://en.wikipedia.org/wiki/Nickel_titanium ; SparkFun listings (seen in search) https://www.sparkfun.com/muscle-wire-0-005-diameter-1-foot.html .
- Access: off the shelf, a few dollars per foot (SparkFun, RobotShop; exact current price not confirmed).
- Magic relevance: L2/L3. The quietest way to pull a pin, drop a flap, release a spring, tip a balance or free a load inside a wallet, frame, book cover, card box, pen or coin-sized shell. Replaces solenoids (click, magnetic), servos (whine, bulk) and thread pulls (performer must be attached).
- Prior magic use: self-bending nitinol spoons, paperclips and "memory wire" novelties (Grand Illusions teaspoon, 60 GBP; Walmart paperclip about $6, seen in search). I found no product that uses nitinol as a hidden release, though some electronic props surely do (unverified).

**A2. Body-temperature and other transition grades; one-way memory; superelastic wire.**
Composition tunes the austenite-finish temperature from about -20 to +110 C. Kellogg's Research Labs stocks five grades named SuperElastic, AirTemp, Body Temp, Std Temp and High Temp in wire, sheet, springs and "separation actuators"; prices are quote-only. A design studio that bought from them reports 35 C, 45 C and 80 C grades (seen in search). Below transition the metal is dead-soft and stays where bent (up to 6 to 8% strain); above it springs back with 150 to 300 MPa recovery stress. Shape is set by clamping and heating to about 500 C (kitchen torch or kiln). Superelastic grade is the opposite trick: a wire that can be tied in a knot and springs straight.
- References: https://www.kelloggsresearchlabs.com/ ; https://www.rochemodern.com/rm-works/shape-memory-alloy (seen in search) ; Wikipedia as above; SMA versus SMP stress table https://en.wikipedia.org/wiki/Shape-memory_polymer .
- Magic relevance: one object, two mechanical states that look identical (a pin that is as soft as solder at 20 C and a spring at 40 C). A hold that lets go at hand temperature. L1 if shown as a bending spoon, L2/L3 as a hidden hand-heat latch.
- Risk: the transition has 20 to 50 C hysteresis, so "body temperature" grades behave differently on a cold night and in a hot room. Test in the performing environment.

**A3. Shape-memory polymers, including ordinary PLA, heat-shrink and prestrained polystyrene.**
SMPs recover very large strains (up to 800%) but with low force (1 to 3 MPa), in seconds to minutes, between -10 and 100 C depending on chemistry. Printed PLA is a usable SMP with a transition near 60 C: Thermorph (CHI 2018) uses the built-in print stress of a cheap FDM printer so flat prints fold themselves when heated. The Printed Paper Actuator (2018) prints one layer of conductive PLA on copy paper to make a reversible, electrically heated bending strip. Prestrained polystyrene (Shrinky Dinks) folds along printed black lines under a heat lamp, with fold angle set by line width (Liu, Boyles, Genzer, Dickey, Soft Matter 2012); Felton et al. (Science 2014) folded a whole walking robot from paper plus polystyrene in about four minutes for about $20 of body material.
- References: https://en.wikipedia.org/wiki/Shape-memory_polymer ; https://morphingmatter.org/projects/thermorph ; https://morphingmatter.org/projects/printed-paper-actuator ; https://news.ncsu.edu/2011/11/wmsdickeyfolding/ ; https://pubs.rsc.org/en/content/articlelanding/2012/sm/c1sm06564e (seen in search) ; https://wyss.harvard.edu/news/robot-folds-itself-up-and-walks-away/ .
- Access: hobbyist, near zero cost. Printing details belong to agent 6.
- Magic relevance: L2. A one-shot stored-energy part that fires when warm tea, a hair dryer, a lamp or a resistor heats it: a printed latch that lets go at 60 C, a flat sheet in a sealed envelope that takes a 3D shape. Low force and slow, so use it as a trigger, not as the load path.

**A4. Twisted-and-coiled polymer muscles (fishing line).**
Nylon line twisted until it coils contracts up to 49% when heated and lifts over 100 times what human muscle of the same size does (Haines et al., Science 343, 868, 2014). Drive is heat (metal-coated sewing thread or a twisted-in wire).
- References: https://softroboticstoolkit.com/publications/artificial-muscles-fishing-line-and-sewing-thread (seen in search) ; https://spectrum.ieee.org/fishing-line-makes-superhuman-artificial-muscles .
- Verdict: cents per actuator and far more stroke than nitinol, but needs a large temperature swing and cools slowly (exact temperatures unverified). Good for a slow, strong, one-way pull inside a stage-size prop; nitinol is better at close-up scale.

**A5. Bilayers that answer to heat, humidity or breath (hygromorphs, bimetals).**
Any strip made of two layers that swell differently curls. Pine-cone scales and the cellophane "fortune fish" work this way on moisture (fish mechanism from memory, unverified). MIT's bioLogic (CHI 2015) printed natto-cell films that open flaps on sweat. Bimetal strips do the same with temperature. Forces are millinewtons; response of a thin film to breath is a second or two (unverified).
- References: https://tangible.media.mit.edu/project/biologic/ ; https://en.wikipedia.org/wiki/Bimetallic_strip ; Reyssat and Mahadevan, "Hygromorphs", J. R. Soc. Interface 2009 (page blocked, unverified).
- Magic relevance: L3 as a trigger. "Blow on it" or "hold it in your hand" becomes a real physical input that needs no sensor: a film sliver that curls and trips a balanced catch. Speculative but nearly free to test.

**A6. Liquid crystal elastomers, azobenzene films, 4D-printed hydrogels.** Reversible 30 to 40% contraction on heat or light in the papers (Kotikian et al. 2018; Gladman et al. 2016, both unverified this session). Lab synthesis, no retail supply found. See dead ends.

### B. Magnets as programmable material

**B1. Electropermanent magnets (EPM).**
A NdFeB magnet and an AlNiCo magnet of equal remanence (about 1.3 T) sit side by side between iron pole pieces with a coil around the AlNiCo. NdFeB coercivity is about 1120 kA/m, AlNiCo about 50 kA/m, so a short coil pulse flips only the AlNiCo. Aligned: both push flux out through the poles (on). Opposed: flux circulates inside (off). No power is needed in either state. Numbers: holding force follows F = B^2 A / mu0 at the pole area; Wikipedia's worked example gives an on/off force ratio of at least four orders of magnitude (that section is flagged as disputed) and a patent reports 450:1 for one cylindrical design. A Knaian-type millimetre-scale device was switched from a 100 uF capacitor at 20 V, at most about 20 mJ per switch. Force scales with area and switching energy with volume, so small EPMs are very efficient. The OpenGrab EPM v3 drone gripper is quoted at 200 N minimum and $149.99 (student thesis citing the vendor; not confirmed on the vendor page). Holding force collapses with air gap, so the working face must be within about a millimetre of the steel.
- References: https://en.wikipedia.org/wiki/Electropermanent_magnet ; Knaian, MIT PhD thesis 2010 https://dspace.mit.edu/handle/1721.1/60151 (seen in search) ; https://hizook.com/electropermanent-magnets-programmable-magnets-zero-static-power-consumption-enable-s/ ; CTU thesis with OpenGrab figures https://dspace.cvut.cz/bitstream/handle/10467/79592/F3-BP-2019-Martonova-Veronika-Electropermanent_Magnet_Study.pdf (seen in search) ; axisymmetric EPM patent https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/10971292 (seen in search).
- Access: hobbyist-buildable from two small rod magnets, two steel bars, about 100 turns of wire, an H-bridge and a capacitor (roughly $10 to $30 in parts, my estimate); or buy a drone gripper; or salvage the detent unit from a Logitech MX Master 3 scroll wheel (Wikipedia lists it as an EPM application).
- Magic relevance: L2 for the 1845 "Light and Heavy Chest" (Robert-Houdin used an electromagnet); L3 for anything that must hold for hours on a coin cell and then be examined. An off EPM does not attract a paperclip and does not swing a compass much, and there is no hum or heat. Also usable as a latch inside a prop, switched from outside by a pulse coil.
- Prior magic use: electromagnets, yes, since Robert-Houdin (https://en.wikipedia.org/wiki/Jean-Eug%C3%A8ne_Robert-Houdin). EPMs: none found (unverified).

**B2. Mechanically switched magnets (rotating diametric magnet, as in a magnetic base).**
A round diametrically magnetised magnet in a split iron housing: turn it 90 degrees and the iron either extends the poles (on) or shorts them (off). No electronics at all.
- Reference: https://en.wikipedia.org/wiki/Magnetic_switchable_device .
- Magic relevance: L2. A 3D-printed housing with two steel inserts and a 6 mm diametric magnet turned by a nitinol wire or a thumb wheel is a silent on/off shim. Slower and bulkier than an EPM but needs no pulse circuit.

**B3. Programmed magnets: Polymagnets and Mixels.**
Correlated Magnetics prints many small poles into one magnet so a pair behaves as a spring (attract far, repel near), a latch, a twist-to-release coupling or a rotational detent, and so the field stays close to the surface. A demo kit with attach, twist-release, near-field, spring, repel-latch and detent magnets plus viewing film was $96.54 at Amazing Magnets. Mixels does the same on soft magnetic sheet: 3 mm pixels, about 0.7 s per pixel, rewritable, readable with a Hall sensor; add-on parts $62 on a desktop CNC; sheet $0.008/cm2; Hadamard-coded pairs attract only their partner; two 25 mm squares hold 1.09 N in pull and 1.31 N in shear.
- References: https://www.polymagnet.com/ ; https://amazingmagnets.com/polymagnet ; https://hcie.csail.mit.edu/research/mixels/mixels.html ; https://arxiv.org/abs/2208.03804 ; https://en.wikipedia.org/wiki/Programmable_magnet (seen in search).
- Magic relevance: L3. Selective attraction (object A sticks to B but not to C, D, E), position- and orientation-specific sticking, short-range fields that a compass a few centimetres away barely notices, and a magnetic "ID" that a Hall sensor can read through a card or table. 1 N is enough to lift a card, a token, a banknote with a shim or a light box.
- Prior magic use: PK rings, shimmed cards and coins, magnetic vanishers and holdouts are everywhere, but all use plain dipoles. Coded pairing: none found (unverified).

**B4. Halbach arrays and one-sided flux.** A rotating magnetisation pattern puts nearly all the flux on one face (about double) and almost none on the other; fridge-magnet sheet is made this way. A hidden magnet can therefore be strong toward the table top and nearly dead toward a spectator's ring, watch or phone below or behind it. Reference: https://en.wikipedia.org/wiki/Halbach_array . Hobbyist-buildable from five or more block magnets in a printed tray.

**B5. Shielding.** Mu-metal (relative permeability 80,000 to 100,000) redirects flux through itself; it does not block it, it saturates at low fields, and bending it ruins it until re-annealed in hydrogen. Next to a strong neodymium magnet ordinary steel is the right keeper. Use: a steel-lined pocket or case so a carried magnet does not grab keys or trip a phone compass. Reference: https://en.wikipedia.org/wiki/Mu-metal .

**B6. Force through a table, a hand or a glass (calc).** On-axis estimate for N52 magnets, small magnet treated as a dipole:

| Hidden magnet | Target magnet | 10 mm gap | 20 mm | 30 mm | 40 mm |
|---|---|---|---|---|---|
| 50 x 25 mm disc | 10 x 3 mm disc | 460 g | 265 g | 140 g | 75 g |
| 25 x 10 mm disc | 10 x 3 mm disc | 440 g | 125 g | 42 g | 17 g |
| 12 x 6 mm disc | 10 x 3 mm disc | 220 g | 33 g | 9 g | 3 g |
| 25 x 10 mm disc | 5 x 2 mm disc | 78 g | 22 g | 7 g | 3 g |

Reading: through a 20 to 30 mm table top a palm-sized magnet still puts tens to hundreds of grams on a coin-sized shim; a ring-sized magnet is useless beyond about 15 mm. A steel shim instead of a magnet gets less. Large N52 discs are finger-crushing and wipe cards and pacemaker settings: handle as a hazard.

**B7. Thermally switched magnetism (Curie point).** Gadolinium: Curie point 20 C (293 K); ferromagnetic below, strongly paramagnetic above; tarnishes in moist air, so seal it. Manganese arsenide: 45 C. Soft ferrites and nickel-iron "compensator" alloys with Curie points chosen between about 30 and 150 C exist and are used in thermal reed switches and rice-cooker cut-outs (unverified this session; Wikipedia's Curie page confirms Curie-point soldering irons and a reactor safety latch that drops control rods when a magnet circuit passes its Curie point).
- References: https://en.wikipedia.org/wiki/Curie_temperature ; https://en.wikipedia.org/wiki/Gadolinium .
- Access: gadolinium metal pieces are sold by element dealers for a few dollars per gram (unverified).
- Magic relevance: L3. A keeper or shim that is magnetic only when cold. Hold needs no power; release is the warmth of a hand, a breath of warm air, or the room; afterwards the object is non-magnetic to any test. The transition is gradual, so the cold state needs to be well below 20 C (iced drink, fridge-cold prop, winter street).

**B8. Magnetic soft matter.** Kim, Yuk, Zhao, Chester, Zhao (Nature 558, 274, 2018): silicone ink with 20 vol% 5 um NdFeB particles, magnetised at about 2.7 T, printed under 50 mT so each filament has its own magnetisation direction; under a 30 to 200 mT field the part snaps between programmed shapes in 0.1 to 0.5 s at 22 to 309 kW/m3. A hobby version is cast silicone plus NdFeB powder, magnetised while folded. Magnetic putty and "magnetic slime" are retail toys; ferrofluid is 10 nm magnetite in oil.
- References: https://zhaolab.stanford.edu/sites/g/files/sbiybj21256/files/media/file/s41586-018-0185-0.pdf (opened, text extracted) ; https://en.wikipedia.org/wiki/Ferrofluid ; https://en.wikipedia.org/wiki/Silly_Putty .
- Verdict: mostly L1 and needs 30 to 200 mT across the whole object, which means a big magnet a few centimetres away. One L2 use: a soft silicone "skin", flap or membrane that is pulled flat or popped open by a hidden magnet, with no hinge and no rigid shim to feel.

**B9. Flat coils on PCBs.** Flexar (Carl Bugeja / Microbots) 12-layer coil: 24 x 20 x 2 mm, 2.7 g, 200 turns, 9.4 ohm, 12 mT peak (20 mT with a steel back plate), 1.5 W continuous, moves a 5 x 2.5 mm N52 magnet at up to 30 Hz. Thinner flex versions exist with less field; an older post priced one at 2 EUR (seen in search). Reference: datasheet https://cdn.shopify.com/s/files/1/0766/9855/0605/files/Flexar_12L_Datasheet_Rev1.6.pdf . Use: a silent flap, flip-dot or tap cue inside a 2 to 3 mm panel. Details belong to agent 14.

**B10. Diamagnetic pyrolytic graphite.** Susceptibility about -4e-4; floats over magnet arrays and moves when lit by a laser. Pointer to agent 9. Reference: https://en.wikipedia.org/wiki/Pyrolytic_carbon .

### C. Phase change, stiffness switching, transient and self-removing materials

**C1. Low-melting metals.** Gallium melts at 29.76 C, wets skin and glass (grey smear), expands 3.1% on freezing, supercools readily and destroys aluminium by embrittlement. Field's metal (Bi 32.5, In 51, Sn 16.5) melts at 62 C, has no lead or cadmium, and is costly because of the indium (10 g for about 15 GBP at a UK school supplier, seen in search).
- References: https://en.wikipedia.org/wiki/Gallium ; https://en.wikipedia.org/wiki/Field%27s_metal ; https://www.philipharris.co.uk/product/fe00054323 (seen in search).
- Magic relevance: the melting spoon is an old gag (L1). The L2/L3 use is a fusible link or solder joint: a metal-to-metal joint with real strength that turns liquid at hand temperature (gallium) or in hot water (Field's metal), and a rigid core that makes a floppy tube stiff until warmed. Gallium's smear and supercooling make it unreliable against skin; enclose it.

**C2. Polycaprolactone (PCL).** Nylon-like at room temperature, putty at 60 C, comfortable to handle at that temperature, sold as InstaMorph, Polymorph, Plastimake and others. Reference: https://en.wikipedia.org/wiki/Polycaprolactone . Use: instant custom gimmicks, and a stiff part that goes limp in hot water or under a hidden heater.

**C3. Wax actuators.** Paraffin expands 5 to 20% on melting; commercial wax motors push up to 4000 N, slowly. Reference: https://en.wikipedia.org/wiki/Wax_motor . Use: a slow, strong, silent push (seconds to minutes) from a resistor, or simply a wax pellet as a thermal fuse with a chosen melting point.

**C4. Jamming (granular and layer).** Loose grains or stacked sheets in an airtight skin flow freely; pump the air out and friction locks them. Brown et al. (PNAS 2010) made the coffee-grounds gripper (page blocked, unverified; a vacuum-packed coffee brick is the everyday version). For sheets, bending stiffness under vacuum is up to n squared times the unjammed value for n layers (Harvard thesis and Ohio State paper, seen in search), and MIT's jamSheets (TEI 2014) showed thin, light, stiffness-tunable sheets from paper, plastic and fabric layers.
- References: https://tangible.media.mit.edu/project/jamsheets/ ; https://dash.harvard.edu/bitstream/1/41292201/1/55117739.pdf (seen in search) ; https://arxiv.org/html/2511.07882 (2025 characterisation, seen in search).
- Access: hobbyist. Heat-sealed bag film, 10 to 20 strips of 0.1 mm PET or paper, a 5 to 10 ml syringe and a pinch valve. Under $10.
- Magic relevance: L2/L3. Rope, ribbon, tie, napkin or newspaper that is honestly limp, becomes a beam on a squeeze, holds that state with the valve shut and no power, and relaxes silently. Weak points: the airtight skin (crinkle, sheen), a tube to hide, and leaks.

**C5. Magnetorheological fluid.** Iron particles in oil; yield stress up to about 100 kPa in a field, more under compression; particles settle. Reference: https://en.wikipedia.org/wiki/Magnetorheological_fluid . Use: a sealed flexible tube or pad that stiffens only over a hidden magnet. Messy if it leaks.

**C6. Self-removing and time-fuse solids.**
- Cyclododecane: waxy solid, melts at 60.4 C, "slowly sublimates over days or weeks without leaving any residue", used by conservators as a temporary binder; pure grade needed; persistent in the environment. https://en.wikipedia.org/wiki/Cyclododecane .
- PVA film, thread and paper: water-soluble grades dissolve in cold or warm water (laundry pods, embroidery backing, anglers' PVA bags; dissolve times not confirmed). SmartSolve sells water-soluble paper in 2, 3 and 5 pt thickness. https://en.wikipedia.org/wiki/Polyvinyl_alcohol ; https://www.smartsolve.com/ .
- Viscoelastic putty: bounces in the short term, flows to a puddle given time. https://en.wikipedia.org/wiki/Silly_Putty .
- Electrically debonding adhesive: the iPhone 16 battery adhesive (believed to be tesa "Debonding on Demand") lets go with no force after 5 s at 20 V, about 60 s at 12 V, about 6 min at 5 V; it is one-shot and stays on the positive side. https://www.ifixit.com/News/100352/iphone-16-and-16-pro-teardown . Retail supply of the tape not confirmed.
- Thermal-release and UV-release tapes from wafer dicing (unverified this session).
- Magic relevance: L3. These are *delay* and *erase the evidence* primitives: a structural support, bond or stop that disappears by itself, on a schedule set by chemistry and geometry, leaving an object that is exactly what it appears to be.

**C7. Self-healing polymers and vitrimers.** Real, but slow and soft: one room-temperature polyurea-urethane is quoted at 80% recovery in 2 h and 97% in 24 h (Wikipedia, tagged citation needed); Diels-Alder systems need 90 to 120 C; vitrimers weld only when hot. References: https://en.wikipedia.org/wiki/Self-healing_material ; https://en.wikipedia.org/wiki/Vitrimers . See dead ends.

**C8. Mechanical metamaterials, bistable and multistable structures, auxetics, origami.** Printed lattices and cut sheets with snap-through elements store elastic energy and release it on a small push; reprogrammable ones hold a mechanical "memory" (Chen, Pauly, Reis, Nature 2021; Haghpanah et al., Adv. Mater. 2016; Rafsanjani et al., Adv. Mater. 2015). Auxetic sheets get fatter when pulled. Kresling origami cylinders are bistable twist-to-collapse cells (unverified this session).
- References: https://en.wikipedia.org/wiki/Mechanical_metamaterial ; https://en.wikipedia.org/wiki/Auxetics .
- Access: hobbyist (TPU or PETG print, laser-cut sheet). Agent 6 covers printing.
- Magic relevance: L2. A bistable printed flexure is a zero-power latch that fires on a millinewton cue from nitinol, a magnet, a bimetal or a hygromorph, and it can look the same in both states from outside. Auxetic or pattern-switching sheets can make a hole, slot or sleeve change size without an obvious mechanism.

### D. Soft and unconventional actuators

**D1. Electrostatic clutches and electroadhesion.** Interleaved conductive strips with a thin dielectric lock together in shear when charged. EPFL's textile clutch: up to 20 N/cm2 at 300 V, 30 mg/cm2, under 15 ms on and off, 1 mW/cm2 (Hinchet and Shea, Adv. Mater. Technol. 2019; Adv. Intell. Syst. 2022). An all-fabric version held 10 kg with a 120 x 70 mm overlap at 400 V and about 1 mW. Generic electroadhesive pads on arbitrary surfaces manage only 0.5 to 1.5 N/cm2 and are sensitive to roughness; residual charge can keep them stuck for a while (Diller, Collins, ICRA 2016).
- References: https://www.epfl.ch/labs/lmts/lmts-research/haptics/textile-clutch ; https://infoscience.epfl.ch/record/261177 (seen in search) ; https://www.andrew.cmu.edu/user/shc17/Diller_2016_ICRA.pdf (seen in search) ; https://en.wikipedia.org/wiki/Electroadhesion .
- Access: hobbyist with care. Metallised film or flex PCB, a thin high-permittivity coating, and a 300 V micro-boost module (camera-flash class). Current is microamps but 300 V near spectators must be current-limited and fully insulated.
- Magic relevance: L3. A silent lock 0.2 mm thick: a ribbon, strap, drawer slide or stack of leaves that slides freely or is immovable, switched in milliseconds, holding its state on a charged capacitor for minutes.

**D2. HASEL and dielectric elastomer actuators.** HASEL: oil-filled polypropylene pouches with electrodes; 10 to 22.5 kV; up to 24% contraction or 118% expansion; activation in 12 ms; over 10^4 to 10^6 cycles; material cost about $0.10 per actuator (Rothemund et al., Adv. Mater. 2021). DEAs: 10 to 35% typical strain in VHB tape, also kilovolts. References: https://pmc.ncbi.nlm.nih.gov/articles/PMC11469257 ; https://en.wikipedia.org/wiki/Dielectric_elastomers ; low-cost 10 kV supply paper https://www.mdpi.com/2076-0825/14/12/601 (seen in search). See dead ends.

**D3. Pouch motors and heat-sealed pneumatics.** aeroMorph (UIST 2016) heat-seals paper, plastic or fabric into inflatable hinges with a sealing head on a 3-axis CNC. Reference: https://tangible.media.mit.edu/project/aeromorph/ . A 1 mm flat pouch that swells to 10 mm on a puff of air is a strong, silent, cheap lifter; it needs a tube or a hidden bulb. L2 for card rises, lids and "breathing" objects.

**D4. Electrowetting droplet tables.** OpenDrop: 8 x 16 gold pads, up to 250 V DC generated on board, 12 um ETFE foil with fluoropolymer coat, about $300 in parts or 695 EUR assembled (2017 era). References: https://hackaday.io/project/12142 ; https://www.hackster.io/news/opendrop-makes-precision-fluid-control-accessible-to-home-science-labs-221d8e3878e (seen in search) ; https://www.media.mit.edu/projects/programmable-droplets/overview/ . L1 and it only works on its own special surface. See dead ends.

**D5. Ionic polymer-metal composites.** Bend at 1 to 5 V; tip force about 40 times strip weight (millinewtons); best wet. Reference: https://en.wikipedia.org/wiki/Ionic_polymer%E2%80%93metal_composites . Dead end at prop scale.

**D6. Ultrasonic and stick-slip piezo motors.** Driven above 20 kHz, so inaudible; camera autofocus motors. Reference: https://en.wikipedia.org/wiki/Ultrasonic_motor . Pointer to agent 14.

**D7. Vibration-driven locomotion.** Slanted bristles turn vibration into travel. Bristlebot: toothbrush head, pager motor, coin cell. Kilobot: two vibrators, about 1 cm/s, 45 degrees/s, under $15 in parts. The "Electric Football" game moves bristle-based figures with a vibrating field. References: https://en.wikipedia.org/wiki/Bristlebot ; https://en.wikipedia.org/wiki/Kilobot . L2: the vibrator can be in the table rather than the object, and the direction each object travels is set by the lean of its feet, so the object itself is passive and examinable.

**D8. Reaction wheels and inertial actuation in sealed objects.** M-Blocks (MIT, 2013 onward): a flywheel at up to 20,000 rpm is braked in milliseconds, and the cube rolls, jumps or climbs with no external moving parts. Cubli (ETH, 2013): a 15 cm cube that jumps onto a corner and balances. A hobby build (ESP32, MPU6050, three Nidec 24H brushless motors, 3S 500 mAh pack, printed frame) balances on an edge or corner.
- References: https://news.mit.edu/2013/simple-scheme-for-self-assembling-robots-1004 ; https://spectrum.ieee.org/mit-deploys-swarm-of-selfassembling-robot-cubes (seen in search) ; https://robohub.org/swiss-robots-cubli-a-cube-that-can-jump-up-balance-and-walk-across-your-desk ; https://github.com/remrc/Self-Balancing-Cube .
- Magic relevance: a sealed box that moves on any borrowed surface with nothing under the table, which cancels the "magnet in the table" theory. Weaknesses: flywheel whine, brake clack, weight, and the audience's default guess of "there's a motor in it". Best as L2: one small hidden shove (a box that tips over once on cue) rather than a balancing display.

### E. Surfaces, densities and threads

**E1. Superhydrophobic and liquid-repelling surfaces.** Contact angle above 150 degrees; drops bounce; submerged surfaces carry an air film and come out dry. Hydrophobic "magic sand" was described as a conjurors' material in The Boy Mechanic (1915). Consumer two-part sprays (NeverWet, Ultra-Ever Dry) leave a whitish haze and rub off (from memory, unverified); clear durable coatings are reported in the literature. References: https://en.wikipedia.org/wiki/Ultrahydrophobicity ; https://en.wikipedia.org/wiki/Hydrophobic_sand . L2 uses: paper or a card that can be dunked and stays dry and writable; a liquid that will not leave a tilted container until the surface is touched. Hydrochromic inks: agent 8.

**E2. Dry adhesives.** Gecko-type shear adhesives reach 9 to 55 N/cm2 in shear, release by peeling, and survive about 1,000 cycles; ShearGrip is sold to consumers. Reference: https://en.wikipedia.org/wiki/Synthetic_setae . L2: a hold that is strong sideways and free when lifted, with no residue, useful for hanging an object on glass or a palm-side steal.

**E3. Very light and very dense solids.** Silica aerogel: record density 1.9 mg/cm3 (air is 1.2), translucent blue, dents and shatters; discs from $35, hydrophobic discs $60, blocks $75, machinable polymer aerogel tiles $90 to $120 (Aerogel Technologies store). Tungsten cubes: 1 cm is 18 g, 1 inch is 300 g, 1.5 inch is 1 kg, 2 inch is 2.36 kg; from $39.99 (Midwest Tungsten). Same one-inch cube (calc): aluminium 44 g, steel 129 g, PLA 20 g, balsa 2.5 g.
- References: https://en.wikipedia.org/wiki/Aerogel ; http://www.buyaerogel.com/ ; https://www.tungsten.com/products/tungsten-cube .
- Magic relevance: L2/L3. Weight is felt, not seen, and is checked by nobody until you invite it. Tungsten inserts or tungsten-loaded resin make a small prop startlingly heavy; a hollow print or foam core makes its twin weigh a twentieth as much.

**E4. Threads and filaments.** Classic invisible thread is a single strand stripped from multifilament nylon (Wikipedia). A commercial 20-denier magic monofilament is rated at 200 g and one dealer claims 400 g for its strongest (seen in search); 20 denier nylon works out to about 50 um diameter (calc). Breaking loads from published strengths (calc):

| Filament | Diameter | Break load | Notes |
|---|---|---|---|
| Nylon strand | 12 um | 9 g | classic stripped thread range |
| Nylon mono, 20 denier | 50 um | 160 g | matches dealer rating |
| Kevlar single filament | 12 um | 35 g | 3.0 GPa; yellow; degrades in UV |
| UHMWPE (Dyneema) filament | 12 to 17 um | 38 to 76 g | 2.4 to 3.3 GPa; white; slippery knots; creeps; melts about 130 to 145 C |
| Vectran filament | similar | similar to Kevlar | golden; low creep |
| Tungsten wire | 5 to 10 um | 6 to 24 g | conducts; dark grey; kinks |
| Carbon fibre filament | 7 um | 16 g | black; conducts; snaps if bent sharply |
| Spider dragline | 3 um | 0.9 g | shrinks up to 50% when wet |

- References: https://en.wikipedia.org/wiki/Invisible_thread ; https://vanishingincmagic.com/magic-accessories/the-strongest-monofilament (seen in search; page blocked) ; https://en.wikipedia.org/wiki/Kevlar ; https://en.wikipedia.org/wiki/Ultra-high-molecular-weight_polyethylene ; https://en.wikipedia.org/wiki/Vectran ; https://en.wikipedia.org/wiki/Spider_silk .
- Reading: at the same visibility, aramid or UHMWPE single filaments carry about four to eight times the load of nylon. They are harvested by unpicking a strand from braided fishing line or aramid sewing thread (fishing braid is sold in dark colours; whether single filaments are dyed through is unverified). Conductive filaments open new uses (section 4).
- Prior magic use: invisible thread reels, elastic thread loops and thread-handling devices are standard (Mesika's Tarantula and Spider Pen are named on https://www.yigalmesika.com/). Kevlar thread is sold to magicians (unverified).

## 3. Capability primitives

1. *Now possible:* pull 80 to 320 g through 3 to 5 mm in 1 s, silently, from a wire 0.08 to 0.15 mm thick on 150 to 400 mA. *Because:* Flexinol. *Before:* solenoid, servo, or a thread to the performer. *Primitives:* release, move.
2. *Now possible:* hold up to 200 N for days on zero power and drop it with a pulse of tens of millijoules, leaving almost no stray field. *Because:* electropermanent magnets. *Before:* always-on magnet or hot, humming electromagnet. *Primitives:* hold/release, prove ordinariness.
3. *Now possible:* a shim that is magnetic below about 20 C and inert above. *Because:* gadolinium's Curie point. *Before:* shims are permanently detectable. *Primitives:* hold/release, erase evidence.
4. *Now possible:* tile A sticks to tile B (about 1 N per 25 mm square) but not to seven look-alikes. *Because:* Hadamard-coded magnetic pixels on $0.008/cm2 sheet. *Before:* any magnet grabs any shim. *Primitives:* control choice, swap, know.
5. *Now possible:* a magnet pair that repels until given a quarter turn, or attracts down to 1 cm then floats. *Because:* Polymagnets ($97 kit). *Before:* springs and catches. *Primitives:* hold/release.
6. *Now possible:* strong field on the working face, near zero on the back. *Because:* Halbach layouts. *Before:* hidden magnets grabbed watches and tripped compasses. *Primitives:* conceal.
7. *Now possible:* put 40 to 140 g on a 10 mm shim through 30 mm of table from a hidden 25 to 50 mm disc (calc). *Because:* N52 magnets are cheap. *Before:* thin tops or weak holds. *Primitives:* hold, move.
8. *Now possible:* a support or bond that vanishes in days to weeks with no residue. *Because:* cyclododecane. *Before:* ice (wet), salt (residue), or a confederate. *Primitives:* delay, erase evidence.
9. *Now possible:* a structural glue joint that falls apart after 5 to 60 s at 12 to 20 V with no force. *Because:* electrically debonding adhesive. *Before:* mechanical latches with seams. *Primitives:* release, prove ordinariness.
10. *Now possible:* a metal joint that turns liquid at 29.8 C or 62 C. *Because:* gallium, Field's metal. *Before:* wax. *Primitives:* release, delay.
11. *Now possible:* a rope, ribbon or cloth 10 to 100 times stiffer on a 5 ml syringe pull, held with no power. *Because:* layer jamming. *Before:* hidden rods, segmented inserts. *Primitives:* transform, prove ordinariness.
12. *Now possible:* a lock 0.2 mm thick holding 20 N/cm2, on or off in 15 ms, 1 mW/cm2. *Because:* textile electrostatic clutches at 300 V. *Before:* no thin lock existed. *Primitives:* hold/release, control.
13. *Now possible:* a printed plastic part that changes shape once at 60 C. *Because:* PLA shape memory and print stress. *Before:* springs with mechanical triggers. *Primitives:* delay, release.
14. *Now possible:* a pin that is putty-soft at 20 C and a spring at 40 C, same appearance. *Because:* body-temperature nitinol. *Before:* a switch of objects. *Primitives:* transform, prove ordinariness.
15. *Now possible:* a real trigger from breath or palm moisture with no sensor or battery. *Because:* hygromorph bilayers. *Before:* performer timing. *Primitives:* release, delay.
16. *Now possible:* a latch that fires on a few millinewtons and looks identical set or fired. *Because:* printed bistable flexures. *Before:* machined catches. *Primitives:* hold/release.
17. *Now possible:* a sealed box that shoves itself on any surface. *Because:* braked flywheels, $50 to $100 of parts. *Before:* threads, table magnets. *Primitives:* move.
18. *Now possible:* passive objects that each travel their own programmed direction on a faintly vibrating table. *Because:* bristle or directional-pile feet. *Before:* under-table magnets on tracks. *Primitives:* move, control.
19. *Now possible:* twin objects whose weights differ 7 to 15 times (300 g against 20 to 44 g per cubic inch). *Because:* tungsten at $40 a cube, hollow prints. *Before:* lead (11.3 g/cm3, toxic). *Primitives:* transform, control chance.
20. *Now possible:* 35 to 75 g on a 12 to 17 um filament, against about 9 g for nylon (calc). *Because:* aramid and UHMWPE filaments from fishing braid. *Before:* thicker thread or lighter objects. *Primitives:* move, hold.
21. *Now possible:* a near-invisible filament that carries milliamps. *Because:* 5 to 10 um tungsten wire, 7 um carbon fibre. *Before:* threads were only mechanical. *Primitives:* tell, release, erase evidence.
22. *Now possible:* a thread that cuts itself at the anchor on a 1 s pulse. *Because:* UHMWPE and nylon melt at about 130 to 220 C against a hot nichrome or nitinol loop. *Before:* break it by a tug or leave it attached. *Primitives:* erase evidence.
23. *Now possible:* paper that is dunked and comes out dry. *Because:* superhydrophobic sprays. *Before:* wax, lycopodium powder. *Primitives:* prove ordinariness, invulnerability.
24. *Now possible:* a silent flap or tap inside a 2 mm panel on 1.5 W. *Because:* 12-layer PCB coils at a few dollars. *Before:* wound coils, pager motors. *Primitives:* move, tell.
25. *Now possible:* an on/off magnet with no electronics, turned 90 degrees by a wire or thumb. *Because:* diametric magnet in a split steel housing, printable. *Before:* slide a magnet away. *Primitives:* hold/release.
26. *Now possible:* a flat pouch 1 mm thick that lifts tens of grams by 10 mm on a puff of air. *Because:* heat-sealed pouch motors. *Before:* bellows, springs. *Primitives:* move.

## 4. Effect concepts

**4.1 The pairs that find each other (L3, selective magnetism).**
Effect: eight photographs are torn in half (or eight two-part tokens are split). Spectators mix both piles face down, then drop one pile onto the other and stir. Lifted one at a time, each half comes up with its own mate clinging to it.
Method: each tile carries a 25 mm square of fridge-magnet sheet under its printed face, written with one of eight Hadamard codes; only the true mate nets an attraction (about 1 N; wrong pairs net about zero). Tiles weigh 3 to 5 g. Classical cover: the stirring is real, and the performer can do the lifting to pace it.
BOM: magnetic sheet ($5), Mixels-style printhead on a 3D printer gantry (electromagnet, H-bridge, Hall sensor, Arduino: about $60), printed tiles. Difficulty: medium (pixel-writing rig, alignment tolerance about 1 mm; tiles need to self-centre, so add a shallow nesting rim). Risks: wrong pairs give weak partial holds if offset; a spectator finds the tiles are magnetic (they are weakly so everywhere, like a fridge magnet, which does not explain selectivity). Novelty: high; I found no coded-magnet method in magic (unverified).

**4.2 The shim that is not there (L3, Curie-point release).**
Effect: a coin, ring or small token is fished from the ice in someone's drink. It clings under the performer's fingertips, hangs from a borrowed key, climbs the outside of the glass. Dropped into the spectator's hand, it becomes ordinary: they can test it against a magnet of their own and nothing happens.
Method: the token has a sealed gadolinium core. At 0 to 5 C it is ferromagnetic and follows a PK ring or a magnet behind the glass; in a closed hand it passes 20 C within a minute or so and is then only weakly paramagnetic. Speculative: the holding force at ice temperature needs measuring, and the transition is gradual.
BOM: 5 to 10 g gadolinium ($10 to $50, unverified), lacquer or a brass shell, PK ring. Difficulty: low to medium. Risks: warm rooms shorten the working window; gadolinium corrodes if the seal fails. Novelty: high (unverified).

**4.3 Zero-power light and heavy box (L2, EPM).**
Effect: a small wooden box on a tray. A child lifts it; the strongest person present cannot; the child lifts it again. The tray is handed round and is cold, silent and does not attract a paperclip.
Method: a row of electropermanent magnets under a 0.5 to 1 mm veneer in the tray; a steel plate in the box base. A 20 V capacitor pulse from a coin-cell boost circuit toggles them (radio or timer cue). On: tens of kilograms of hold at contact. Off: flux stays inside the tray.
BOM: 4 to 8 NdFeB plus AlNiCo rod pairs, mild steel bar, magnet wire, H-bridge, capacitor, microcontroller: $40 to $80; or one OpenGrab-class module at about $150. Difficulty: medium to high (winding, pulse current of several amps, pole flatness). Risks: any gap (felt, warped veneer) cuts force sharply; residual off-state field must be measured. Novelty: the effect is from 1845; the examinable, silent, battery-for-months tray is new.

**4.4 The frame that works alone (L2, nitinol release).**
Effect: a thin picture frame or slate is shown blank, wrapped in a spectator's scarf and held by them at arm's length. When unwrapped, the chosen word or card is on it.
Method: a classic flap, but released by 60 mm of 0.076 mm nitinol wire pulling a 1 mm pin (80 g pull, 150 mA, 1 s, no sound), fired by a tilt switch, timer or radio inside the 4 mm moulding. The flap is retained on the other side by a second catch, so nothing rattles.
BOM: wire ($5), 20 mAh cell, small microcontroller board, printed frame: about $25. Difficulty: low to medium. Risks: wire fatigue if overstretched; heat near paper (put the wire in a PTFE sleeve). Novelty: the flap is old; removing the performer from the moment of release is the gain.

**4.5 The napkin beam (L2, jamming).**
Effect: a cloth napkin is drawn through the fist, held by one corner, and stands out horizontally; a full wine glass is set on the far end. A snap of the fingers and it collapses; it is used to mop the spill and tossed to a spectator.
Method: the hem carries a 15 mm wide sleeve with 12 strips of 0.1 mm PET inside a thin heat-sealed film tube; a 5 ml syringe or squeeze bulb in the hand pulls vacuum through a fine tube at the held corner, giving up to about 100 times the bending stiffness; a pinch holds it; letting air in drops it. Uncouple the tube under cover of the catch.
BOM: under $10. Difficulty: medium (airtight sealing; choosing layer count so the limp state drapes naturally). Risks: leaks, crinkle sound, a spectator feeling the stiff hem. Novelty: medium; stiff-rope and stiff-handkerchief effects exist, the honest limp state is the improvement.

**4.6 It happens on Thursday (L3, sublimation fuse).**
Effect: on Monday a sealed, signed glass jar is left with the host. Inside, a ring hangs on a ribbon above a small padlock, or a folded paper sits beside an empty envelope. By Thursday the ring is locked on, or the paper is inside the sealed envelope, with nothing else in the jar.
Method: a spring-loaded mechanism is held back by a pellet of pure cyclododecane, which sublimes away over days to weeks and leaves no residue; when it thins, a bistable printed flexure snaps and does the work. Vent area and pellet size set the delay; sublimation depends on temperature and airflow, so calibrate with test jars and promise a window, not an hour. The vapour must have somewhere to go (a paper lid insert).
BOM: cyclododecane from a conservation supplier (price unverified), printed flexure, jar: about $20. Difficulty: medium, mostly calibration. Risks: timing spread; a faint waxy smell on opening; environmental persistence of the chemical (do not dump). Novelty: high as a method architecture: the cause is material physics and the performer is days away.

**4.7 The block that was solid (L3, debonding adhesive; speculative).**
Effect: a signed coin vanishes. A solid aluminium block that has been on the table throughout, and was handled earlier, is tapped on the table edge and falls into two halves with the coin in a fitted cavity.
Method: two machined halves are bonded with an electrically releasing adhesive; the halves themselves are the electrodes. The block sits on a stand whose contacts apply 12 to 20 V for 5 to 60 s when wanted. Before that the bond is structural and survives tugging. The coin load is conventional (duplicate, or loaded beforehand with a forced or duplicated signature method).
BOM: block halves from a CNC service ($40 to $80), adhesive (source unverified; replacement phone battery adhesive may work), boost converter. Difficulty: high until the adhesive is sourced and tested. Risks: one-shot per bond; release time varies with voltage and temperature. Novelty: high.

**4.8 The weight that moved (L3, density plus a hidden transfer).**
Effect: two identical small boxes. A spectator weighs both on a kitchen scale: 40 g and 340 g. The boxes are stacked and unstacked; now the scale reads 340 g and 40 g. Everything can be handled.
Method: a one-inch tungsten slug (300 g) rides in a close-fitting printed sleeve inside one box and drops through matching trapdoors into the other when they are stacked in one orientation. The doors are held by Polymagnet-style twist latches or a nitinol pin and re-latch on separation; a foam-lined sleeve kills the thud, and the lower box is set down at the same instant to cover it. No magnets act through the table, and the scale is the convincer.
BOM: tungsten cube ($40 and up), printed boxes, latch parts: about $70. Difficulty: medium (silent transfer, hidden door seams). Risks: noise; the shifted centre of mass as the slug moves. Novelty: medium to high.

**4.9 The thread that leaves (L2, self-cutting hook-up).**
Effect: a borrowed ring floats and turns between the hands, drifts to the spectator's open palm, and stays there. They keep it; there is nothing attached, and no tug or wax pellet.
Method: a single UHMWPE or nylon filament runs through a 2 mm loop of fine nichrome or 0.05 mm nitinol at the body anchor. A one-second pulse melts the filament at the anchor; the far end is simply looped through the ring and falls free, to be drawn off unseen. Variant (speculative): a 10 um tungsten filament as both support and conductor, cut by a brief over-current.
BOM: braided fishing line to harvest filaments ($10), nichrome, coin cell, switch: under $20. Difficulty: low to medium. Risks: a 15 um loose filament left on the spectator; UHMWPE knots slip (use a wrapped anchor). Novelty: medium.

**4.10 The spoon you bent yourself (L1, body-temperature nitinol).**
Effect: a spectator bends a thin key-shaped tag or nail-like pin with their own fingers, closes it in their fist, and feels it straighten.
Method: body-temperature nitinol, shape-set straight; soft at 20 C, recovers at about 35 C. Novelty: low to medium; included because it puts the classic in the spectator's hand. Hysteresis makes it room-dependent.

**4.11 The strap that cannot be pulled (L3, electrostatic clutch; speculative).**
Effect: a ribbon threaded through a slim leather bookmark or luggage tag slides freely for everyone, then for one chosen person it will not move, then it does again.
Method: two interleaved metallised-film strips with a thin dielectric inside the tag form a 2 x 6 cm clutch (calc: up to about 240 N of shear at 300 V from the EPFL figure; expect far less in a hobby build). A 300 V micro-boost and a 10 mAh cell fit in the tag; switching takes 15 ms and is silent.
BOM: about $30. Difficulty: high (dielectric coating quality decides everything). Risks: 300 V must be current-limited to microamps and fully encapsulated; residual charge can delay release. Novelty: high.

Level count: nine of eleven concepts are L2 or L3.

## 5. Dead ends and overhyped items

- **HASEL and dielectric elastomer "artificial muscles".** 10 to 22.5 kV, oil-filled pouches, breakdown failures. Cheap in materials, but not something to hide in a prop near people. Nitinol, pouch motors and clutches cover the same needs.
- **Liquid crystal elastomers, azobenzene light-driven films, 4D hydrogels.** Impressive strains, but lab synthesis and no retail stock found; light-driven versions need UV or high irradiance aimed at the object.
- **Self-healing polymer as cut-and-restore.** Hours to heal, soft rubbery materials, the cut faces must be pressed together and the scar shows. Vitrimers need heat.
- **Electrowetting droplet control.** Works only on a coated electrode board under a thin foil at up to 250 V with tiny drops; reads as a gadget.
- **Ferrofluid and magnetic slime.** Stain everything, and audiences recognise them from videos.
- **Aerogel as "frozen smoke".** $35 to $75 for a small piece that dents and shatters; a science exhibit, not a method. The strong polymer aerogels are more interesting as ultralight load-bearing fillers.
- **Mu-metal as a magnet blocker.** It redirects and saturates; a steel keeper does more for less.
- **Ionic polymer-metal composites.** Millinewton forces and they dry out.
- **Printed ferromagnetic-domain soft robots at full fidelity.** Needs a 2.7 T pulse magnetiser and a direct-ink-write printer, then 30 to 200 mT over the whole object to actuate.
- **Carbon nanotube yarn, recombinant spider silk as thread.** Not purchasable as single filaments in useful form; natural dragline holds under a gram and shrinks when damp.
- **Balancing reaction-wheel cubes as a routine.** The first guess, "there is a motor in it", is correct, and the flywheel is audible.
- **Electroadhesion to arbitrary surfaces (walls, skin).** 0.5 to 1.5 N/cm2 at kilovolts on smooth clean surfaces only.
- **Gallium against bare skin.** Smears grey, supercools and may refuse to re-solidify on cue, and must be kept away from aluminium props and phones.

## 6. Open leads

- Low-Curie soft ferrites and nickel-iron compensator alloys (selectable 30 to 150 C) as cheap alternatives to gadolinium; thermal reed switches as a ready-made part. Not verified this session.
- Retail sources and release data for electrically debonding tape, thermal-release tape (about 90 to 150 C grades) and UV-release dicing tape.
- CubeSat "burn wire" release designs (nichrome through nylon or Dyneema): published hold and release-time numbers would transfer directly.
- Measured force-versus-temperature for a gadolinium slug against a PK-ring-size magnet between 0 and 25 C.
- Sublimation rate of cyclododecane per unit area at room temperature, to turn concept 4.6 into a design chart; also menthol and camphor as faster alternatives.
- Hobby EPM build notes with measured hold and off-state leakage at 10 to 20 mm scale; salvage of the MX Master 3 unit.
- Writing magnetic pixels onto thinner sheet (0.3 mm) laminated inside a playing card, and how many mutually exclusive codes fit on a 20 mm patch.
- Card-thickness layer jamming and clutch stacks: could a whole deck be locked as a block and released?
- Sources and prices for 5 to 10 um tungsten wire and for dark-dyed aramid or UHMWPE single filaments; visibility tests against classic thread under stage and daylight conditions.
- Prices for body-temperature nitinol wire, springs and "separation actuators" (Kellogg's is quote-only).
- Kresling and other bistable origami cells printed in TPU as stored-energy triggers.
- Tungsten-powder-loaded resin or filament densities achievable at home.

## 7. Sources

Opened and read this session:
- https://www.dynalloy.com/tech_data_wire.php - Flexinol force, current, timing and cycle-life table.
- https://en.wikipedia.org/wiki/Nickel_titanium - nitinol transition range, strain, shape setting, self-bending spoon note.
- https://www.kelloggsresearchlabs.com/ - nitinol grades (Body Temp etc.), forms, quote-only pricing.
- https://www.grand-illusions.com/products/nitinol-teaspoon - nitinol trick spoon, 60 GBP.
- https://en.wikipedia.org/wiki/Shape-memory_polymer - SMP versus SMA strain, stress, cost.
- https://morphingmatter.org/projects/thermorph - self-folding FDM prints (CHI 2018).
- https://morphingmatter.org/projects/printed-paper-actuator - conductive PLA on paper actuator (2018).
- https://news.ncsu.edu/2011/11/wmsdickeyfolding/ - light-driven self-folding polystyrene sheets.
- https://wyss.harvard.edu/news/robot-folds-itself-up-and-walks-away/ - Felton et al. self-folding robot, Science 2014.
- https://spectrum.ieee.org/fishing-line-makes-superhuman-artificial-muscles - coiled fishing-line muscles.
- https://tangible.media.mit.edu/project/biologic/ - humidity-driven natto-cell actuators (CHI 2015).
- https://en.wikipedia.org/wiki/Bimetallic_strip - bimetal bending.
- https://en.wikipedia.org/wiki/Electropermanent_magnet - EPM principle, materials, applications.
- https://hizook.com/electropermanent-magnets-programmable-magnets-zero-static-power-consumption-enable-s/ - EPM scaling, pulse figures.
- https://en.wikipedia.org/wiki/Magnetic_switchable_device - rotating-magnet switchable base.
- https://www.polymagnet.com/ - Polymagnet functions and catalogue categories.
- https://amazingmagnets.com/polymagnet - Polymagnet demo kit, $96.54.
- https://hcie.csail.mit.edu/research/mixels/mixels.html - Mixels numbers (pixel size, cost, forces).
- https://arxiv.org/abs/2208.03804 - Mixels paper, UIST 2022.
- https://en.wikipedia.org/wiki/Halbach_array - one-sided flux.
- https://en.wikipedia.org/wiki/Mu-metal - shielding limits.
- https://en.wikipedia.org/wiki/Curie_temperature - Curie points table and applications.
- https://en.wikipedia.org/wiki/Gadolinium - 20 C Curie point, corrosion.
- https://zhaolab.stanford.edu/sites/g/files/sbiybj21256/files/media/file/s41586-018-0185-0.pdf - Kim et al., Nature 2018, printed ferromagnetic domains.
- https://en.wikipedia.org/wiki/Ferrofluid - composition and limits.
- https://en.wikipedia.org/wiki/Magnetorheological_fluid - yield stress, settling.
- https://en.wikipedia.org/wiki/Pyrolytic_carbon - diamagnetism, light-driven motion.
- https://cdn.shopify.com/s/files/1/0766/9855/0605/files/Flexar_12L_Datasheet_Rev1.6.pdf - Flexar PCB coil datasheet.
- https://en.wikipedia.org/wiki/Jean-Eug%C3%A8ne_Robert-Houdin - Light and Heavy Chest history.
- https://en.wikipedia.org/wiki/Gallium - melting point, wetting, embrittlement.
- https://en.wikipedia.org/wiki/Field%27s_metal - composition, 62 C.
- https://en.wikipedia.org/wiki/Polycaprolactone - 60 C mouldable plastic, brand names.
- https://en.wikipedia.org/wiki/Wax_motor - wax expansion and force.
- https://tangible.media.mit.edu/project/jamsheets/ - layer-jamming sheets (TEI 2014).
- https://en.wikipedia.org/wiki/Cyclododecane - residue-free sublimation over days to weeks.
- https://en.wikipedia.org/wiki/Polyvinyl_alcohol - water-soluble PVA uses.
- https://www.smartsolve.com/ - water-soluble paper stock.
- https://en.wikipedia.org/wiki/Silly_Putty - viscoelastic flow.
- https://www.ifixit.com/News/100352/iphone-16-and-16-pro-teardown - electrically debonding adhesive, voltages and times.
- https://en.wikipedia.org/wiki/Self-healing_material - healing times and conditions.
- https://en.wikipedia.org/wiki/Vitrimers - heat-weldable networks.
- https://en.wikipedia.org/wiki/Mechanical_metamaterial - multistable and programmable metamaterial references.
- https://en.wikipedia.org/wiki/Auxetics - negative Poisson ratio structures.
- https://www.epfl.ch/labs/lmts/lmts-research/haptics/textile-clutch - textile electrostatic clutch numbers.
- https://en.wikipedia.org/wiki/Electroadhesion - generic electroadhesion pressures.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC11469257 - Rothemund et al., HASEL progress report, Adv. Mater. 2021.
- https://en.wikipedia.org/wiki/Dielectric_elastomers - DEA strains and failure modes.
- https://tangible.media.mit.edu/project/aeromorph/ - heat-sealed inflatable hinges (UIST 2016).
- https://hackaday.io/project/12142 - OpenDrop electrowetting platform.
- https://www.media.mit.edu/projects/programmable-droplets/overview/ - PCB electrowetting droplets.
- https://en.wikipedia.org/wiki/Electrowetting - EWOD background and limits.
- https://en.wikipedia.org/wiki/Ionic_polymer%E2%80%93metal_composites - IPMC drive and force.
- https://en.wikipedia.org/wiki/Ultrasonic_motor - inaudible piezo motors.
- https://en.wikipedia.org/wiki/Bristlebot - vibration locomotion.
- https://en.wikipedia.org/wiki/Kilobot - 1 cm/s vibration robot, under $15.
- https://news.mit.edu/2013/simple-scheme-for-self-assembling-robots-1004 - M-Blocks flywheel cubes.
- https://robohub.org/swiss-robots-cubli-a-cube-that-can-jump-up-balance-and-walk-across-your-desk - Cubli.
- https://github.com/remrc/Self-Balancing-Cube - hobby reaction-wheel cube parts list.
- https://en.wikipedia.org/wiki/Ultrahydrophobicity - superhydrophobic surfaces.
- https://en.wikipedia.org/wiki/Hydrophobic_sand - magic sand and its 1915 conjuring reference.
- https://en.wikipedia.org/wiki/Synthetic_setae - gecko-type adhesive strengths.
- https://en.wikipedia.org/wiki/Aerogel - density, fragility.
- http://www.buyaerogel.com/ - aerogel retail prices.
- https://www.tungsten.com/products/tungsten-cube - tungsten cube sizes and weights, from $39.99.
- https://en.wikipedia.org/wiki/Invisible_thread - what invisible thread is.
- https://en.wikipedia.org/wiki/Kevlar - 3,000 MPa, 12 um filament reference, UV sensitivity.
- https://en.wikipedia.org/wiki/Ultra-high-molecular-weight_polyethylene - Dyneema strength, creep, melting.
- https://en.wikipedia.org/wiki/Vectran - Kevlar-like strength, low creep.
- https://en.wikipedia.org/wiki/Spider_silk - 2.5 to 4 um, 1.3 GPa, supercontraction.
- https://www.yigalmesika.com/ - thread-device maker (Tarantula, Spider Pen named).

Seen in search results but not opened (or blocked when opened):
- https://www.sparkfun.com/muscle-wire-0-005-diameter-1-foot.html - retail Muscle Wire listing.
- https://www.imagesco.com/nitinol/wire.html - Flexinol retail and 2 to 5% stroke note.
- https://www.rochemodern.com/rm-works/shape-memory-alloy - 35, 45 and 80 C nitinol grades from Kellogg's.
- https://rimstar.org/science_electronics_projects/nitinol_wire_shape_memory_alloy.htm - hobbyist shape-setting notes.
- https://www.walmart.com/ip/1545379120 - nitinol self-bending paperclip novelty.
- https://vanishingincmagic.com/close-up-magic/deformer-menny - Deformer mechanical bending gimmick, $99.95.
- https://softroboticstoolkit.com/publications/artificial-muscles-fishing-line-and-sewing-thread - Haines et al., Science 2014.
- https://pubs.rsc.org/en/content/articlelanding/2012/sm/c1sm06564e - Liu et al., Soft Matter 2012.
- https://dspace.mit.edu/handle/1721.1/60151 - Knaian thesis, electropermanent magnets.
- https://fab.cba.mit.edu/classes/865.18/discrete/micro/knaian_electropermanent.pdf - Knaian thesis copy.
- https://dspace.cvut.cz/bitstream/handle/10467/79592/F3-BP-2019-Martonova-Veronika-Electropermanent_Magnet_Study.pdf - EPM study with OpenGrab figures.
- https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/10971292 - axisymmetric EPM patent.
- https://en.wikipedia.org/wiki/Programmable_magnet - programmed magnets overview.
- https://www.hackster.io/news/carl-bugeja-debuts-microbots-and-four-products-for-miniaturized-robotics-2f6d5bca420d - Flexar / Microbots products.
- https://hackaday.com/2018/07/29/flexible-pcb-becomes-the-actuator - flex PCB actuator.
- https://www.philipharris.co.uk/product/fe00054323 - Field's metal 10 g price.
- https://www.goodfellow.com/p/ga04-lp-000100/gallium-indium-alloy-pellets - lab gallium pricing.
- https://dash.harvard.edu/bitstream/1/41292201/1/55117739.pdf - laminar jamming thesis, n squared stiffening.
- https://arxiv.org/html/2511.07882 - 2025 layer-jamming characterisation.
- https://infoscience.epfl.ch/record/261177 - all-fabric electroadhesive clutch, 10 kg at 400 V.
- https://www.andrew.cmu.edu/user/shc17/Diller_2016_ICRA.pdf - electroadhesive clutch, residual force.
- https://kilthub.cmu.edu/articles/thesis/Design_Characterization_and_Implementation_of_Lightwieght_and_Energy-Efficient_Electroadhesive_Clutches_for_Robotics/7571279 - Diller thesis.
- https://www.mdpi.com/2076-0825/14/12/601 - low-cost 10 kV HASEL supply.
- https://www.hackster.io/news/opendrop-makes-precision-fluid-control-accessible-to-home-science-labs-221d8e3878e - OpenDrop price.
- https://spectrum.ieee.org/mit-deploys-swarm-of-selfassembling-robot-cubes - M-Blocks follow-up.
- https://dspace.mit.edu/handle/1721.1/119098 - Romanishin thesis.
- https://vanishingincmagic.com/magic-accessories/the-strongest-monofilament - magic monofilament, 400 g claim.
