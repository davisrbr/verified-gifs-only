# 25. Thinness, concealment volume and rapid duplication

Slice: the geometry of secrecy. Part A asks how thin, small and light functional things can now be
made and where ordinary objects have unused volume. Part B asks how fast and how faithfully an
object, or its identifying marks, can be duplicated.

Conventions: "(unverified)" marks a figure recalled from memory or estimated by me and not
confirmed against a page in this session. "(seen in search results, page not opened)" marks a URL
whose content I only saw as a search snippet. Prices are as of late 2026 and come from the page
cited. The shared web-search budget ran out part-way through; the gaps this left are listed in
section 6 and in the hand-back note.

## 1. Summary

- **The useful unit of thinness in card magic is "one card" = about 0.30 mm and 1.8 g (about
  320 g/m2).** A split card half is about 0.12 to 0.17 mm. Several functional materials now fit
  inside that budget with room to spare and can be ordered by a hobbyist: laser-cut 304 stainless
  at 0.03 to 0.10 mm from PCB-stencil houses (from about $3 a sheet), photo-etched metals down to
  0.01 mm, polyester film at 1.4 to 12 microns, and 0.2 mm resin-printed walls.
- **PCB solder-paste stencils are an overlooked precision sheet-metal service.** JLCPCB cuts 304
  stainless from 0.03 to 0.5 mm with apertures down to about 0.08 mm, in any outline, for a few
  dollars. That is a spring, hinge, shim, mask and inlay factory for flap cards and thin gimmicks.
- **A "double card" (0.6 mm) is now a viable electronics chassis**: catalogue lithium-polymer cells
  exist at 0.4 mm (7.5 to 30 mAh), which leaves 0.1 mm skins on either side. Pointer to agent 14.
- **The coin shell remains a craft secret**: I found no published wall thickness or fit tolerance
  for an expanded shell, only makers' statements that each coin in a set is trued to identical size
  and the shell expanded "only enough". The modern route is not to beat the turners at coins but to
  apply the shell principle to any scanned object (0.02 to 0.05 mm scanners, 0.2 mm resin walls,
  0.1 mm electroformed copper).
- **Concealment-by-angle is available as a 0.5 mm film**: micro-louvre light-control film passes
  light within a 60 degree cone and is black outside it. Nothing in the magic literature I searched
  uses it as a one-viewer window.
- **Tearing is more reproducible than magicians assume, crumpling is less.** Fracture-mechanics
  work treats tear paths in thin sheets as reproducible and steerable by pre-cuts and perforations,
  while crumple networks are not reproducible in detail (only total crease length is). So a
  "programmed tear" is plausible and a "programmed crumple" is not.
- **Fastest credible duplication pipelines**: a printed flat item, about 2 to 4 minutes (scan,
  dye-sub print at 23 to 59 s, cut). A small monochrome solid, about 20 to 40 minutes (silicone
  putty mould cures in 7 minutes, urethane demoulds in 10). Anything needing a scan, print and
  paint is an overnight job, not an interval job.
- **Signature duplication is an established theatrical technique with a deep literature** (the
  Conjuring Archive lists 123 "Signed Duplicate" entries from 1905 on) and current TV practice is a
  person tracing over a lightbox onto a split card layer. A camera plus a pen plotter holding the
  same marker is the obvious unbuilt upgrade.
- **What exposes a duplicate depends entirely on who is looking.** Collectors use a loupe (offset
  rosette versus inkjet dither), weight to 0.03 g, light transmission and feel. Lay audiences apply
  none of these; they check gist, their own mark, and (if they handle it) feel. Match stock and
  finish first, print second.
- **Legal lines are narrow and clear**: no colour reproductions of US currency unless one-sided and
  under 75% or over 150% size with files destroyed; imitation coins must be marked "COPY"; never
  reproduce signatures on anything but theatrical props.

## 2. Catalog

### Part A: thinness and hidden volume

#### A1. The card as a thickness and mass budget

*What it is.* Commonly cited figures for a poker-size card are 0.25 to 0.31 mm thick and 1.75 to
1.8 g; a 52-card deck plus jokers is about 94 g. At 63.5 x 88.9 mm that is roughly 320 g/m2 and a
bulk density near 1.06 g/cm3 (my arithmetic). USPCC cards are two paper plies laminated with an
opaque glue layer, and since about 2013 USPCC has specified stock by measured thickness, not by
grams per square metre; "crushed" stock is the same stock made thinner. When split, forum sources
describe either a thick half and a thin half (a correct-thickness double-backer is one thick plus
one thin) or three layers with the black glue layer discarded.

*References.* PlayingCardDecks, "Factors that affect the handling of a deck"
https://playingcarddecks.com/blogs/all-in/factors-that-affect-the-handling-of-a-deck ; Packlim
dimensions page https://packlim.com/playing-card-dimensions (seen in search results);
theory11 thread https://www.theory11.com/forums/threads/splitting-cards-trouble.35466 (seen in
search results; the page returned 403 when opened).

*Budget arithmetic (mine).* Anything up to 0.30 mm passes as one card and up to 0.60 mm as a
double, which audiences already accept by default. A full-area sheet of 0.05 mm stainless weighs
2.2 g, more than the card itself, so metal inlays must be skeletonised: a 0.03 mm fret covering 20%
of the area adds about 0.27 g. A full-area 0.1 mm PET core weighs 0.78 g and has roughly paper's
modulus, so it is mechanically invisible. Bending stiffness scales with modulus times thickness
cubed, so a stiff layer placed on the neutral axis (the glue line) changes the feel far less than
the same layer on a face: hide stiff things in the middle. Perception thresholds for weight,
thickness and stiffness belong to agent 4.

*Magic relevance.* Conceal, prove ordinariness. Every card gimmick should be designed against this
budget before anything else.

#### A2. Thin metal by service: photo-etching and PCB stencils

*What it is.* Photochemical etching dissolves metal through a photoresist mask, so the part has no
burr and no heat-affected edge. Precision Micro lists sheet from 0.01 mm up to 2.5 mm (steel),
tolerance +/-0.025 mm in the 0.01 to 0.25 mm range, minimum holes and slots of 0.1 mm in the
thinnest gauges, and no minimum order quantity; pricing is per sheet. Fotofab's minimum is two
sheets; Ponoko's guide notes a kerf of up to 0.17 mm. One industrial vendor's FAQ says orders
typically start near $5,000, so vendor choice matters.

The hobby route is the solder-paste stencil. JLCPCB's capability page lists 304 "HTA" stainless,
standard thicknesses 0.10 to 0.20 mm at no surcharge and 0.03, 0.04, 0.05, 0.06 and 0.08 mm at
extra cost, minimum aperture above 0.08 mm, laser cutting tolerance stated as +/-0.003 mm, and
frameless custom outlines up to 650 x 580 mm. Its blog quotes frameless stencils from $3. Loose
foil is cheaper still: 304 stainless strip at 0.01 mm is sold retail (5 m x 12.7 mm for about $37),
and 0.001 inch foil in 100 ft rolls.

*References.* https://www.precisionmicro.com/?p=26 ; https://www.precisionmicro.com/?p=22 (seen in
search results); https://fotofab.com/about-us/faq/ (seen in search results);
https://help.ponoko.com/en/articles/3003413-photochemical-machining-design-guide (seen in search
results); https://jlcpcb.com/capabilities/pcb-stencil-manufacturing ;
https://jlcpcb.com/blog/how-to-choose-an-smt-stencil (seen in search results);
https://homediyer.com/products/stainless-steel-shim-sheet-foil-gasket-0-01-0-6mm (seen in search
results).

*Accessibility.* Off-the-shelf service, $3 to $30 per sheet of parts for stencils; $100 to $400
for a true etched sheet (unverified).

*Magic relevance.* Hold/release, move, conceal. Flat springs, bistable snap elements, flap frames,
card-thickness shims, masks for barrier grids, stiffeners, and ferromagnetic targets all come out
of one drawing. Half-etched fold lines, standard in etched model kits (unverified), would give
hinges with no added thickness. No prior magic use found.

#### A3. Thin films and foils: the lower limits

- Polyester (Mylar): indoor free-flight modellers handle OS7 film at 0.68 microns and UltraFilm at
  1.4 microns (128 mg per 100 sq in, about 2 g/m2), with 5 micron film at 6.8 g/m2 as the ordinary
  "light" grade and iron-on Oracover Air Indoor near 12 microns. NASA's Echo II skin was 9 micron
  boPET between two 4.5 micron aluminium foils. Model Aviation covering-materials article
  https://prod-8babe12b-be845633-ssb7vc4z.app.devpanel.com/article/covering-materials-ff (seen in
  search results); https://en.wikipedia.org/wiki/BoPET .
- Glass: Corning Willow launched at 100 and 200 microns on rolls; I found no current retail
  channel. https://www.corning.com/emea/en/about-us/news-events/features/willow-samples.html (seen
  in search results).
- Polyimide at 7.5 to 25 microns, carbon-fibre laminate at 0.1 to 0.2 mm, and metallised film
  mirrors at 12 to 50 microns all exist (unverified; searches for these were cut off).

*Practical reading.* Below about 5 microns a film is governed by static and air currents and
cannot be handled in performance; 12 to 25 microns is the practical floor for a hinge, a membrane
or a transfer carrier. A stack of fifty-two 12 micron leaves is 0.62 mm, two cards thick.

*Magic relevance.* Conceal, erase evidence. Film hinges replace the paper crease that betrays a
flap card; metallised 12 micron film gives opacity for 17 g/m2.

#### A4. Thin shells: turned, expanded, printed, formed and electroformed

*Benchmark.* The expanded coin shell. I could not find a published wall thickness or clearance
for one. What is on record: a maker selling through Tannen's trues every coin in a set to identical
size and expands the shell only enough to fit those coins; too loose gives play, noise and a
visible rim gap, too tight jams and can destroy the shell; a Morgan dollar set lists at $390.
Machinist forums describe the process only speculatively (press the hollowed coin over
progressively larger mandrels with annealing between passes; one poster's previous machinist
"destroyed 6 expensive silver coins"). A US half dollar is 30.61 x 2.15 mm, a quarter 24.26 x
1.75 mm, so a shell has perhaps 0.2 to 0.3 mm of wall to work with (my inference, unverified).
https://www.tannens.com/products/expanded-shell-set-morgan ;
https://mitxela.com/forum/topic/making-an-expanded-shell-coin ;
https://homemodelenginemachinist.com/threads/magic-coins.22044 ;
https://en.wikipedia.org/wiki/Coins_of_the_United_States_dollar .

*What a hobbyist can now reach by other processes.*

- Resin printing: Formlabs gives 0.2 mm as the minimum wall for SLA, supported or not (Form 4,
  grey resin, 50 micron layers; measured walls came out at 0.18 to 0.26 mm), against 1 mm for FDM
  and 0.6 mm for SLS. Thin walls swell in alcohol during washing.
  https://formlabs.com/blog/minimum-wall-thickness-3d-printing/
- Home electroforming: acid copper bath (200 g copper sulphate, 130 ml battery acid per litre),
  graphite paint on a printed PLA former, about 0.2 A per square inch, roughly 1 W, bath at 35 C.
  The hobbyist source aims for 1 mm walls for engine parts; the process itself deposits "a few to
  several hundred microns" and replicates the mandrel surface. Corners build faster than recesses,
  so thin shells need slow plating and rotation. Home workshops are practically limited to copper,
  which can then take a thin nickel, silver or gold plate.
  https://homemodelenginemachinist.com/threads/electroforming-thin-walled-copper-parts-from-3d-prints.33998/page-2 ;
  https://en.wikipedia.org/wiki/Electroforming (seen in search results);
  https://makezine.com/2020/11/17/this-copper-electroforming-kit-is-just-cool (seen in search
  results). Safety: sulphuric acid, copper salts; nickel salts are sensitisers.
- Vacuum-formed sheet at 0.25 mm and below, and spun or drawn metal shells, exist (unverified; not
  searched).

*Magic relevance.* Conceal, duplicate, prove ordinariness. The interesting move is generalisation:
a scanner with 0.02 to 0.05 mm precision plus a CAD surface offset produces a shell for any small
rigid object, not just coins (see concept 1). Legal note: a cast or electroformed replica of a coin
is an "imitation numismatic item" in the US and must be marked COPY (section B7), which is one
reason gaff makers machine real coins.

#### A5. Flaps and hinges at card scale

*State of the art.* The flap card is old: a dealer catalogue listed one "with rubber" in 1889.
Hondo Chen's Modern Flap Card is the current benchmark, sold as a three-hour tutorial ($11.95)
covering card splitting, the flap and a locking system; its marketing names the classic weakness
as "visible lines and thick creases down the centre". Reviewers report elastic thread and glue,
unspecified elastic diameter, and very low build yield (one buyer got one working card from
fifteen attempts). https://www.ellusionist.com/flap.html ;
https://www.penguinmagic.com/p/14540 (seen in search results);
https://www.conjuringarchive.com/list/category/1725 (seen in search results; 403 when opened).

*What newer fabrication offers (my analysis, no prior art found).* A film hinge of 12 to 25
micron PET laminated in the glue line instead of a creased paper hinge; an etched 0.03 to 0.05 mm
stainless spring and frame replacing hand-tied elastic; registration by fret rather than by eye;
0.5 x 1 mm magnets as latches. Electrostatic, shape-memory and electro-permanent drives belong to
agents 7 and 14. E-paper is the zero-moving-part flap and is agent 14's.

*Sliding-shutter faces.* A barrier grid (the principle of Scanimation books, patented in 1896 and
commercialised as "Magic moving pictures" postcards in 1906) interleaves several images in strips
under a striped mask. Sliding the mask by one stripe width replaces the whole image. With 0.15 to
0.25 mm stripes the stroke is 0.15 to 0.25 mm, and the stack is two films thick. The cost is
brightness: with N images only 1/N of the area shows. See concept 4.
https://en.wikipedia.org/wiki/Barrier-grid_animation_and_stereography

#### A6. Angle-selective and light-absorbing surfaces

- **Micro-louvre film.** 3M ALCF-P light-control film is about 0.5 mm thick with a 60 degree
  viewing cone: transparent inside the cone, black outside. A patent in the same family gives
  typical louvre aspect ratios of 10:1 to 15:1. Laptop and phone privacy filters are the cheap
  source. https://3mcanada.ca/3M/en_CA/p/d/v000202250 (seen in search results);
  https://www.edmundoptics.com/p/12quot-x-115quot-0deg-glossy-3m-light-control-film/10599/ (seen
  in search results). Capability: a window for one seat only. See concept 7.
- **Ultra-black coatings.** Musou Black absorbs 99.4% of visible light when airbrushed in thin
  layers and 98.8% brushed, against 94 to 98% for ordinary black acrylic; about $23 to $28 per
  100 ml. https://www.edmundoptics.com/p/musou-black-absorbing-paint-100-ml/58204/ (seen in search
  results). That is 4 to 10 times less reflected light than a normal matte black, which extends
  black-art wells and cavities to brighter light and closer range. The coating is fragile to touch
  (unverified), so it suits recesses, not handled surfaces.
- **Colour matching.** The Nix Mini 3 sensor ($80 to $130) reports repeatability of 0.1 delta-E on
  white and under 0.5 on paint tiles, and maps a reading to commercial paints.
  https://cdn.shopify.com/s/files/1/0280/3276/1928/files/Nix_Mini-3_Spec_Sheet_V1.0.pdf (seen in
  search results). Capability: paint a cover, plug or patch to match a specific surface from one
  reading. Trade techniques for flesh and surface matching are agent 15's.
- **Printed camouflage.** UV flatbed printing and dye-sublimation put any photographed pattern on
  thin sheet or fabric (machines and services: agent 13). The principle is black art with the
  black replaced by the background's own pattern. See concept 8.
- **Active camouflage.** The reference device is Yu et al., PNAS 2014: a 16 x 16 array on a 1.4 cm
  square, black and white only, thermochromic dye switching at 47 C, 1 to 2 s per change, about
  190 mA per diode at 10.5 V. The authors list colour and texture as open problems. Lab-only, and
  nothing I found in this session changes that assessment.
  https://pmc.ncbi.nlm.nih.gov/articles/PMC4246966

#### A7. Dead volume in accepted objects

Industrial CT is the right reference for internal layouts. Lumafield's public teardown series
covers AirPods (three generations), headsets, pens ("How Four Pens Solve the Same Problem"), a
ketchup cap, packaging and 1,054 lithium cells; its counterfeit AirPods scans show pouch cells
squeezed into round bays, unused space, and **internal dead weights added only to match the heft of
the genuine article**. That is direct evidence that weight is the test consumers actually apply and
that ballast defeats it. https://www.lumafield.com/scan-of-the-month ;
https://lumafield.com/article/pen-comparison-using-industrial-ct (page opened, article body not
retrieved); https://9to5mac.com/2023/11/07/x-rays-airpods-vs-counterfeits/ .

The historical benchmark for detection is the 1953 Hollow Nickel Case: a newsboy noticed a nickel
"felt too light", dropped it, and it popped open. Commercial hollow "spy coins" machined from two
real coins sell for $24 to $70, open with a ring-and-tap tool, hold a micro-SD card in the nickel
and half dollar (reviewers say a quarter is too thin), and "pass except when jingled with other
coins". https://en.wikipedia.org/wiki/Hollow_Nickel_Case ;
https://www.cryptomuseum.com/covert/deaddrop/coin.htm ;
https://wallofsheep.com/products/hollow-spy-coin-u-s-nickel-05 (seen in search results).

Survey table. Dimensions other than the coins are my estimates from memory (unverified) and should
be measured before design; component fits are pointers to agents 7 and 14.

| Object | Usable bay (approx.) | What exposes it without X-ray |
|---|---|---|
| Deck of cards, glued hollow block | 55 x 80 x 13 mm, about 57 cm3 | Cannot be spread or riffled; weight if not ballasted to 94 g |
| Card box (tuck) | 1 mm false wall; flap and thumb-notch zone; cellophane as a sleeve | Flex of the wall; transparency against light |
| "Double card" | 0.4 mm cavity over most of 63 x 88 mm, about 2 cm3 | Stiffness, edge view, riffle sound |
| Sharpie-type marker | Cap about 1 cm3; barrel 4 to 5 cm3 if the reservoir is shortened | Roll test (off-axis mass), rattle, light weight |
| AA cell dummy | 14.5 x 50.5 mm, 8.3 cm3 gross | Weight (alkaline about 23 g); no voltage |
| 16 mm die | about 2 cm3 with 1.5 mm walls | Roll bias, rattle, translucency |
| Coin (nickel, half dollar) | about 0.2 cm3 | Weight, ring when dropped, jingle |
| Stack of 4 quarters | up to 2.5 cm3 as a glued shell | Cannot be spread; sound |
| Disposable lighter, lip balm tube | 2 to 5 cm3 | Function test (flame, twist) |
| Bottle cap | 2 to 4 cm3 above the liner | Must still seal; hand feel of the liner |
| Drink can base dome and rim recess | 8 to 10 cm3 each, outside the pressure wall | Only visible from below or above |
| Earbud case dummy | 10 cm3 or more | Weight and hinge feel (hence counterfeiters' ballast) |
| Credit-card form | 85.6 x 54 x 0.76 mm, 3.5 cm3 | Flex, embossing, edge |
| Phone case back | 10 to 30 cm3 at 1 to 3 mm | Almost never examined |
| Glasses temple | about 1.8 cm3 each | Weight asymmetry |
| USB stick | about 5 cm3 beside a chip-on-board drive | Shake |
| Hollowed book or pad | 200 cm3 and up | Flex and riffle of the block |
| Matchbox drawer false bottom | 2 mm x 48 x 33 mm, about 3 cm3 | Depth by eye, rattle of matches |

*Design rule.* A lay examination is weight in the hand, shake, squeeze, look through against the
light, and "does it work". Fill bays to the original mass (tungsten powder in resin reaches the
density of brass or silver; my estimate is about 11 g/cm3 at 55% by volume), keep the centre of
mass on the original axis, pot anything that could rattle, and keep the object's function.

#### A8. Thin power and electronics (pointer)

Catalogue rechargeable cells exist at 0.4 mm (7.5 to 30 mAh) and 0.5 mm (20 to 48 mAh), sold for
smart cards; thin primary cells also reach 0.4 mm.
https://www.batteryspace.com/ultra-thin-rechargeable-cells.aspx (seen in search results);
https://www.grepow.com/shaped-battery/ultra-thin-battery.html (seen in search results);
https://www.cnx-software.com/2017/09/21/powerstream-lithium-polymer-batteries-are-bendable-and-ultra-thin-0-5-to-2-mm/
(seen in search results). Everything else here is agent 14's.

### Part B: rapid duplication

#### B1. Shape capture

- Structured-light handhelds: Revopoint's MIRACO Plus lists single-frame accuracy up to 0.04 mm
  and precision up to 0.02 mm, runs standalone, and sells for about $1,760 to $1,980. Budget
  tethered units claim 0.02 mm at about $360 (3DMakerpro Seal Lite) and mid-range units 0.1 mm at
  about $900 (Creality Otter); these last two figures come from third-party round-ups.
  https://revopoint3d.com/pages/all-in-one-3d-scanner-miracoplus (seen in search results; body
  truncated when opened); https://us.elegoo.com/blogs/3d-scanning/best-3d-scanners-for-3d-printing-2026
  (seen in search results). Machine detail is agent 13's.
- Phone photogrammetry: Kersten, Sönksen and Przybilla (ISPRS Archives, 2024) photographed 140 to
  380 mm test figures with six phones and compared the meshes against a Zeiss ATOS 5 reference.
  Scale-bar deviations were mostly 0.3 to 0.95 mm; an iPhone 15 Pro Max set processed in the
  Polycam app gave mean deviations of about +0.3 / -0.3 mm with 0.25 mm standard deviation. Phone
  LiDAR is a different matter: about 1 cm, and Polycam quotes +/- half an inch for room captures.
  https://isprs-archives.copernicus.org/articles/XLVIII-2-W8-2024/211/2024/ ;
  https://learn.poly.cam/hc/en-us/articles/50434745985556-How-Accurate-Are-Polycam-Scans (seen in
  search results).

*Reading.* Forty photographs taken openly "for Instagram" give a 0.3 mm copy of a hand-sized
object. That is good enough for anything viewed from a metre and not good enough for a mating fit;
a shell needs the 0.02 to 0.05 mm class.

#### B2. Mould-and-cast duplication at interval speed

Smooth-On Equinox 35 FAST silicone putty: 1 minute work time, about 7 minutes to cure, Shore 35A,
mixed by kneading equal parts. Smooth-Cast 300 urethane: 3 minute pot life, 7 to 10 minute
demould, Shore 70D, white, 80 cps, 1% linear shrinkage, specific gravity 1.05.
https://www.smooth-on.com/products/equinox-35-fast/ ;
https://www.smooth-on.com/products/smooth-cast-300/ . Low-melting bismuth-tin alloy (about 138 C,
about 8.6 g/cm3, unverified) pours into the same silicone and gives a real-metal copy with
plausible weight and sound within a couple of minutes of cooling; pewter cast into silicone is
mentioned in the mitxela thread.

*Timeline (my estimate).* Putty on at T+0, off at T+8, pour at T+9, demould at T+19, trim and
colour to T+30 or T+40. The 1% shrinkage is invisible. Colour and surface are the slow part, so
this suits plain metal, stone, plastic and wax objects. Safety: molten metal near borrowed
property; avoid lead and cadmium alloys; tungsten and metal powders are a dust hazard. Out of
scope and not to be attempted: duplicating keys or anything else that opens, pays or identifies.

#### B3. Print duplication of flat items

- Stock comes first. Lybrary's long-running guide found blank playing-card board with the same
  two-ply, black-core structure, measured its white at RGB 227/229/229 against Bicycle's
  226/226/224, and reported front-to-back printer misregistration of about 0.5 mm. Colour lasers
  (OKI C612, about $600) and pigment inkjets work; dye inks do not. Factory-coated blank Bicycle
  cards need the varnish removed with acetone before ink will hold, according to a Vanishing Inc.
  tutorial listing. https://www.lybrary.com/how-to-make-your-own-playing-cards-a-11.html ;
  https://vanishingincmagic.com/card-magic-downloads/how-to-print-on-playing-cards (seen in search
  results; 403 when opened). RTINGS has a test article on home-printed card proxies:
  https://www.rtings.com/printer/learn/research/printing-playing-card-proxies (body not retrieved).
- One-off custom decks: MakePlayingCards prints 54 different faces with no minimum order, $1.10 to
  $16.90 a deck depending on quantity, with a black-core linen stock option.
  https://www.makeplayingcards.com/design/custom-poker.html (seen in search results).
- Portable printers: Canon SELPHY CP1500 dye-sub, 300 x 300 dpi, card-size print in about 23 s and
  postcard in 41 s by Canon's figures (59 s in an independent review).
  https://canon-europe.com/printers/selphy-cp1500/specifications (seen in search results). Zink
  printers give 2 x 3 inch prints with optional adhesive backing and no ink.
  https://en.wikipedia.org/wiki/Zink_(technology) . Handheld thermal-inkjet printers print a
  12.7 mm band at 600 dpi from a 2 to 12.7 mm stand-off onto card, wood, plastic, metal or fabric
  with quick-dry solvent ink; one marketplace listing was about $240. Generic units, for example
  https://www.newegg.com/p/2D5-00K7-01FC3 (seen in search results; I could not tie the price to
  one specific listing).
- UV printing and UV DTF: desktop UV printers with real raised texture start near $2,100 (eufyMake
  E1) to $2,500 (xTool O1 Omni); UV DTF prints onto film, laminates, and transfers as a tough
  textured decal onto glass, metal, plastic, wood and ceramics but not flexible fabric; the
  laminator adds $400 to $500. https://www.atomm.com/blog/2828-best-uv-dtf-printer . UV ink sits on
  coated card without solvent prep, so it prints directly on real cards (unverified).
- Stamps: a Silhouette Mint makes a custom stamp in 15 to 30 minutes; small diode lasers engrave
  stamp rubber in under 5 minutes by one review; retail same-day pre-inked stamps reach 600 dpi.
  https://onlycaptions.com/best-stamp-making-machines/ (seen in search results);
  https://learn.adafruit.com/laser-custom-stamps?view=all ;
  https://www.officedepot.com/a/products/512955/Same-Day-Pre-Inked-Stamp-710 (seen in search
  results).
- Classic transfers (toner and solvent, gel medium, water-slide, rub-down, blender pen) all work in
  one to fifteen minutes and are decades old (unverified, not searched).

#### B4. Identity marks: signatures and writing on props

*Prior art in magic.* The Conjuring Archive's "Signed Duplicate" category has 123 entries, from
Henry Leslie's "Conjuring with Signatures" (1905) through Oswald Rae's "Creating a Duplicate
Signature" (1930), Lubor Fiedler's clear-tape impression copy (1963), Karl Fulves (the spectator
unknowingly signs the duplicate, 1979), David Acer's "Writing Twice" (1995) and Roberto Giobbi's
ruse in Card College 5 (2003). https://www.conjuringarchive.com/list/category/2762 .

Rory Adams (One Ahead, April 2024) describes current television practice: get the signature early
(a release form, a "camera test", or an earlier trick), or offload the signed card to a backstage
team (through a table trap, or by freezing a camera frame), who place it on a lightbox under the
**split face layer** of a duplicate, trace it, and rubber-cement the layer to its back. He notes
that a whole card is too thick for the lightbox, that the position of the signature is not known in
advance, that the copy "will not always be 100% perfect", and that two people are needed.
https://www.oneahead.com/p/magician-signature-duplicate .

*What technology adds (props only).*

- Pen plotters hold the real pen. AxiDraw-class machines take markers and fountain pens, need
  vector strokes as input, and address an envelope in 2 to 3 minutes; the MiniKit (6 x 4 inch
  travel) sold at $325 and the Bantam NextDraw A4 model at $699. Pressure is fixed, which a felt
  marker hides and a ballpoint does not. https://www.evilmadscientist.com/2016/axidraw/ ;
  https://www.hackster.io/news/bantam-tools-fresh-from-its-evil-mad-scientist-acquisition-launches-the-new-nextdraw-plotter-range-c483cf743665
  (seen in search results);
  https://spectrum.ieee.org/the-axidraw-minikit-is-the-modern-xy-plotter-you-didnt-know-you-wanted
  (seen in search results).
- Handwriting synthesis: Haines, Mac Aodha and Brostow, "My Text in Your Handwriting" (ACM TOG
  2016) renders arbitrary text in a sampled hand. https://www.doi.org/10.1145/2886099 (seen in
  search results). For a performer's own handwriting on their own prediction this is unproblematic.
- Constrain the mark instead of copying it: initials in a printed box, a tick, a single digit, a
  sticker chosen from a sheet. The more constrained the mark, the smaller the set of pre-made
  duplicates that covers it.

#### B5. Reproducible "random" damage

- Tearing. Fracture-mechanics papers treat thin-sheet tear paths as lawful: a Sorbonne study is
  summarised as finding the crack path "highly reproducible in thin sheets" and set by a tearing
  vector plus material anisotropy (https://hal.sorbonne-universite.fr/hal-03402424v1/document ,
  seen in search results; access was blocked when opened); Tallinen and Mahadevan derive laws for
  crack paths in forced tearing (https://arxiv.org/abs/1108.3534); a 1993 paper-science study of
  cartonboard perforations shows the cut-to-gap ratio decides whether a tear follows the line
  (https://bioresources.cnr.ncsu.edu/wp-content/uploads/2020/03/1993.2.1023.pdf , seen in search
  results); and a patent describes film whose perforation pattern steers tears from hole to hole
  (https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/7138169 , seen in search
  results). So a tear can be programmed.
- Crumpling. Gottesman, Andrejevic, Rycroft and Rubinstein (Communications Physics, 2018) found
  that the total crease length of a repeatedly crumpled sheet is a predictable state variable but
  the detailed crease network depends on the whole history. https://arxiv.org/pdf/1807.00899 (seen
  in search results). So two sheets cannot be made to crumple alike.
- Breaking. A fracture surface is a shape like any other and silicone reproduces it to finer than
  the eye resolves (unverified), so "broken halves that fit" can be cast in quantity.

#### B6. How duplicates are detected

Collectors' tests for trading cards, in rough order of reliability: side-by-side comparison with a
known original; a 10x loupe (offset printing shows a rosette of dots with solid, sharp black text
on its own plate; inkjet and laser copies show dither and rosette-built black); weight (1.7 to
1.8 g normal, 1.9 to 2 g foil, with set-specific values quoted to 0.03 g); feel and springiness
("touch is more reliable than sight" for stock); light transmission (many modern fakes pass); UV
(unreliable); bend and rip (destructive).
https://seller.tcgplayer.com/blog/articles/how-to-identify-counterfeit-magic-the-gathering-cards ;
https://blogs.magicjudges.org/europeeast/?p=2518 (seen in search results; 503 when opened);
https://magic.wizards.com/en/news/feature/buyer-beware-2004-04-26 (seen in search results).

*Which would an audience apply?* None of the instrument tests. A spectator checks that the thing
looks like the thing, that their mark is on it, and, if it is in their hands among its fellows,
that it does not feel different. Gloss, slip, stiffness and edge colour are therefore the
priorities; halftone structure is irrelevant unless a camera close-up is involved.

#### B7. Legal lines (stated plainly; not legal advice)

- **Currency.** 31 CFR 411.1 permits colour illustrations of US currency only if they are under
  three-quarters or over one and a half times the size in linear dimension, one-sided, and the
  files, plates and negatives are destroyed after use. A same-size, two-sided copy of a banknote is
  counterfeiting whatever the purpose. Use real notes. https://www.law.cornell.edu/cfr/text/31/411.1 ;
  https://www.bep.gov/currency/currency-image-use (seen in search results).
- **Coins.** The Hobby Protection Act makes it unlawful to manufacture or import an imitation
  numismatic item not plainly and permanently marked "COPY"; the FTC rule sets the size and
  placement. https://www.ftc.gov/system/files/ftc_gov/pdf/Imitation-Coins.pdf (seen in search
  results).
- **Brands.** 18 USC 2320 criminalises trafficking in goods or packaging bearing a counterfeit
  mark, where trafficking means transfer for commercial advantage or gain, or making with that
  intent. A one-off duplicate prop for a show is a different thing from selling replicas, but
  selling gimmicks that carry someone else's registered marks is the risk to avoid.
  https://www.law.cornell.edu/uscode/text/18/2320 .
- **Signatures.** Everything in B4 is about a mark made on a playing card or similar prop, for
  theatre, with the spectator present. It must never be applied to cheques, contracts, identity
  documents, tickets with monetary value, release forms or anything else with legal effect.
  Captured signature images are personal data and should be deleted after the show.

## 3. Capability primitives

1. *Now possible:* cut any outline in springy 304 stainless at 0.03 to 0.10 mm with 0.08 mm
   features for about $3 to $30 a sheet. *Because:* PCB stencil services. *Before:* hand-cut shim
   or hand-tied elastic. *Primitives:* hold/release, move, conceal.
2. *Now possible:* metal parts at 0.01 mm with +/-0.025 mm tolerance and no burr, no minimum
   quantity. *Because:* photochemical etching sold per sheet. *Before:* not obtainable by an
   amateur. *Primitives:* conceal, hold.
3. *Now possible:* a hinge or membrane 12 microns thick weighing 17 g/m2. *Because:* commodity
   polyester film. *Before:* a creased paper hinge that shows as a line. *Primitives:* conceal,
   move.
4. *Now possible:* a rigid shell with 0.2 mm walls fitted to any scanned object. *Because:* resin
   printers plus 0.02 to 0.05 mm scanners at $360 to $2,000. *Before:* a master turner, coins
   only, $390 a set. *Primitives:* conceal, duplicate, swap.
5. *Now possible:* a metal skin about 0.1 mm thick that copies a surface at mandrel fidelity.
   *Because:* home copper electroforming over printed formers, about 1 W of power. *Before:*
   industrial electroforming. *Primitives:* duplicate, prove ordinariness.
6. *Now possible:* a powered cavity inside two cards' thickness. *Because:* 0.4 mm lithium cells of
   7.5 to 30 mAh. *Before:* thinnest powered card gimmick was several cards thick (unverified).
   *Primitives:* know, tell, move.
7. *Now possible:* a panel that is a window inside a 60 degree cone and black outside it, in
   0.5 mm. *Because:* micro-louvre film. *Before:* angles managed by body position only.
   *Primitives:* conceal, know.
8. *Now possible:* a cavity reflecting 0.6% of light instead of 2 to 6%. *Because:* $25 ultra-black
   paint. *Before:* velvet and dim light. *Primitives:* conceal.
9. *Now possible:* a cover matched to a measured surface colour within about 0.5 delta-E.
   *Because:* $100 colour sensors and paint-matching apps. *Before:* mixing by eye.
   *Primitives:* conceal, prove ordinariness.
10. *Now possible:* a cover carrying the photographed pattern of the actual table, mat or cloth.
    *Because:* UV and dye-sub print on demand. *Before:* black art only on black.
    *Primitives:* conceal.
11. *Now possible:* a 0.3 mm copy of a hand-sized object from 40 phone photographs. *Because:*
    phone photogrammetry. *Before:* measuring and sculpting. *Primitives:* duplicate.
12. *Now possible:* a rigid cast copy of a small object 20 minutes after first touching it.
    *Because:* 7 minute silicone putty and 10 minute urethane. *Before:* overnight moulds.
    *Primitives:* duplicate, swap.
13. *Now possible:* a cast copy with the density of brass or silver. *Because:* tungsten-filled
    resin or bismuth-tin alloy in a silicone mould. *Before:* light plastic dummies that fail the
    heft test. *Primitives:* duplicate, prove ordinariness.
14. *Now possible:* fill a hollow gimmick back to its original weight and balance. *Because:* cheap
    tungsten powder and putty; counterfeiters already do it. *Before:* light, rattling fakes.
    *Primitives:* prove ordinariness.
15. *Now possible:* one deck of 54 arbitrary faces and backs on black-core stock for $10 to $17,
    no minimum. *Because:* print-on-demand card printers. *Before:* 1,000-deck minimums or
    hand-made gaffs. *Primitives:* duplicate, control choice, brute-force outs.
16. *Now possible:* a 300 dpi continuous-tone print in 23 to 59 s from a 1 kg battery printer.
    *Because:* compact dye-sub. *Before:* photo lab. *Primitives:* duplicate, delay.
17. *Now possible:* print a 12.7 mm band at 600 dpi straight onto an object in one swipe.
    *Because:* handheld thermal-inkjet coders at about $240. *Before:* pre-printed props only.
    *Primitives:* transform, delay, erase evidence.
18. *Now possible:* a textured full-colour mark on glass, metal or plastic that looks factory
    applied. *Because:* UV DTF from $2,100 desktops or by-the-sheet services. *Before:* decals
    with visible film. *Primitives:* prove ordinariness, duplicate.
19. *Now possible:* reproduce a captured pen stroke with the same pen, in real ink, in about 10 s
    (my estimate). *Because:* $325 to $700 pen plotters. *Before:* a hidden assistant tracing on
    a lightbox. *Primitives:* duplicate, delay.
20. *Now possible:* arbitrary text in a sampled handwriting, drawn with real ink. *Because:*
    handwriting synthesis plus a plotter. *Before:* nail writers (a few characters) or pre-written
    outs. *Primitives:* delay, tell, prove ordinariness.
21. *Now possible:* two or two hundred sheets that tear along the same irregular line.
    *Because:* craft cutters and lasers cutting identical internal pre-cuts; tear paths are lawful.
    *Before:* the torn corner had to be switched. *Primitives:* duplicate, prove ordinariness.
22. *Now possible:* any number of "broken halves" that all fit each other. *Because:* silicone
    moulding of one real fracture, or a scanned fracture surface in CAD. *Before:* each break
    unique. *Primitives:* duplicate, control chance.
23. *Now possible:* change a whole printed face by a 0.2 mm slide inside a 0.3 mm stack.
    *Because:* 1,200 to 2,400 dpi film and UV printing with one-off matching decks. *Before:*
    flaps and lenticulars with visible lenses. *Primitives:* transform, conceal.
24. *Now possible:* see the true internal layout of a consumer product before designing a gimmick
    inside it. *Because:* published industrial CT teardowns. *Before:* destructive teardown.
    *Primitives:* conceal.
25. *Now possible:* a custom stamp from a drawing in 5 to 30 minutes. *Because:* diode lasers and
    thermal stamp makers. *Before:* ordered from a stamp shop. *Primitives:* duplicate.

## 4. Effect concepts

Level 1 means the phenomenon is the effect, level 2 a hidden input to a classical method, level 3
a new method architecture. All eleven below are level 2 or 3. Concepts 1, 4, 5, 6, 8, 10
and 11 rest on capabilities that did not exist, or were not affordable, ten years ago.

**1. Computed shells for the venue's own objects (level 3).**
*Effect.* The magician works with whatever the event supplies: the host's chess pawns, the
company's enamel lapel pin, the bar's own bottle caps. One becomes two, a white pawn turns black in
a closed fist, a cap passes through the table. The objects are the venue's and are left behind.
*Method.* Get one sample a day ahead. Scan at 0.02 to 0.05 mm, offset the surface outward by the
wall thickness plus 0.05 mm clearance in CAD, print the shell in resin at 0.2 to 0.3 mm (or
electroform 0.1 mm copper over a printed core and plate it), finish to match with a colour-sensor
paint match or UV print. The solid pieces are genuine; only the shell is made. Classical shell
handling does the rest. *BOM.* Scanner $360 to $1,980, resin printer about $300, paint; a few
dollars per shell. *Difficulty.* Moderate; finish matching is the skill. *Risks.* A 0.25 mm wall
makes the shelled piece visibly 0.5 mm larger on small objects; resin shells chip; gloss mismatch.
*Novelty.* The shell is ancient; a one-day shell of an arbitrary object supplied by the audience's
own venue is, as far as I can tell, new.

**2. The programmed tear (level 3).**
*Effect.* A spectator tears the corner off a card with their own hands and keeps it. The card is
burned. A card found sealed elsewhere has a missing corner, and the spectator's piece fits it fibre
for fibre. There was no corner switch because the spectator did the tearing.
*Method.* Split each card. On a craft cutter, cut the same irregular line through every face ply,
and a second line offset by 2 to 3 mm through every back ply, then re-laminate with rubber cement.
The card looks and handles as whole, because each ply bridges the other's cut. When torn at that
corner the overlap peels, leaving the bevelled, feathered edge a real tear has, on the same line
every time. The duplicate's corner was removed in advance along the identical cut. *BOM.* Cutter
about $300, cards, rubber cement; cents per card. *Difficulty.* High craft, low cost. *Risks.* The
spectator must tear the right corner (a printed "tear here" would be fatal; a natural thumb notch
or prior crease could guide it); a tear started elsewhere ignores the programme; knife-cut plies
may look too clean under a loupe. *Novelty.* I found nothing like it; unverified.

**3. The interval double (level 2).**
*Effect.* A borrowed ring or keepsake is sealed in a box held by its owner before the interval. In
the second half the "same" object, recognisably theirs down to the dents, is flattened with a
hammer or dropped in acid. The owner opens the box and finds the original intact.
*Method.* The object is offloaded for eight minutes during the first half, pressed in fast silicone
putty and returned to the box. In the interval a bismuth-tin or tungsten-filled casting is made and
coloured. It has the right weight and sound and is destroyed for real. *BOM.* Putty and resin
about $60 in trial sizes, alloy $20, hotplate. *Difficulty.* Moderate, needs an assistant.
*Risks.* Handling borrowed valuables at all (stones, soft metals); hot metal; a poor colour match
on anything but plain metal. *Novelty.* Destroying a look-alike is classical; destroying a
same-day cast of this specific object is a refinement, not a new principle.

**4. The shear-change deck (level 2 to 3).**
*Effect.* A card's back changes from red to blue (or a face from one value to another) under a
fingertip, with no flap, no fold line and no lens, and it lies among the other cards looking the
same as they do.
*Method.* Design a one-off deck whose back is a fine line screen, printed on demand so every card
shares it. The gimmick is two films in a 0.3 mm stack: a lower film with alternating red and blue
stripes at 0.15 to 0.25 mm pitch and an upper clear film carrying opaque white stripes at the same
pitch. Shifting the upper film one stripe swaps the colour everywhere. A stencil-foil frame gives
two detents. *BOM.* Custom deck $10 to $17, film positives or UV print, stencil frame $3 to $10.
*Difficulty.* High: registration must hold to about 20 microns over 80 mm. *Risks.* Moiré flashes
during the slide; the design is locked to a custom deck; half the area is always white, so both
states are pastel. *Novelty.* Barrier grids date from 1896; I found no playing card built on one.

**5. Stencil-foil flap chassis (level 2).**
*Effect.* The standard visual colour change of a flap card, but the card locks flat, survives a
riffle and has no centre crease.
*Method.* One 0.03 mm stainless fret contains the perimeter frame, a bistable leaf spring and
registration tabs; a 12 micron film is the hinge. Fifty frets fit on one stencil. Split card
plies are glued on. The build becomes assembly on a jig instead of freehand craft, which is where
the reported one-in-fifteen yield comes from. *BOM.* Stencil $3 to $30, film, cards.
*Difficulty.* Moderate after the drawing is right. *Risks.* Added mass of 0.3 to 0.5 g; steel
edges cutting through paper over time; a click on actuation. *Novelty.* Unknown in print; the
materials are new to the craft.

**6. Signature by camera and plotter, on a card, for the stage (level 2).**
*Effect.* A spectator signs a card. It is torn up and the pieces burned in their own hand. A card
sealed in a block of ice since before the show bears the signature.
*Method.* A camera watches the signing (in the table, or the "close-up camera" that is there
anyway). Software extracts the strokes. A plotter backstage, holding the same model of marker,
writes them on the duplicate in about ten seconds, and the duplicate is loaded. Because the copy
exists, the original can really be destroyed, which the classical one-card methods cannot allow.
Sleight of hand is still needed for the load, and it is the load people will suspect, not a
machine. *BOM.* Plotter $325 to $700, camera, laptop. *Difficulty.* Software moderate, staging
hard. *Risks.* Stroke extraction from video when the hand occludes the pen; fixed line weight;
latency. *Limits.* Playing cards and similar props only; see B7. *Novelty.* Replaces the human
tracer in a known backstage procedure.

**7. The one-seat window (level 2).**
*Effect.* None visible. The performer knows the card inside a closed case, or reads a cue, in full
view of people standing all round.
*Method.* A panel of micro-louvre film is built into the end of a card case or the top of a
"black glass" coaster. On the performer's axis it is clear; from more than 30 degrees off it is
black plastic. Passive version: tilt the case end toward your eye and read the index. Active
version: a small display under the film shows a cue visible only from one chair. *BOM.* Privacy
filter $10 to $30. *Difficulty.* Low. *Risks.* Anyone directly behind the performer shares the
view; the film has a faint striped texture at close range. *Novelty.* Shiners and peek cases are
old; angle-selective film as the cover appears unused.

**8. Pattern-matched table tiles (level 3).**
*Effect.* Coins and cards vanish and appear on an ordinary patterned close-up mat in normal room
light, with the hands away from the objects.
*Method.* Design the mat as a tessellation with dark joints and have it dye-sub printed on demand.
Print the same pattern on 0.1 to 0.2 mm sheet, cut along the joints, blacken the edges. A tile
lying on the mat is a flap that matches whatever it covers; it is moved by a thread or a magnet
under the mat. For a venue, photograph the tablecloth and print overnight. *BOM.* Printed mat $20
to $30, tiles by UV print or the same dye-sub service. *Difficulty.* Moderate. *Risks.* Raking
light throws an edge shadow; gloss mismatch; parallax from very low seats. *Novelty.* A
generalisation of the black-art well to arbitrary backgrounds; I know of no marketed version
(unverified).

**9. Halves that always fit (level 3 by architecture, old materials).**
*Effect.* A spectator snaps a clay token in two and keeps half. The other half is dropped in a
river on video or ground to dust. A half found in a sealed parcel posted last week fits theirs.
*Method.* Every token is cast as two pieces along one master fracture surface and joined with a
weak bond, so it breaks there every time and any A-half fits any B-half. *BOM.* One silicone
mould, plaster or resin; cents each. *Difficulty.* Low. *Risks.* Tokens that break identically
must never be compared side by side; the weak joint may show as a hairline. *Novelty.* The torn
corner principle moved to a medium where the proof is a three-dimensional fracture; no prior art
found, unverified.

**10. The late edge print (level 3).**
*Effect.* The named card, word or number is found printed across the edge of the squared deck.
After one shuffle it is gone.
*Method.* The guts of a handheld thermal-inkjet coder are built into a wooden card case or deck
stand. As the deck slides home its long edge passes the 12.7 mm print head and receives the text
in under a second, chosen after the spectator speaks. Each card carries a 0.3 mm fragment, so a
shuffle really does erase the evidence. *BOM.* Donor printer about $240, case, microcontroller.
*Difficulty.* High: stand-off, encoder sync and nozzle capping. *Risks.* Solvent smell, wet ink
on fingers, a head that dries out. *Novelty.* Pre-printed edge designs exist; printing one on
demand does not, as far as I know.

**11. A prediction in real ink, written late (level 3).**
*Effect.* A card in a sealed clear box since the start carries the performer's handwritten
prediction of a freely named word. It is handed out; the ink is pen ink and smudges.
*Method.* A two-axis micro plotter in the box lid writes with a marker insert after the word is
known, in strokes synthesised from the performer's own handwriting, then parks. *BOM.* About $40
to $80 in motors, driver and microcontroller. *Difficulty.* High mechanically. *Risks.* Motor
noise, ten to twenty seconds of writing time, the too-perfect problem. *Novelty.* Thermal-print
and e-paper prediction devices exist (agent 2); a real-pen one I have not seen (unverified).

## 5. Dead ends and overhyped items

- **Active camouflage skins.** The best published device is 256 black-and-white pixels at 47 C.
  Not a prop material this decade.
- **Sub-5-micron films as handled props.** They exist and are cheap, but static and air movement
  make them unusable outside a still room.
- **Flexible ultra-thin glass.** No retail supply found, and polyester does the same job without
  the edge fragility.
- **Programmed crumpling.** The physics says the crease network is history-dependent; two balls of
  paper cannot be made to match.
- **Phone LiDAR for object duplication.** Centimetre accuracy. Use photographs, not the depth
  sensor.
- **Scan, print and paint during an interval.** Printing is hours, finishing is hours. Only
  mould-and-cast or flat printing fits in twenty minutes.
- **Stamps as fake handwriting.** Uniform edges and no stroke overlap; passes at a distance only.
- **Electroformed replica coins.** Uneven wall build-up at edges, and the COPY-marking rule.
- **Copies that pass a collector's loupe.** Possible in principle, irrelevant to a lay audience,
  and the wrong place to spend effort; stock and finish matter more.
- **Ultra-black on handled surfaces.** It rubs off and looks like soot (unverified); recesses only.
- **Thin steel as a full-area card core.** At 0.05 mm it already outweighs the card.

## 6. Open leads

- Measured wall thickness and clearance of expanded shells from named makers; nobody publishes it.
- Whether silicone that swells uniformly in solvent, or expanding casting compounds, can make an
  enlarged master for an expanded shell (suggested in the mitxela thread; unverified).
- Half-etch fold lines and bistable geometries in 0.03 mm stainless: a fatigue test is needed.
- The Sorbonne tearing paper and laser micro-perforation of paperboard: read in full, then test
  whether an internal pre-cut really produces a convincing tear edge on playing-card stock.
- Lumafield's pen scans and the RTINGS card-proxy study, neither of which I could read.
- Custom dry-transfer (rub-down) sheets as an index of marks that leave ink and no film.
- Stretched metallised-film mirrors for miniature mirror boxes with no visible edge.
- Kiss-cut depth repeatability of craft cutters on 0.15 mm card plies.
- Stroke extraction from overhead video of a hand signing, with the pen partly hidden.
- NFC inlay and flex-circuit thickness inside a split card (agent 14).

## 7. Sources

Opened in this session:

- https://playingcarddecks.com/blogs/all-in/factors-that-affect-the-handling-of-a-deck - card construction, USPCC stocks.
- https://www.precisionmicro.com/?p=26 - photo-etching thickness, tolerance and feature limits.
- https://jlcpcb.com/capabilities/pcb-stencil-manufacturing - stainless stencil thicknesses and limits.
- https://formlabs.com/blog/minimum-wall-thickness-3d-printing/ - minimum walls by process.
- https://homemodelenginemachinist.com/threads/electroforming-thin-walled-copper-parts-from-3d-prints.33998/page-2 - home copper electroforming recipe.
- https://www.tannens.com/products/expanded-shell-set-morgan - expanded shell fit and price.
- https://mitxela.com/forum/topic/making-an-expanded-shell-coin - speculation on shell making.
- https://homemodelenginemachinist.com/threads/magic-coins.22044 - machinists on coin shells.
- https://en.wikipedia.org/wiki/Coins_of_the_United_States_dollar - coin dimensions.
- https://en.wikipedia.org/wiki/BoPET - polyester film facts.
- https://en.wikipedia.org/wiki/Barrier-grid_animation_and_stereography - barrier-grid history.
- https://www.ellusionist.com/flap.html - Hondo flap card tutorial and reviews.
- https://pmc.ncbi.nlm.nih.gov/articles/PMC4246966 - Yu et al., adaptive camouflage, PNAS 2014.
- https://www.lumafield.com/scan-of-the-month - index of public CT teardowns.
- https://lumafield.com/article/pen-comparison-using-industrial-ct - pen CT article (body not retrieved).
- https://lumafield.com/article/real-vs-fake-apple-products-through-industrial-ct-airpods-pro-macbook-magsafe-charger - CT of batteries and products.
- https://9to5mac.com/2023/11/07/x-rays-airpods-vs-counterfeits/ - ballast weights in fake AirPods.
- https://en.wikipedia.org/wiki/Hollow_Nickel_Case - hollow coin detected by weight, 1953.
- https://www.cryptomuseum.com/covert/deaddrop/coin.htm - hollow coin concealment devices.
- https://isprs-archives.copernicus.org/articles/XLVIII-2-W8-2024/211/2024/ - Kersten et al., phone photogrammetry accuracy (PDF read).
- https://www.smooth-on.com/products/equinox-35-fast/ - 7 minute silicone putty.
- https://www.smooth-on.com/products/smooth-cast-300/ - 10 minute urethane.
- https://www.lybrary.com/how-to-make-your-own-playing-cards-a-11.html - home card printing.
- https://www.atomm.com/blog/2828-best-uv-dtf-printer - UV and UV DTF machines and prices.
- https://en.wikipedia.org/wiki/Zink_(technology) - Zink printing.
- https://learn.adafruit.com/laser-custom-stamps?view=all - laser-engraved stamps.
- https://www.evilmadscientist.com/2016/axidraw/ - AxiDraw capabilities.
- https://www.oneahead.com/p/magician-signature-duplicate - Rory Adams on signature duplication for TV.
- https://www.conjuringarchive.com/list/category/2762 - "Signed Duplicate" literature list.
- https://arxiv.org/abs/1108.3534 - Tallinen and Mahadevan, forced tearing of thin sheets.
- https://seller.tcgplayer.com/blog/articles/how-to-identify-counterfeit-magic-the-gathering-cards - counterfeit tests.
- https://www.law.cornell.edu/cfr/text/31/411.1 - currency illustration rule.
- https://www.law.cornell.edu/uscode/text/18/2320 - counterfeit marks statute.

Seen in search results only (not opened, or blocked when opened):

- https://packlim.com/playing-card-dimensions - card dimensions.
- https://www.theory11.com/forums/threads/splitting-cards-trouble.35466 - split layers.
- https://vanishingincmagic.com/card-magic/learn-to-split-cards-in-four-minutes - splitting tutorial.
- https://vanishingincmagic.com/card-magic-downloads/how-to-print-on-playing-cards - printing on real cards.
- https://www.rtings.com/printer/learn/research/printing-playing-card-proxies - proxy printing tests.
- https://www.makeplayingcards.com/design/custom-poker.html - one-off decks.
- https://www.precisionmicro.com/?p=22 and https://fotofab.com/about-us/faq/ - etching FAQs.
- https://help.ponoko.com/en/articles/3003413-photochemical-machining-design-guide - etching kerf.
- https://jlcpcb.com/blog/how-to-choose-an-smt-stencil - stencil pricing.
- https://homediyer.com/products/stainless-steel-shim-sheet-foil-gasket-0-01-0-6mm - 0.01 mm foil.
- https://prod-8babe12b-be845633-ssb7vc4z.app.devpanel.com/article/covering-materials-ff - Model Aviation on micro-films.
- https://www.corning.com/emea/en/about-us/news-events/features/willow-samples.html - Willow Glass.
- https://en.wikipedia.org/wiki/Electroforming and https://makezine.com/2020/11/17/this-copper-electroforming-kit-is-just-cool - electroforming.
- https://www.penguinmagic.com/p/14540 and https://www.conjuringarchive.com/list/category/1725 - flap cards.
- https://3mcanada.ca/3M/en_CA/p/d/v000202250 and https://www.edmundoptics.com/p/12quot-x-115quot-0deg-glossy-3m-light-control-film/10599/ - light-control film.
- https://www.edmundoptics.com/p/musou-black-absorbing-paint-100-ml/58204/ - Musou Black.
- https://cdn.shopify.com/s/files/1/0280/3276/1928/files/Nix_Mini-3_Spec_Sheet_V1.0.pdf - colour sensor.
- https://wallofsheep.com/products/hollow-spy-coin-u-s-nickel-05 - hollow coin price.
- https://www.batteryspace.com/ultra-thin-rechargeable-cells.aspx , https://www.grepow.com/shaped-battery/ultra-thin-battery.html , https://www.cnx-software.com/2017/09/21/powerstream-lithium-polymer-batteries-are-bendable-and-ultra-thin-0-5-to-2-mm/ - thin cells.
- https://revopoint3d.com/pages/all-in-one-3d-scanner-miracoplus and https://us.elegoo.com/blogs/3d-scanning/best-3d-scanners-for-3d-printing-2026 - scanners.
- https://learn.poly.cam/hc/en-us/articles/50434745985556-How-Accurate-Are-Polycam-Scans - Polycam accuracy.
- https://canon-europe.com/printers/selphy-cp1500/specifications - dye-sub printer.
- https://www.newegg.com/p/2D5-00K7-01FC3 - handheld inkjet listing.
- https://onlycaptions.com/best-stamp-making-machines/ and https://www.officedepot.com/a/products/512955/Same-Day-Pre-Inked-Stamp-710 - stamp makers.
- https://www.hackster.io/news/bantam-tools-fresh-from-its-evil-mad-scientist-acquisition-launches-the-new-nextdraw-plotter-range-c483cf743665 and https://spectrum.ieee.org/the-axidraw-minikit-is-the-modern-xy-plotter-you-didnt-know-you-wanted - plotters.
- https://www.doi.org/10.1145/2886099 - Haines et al., handwriting synthesis.
- https://hal.sorbonne-universite.fr/hal-03402424v1/document - tearing paths in paper.
- https://bioresources.cnr.ncsu.edu/wp-content/uploads/2020/03/1993.2.1023.pdf - cartonboard perforations.
- https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/7138169 - directional-tear film patent.
- https://arxiv.org/pdf/1807.00899 - Gottesman et al., crumpling state variable.
- https://blogs.magicjudges.org/europeeast/?p=2518 and https://magic.wizards.com/en/news/feature/buyer-beware-2004-04-26 - card counterfeit tests.
- https://www.bep.gov/currency/currency-image-use - currency image rules.
- https://www.ftc.gov/system/files/ftc_gov/pdf/Imitation-Coins.pdf - Hobby Protection Act.
