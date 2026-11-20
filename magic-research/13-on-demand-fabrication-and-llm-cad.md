# 13. The prototyping supply chain as of late 2026: on-demand fabrication, custom printing, consumer machines and LLM-assisted design

Slice: tests the "it is now cheap" half of the thesis with real prices and capabilities.
All prices are as of November 2026 unless a different date is given.

**Research limits, stated up front.** The shared web-search budget for the whole project ran out
after my first 14 searches, so most of this report rests on direct fetches of supplier, standards
and paper pages (about 60 pages opened). Several store pages returned errors or script-only
content (Bambu Lab store, xTool, Elegoo, Revopoint, K&J Magnetics, Craftcloud, supermagnete,
Rack Robotics, toddlassen.com, which currently serves unrelated spam). Where a number comes from
my memory instead of a page I opened, it is marked **(unverified)**. I could not search the magic
literature for prior use, so every novelty claim below is my belief, not a checked fact.

## 1. Summary

- **The first unit now costs about the same as the hundredth for most flat and printed things.**
  Five 2-layer boards cost $2 at JLCPCB with a 24-hour build; five flex boards cost the same
  entry price; one custom 55-card deck costs $16.95; a 300-page paperback costs $4.60 to print;
  a single CNC part starts at $5 with a minimum order of one. Setup fees have collapsed, which
  is what makes one-off, personalised and disposable props affordable.
- **Brute-force variety is cheap.** MakePlayingCards prints up to 612 different cards in one
  order for $139, about $0.23 per unique card. Every outcome of a routine can be pre-made as a
  physical object instead of being forced or switched in.
- **A circuit cannot hide inside the thickness of one playing card, but it gets close.**
  JLCPCB flex is 0.07 mm (1 layer) or 0.11 mm (2 layer) finished, and a transparent PET flex is
  0.14 mm. The limit is components: the thinnest common LEDs are about 0.25 mm, so a lit card is
  about 0.5 to 0.6 mm locally against roughly 0.3 mm for a real card. Passive copper (coils,
  antennas, capacitive pads, shims) fits inside a card with room to spare.
- **Thin rigid boards are a standard catalogue option.** FR4 at 0.4 and 0.6 mm, castellated
  modules down to 10 x 10 mm, boards as small as 3 x 3 mm, 4/4 mil traces, and matte black,
  white or clear-over-black finishes that pass as cosmetic parts.
- **Metal is the weak point for services, and coins are a legal problem.** Printed steel is
  $0.21/g and cast silver has 0.6 mm walls with 0.3 mm detail, but neither gives a struck-coin
  surface. US law (18 U.S.C. 489) prohibits making discs "in the likeness or similitude" of
  coins, which is why professional gimmick makers machine genuine coins. Services can make the
  inserts, rings, slugs and brass props around the coin, not the coin.
- **Turnaround from services is 3 to 10 days door to door; "tonight for tomorrow" needs
  in-house machines.** The set that covers most of it: a multi-material FDM printer, a 12K to
  16K resin printer, a craft cutter, and either a small laser or a UV flatbed printer.
- **A consumer UV flatbed printer (eufyMake E1, from $1,799 on sale) prints on arbitrary
  objects** up to 330 x 420 mm with white ink and up to 5 mm of raised texture. This is the
  single machine that most changes "prove ordinariness": printing on genuine cards, real
  product packaging, borrowed-looking objects.
- **Looking factory-made is cheap; looking factory-sealed is cheap too.** Short-run retail
  boxes ("tiny minimums", 7 to 15 business days), holographic stickers (50 minimum, 4 days),
  shrink bags and an impulse sealer cost tens of dollars. Magic makers use almost none of this.
- **LLM-written CAD works for simple parametric parts and fails on multi-step spatial
  reasoning.** Published single-shot results: 92 to 96% of GPT-4 CadQuery programs compile, but
  five-operation parts succeeded only 3 to 30% of the time in an independent 2025 test. What
  makes it usable is a loop the agent can run itself: code CAD, render, measure, check
  interference, slice, then a test print.
- **Electronics-as-code plus headless checks closes the loop for PCBs.** KiCad 9 runs ERC and
  DRC from the command line with JSON output; atopile and tscircuit describe boards in code;
  Wokwi simulates ESP32 firmware in CI. An agent can go from a text description to checked
  fabrication files, with a person still needed for layout judgement and bring-up.

## 2. Catalog: capabilities and prices

### 2.1 PCB fabrication and assembly

**Rigid boards (JLCPCB as the reference).** 1 to 32 layers. FR4 thickness options are 0.4, 0.6,
0.8, 1.0, 1.2, 1.6 and 2.0 mm. Minimum trace/space is 0.10/0.10 mm on 1 to 2 layers and
0.09/0.09 mm on multilayer. Minimum drill is 0.15 mm. Minimum board size is 3 x 3 mm.
Castellated holes need a board of at least 10 x 10 mm and 0.6 mm thick. Solder mask colours are
green, purple, red, yellow, blue, white and black; no clear mask on rigid boards. Entry price is
$2 for 5 pieces; 5 pieces of a 2-layer board build in 24 hours, 4-layer in 2 to 5 days, 6-layer
in 6 to 7 days. Restrictions matter for thin boards: 0.4 mm is ENIG only, not panelised, not
1-layer; 0.6 mm is suggested up to 100 x 100 mm and not offered for 1, 4 or 6 layers.
Sources: JLCPCB capabilities and production-time pages (opened), thickness FAQ (search result).

**Flex.** JLCPCB finished thickness, excluding stiffeners: 1-layer 0.07 or 0.11 mm; 2-layer
0.11, 0.12 or 0.2 mm; transparent PET 0.14 mm (1 layer) or 0.24 mm (2 layer), about 85%
transmittance. Trace/space is 3/3 mil on 1/3 oz copper. Coverlay is yellow, black, white or
transparent. Stiffeners: polyimide 0.1 to 0.25 mm, FR4 0.1 to 1.6 mm, stainless steel 0.1 to
0.3 mm. Maximum size 234 x 490 mm. Entry price $2 for 5 pieces of a 2-layer board up to
100 x 100 mm (JLCPCB says it verified this on 23 October 2026; shipping and duties extra).
PCBWay lists thinner options: 0.025 and 0.05 mm single-layer, 0.08 mm 2-layer, and black FR4
stiffeners from 0.2 mm. OSH Park flex is about 0.23 mm, 6/6 mil, $10 per square inch for three
copies, with clear mask instead of coverlay and no stiffeners; its page currently says turn
times are "temporarily suspended".

**Can a circuit fit inside a playing card, a coin, a laminate?**

| Host | Thickness budget | Verdict |
|---|---|---|
| Playing card, about 0.3 mm (unverified, from memory) | 0.07 to 0.11 mm flex between two split faces | Passive copper only (coil, antenna, capacitive pads, a steel stiffener as a shim). Any soldered part makes a bump. |
| "Thick card" or double card, 0.5 to 0.6 mm | 0.11 mm flex + 0.25 mm LED + faces | Works: NFC-harvesting LED card, no battery. A PCB business card that harvests phone NFC to drive 21 LEDs was on Hackaday in August 2026. |
| Credit-card or poker-chip thickness, 0.8 to 3.3 mm | 0.4 mm FR4 + 1 mm parts + thin cell | Works with a battery: BLE, IMU, haptics. |
| US half dollar, 2.15 mm thick (unverified) | 0.4 mm FR4 + parts, no room for a cell with walls | A genuine-thickness coin cannot hold a powered board plus a battery behind metal faces. A coin stack, a poker chip or a "coin box" can. |

**Assembly.** JLCPCB Economic PCBA: setup fee $8.00 to $8.18, small batches of 2 to 50,
extended (non-stocked-on-feeder) parts $3 to $3.07 each as a loading fee, "basic" parts free
of that fee; Standard PCBA setup is $25.56 single-side or $51.12 double-side. Library: about
700 basic and 300k+ extended parts (JLCPCB help pages, search results; figures differ slightly
between pages). In practice a 20-part sensor board costs $60 to $110 for the first five,
delivered, and the marginal board is $8 to $25. Aisler (EU): about EUR 10 to 12 job fee plus
EUR 0.05 to 0.13 per cm2, minimum 3 boards, Blitz 2-layer from 2 business days (community
posts, undated). Seeed Fusion: 4/4 mil, 24-hour builds, free DFM review; prices only via quote
tool. OSH Park "After Dark" (black substrate, clear mask, bare copper visible): $5 per square
inch for three, 12 to 21 days.

**PCBs as mechanical and cosmetic parts.** A PCB is also a precisely routed, plated,
printed sheet: 0.4 mm black FR4 with gold ENIG lettering is a ready-made "engraved brass
plate", dial, token or box lid at $2 for five. Aluminium-core boards (1 layer, 5 x 5 mm
minimum) are a cheap way to get printed, routed aluminium. Planar coils are free copper:
Carl Bugeja's flex actuators and the 12-layer Flexar board are voice coils made of traces
that flap or push a small magnet (Hackaday.io; Flexar datasheet). PCBWay and JLCPCB both offer
full-colour UV-printed boards (unverified; the PCBWay page I tried returned 404).

*Magic relevance.* Primitives: know, tell, hold/release, conceal, prove ordinariness. A
0.11 mm flex with a 0.1 mm steel stiffener is a custom-shaped shim, antenna and touch sensor
in one part. Known prior use: electronic card and coin products exist in the magic trade, but
I could not check which use custom flex (unverified).

### 2.2 3D printing services

| Process / material | Reference service and price | Tolerance, wall, detail | Notes for props |
|---|---|---|---|
| SLA resin (incl. clear 8001) | JLC3DP from $0.30, 2-day build | down to +/-0.2 mm | Clear resin needs sanding and clear coat to look like glass. |
| MJF nylon PA12 | JLC3DP from $1.00, 3-day build; $0.275/g since Aug 2025 | +/-0.3 mm | Tough, grainy grey; dyeable black; good for mechanisms. |
| SLM steel 316L, titanium TC4 | JLC3DP from $8.00, 3 days; 316L $0.21/g | +/-0.3 mm | Rough as printed; polishable; real metal weight and sound. |
| Cast silver 925 (printed wax) | Shapeways, online order for Natural and Polished | wall 0.6 mm (0.8 polished), detail 0.3 mm, max 89 x 89 x 100 mm, about 3% total shrink, ring bores within 0.05 to 0.10 mm | Also tin brass, tin bronze, copper, gold, platinum, gold-plated and rhodium-plated brass, vermeil. |
| Full colour | Shapeways: MJF full-colour PA12 and "High Definition Full Color" material jetting | not shown | Colour-matched copies of small objects. |
| FDM, SLS, SAF, TPU | Shapeways; JLC3DP also lists SLS, FDM, wax-jet and binder jet | | |

A 30 mm part (about 5 cm3, 5 g in resin) is therefore roughly $1 to $5 in resin or nylon and
$8 to $25 in steel before shipping (my arithmetic from the per-gram and minimum prices above).
An independent 2022 test paid about EUR 1.04 per part for MJF and resin and EUR 8.30 for a
316L part, found MJF precise, SLA off by over 3% on one part, and SLM "surprisingly very
precise" (xyzdims, search result).

**Shapeways status.** Shapeways Inc. went bankrupt in July 2024. The Eindhoven management team
bought the assets, operated first as Manuevo, and relaunched the Shapeways brand in December
2024 with the founders back; in 2025 it added FDM, repriced MJF and SLS, reinstated self-serve
cast metals for eight metals, and acquired the model site Thangs (3DPrint.com, 3D Printing
Industry, Tom's Hardware; search results). Its materials page today lists eight processes.
Current cast-metal prices are only shown in the quote tool; old published figures ($28 to
$48 per cm3 for silver plus a $30 to $45 fee) are a decade old and only indicate scale.

PCBWay lists SLA, DLP, FDM, SLS, SLM (AlSi10Mg, 316L, TC4, tool steel), PolyJet and vacuum
casting, transparent UTR-8100 resin, chrome and gold plating and anodising, with CNC "as fast
as 1 day". Craftcloud, Xometry, Protolabs, Sculpteo, i.materialise and Treatstock: not
checked this session (blocked or not reached); from memory they cover the same processes at
1.5 to 5 times the Chinese price with faster domestic shipping (unverified).

*Legal note on coins and rings.* See 2.4. Cast silver or brass rings, charms, keys, tokens of
your own design and "antique" props are unrestricted. Coins are not.

### 2.3 CNC, sheet, laser, EDM, magnets, optics, moulding

**JLCCNC.** Milling (3, 4 and 5 axis), turning and EDM (sinker and wire) from $5, 3-day lead,
tolerance "down to +/-0.05 mm", minimum order one part. Sheet metal from $0.40, 2 days.
Materials: aluminium 6061 and 7075, brass H59, copper T2, steel, stainless 304, ABS, FR4,
nylon, polycarbonate, PMMA, POM. Titanium is not listed for CNC.

**SendCutSend (US).** No minimum quantity; free US shipping over $39; many small parts price
at a floor of about $19.51 each for one-offs (their own example table: a 1.5 x 3 in acrylic
part, a 2 x 2 in steel part and a small CNC-machined 6061 billet part all show $19.51), with
hardboard at $1.77. The materials list is the useful part for gimmick makers: brass from
1.0 mm, copper from 0.8 mm, titanium from 1.0 mm, stainless from 0.76 mm, acrylic in 10
colours from 1.6 mm, carbon fibre from 1.0 mm, chipboard 0.76 mm, and **1075 blue-temper
spring steel at 0.015 in (0.38 mm)**, which is laser-cut custom flat springs, flippers and
clips to order. Services include bending, tapping, countersinking, hardware insertion,
tumbling, anodising, plating and powder coating.

**How coin-gimmick makers work, and whether services can match them.** From memory
(unverified): Todd Lassen hand-machines genuine coins on a manual lathe with custom collets
and has long waiting lists; Tango Magic (Argentina) machines genuine coins in volume on
production tooling. Tango's site currently lists 22 dollar-coin expanded shells, flipper coins
in several elastic and magnetic systems, and 12 dollar-coin Scotch and Soda sets (opened; no
prices shown). The craft is in work-holding, stretching a shell without thinning the design,
and hand-fitting a nest so the seam is hidden by the rim. A service can turn a brass insert to
+/-0.05 mm, or wire-EDM a slug, for $5 to $40; most services will not accept a customer's
coins as stock, and the fits needed (a shell that drops on by gravity but does not rattle
needs roughly 0.03 to 0.08 mm of clearance, my estimate) are at or beyond standard service
tolerance. The practical answer is brute force: order five inserts stepped by 0.02 mm and keep
the one that fits. Desktop wire EDM (Rack Robotics Powercore) exists but I could not reach the
site; price and accuracy unverified.

**Magnets.** K&J Magnetics and supermagnete custom pages could not be opened. From memory
(unverified): US and EU suppliers quote custom sintered NdFeB from a few hundred dollars
minimum with 4 to 8 week lead; Alibaba suppliers make custom shapes, diametric, multipole and
radial magnetisation from about $50 to $200 minimum order. Stock catalogues already cover
discs from 1 x 0.5 mm, which is usually enough. Safety: larger NdFeB magnets pinch hard,
shatter, and are dangerous near pacemakers and if swallowed.

**Optics.** Not checked this session. From memory (unverified): Edmund and Thorlabs stock
first-surface mirrors and lenses from $15 to $100; AliExpress sells first-surface mirror
offcuts, beam-splitter glass and lenticular sheet for a few dollars; custom-ground lenses from
Chinese shops start around $100 to $300 for a few pieces. Freeform acrylic optics are within
hobby reach: Matt Ferraro's 2021 "magic window" was a 10 x 10 cm acrylic caustic plate with
2 mm of relief, cut on a home-built CNC router in 10 minutes of roughing plus 90 minutes of
finishing with a 1/4 in ball cutter, then wet-sanded 200 to 1500 grit and polished in about
half an hour; his solver is MIT-licensed.

**Moulding and casting.** Protolabs moulds in aluminium tools with lead times "as fast as
1 day" and +/-0.08 mm machining tolerance; no price shown, from memory $1,500 to $5,000 for a
simple tool (unverified). PCBWay offers rapid tooling and vacuum (urethane) casting. For soft
gimmicks, platinum silicone is the hobby route: Smooth-On Dragon Skin 10 Fast is Shore 10A,
8-minute pot life, 75-minute cure, "skin safe" when cured, pigmentable, sold in a 0.91 kg
trial kit (price not shown; about $35 to $45 from memory, unverified). A printed two-part
mould plus Dragon Skin gives fake fingertips, skin patches and soft shells in one evening.
Uncured silicone components and some pigments are irritants; follow the data sheets.

### 2.4 Printing on things

**Custom playing cards.** MakePlayingCards (MPC), poker size 63 x 88 mm, no minimum:
"Buy 1 deck for $16.95" for up to 55 cards. The price table, read in tier order, gives for
1 to 5 decks: 18 cards $10.25, 36 cards $13.85, 55 cards $16.95, 72 cards $20.50, 108 cards
$29.70, and 612 cards $139.00; at 6 to 29 decks the 55-card deck is $12.45 (the page text is
flattened, so the tier mapping is my inference from the sorted values and the $16.95 headline).
Stocks: S30 (blue core, smooth), S33 (black core, smooth), M31 (black core, linen), M28/M29
linen, P10 plastic, and M30 "magic quality" linen air light and M32 linen air, both with a
1,000-deck minimum. Custom tuck boxes, sticker seals, foil and embossing are options.
Every card can differ, front and back (how the product works; the FAQ I opened did not state
it in words). Shuffled Ink (Florida) prints in the USA with "low minimums", smooth or linen;
quote only. WJPC and Ace Card Co. not checked.

How close to Bicycle can one go? Not close, legally: the Rider Back, the Bicycle name and
USPCC's Ace of Spades and Joker art are trademarks, and printers generally refuse them
(from memory; MPC's policy page not found, unverified). Workable routes are (a) your own back
design across the whole routine, (b) splitting and re-gluing genuine cards, (c) buying
USPCC-printed gaff and blank-face stock, and (d) printing your gaff faces directly onto
genuine blank-face cards with a UV flatbed (see 2.6). MPC stock does not feel like USPCC
air-cushion stock to a card handler; to a lay spectator it does. UV-invisible and
thermochromic layers are not a catalogue option at card printers as far as I know
(unverified); they are a DIY overprint (materials: agent 7).

**Books.** KDP paperback print cost is $1.00 + $0.012 per page in black ink: $4.60 for 300
pages, with no setup fee and no minimum. Colour is $8.65 (standard) or $20.50 (premium) for
300 pages. Blurb needs no publication step and no minimum: 6 x 9 paperback $16.03 (200 pages)
or $20.03 (300 pages), hardcover with dust jacket $26.03 or $30.03. From memory (unverified):
KDP proof copies carry a "Not for Resale" band on the cover, so a realistic prop needs a
published title's author copies or a different printer; Lulu allows private one-off printing.
Realism is high for trade paperbacks, since much real publishing uses the same presses; it is
lower for mass-market paperbacks (paper tone, cover stock) and for anything with a known
publisher's logo, which is a trademark issue.

**Banknotes.** United States: colour illustrations of currency are allowed only if under 75%
or over 150% of real size, one-sided, with all files destroyed after use (31 CFR 411.1).
United Kingdom: at least 25% smaller or larger, one side only, SPECIMEN across it in most
cases, no novelty alterations (Bank of England). A full-size, two-sided, realistic note is
illegal to print in both places regardless of intent. Use genuine notes, stage money that
meets the rules, or invented currencies.

**Coins.** 18 U.S.C. 489: whoever makes or possesses with intent to use "any token, disk, or
device in the likeness or similitude as to design, color, or the inscription" of US or foreign
coins is liable to a fine. 18 U.S.C. 331 punishes whoever "fraudulently alters, defaces,
mutilates..." coins, where fraud is the operative element; this is why machining genuine coins
into gimmicks is the trade's long-standing practice. The Hobby Protection Rules (16 CFR 304.6)
require imitation numismatic items to be marked COPY in letters at least 2 mm high. So
casting, printing or striking look-alike coins from scratch is the wrong route; invented
tokens, casino-style chips and challenge coins of your own design are free. Challenge-coin
vendors: typically 50-piece minimum, $3 to $6 each at 100 plus a die fee (unverified). This
is general information, not legal advice.

**Packaging and "factory sealed".** Packlane: custom mailer, shipping and product boxes with
"tiny minimums", inside printing, 7 to 15 business days. Sticker Mule holographic stickers:
minimum 50, 4-day turnaround, free shipping. From memory (unverified): generic tamper-evident
"VOID" and serial-numbered hologram seals are a few cents each from marketplaces; shrink bags
and a heat gun are under $30; an impulse bag sealer is $25 to $40; cellophane deck wrappers
with tear strips are sold to magicians; bench can seamers are roughly $400 to $2,000; a
desktop vacuum former for blister shells is roughly $700. A retail-looking, sealed, barcoded
box for a gimmicked object is therefore a $30 to $100 problem, not a factory problem.

**Other print.** Not checked this session; from memory (unverified): one-off digital
newspapers (Newspaper Club and similar) cost roughly $10 to $30 for a single copy; custom
lenticular prints from online shops start around $10 to $30 each at small sizes; custom
rubber stamps, water-slide decal paper, sublimation blanks, custom fabric (Spoonflower),
custom dice and engraved tokens are all single-digit to low double-digit dollars per piece.

### 2.5 Consumer machines and what each unlocks

Prices marked (u) are from memory and unverified; store pages could not be read.

| Machine class | Examples and 2026 price | What it unlocks in a magic workshop |
|---|---|---|
| Multi-material FDM | Bambu Lab A1 mini to P2S about $200 to $800 with AMS (u); H2D about $1,900 to $3,500 with laser edition (u); Prusa Core One $925 kit / about $1,200 assembled (opened), INDX 8-tool "coming soon"; Prusa XL five heads about $4,000 (u). Bambu's 2026 line-up per Wikipedia: X2D (April), A2L with blade cutter (June), R1 standalone laser (September), H3C tool changer (November). | Overnight housings, holdouts, card boxes, pulls, jigs. Multi-material means rigid plus TPU in one print (living hinges, soft-touch grips, embedded magnets and nuts by pausing), and printed text and wood or marble patterns without paint. |
| Resin, 12K to 16K | Elegoo Saturn 4 Ultra 16K, Mars 5 Ultra, Anycubic M7: about $270 to $520 (u); XY pixel about 18 to 24 micron (u) | Coin-edge reeding, engraved lettering, threads, copies of small objects at visual fidelity; clear resin; castable wax resin for lost-wax work at a local jeweller. |
| Diode, IR, fibre and CO2 lasers | xTool F1 about $1,100 to $1,500 (u); F1 Ultra 20 W fibre + 20 W diode about $4,000 (u); F2 Ultra 60 W MOPA + 40 W diode (page title confirmed, price not readable); Glowforge Aura/Spark about $600 to $1,200 (u) | Diode: cuts card stock, paper, thin wood and leather; marks anodised and coated metal. Fibre/MOPA: engraves and relief-carves bare metal, including brass tokens and steel. CO2: clear acrylic. Laser-cut card gaffs have a brown edge; a blade cutter does not. Eye hazard: enclosed machines only, never defeat interlocks. |
| Craft cutters | Cricut Explore/Maker, Silhouette Cameo: about $250 to $400 (u) | Clean-edged gaff cards, windows, flaps, stencils, vinyl, kiss-cut stickers, envelopes with secret slits, to 0.1 mm repeatability. The most under-rated tool for card and paper magic. |
| UV flatbed printer | eufyMake E1: from $1,799 on the current sale, up to $1,010 off bundles; 330 x 420 mm; up to 1440 dpi; CMYK + white; raised texture to 5 mm; rotary for mugs and cylinders; UV DTF film (opened) | Full-colour print on genuine cards, coins' packaging, phone cases, pens, lighters, wood, metal, glass, leather. Printed "engraving", fake wear, fake labels directly on real objects; UV DTF transfers for curved things. |
| Desktop CNC | Makera Z1, Carvera Air, Carvera (4th axis and laser modules listed; prices not readable; about $1,000 to $6,000 (u)); Nomad 3 about $2,800 (u); 3018-class $150 to $250 (u) | Brass, aluminium and acrylic parts, PCB milling, freeform acrylic optics, modifying real objects (pockets in books, boxes, coins held in soft jaws). |
| Pick-and-place and reflow | Opulo LumenPnP v4 $1,995 (bundles $2,450 to $7,990), 0402 passives, 0.4 mm pitch (opened); hot plate about $50 to $100 (u) | Not needed for one-offs; a stencil, paste and a hot plate do 0402 parts. Worth it only for selling gimmicks. |
| 3D scanners | Revopoint, Creality, Einstar handhelds about $400 to $1,900 with claimed 0.02 to 0.05 mm accuracy (u; pages not readable) | Copying the outside of small matte objects; fitting a gimmick to a specific real object (a phone, a ring box, a hand). Shiny and transparent objects need scanning spray. |
| Vacuum former, silicone, sewing | Mayku-class former about $700 (u); silicone kits $35+; domestic sewing machine and iron-on bonding web | Blister packs, thin shells of real objects, masks; skin-like gimmicks; pockets, topits and cloth props. |
| Desktop wire EDM, desktop injection | Rack Robotics Powercore (site unreachable); bench injection machines from a few hundred dollars for lever types to $13,000+ for automatic (u) | Hard-metal precision parts and short plastic runs. For selling, not for one-offs. |

### 2.6 LLM-assisted design tooling, and how well it works

**Mechanical CAD.** Three families exist.

1. *Code CAD driven by a general LLM or coding agent* (OpenSCAD, CadQuery, build123d).
   This is the approach with the best evidence. CADAM (open source, 5.4k stars) turns text or
   reference images into OpenSCAD, exposes dimensions as sliders, and runs OpenSCAD in the
   browser with BOSL2. MCP servers let an agent drive real CAD: FreeCAD MCP (3.4k stars:
   create and edit, run Python, screenshots, FEM) and Blender MCP (35k stars; also wraps
   Hyper3D Rodin, Hunyuan3D, Meshy and Tripo generation). Fusion and Onshape MCP servers
   exist (unverified this session).
2. *Dedicated text-to-CAD products.* Zoo's Zookeeper is a conversational agent inside Zoo
   Design Studio with tools to "inspect, snapshot, and debug geometry", producing editable
   KCL code. In the independent CadEval test below, Zoo's earlier text-to-CAD API "did not
   perform particularly well" against general LLMs writing OpenSCAD.
3. *Generative mesh models* (Meshy, Tripo, Rodin, Hunyuan3D, TRELLIS). These turn a photo or
   prompt into a textured mesh. Meshy: free tier 100 credits a month, Pro $20 a month, exports
   STL and 3MF. Hunyuan3D-2.1 is open weights and needs 10 GB of VRAM for shape, 29 GB with
   textures. Good for organic props, figurines, fake food, a plausible copy of a photographed
   object's look. Dimensions are not controlled; they are useless for anything that must fit.

**What the benchmarks say.**

- CADPrompt / CADCodeVerify (Alrashedy et al., 2024 to 2025): 200 objects with expert
  CadQuery. GPT-4 programs compiled 92% zero-shot and 96% few-shot; visual-feedback
  refinement gave about 7% lower point-cloud distance. On "hard" objects one refinement
  method dropped GPT-4's compile rate to 62%. Their checker's answers were correct only 65 to
  68% of the time, and distance metrics missed structural faults such as gaps between a
  desk's legs and top.
- CadEval (Will Patrick, April 2025): 25 single-answer parts, OpenSCAD, pass means volume
  within 2% and bounding box, chamfer and Hausdorff within 1 mm. Reasoning models led. Easy
  parts passed over 80% of the time; five-operation parts passed 3 to 30%; two tasks passed
  0%. Failures were mostly wrong geometry, not syntax: an eyebolt shank extruded
  perpendicular to its ring, a hull used where a loft was needed.
- Text-to-CadQuery (Xie and Ju, 2025): fine-tuned models reach 69.3% top-1 exact match.
  CAD-Coder (Doris et al., MIT, 2025): image to CadQuery with a 100% valid-syntax rate,
  beating GPT-4.5 and Qwen2.5-VL-72B on solid similarity. CAD-Recode (Rukhovich et al., 2024):
  point cloud to executable CAD code, a route from a 3D scan to editable CAD. Text2CAD
  (Khan et al., NeurIPS 2024 spotlight): 660k text annotations over 170k DeepCAD models.
  BlenderLLM/CADBench (Du et al., 2024) and the survey by Zhang et al. (2025, revised March
  2026) frame the field; Makatura et al. (2023) is the foundational study of GPT-4 across the
  design-to-manufacture workflow.

These are single-shot or lightly refined results on models up to early 2025. Current frontier
models with agentic loops do better in my experience of the tooling, but I have no verified
late-2026 number.

**Failure modes that matter for gimmicks.** Parts that look right in a render and do not
assemble (no clearance, mirrored features, a hinge axis off by one wall thickness); wrong
plane or axis; ignoring printing process limits (unsupported overhangs, 0.2 mm walls);
"creative" mechanisms that are kinematically locked; confident wrong arithmetic on stacked
tolerances.

**Workflows that make it reliable** (my assessment):

- Parametric code with named dimensions and one clearance variable per fit.
- A loop the agent runs itself: export STL, read back bounding box and volume, intersect
  mating parts and require zero overlap volume, render fixed views and look at them, then run
  a slicer from the command line for print time and unsupported regions.
- Print a fit coupon first (a ladder of holes or slots at 0.05 mm steps), then feed the
  measured clearance back into the parameter.
- Give the model measured numbers from calipers or a scan; never ask it to guess a real
  object's dimensions.

**Electronics.** KiCad 9's `kicad-cli` runs `sch erc` and `pcb drc` headlessly with
`--format json` and a non-zero exit code on violations, and exports Gerbers, drill, position
files, BOM, STEP and ray-traced renders. That is a complete machine-checkable loop.
Schematic-as-code: atopile (MIT, 4.1k stars) compiles `.ato` modules with units, tolerances
and assertions, picks parts and updates a KiCad layout, and ships agent instruction files;
tscircuit (MIT) describes boards in TypeScript/React, advertises "sub-second routing on
4-layer boards" and ships a skill for coding agents; SKiDL is the older Python option.
Quilter automates placement and routing for KiCad and Altium projects (100 to 1,000
components, through vias only, RF not yet), with a free version whose terms I could not see.
Flux.ai has an AI agent mode but no permanent free tier now: a 7-day trial, then paid for
private projects and export. JITX not checked. LLMs read datasheets well enough to draft pin
maps and register code, and make plausible errors on pin numbers and footprints; check every
pin against the PDF. The Hackaday NFC-harvesting card used an LLM-written script inside KiCad
to draw its antenna, which is typical of where LLMs already help.

**Firmware.** Arduino, ESP-IDF, PlatformIO, MicroPython and CircuitPython are all well
within coding agents' ability for BLE peripherals, IMU gesture detection, haptic patterns and
LED control; ESPHome and WLED remove the code entirely for many lighting and sensor props.
Wokwi's CLI simulates firmware and asserts on serial output and scripted button presses
(free tier: 50 simulated minutes per 30 days, 5 minutes per session). The remaining hard part
is physical: radio range inside a metal or body-worn prop, battery life, and timing.

### 2.7 Worked cost examples

Figures combine prices verified above with component estimates (unverified, marked u).

1. **Coin-sized BLE + IMU + haptic puck, 22 mm round, 4-layer 0.8 mm board.** Boards $2 to
   $10 for five; Economic PCBA setup $8; four extended parts about $12; parts per board about
   $8 to $12 (BLE SoC or module, IMU, haptic driver, charger, passives) (u); 8 mm LRA $1 to
   $2 and 40 to 60 mAh LiPo $3 to $5 each (u); shipping and duty $20 to $40 (u). **About
   $110 to $150 for five working pucks; marginal unit about $20.** Design to delivery 7 to 12
   days. Fits a poker chip, a ring box lid or a deck case; does not fit inside one real coin.
2. **0.5 to 0.6 mm NFC-harvesting LED insert laminated into a "playing card".** 2-layer flex
   0.11 mm, 5 pieces $2 entry, realistically $15 to $40 with ENIG, coverlay choices and
   shipping; four hand-soldered parts (0.25 mm LED, NFC or rectifier parts) under $2 a card
   (u); two faces from a split card or printed 0.1 mm stock. **About $40 for five cards.**
   Thicker than a real card by about 0.25 mm at the components: passes in the hand, fails a
   riffle by a card worker. Lights only near a phone or a hidden reader coil.
3. **Custom 56-card gaffed deck.** MPC up-to-72-card tier: **$20.50 for one deck**, or 55
   cards for $16.95; add a custom tuck box and shipping (u, roughly $10 to $20). Ten or more
   decks drop to $12.45 for 55 cards. All 56 cards can be different at no extra cost.
4. **Fake ring or shell-type metal prop.** Own-design ring in cast silver or brass from
   Shapeways: 0.6 mm minimum wall, 0.3 mm detail, bores within 0.05 to 0.10 mm; price by quote
   tool, roughly $25 to $80 from memory (u). SLM 316L from JLC3DP: about 5 g, so the $8
   minimum applies, then hand polishing. Home route: 16K resin print, conductive paint and a
   small copper/nickel plating kit, $50 to $100 in consumables (u; plating chemicals are
   toxic and need gloves, ventilation and proper disposal). **$10 to $80 per piece.** A coin
   shell in the likeness of real money is the legal problem described in 2.4.
5. **200 mm acrylic caustic lens.** Home route: 10 mm cast acrylic sheet about $15 (u), a
   3018-class or better CNC, Ferraro's open solver; scaling his 10 cm plate (100 minutes of
   machining, 30 minutes of polishing) by four in area gives roughly 7 hours of cutting and
   2 hours of polishing. Service route: PMMA 3D-surface milling at JLCCNC or PCBWay; my
   estimate $60 to $200 plus shipping (u), unpolished. **$15 in material at home, $100 to
   $250 from a service.**
6. **One-off printed book hiding an e-ink panel.** Blurb 6 x 9 hardcover, 300 pages, $30.03,
   no minimum; or two KDP paperbacks at $4.60 each. Waveshare 7.5 in raw e-paper panel,
   800 x 480, 0.98 to 1.18 mm thick, 0.4 s partial refresh, $47.99; ESP32 driver board $15 to
   $20 (u); 1 mm LiPo $8 (u). A 1.2 mm pocket cut through about 12 leaves with a craft cutter
   or laser, a printed page laminated over the panel as a diffuser. **About $110 to $130.**

### 2.8 Turnaround: what can be designed tonight

| Source | Design-to-hand |
|---|---|
| Own FDM or resin printer, craft cutter, laser, UV printer | Same night |
| JLCPCB bare 2-layer boards | 24 h build + 2 to 5 days courier (u) |
| JLCPCB 4-layer or assembled | 2 to 5 days build + courier; about 7 to 12 days |
| JLC3DP / JLCCNC | 2 to 3 days build + courier |
| SendCutSend | "a matter of days" within the US |
| Sticker Mule stickers | 4 days |
| MPC cards, POD books | about 1 to 3 weeks (u) |
| Packlane boxes | 7 to 15 business days + shipping |

So a prop personalised to one audience is an overnight job only for printed plastic, cut
paper and UV-printed objects; anything with a custom PCB or custom-printed deck needs a
week's notice.

## 3. Capability primitives

1. *Now possible:* 612 different printed cards in one order for $139 ($0.23 each), or a
   unique 55-card deck for $16.95. *Because:* digital card presses with no plate cost.
   *Before:* hand-made gaffs or stock gaff decks. *Primitives:* control chance or choice,
   duplicate, prove ordinariness.
2. *Now possible:* a custom copper pattern 0.07 to 0.11 mm thick, any outline to 234 x 490 mm,
   five copies for $2. *Because:* commodity flex PCB. *Before:* no way to put a custom coil
   or sensor inside paper. *Primitives:* know, conceal.
3. *Now possible:* a see-through circuit (85% transmittance PET, 0.14 mm). *Because:*
   transparent FPC. *Before:* wires had to be hidden behind opaque surfaces. *Primitives:*
   conceal, tell.
4. *Now possible:* a rigid 4-layer computer with radio and motion sensing in a 22 mm disc for
   about $20 marginal, assembled by the factory. *Because:* Economic PCBA at $8 setup.
   *Before:* $200+ commercial electronic gimmicks, one design per trick. *Primitives:* know,
   tell, delay.
5. *Now possible:* matte-black or gold-lettered 0.4 mm FR4 plates, tokens and lids for $0.40
   each. *Because:* PCBs as cosmetic parts. *Before:* engraved brass at $20+ each.
   *Primitives:* prove ordinariness, conceal (the "nameplate" is the antenna).
6. *Now possible:* laser-cut 0.38 mm blue spring steel in any outline from a web upload.
   *Because:* SendCutSend's material list. *Before:* hand-filed feeler gauge and clock
   spring. *Primitives:* hold/release, move.
7. *Now possible:* a one-off metal part to +/-0.05 mm from $5, minimum one, 3 days; or five
   size-stepped variants for under $40 so one fits by selection. *Because:* JLCCNC-class
   services. *Before:* knowing a machinist. *Primitives:* hold/release (friction and air
   fits), duplicate.
8. *Now possible:* real silver, brass or steel in your own shape with 0.3 mm detail for $10
   to $80. *Because:* printed-wax casting and SLM by web order. *Before:* a jeweller's
   commission. *Primitives:* duplicate, transform, prove ordinariness (weight and ring).
9. *Now possible:* a bound book with any text on any page for $4.60 and no setup. *Because:*
   print on demand. *Before:* published book tests in fixed editions costing $50 to $300 (u).
   *Primitives:* control choice, know, prove ordinariness.
10. *Now possible:* a different book for each show (page 137 names tonight's venue) at $4.60
    to $30 a copy with one to three weeks' notice. *Because:* no minimum, no plate.
    *Before:* impossible. *Primitives:* delay, control choice.
11. *Now possible:* full-colour print with white underlay directly on a real object up to
    330 x 420 mm, overnight, at $0.16 to $2.45 of ink per item (vendor figures). *Because:*
    consumer UV flatbed. *Before:* stickers, decals, hand painting. *Primitives:* transform,
    duplicate, prove ordinariness.
12. *Now possible:* retail-grade printed cartons in tiny quantities, holographic seals from
    50 pieces, shrink and tamper bands for cents. *Because:* short-run packaging services.
    *Before:* props came in velvet bags, which say "magic prop". *Primitives:* prove
    ordinariness (looks sealed, looks bought).
13. *Now possible:* cut paper and card to about 0.1 mm with no scorched edge, hundreds of
    identical pieces. *Because:* $250 to $400 craft cutters. *Before:* scalpel and steel
    rule. *Primitives:* conceal (flaps, windows, slits), swap.
14. *Now possible:* surface detail at about 20 micron pixels on a $300 to $500 machine.
    *Because:* 12K to 16K mono LCD resin printers (u). *Before:* injection tooling.
    *Primitives:* duplicate, conceal (seams finer than the eye resolves).
15. *Now possible:* rigid and rubber in one printed part, with printed-in colour.
    *Because:* multi-material FDM. *Before:* glued assemblies. *Primitives:* hold/release
    (compliant latches), move.
16. *Now possible:* a copy of a small matte object's outside shape within a few hundredths
    of a millimetre in an evening (u for accuracy). *Because:* $400 to $900 handheld
    scanners plus resin printing. *Before:* moulding and casting. *Primitives:* duplicate,
    swap.
17. *Now possible:* a plausible 3D model of an object from one photo in minutes, free or $20
    a month. *Because:* image-to-3D models. *Before:* a sculptor. *Primitives:* duplicate
    (appearance only, not dimensions).
18. *Now possible:* a dimensioned enclosure or jig from a paragraph of text and caliper
    readings, in minutes, with the fit corrected after one test print. *Because:* LLM code
    CAD with render-and-measure loops. *Before:* weeks of learning CAD. *Primitives:* all;
    it lowers the cost of trying.
19. *Now possible:* a schematic and board checked by ERC and DRC without opening a GUI.
    *Because:* kicad-cli, atopile, tscircuit. *Before:* an electronics engineer.
    *Primitives:* know, tell.
20. *Now possible:* skin-soft Shore 10A parts from a printed mould in 75 minutes.
    *Because:* platinum silicone kits. *Before:* latex dipping. *Primitives:* conceal,
    hold/release.
21. *Now possible:* a freeform acrylic optic cut on a hobby mill in under two hours per
    100 cm2. *Because:* open caustic solvers and cheap CNC. *Before:* lab optics.
    *Primitives:* tell, delay (the message exists only under one light).
22. *Now possible:* planar coils as free copper that push or sense a magnet. *Because:*
    multilayer PCB at commodity price. *Before:* hand-wound coils. *Primitives:* move,
    know, hold/release.

## 4. Capabilities that are newly cheap and that magic makers appear not to be exploiting

Level tags follow the brief: L1 the phenomenon is the effect, L2 a hidden input to a
classical method, L3 a new method architecture. Novelty is my unverified belief.

1. **Every-outcome decks (L3).** *Prop:* a 52-card "prediction deck" in which each card's
   back carries a different full-colour photograph of the same spectator-free scene with one
   named card in it. *Effect:* any freely named card is the only one whose back shows the
   prediction. *Method:* all outcomes are pre-printed; one unique deck is $16.95, and classical
   handling limits what is shown. *Risk:* the too-perfect "they are all different" theory,
   cancelled by showing a few backs alike with a double lift. *Difficulty:* low. *Novelty:*
   the principle (multiple outs) is old; doing it at full-deck scale per show is cheap only
   now.
2. **The audience-specific book (L3).** *Prop:* a paperback whose pages 100 to 200 each
   contain tonight's host's name or the venue in the first line. *Effect:* a free page choice
   in an "ordinary novel" yields a word the performer could not know, and the book is given
   away. *Method:* a public-domain novel re-typeset with force words, printed for $4.60 to
   $30. *Cost:* under $40 a show. *Risk:* lead time of one to three weeks; examine-proof only
   if the edits read naturally (an LLM does the rewriting). *Novelty:* high for per-show
   editions.
3. **Sealed-retail packaging as the convincer (L2).** *Prop:* a gimmicked deck, pen or cube
   inside a printed carton with barcode, hologram seal and shrink wrap, opened by the
   spectator. *Method:* Packlane or MPC tuck box, sticker seals, shrink bag and heat gun.
   *Cost:* $2 to $5 a unit after a $50 to $100 first order. *Risk:* an invented brand is fine;
   copying a real brand's trade dress is not. *Novelty:* resealing real cello is known;
   manufacturing your own "retail" is rare.
4. **Printing on the genuine article (L2).** *Prop:* a spectator's signed card that later
   carries a printed photograph of their own signature on a duplicate, or a real coin's
   cardboard holder, a real lighter, a real pen with altered text. *Method:* UV flatbed print
   onto genuine blank-face or ordinary objects overnight. *Cost:* machine $1,800+; cents per
   print. *Risk:* UV ink gloss and feel differ from offset print; needs matte coat tests.
   *Novelty:* medium to high.
5. **Flex-PCB copper as the secret layer in paper (L2).** *Prop:* an envelope, a card box
   flap or a book cover with a 0.1 mm coil and capacitive pads inside the paper, read by a
   hidden reader in the table or wallet. *Effect:* the performer knows which of five sealed
   envelopes is held, or when a box is opened. *Cost:* $2 to $40 for five inserts plus a $20
   reader. *Risk:* range of a few centimetres. *Novelty:* RFID stickers are used; custom
   shaped, paper-thin, multi-function inserts are not common (unverified). Sensing details:
   agent 14.
6. **Tolerance ladders for air and friction fits (L2).** *Prop:* a brass tube and plug that
   sinks slowly on an air cushion for the performer and sticks for the spectator, set by which
   of two near-identical plugs is in play. *Method:* order five plugs stepped by 0.02 mm for
   about $40 and select. *Risk:* temperature and dirt change the fit. *Novelty:* the
   air-fit principle is old; buying it by web quote is new.
7. **PCB nameplates that are the device (L3).** *Prop:* a wooden box with an "engraved
   brass" maker's plate that is a 0.4 mm ENIG board carrying an NFC antenna, a touch sensor
   and a Hall sensor on its hidden side. *Effect:* an examinable antique box that knows what
   is put in it. *Cost:* $2 for five plates plus $15 of parts. *Risk:* low. *Novelty:* high,
   I believe.
8. **Custom spring-steel parts by upload (L2).** *Prop:* a flipper, card clip, holdout
   catch or snap-through bistable strip cut from 0.38 mm blue steel to an LLM-drawn DXF.
   *Cost:* about $20 to $39 an order. *Risk:* burrs need stoning. *Novelty:* low as an
   object, new as an accessible process.
9. **Scan, shell, swap (L2).** *Prop:* a thin printed shell that fits over one specific
   everyday object (a particular lip balm, a specific dice set, a bottle cap), carrying a
   different colour or number. *Method:* handheld scan, offset the surface by 0.3 mm in CAD,
   resin print at 16K, paint or UV print. *Cost:* consumables under $5. *Risk:* gloss and
   colour match under close light. *Novelty:* shells are classical; fitting them to arbitrary
   borrowed-looking objects in an evening is new.
10. **Silicone skin gimmicks from printed moulds (L2).** *Prop:* a thumb-pad overlay with an
    embedded 0.1 mm flex coil or magnet, colour-matched to the performer. *Cost:* $40 kit.
    *Risk:* edges show at close range under raking light. *Novelty:* medium. Skin-contact
    safety: use certified skin-safe silicone only.
11. **Disposable electronics (L3).** *Prop:* an assembled $8 to $20 board sealed into a
    giveaway object (a "lucky token", a sealed prediction box) that does one job once, hours
    after the performer has left, and is never recovered. *Method:* Economic PCBA makes the
    marginal board cheap enough to give away. *Risk:* lithium cells in giveaways are a safety
    and shipping problem; prefer coin cells or harvested power. *Novelty:* high.
12. **Agent-searched mechanisms (L3).** *Prop:* none directly; a workflow. An agent
    generates 50 parametric variants of a latch, card index or folding path, checks each for
    interference and printability, and the builder prints the top three. *Cost:* filament.
    *Risk:* the checker passes parts that jam in reality; a human must still test. *Novelty:*
    high for magic.

## 5. Dead ends and overhyped items

- **Electronics inside a true-thickness playing card.** Component height, not board
  thickness, sets the limit. Passive copper only, unless you accept a thick card.
- **Printed or cast look-alike coins.** Illegal to make in the US in the likeness of money,
  and the surface never matches a struck coin anyway. Machine genuine coins or avoid coins.
- **Realistic full-size banknote props.** Illegal in the US and UK at real size and two
  sides.
- **Matching Bicycle stock and backs from a custom printer.** Trademarked backs, and the
  premium air-finish stocks have 1,000-deck minimums at MPC.
- **Text-to-CAD for mechanisms in one shot.** Multi-operation parts fail most of the time
  in published tests. It needs the loop and a test print.
- **Image-to-3D for parts that must fit.** Shapes are plausible, dimensions are invented.
- **"AI designs the whole PCB".** Quilter's own limits exclude RF and blind vias; agentic
  EDA still needs a human for antennas, power and bring-up.
- **Service metal printing as finished props.** SLM parts arrive rough and need hand
  finishing; tolerance is +/-0.3 mm at the cheap end.
- **Desktop pick-and-place, wire EDM and injection moulding for one-offs.** They pay back
  only when selling a gimmick in quantity.
- **Wringing fits.** Gauge-block wringing needs sub-micron flatness; no web service sells
  that. Air-damped and friction fits are reachable, wringing is not.

## 6. Open leads

- Verify consumer machine prices and scanner accuracy claims on live pages; the store pages
  were unreadable in this session.
- Get real quotes: a 0.11 mm flex with steel stiffener at JLCPCB, a cast silver ring at
  Shapeways, a 200 mm PMMA surface-milled plate at JLCCNC, a 50-piece printed carton.
- Test UV flatbed printing on genuine USPCC cards for feel, gloss and thickness change.
- Check MPC, Shuffled Ink, WJPC and Ace Card Co. policies on marked backs, near-Bicycle
  designs and special inks; check Lulu private-print pricing and KDP proof markings.
- Rack Robotics Powercore, custom magnet minimums (K&J, supermagnete, Alibaba), custom
  lenticular and one-off newspaper prices: not reachable.
- Fusion and Onshape MCP servers, JITX, and any 2026 benchmark of agentic CAD loops with
  current frontier models.
- Search the magic literature and trade for existing use of flex PCBs, POD book tests and
  self-made retail packaging; I could not, and the novelty claims depend on it.
- Small-scale packaging equipment prices (can seamers, cello overwrappers, blister sealers).

## 7. Sources

Opened this session:

- https://jlcpcb.com/capabilities/flex-pcb-capabilities - flex thickness, trace/space, coverlay, stiffeners, transparent PET
- https://jlcpcb.com/capabilities/pcb-capabilities - rigid thickness, trace/space, castellation, minimum size, mask colours
- https://jlcpcb.com/help/article/pcb-fabrication-services-and-production-time - build times by layer count
- https://jlcpcb.com/blog/flexible-pcb-cost - $2 flex entry price, verified by JLCPCB 23 Oct 2026
- https://jlccnc.com/ - CNC, EDM and sheet-metal starting prices, tolerances, materials, MOQ 1
- https://sendcutsend.com/pricing/ - no minimum, example part prices, free shipping threshold
- https://sendcutsend.com/materials/ - material and thickness list including 0.015 in spring steel
- https://sendcutsend.com/faq/ - services list
- https://www.pcbway.com/rapid-prototyping/ - PCBWay CNC, 3D printing, moulding, finishes
- https://www.cnx-software.com/2024/03/25/pcbway-adds-new-parameters-to-its-flexible-pcb-manufacturing-services/ - PCBWay 0.025 to 0.08 mm flex, black FR4 stiffeners
- https://docs.oshpark.com/services/flex/ - OSH Park flex stackup, price, suspended status
- https://www.seeedstudio.com/fusion_pcb.html - Seeed Fusion specs and turnaround
- https://www.opulo.io/products/lumenpnp - LumenPnP v4 price and capability
- https://hackaday.com/2026/08/31/building-an-energy-harvesting-business-card/ - NFC-harvesting LED card, LLM-scripted antenna
- https://www.shapeways.com/materials - current Shapeways processes and materials
- https://www.shapeways.com/materials/silver - cast silver walls, detail, shrinkage, finishes
- https://www.makeplayingcards.com/design/custom-blank-card.html - MPC price table and card stocks
- https://www.makeplayingcards.com/faq-photo.aspx - MPC tuck box, seals, foil options
- https://shuffledink.com/custom-playing-cards/ - Shuffled Ink overview
- https://kdp.amazon.com/en_US/help/topic/G201834340 - KDP paperback print-cost formula
- https://www.blurb.com/pricing - Blurb trade book one-off prices
- https://www.packlane.com/ - short-run custom boxes, lead times
- https://www.stickermule.com/products/holographic-stickers - holographic sticker minimum and turnaround
- https://www.waveshare.com/7.5inch-e-paper.htm - 7.5 in e-paper price, thickness, refresh
- https://www.smooth-on.com/products/dragon-skin-10-fast/ - silicone hardness, cure, skin-safe statement
- https://www.eufymake.com/ and https://www.eufymake.com/eufymake-uv-printer-e1 - E1 sale price and specifications
- https://en.wikipedia.org/wiki/Bambu_Lab - printer line-up and 2026 release dates
- https://www.prusa3d.com/ and https://www.prusa3d.com/product/prusa-core-one/ - Prusa line-up, Core One price
- https://www.makera.com/ - Makera CNC line-up and modules
- https://www.tangomagic.com/ - Tango coin gimmick catalogue
- https://mattferraro.dev/posts/caustics-engineering - hobby-CNC acrylic caustic lens, times and method
- https://www.law.cornell.edu/uscode/text/18/489 - likeness of coins
- https://www.law.cornell.edu/uscode/text/18/331 - fraudulent alteration of coins
- https://www.law.cornell.edu/cfr/text/31/411.1 - colour illustrations of US currency
- https://www.law.cornell.edu/cfr/text/16/304.6 - COPY marking on imitation coins
- https://www.ftc.gov/legal-library/browse/rules/hobby-protection-act - Hobby Protection Act overview
- https://www.bankofengland.co.uk/banknotes/using-images-of-banknotes - UK banknote reproduction rules
- https://arxiv.org/abs/2505.08137 - Zhang et al., LLMs for CAD survey (2025, rev. 2026)
- https://arxiv.org/html/2410.05340v2 - Alrashedy et al., CADCodeVerify and CADPrompt results
- https://arxiv.org/abs/2409.17106 - Khan et al., Text2CAD, NeurIPS 2024
- https://arxiv.org/abs/2412.14203 - Du et al., BlenderLLM and CADBench
- https://arxiv.org/abs/2505.14646 - Doris et al., CAD-Coder
- https://arxiv.org/abs/2505.06507 - Xie and Ju, Text-to-CadQuery
- https://arxiv.org/abs/2412.14042 - Rukhovich et al., CAD-Recode
- https://arxiv.org/abs/2307.14377 - Makatura et al., LLMs in design and manufacturing
- https://willpatrick.xyz/technology/2025/04/23/teaching-llms-how-to-solid-model.html - CadEval independent benchmark
- https://zoo.dev/text-to-cad - Zoo Zookeeper CAD agent
- https://github.com/Adam-CAD/CADAM - open-source text-to-OpenSCAD app
- https://github.com/neka-nat/freecad-mcp - FreeCAD MCP server
- https://github.com/ahujasid/blender-mcp - Blender MCP server and generative backends
- https://www.meshy.ai/pricing - Meshy plans and export formats
- https://github.com/Tencent-Hunyuan/Hunyuan3D-2.1 - open image-to-3D model, VRAM needs
- https://docs.kicad.org/9.0/en/cli/cli.html - kicad-cli ERC, DRC and export commands
- https://github.com/atopile/atopile - atopile hardware-as-code
- https://tscircuit.com/ - tscircuit
- https://www.quilter.ai/ - Quilter capabilities and limits
- https://www.flux.ai/p/pricing - Flux plans, no permanent free tier
- https://docs.wokwi.com/wokwi-ci/getting-started - Wokwi CI limits and test features

Seen in search results, not opened:

- https://jlcpcb.com/help/article/pcb-assembly-price - PCBA setup and extended-part fees
- https://techoverflow.net/2024/04/09/jlcpcb-pcba-assembly-price-overview/ - PCBA fee overview
- https://jlcpcb.com/resources/pcb-thickness - 0.4 and 0.6 mm board restrictions
- https://jlcpcb.com/blog/jlcpcb-launches-transparent-fpc-see-innovation-in-a-new-light - transparent FPC
- https://www.hackster.io/diyguyChris/diy-transparent-led-matrix-d49616 - 150-LED transparent flex matrix
- https://hackaday.com/2025/07/25/transparent-pcbs-trigger-90s-nostalgia - transparent PCBs
- https://jlc3dp.com/ and https://jlc3dp.com/blog/drastic-material-price-cuts-and-adjusted-post-processing-service-fees - JLC3DP prices
- https://xyzdims.com/?p=18110 - independent 2022 test of JLC 3D printing
- https://oshpark.com/pricing and https://docs.oshpark.com/services/afterdark/ - OSH Park pricing, After Dark
- https://community.aisler.net/t/our-simple-pricing/102 - Aisler pricing model
- https://hackaday.io/project/159936-flexible-pcb-actuator - Bugeja flex PCB actuator
- https://cdn.shopify.com/s/files/1/0766/9855/0605/files/Flexar_12L_Datasheet_Rev1.6.pdf - Flexar 12-layer coil
- https://hackaday.io/project/177897-beeping-blinking-business-card-badge-b4 - sub-1 mm flex badge, thin LEDs
- https://3dprint.com/314952/shapeways-relaunched-with-all-assets-under-one-roof/ - Shapeways relaunch
- https://3dprintingindustry.com/news/shapeways-expands-3d-printing-capabilities-237949/ - cast metals reinstated
- https://www.tomshardware.com/3d-printing/newly-resurrected-shapeways-acquires-thangs-in-surprising-announcement - Thangs acquisition
- https://www.tctmagazine.com/tct-events/cast-yourself/ - historic Shapeways silver pricing
