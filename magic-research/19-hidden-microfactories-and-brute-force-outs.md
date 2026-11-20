# 19. Hidden micro-factories and brute-force outs

Slice: two method architectures for predictions and "impossible object" plots.

- **(A) Hidden micro-factory**: the out is printed, written, marked, sorted or assembled inside (or
  through the wall of) a prop *after* the spectator has chosen.
- **(B) Brute-force outs**: every possible outcome is made in advance for cents each, and a
  mechanism, a window, a trigger or a piece of logistics delivers the right one.

All prices are as seen in late 2026 in the cited pages. Anything recalled from memory and not
confirmed in a page I opened or a search result I saw is marked **(unverified)**. Ideas marked
**(speculative)** are my own mechanism proposals and have not been built.

## 1. Summary

- **Magic has adopted exactly one micro-factory: the motorised Bluetooth thermal printer.** Dealer
  products (PITATA Smart Printer and Smart Printer Mini at about $400, 76 x 42 x 25 mm; BlackBox
  "Cosmos" printer wallet at $450; Electricks support for the consumer PeriPage printer) all hide a
  stock receipt mechanism and print a slip on app command. The engine inside is a $15 to $20
  "cat printer" whose BLE protocol has been reverse-engineered several times. Everything else in
  this report (pen, laser, inkjet, electro-etch, UV mask, heat matrix, pressure) appears to be
  unused in dealer products.
- **The most useful reframing is "write-through".** The factory does not have to be inside the
  sealed thing. Pressure crosses a paper envelope (carbonless paper), light crosses glass and
  clear plastic (laser or UV onto thermal or photochromic paper), near-infrared crosses
  visually opaque "IR-pass" plastic, heat crosses a thin mirror or film, magnetism crosses any
  non-ferrous wall. Each gives "it was sealed and signed before you chose, and nothing was opened".
- **Print during the reveal motion, not before it.** Swipe inkjet printers already clock their
  nozzles from an encoder while a hand moves them. Turning that round (the paper is pulled past a
  fixed head by the performer's own withdrawal) removes the motor, the noise and the stall time
  from a thermal or inkjet gimmick. I found no magic product that does this.
- **Thermal printing has natural disguises that magic under-uses**: receipts, boarding passes,
  lottery and parking tickets, shipping labels, event wristbands and name badges are all direct
  thermal. Likewise 12-nozzle thermal inkjet is exactly what prints "best before" and lot codes,
  so a late-printed date code on a sealed product is technologically indistinguishable from a
  factory one.
- **Real ink in the performer's own handwriting is now a hidden-engine output.** Small pen
  plotters (160 x 101 mm travel in a 36 x 23.5 x 11 cm kit; much smaller DIY designs) plus
  few-shot handwriting synthesis (one to five reference samples in 2024 to 2026 papers) give a
  swami gimmick with no thumb. Limit: own handwriting and playing cards only, never third-party
  signatures or documents.
- **A new medium for the nail writer: metal.** Electrochemical etch marking (a wet pad or wick,
  12 to 24 V, a few seconds) blackens steel and nickel alloys permanently. A thumb-worn etch
  stylus or a thermally printed stencil would put a chosen word on a borrowed key or coin
  (speculative as a magic gimmick; the industrial process is standard).
- **Brute force has a clear crossover point.** Up to 52 outs, a manual index wins (Dex: 52 cards
  in one pocket, 3 to 5 s). From about 50 to 200 physical outs a motorised reel or carousel is
  pocketable. Above about 200 separate objects the volume (roughly 0.3 cm3 per folded billet) pushes
  the index into a table or case, and print-on-demand wins unless the out must be something a
  printer cannot make (real ink, foil, engraving, a sealed commercial object).
- **Information density is no longer the limit.** A 1200 dpi laser printer holds legible text at
  about 1 pt (0.35 mm); a $25 film photoplot holds 10 to 25 micron features, so all 1,000
  three-digit numbers fit in a few square millimetres and all can ride behind a Stanhope-style
  peep lens or a UV exposure mask. A de Bruijn digit sequence lets overlapping windows share
  digits and cuts the travel of a "window that frames one number" by a factor of three.
- **One surface can carry roughly 4 to 6 practical independent messages** (visible, UV
  fluorescent, heat, wet, viewing angle, polariser, breath), and in principle 10 or more; the
  cost is that unused channels stay on the object the spectator keeps.
- **An index can sit in full view if its outs are indistinguishable.** In two-sheet visual
  cryptography, one fixed noise sheet can be paired with a computed "partner" noise sheet for any
  message at all. A hundred partner sheets look identical, so the index needs no hiding, only a
  way to count to the right one.
- **Card re-ordering machines exist but are shoebox-sized.** Open-source camera shufflers
  (about $200, eight bins) and commercial sorters (60 to 100 cards per minute) can stack a
  shuffled deck in one to two minutes; nothing found fits a card case. The casino Deckmate 2
  already reads every card with an internal camera.
- **Overhyped for this slice**: volumetric "prints in seconds" (real, but quote-only lab
  machines), hidden coin presses and embossers (force and noise), cyanotype (10 to 15 minute
  exposures and a wash), Zink (about 50 s per print), hidden FDM printing (minutes and fans).

## 2. Catalog

### 2.1 Prior art inside magic (what already exists)

**Nail writers, swami gimmicks, Boon writers.** A pencil lead, grease point or ink tip on the
thumb writes a short prediction after the fact; modern versions write in ink or marker, and the
standard reference is Corinda's Thirteen Steps to Mentalism
(https://en.wikipedia.org/wiki/Nail_writer). Limits: a few characters, shaky hand, cover needed
for the thumb. This is the manual ancestor of every engine below.

**Pocket and wallet indexes.** Classic two-pocket card indexes hold 26 cards each. The current
state of the art is a thin single-pocket index: Dex (Lloyd Barnes and Javier Fuenmayor) holds all
52 cards in one pocket; one buyer reports 3 to 5 s retrieval; reviews are mixed on build quality
(https://www.penguinmagic.com/p/19078, https://vanishingincmagic.com/card-magic/dex). Multiple-out
wallets (Shogun-style, Heirloom, Hip Shot) are sold on the strength of holding Kenton Knepper's
Kolossal Killer (a small card index plus a verbal "off by one" out) and a dozen or so other
predictions (Penguin review threads:
https://www.penguinmagic.com/reviewcomments.php?rid=84755,
https://www.penguinmagic.com/reviewcomments.php?rid=32691). I found no motorised index on sale.

**Thermal-printer predictions (the only commercial micro-factory).**
- PITATA Smart Printer: a miniature Bluetooth thermal printer supplied with a glass jar to hide
  it; largely out of stock or discontinued (https://vanishingincmagic.com/mentalism/smart-printer,
  https://alakazam.co.uk/products/smart-printer-by-pitata-magic).
- PITATA Smart Printer Mini: 76 x 42 x 25 mm main unit, $400, "smaller, lighter, quieter"
  (https://www.vanishingincmagic.com/mentalism/pitata-smart-printer-mini/, figures from the search
  listing; the page itself returned HTTP 403 to me).
- Cosmos (BlackBox Magic Creations): a bi-fold wallet around "the smallest and thinnest printer in
  the magic market", $450, over 10 hours standby, three paper types (lined notepad, matte
  "feels like real paper", book-test roll), input from Notes, Calculator or API, integrates with
  Inject and WikiTest, iOS (https://shop.52kards.com/products/cosmos-by-blackbox-magic-creations).
  No print time, thickness or dB figure is published.
- Electricks documents a PeriPage (consumer pocket printer) integration for its Atom remote, with
  commands to print text, print a hand-drawn clock face and feed paper, and lists a Cosmos
  printer integration (https://electricks.info/?p=24806, https://electricks.info/?p=32672).
- An "Ultra Prediction Table" is listed by Vanishing Inc.
  (https://vanishingincmagic.com/mentalism/ultra-prediction-table); I did not open it.

**Spirit slates and electronic boards.** Mechanical flap slates (Spirit Slates Pro,
https://vanishingincmagic.com/mentalism/spirit-slates-pro) and the Electricks "Spirit" series of
electronic blackboards that capture writing on one board and display it on another
(https://tricksupply.com/?p=267069). These are screens or flaps, not marking engines.

**Headline predictions.** The Conjuring Archive lists 94 entries under newspaper/headline
prediction and 47 under prediction by mail (https://www.conjuringarchive.com/list/category/227,
https://www.conjuringarchive.com/list/category/2236). The methods on sale are late loading into a
chest or box (Magic Wagon's Telegraph Chest,
https://www.pegani.dk/en/products/mentalism/the-telegraph-chest---magic-wagon), switching or
loading billets in a clear box (Devin Knight and Al Mann's Glass Box,
https://www.lybrary.com/the-glass-box-headline-prediction-p-743506.html), a prediction baked in
bread, and postmark methods (Bally, https://trickshop.com/bally-prediction.html). All move a
finished slip; none manufactures inside the container.

**What is therefore new**: any engine other than a motorised receipt printer; any engine that
writes through a wall; any motorised or optical index; any use of cheap variable-data printing to
cover a whole audience.

### 2.2 Marking engines

| Engine | Resolution | Time for one word / card index | Noise | Smallest practical size | Consumable | Cost |
|---|---|---|---|---|---|---|
| Thermal line head, motorised | 8 dots/mm (203 dpi) | under 1 s at 50 to 100 mm/s | about 53 dB(A) open | 67 x 18 x 30 mm mechanism | thermal paper/card | $15 to $40 |
| Thermal head, pull-to-print (speculative) | 8 dots/mm | 0 s extra (prints while pulled) | paper slide only | about 60 x 20 x 9 mm | thermal paper/card | about $40 |
| 12 mm label printer | 203 to 300 dpi | 1 to 2 s | similar to above | 109 x 78 x 30 mm product | label tape | $25 to $40 |
| Thermal inkjet, 12 nozzle (C6602) | 96 dpi, 3 mm swath | 1 s swipe | near silent | cartridge only | cartridge | $20 to $40 |
| Thermal inkjet, handheld colour | "1200 dpi", 14.3 mm swath | 1 to 3 s swipe | near silent | 72 x 51 x 68 mm product | cartridge | $80 to $200 |
| Pen plotter | pen width | 5 to 20 s | 30 to 50 dB (unverified) | DVD-sled XY about 60 x 60 x 20 mm (unverified) | real pen | $20 to $250 |
| Diode laser, gantry or galvo | 0.05 to 0.1 mm | 2 to 30 s | fan and galvo whine | galvo units are 1.5 kg and up | none | $150 to $1,500 |
| UV mask (LCD or film) on light-sensitive sheet | LCD pixel 20 to 50 micron | under 20 s (best papers) to 15 min (cyanotype) | silent | flat, under 10 mm | coated sheet | $30 to $80 |
| Electro-etch on metal | stencil-limited | 2 to 5 s | silent | thumb tip | electrolyte | $10 to $60 |
| Heater matrix behind mirror (speculative) | 5 to 15 mm pixels | 20 to 60 s preheat | silent | 1 mm PCB | none | $25 |
| Zink | 313 x 512 dpi | about 50 s per 2 x 3 inch | motor | product about 120 x 80 x 20 mm (unverified) | Zink sheets | $80 to $130 |

**Thermal print mechanisms.** A 2-inch (58 mm paper, 48 mm print width, 384 dots) mechanism is the
smallest mass-market line printer. Seiko's LTP02-245 is 67.3 x 18.1 x 30 mm, about 28 g, 203 dpi,
up to 100 mm/s on 5.5 to 9.5 V, with a low-energy variant that runs at 85 mm/s directly from
3.0 to 4.2 V (one lithium cell); head peak current is 2.64 A, motor peak 0.6 A, and head life is
100 million pulses or 50 km of paper. Older Seiko LTPU245 units are 30 g and 75 mm/s; Chinese PRT equivalents are 68 x
24 x 26 mm at 90 mm/s; Citizen's MLT4281 adds an auto-cutter at 80 mm/s
(https://sii-thermalprinters.com/mechanisms-and-components/low-voltage-thermal-printer-mechanisms/ltp02-245/,
https://sii.co.jp/sps/eg/product/oldproduct/ltpu245.html,
https://citizen-systems.com/en/products/printer/kiosk/mlt4281,
https://www.aps-printers.com/product-category/mini-printer-mechanisms/). I did not find a true
1-inch catalogue mechanism; the practical narrow option is the 12 mm label-printer head (below).
Published noise: Epson's mobile TM-P20 and TM-P80II list 52.9 dB(A) in operation
(https://epson.eu/en_EU/products/retail/pos-printers/mobile-printers/tm-p20-series/p/14345);
Phomemo claims under 55 dB. A wallet or box wall should take 10 dB or more off that (unverified),
which is inaudible in a bar and audible in a silent living room. Thermal paper itself is a
leuco dye plus acid developer that colours when the sensitiser melts, with about 100 C as the
practical lower limit; a fast fingernail stroke or a hot coffee cup is enough to mark it
(https://en.wikipedia.org/wiki/Thermal_paper). That sensitivity is why any modest heat source,
not only a print head, can be the "printer".
- *Accessibility*: off the shelf. "Cat printers" (GB01, GB02, GT01, MX05, MX06, MX08 and
  relatives) cost about $20 or 16 pounds, have an internal battery and an openly documented BLE
  protocol with Python, JavaScript and Go drivers (https://github.com/rbaron/catprinter,
  https://werwolv.net/blog/cat_printer, https://github.com/NaitLee/Cat-Printer via
  https://deepwiki.com/NaitLee/Cat-Printer/1.2-supported-hardware,
  https://learn.adafruit.com/ble-cat-thermal-printer-with-memento.md,
  https://magazine.raspberrypi.com/articles/bluetooth-cat-thermal-printer-review). A hobbyist can
  reproduce the function of a $400 dealer printer for under $30 and own the firmware.
- *Label printers*: Niimbot D11/D110 print a 12 mm swath on 15 mm tape at 203 dpi (300 dpi on
  D11-H) at 30 to 60 mm/s; the D11-H is 109 x 78 x 30 mm and 199 g; open MIT-licensed drivers
  exist (https://github.com/AndBondStyle/niimprint, https://github.com/kjy00302/niimprint,
  https://www.bhphotovideo.com/c/product/1937602-REG/niimbot_1aa5e283401_d11h_1_2_portable_hd.html).
  A 12 mm head is the right width for a fortune-cookie slip, a price sticker, a cable label or a
  wristband.
- *Magic relevance*: prediction; the known weakness is that thermal paper looks and feels like a
  receipt and the mechanism whirs. Fixes: (1) make the prediction *be* a receipt, ticket, boarding
  pass, luggage tag, wristband or shipping label; (2) use thermal-coated card or the "matte"
  stocks dealers already ship; (3) remove the motor (concept 1).

**Thermal inkjet cartridges driven directly.** The HP C6602A is a self-contained 12-nozzle,
18 ml cartridge (HP calls it TIJ 1.0) that prints a 96 dpi, roughly 3 mm (1/8 inch) high
dot-matrix line when its nozzles are pulsed for 5 to 6 microseconds at about 21 V
(https://www.hp.com/sa-en/products/ink-toner/product-details/product-specifications/43339,
https://www.homofaciens.de/technics-machines-printhead-hp6602_en.htm). Open hardware: InkShield
(Nicholas Lewis; KiCad files, Arduino library, https://github.com/RazaGR/InkShield,
https://makezine.com/2011/06/01/diy-open-source-inkjet-printer/) and the PrintSpider module for
the higher-resolution HP 63/302 cartridges on ESP32 and Raspberry Pi
(https://hackaday.io/project/176931-hp-printer-cartridge-control-module,
https://www.github.com/lichnost/PrintSpider_Arduino, the latter self-described as untested). The
PrintSpider electronics are a 23 x 38 mm level-shifter board (16 V clock and trigger lines, 9 V
data lines); the project log stops in January 2022 with unresolved protection-circuit problems,
so the 12-nozzle C6602 route remains the dependable one.
Consumer swipe printers package the same idea: PrinCube/MBrush is 72 x 51 x 68 mm, 110 to 160 g,
tri-colour, 14.29 mm swath, launched at $99 to $199 with clones at $24 to $79 wholesale
(https://www.cnx-software.com/2019/11/01/princube-smallest-handheld-smartphone-color-inkjet-printer-prints-on-anything/,
https://techradar.com/news/worlds-smallest-color-printer-can-print-on-anything-including-your-skin,
https://en.techreviewer.de/mbrush-princube-test/). Prinker prints cosmetic-grade ink on primed
skin in about 3 s per sweep, lasting about a day, about 1,000 prints per cartridge, $230 to $330
(https://boingboing.net/2020/08/07/this-temporary-tattoo-printer.html/amp,
https://xatakaon.com/other-devices/this-is-prinker-a-painless-tattoo-printer-that-inks-your-skin-in-seconds,
https://stacksocial.com/sales/prinker-m-mobile-digital-temporary-tattoo-printer).
- *Capability*: a silent print engine with no paper path of its own. The object moves, or the
  hand moves; an encoder clocks the nozzles. It prints on card, wood, eggshell, a can, a
  fingernail, a coaster.
- *Magic relevance*: prediction on an arbitrary ordinary object; the dot-matrix look is a liability
  on a "handwritten" prediction and an asset wherever industry uses the same technology (date
  codes, lot numbers, parcel marks). Skin printing: a number "appears" on the performer's own
  forearm (an ash-on-arm replacement with free choice). Printing on a spectator's skin needs
  consent and a patch-test mindset; keep it to the performer.
- *Give-aways*: ink must dry (seconds on porous stock; solvent inks for non-porous stock smell);
  nozzles clog after days idle; wet ink smears if the reveal is too fast.

**Pen plotters and handwriting synthesis.** AxiDraw MiniKit 2: 160 x 101 mm travel, up to 25 cm/s,
36 x 23.5 x 11 cm overall (https://shop.pimoroni.com/products/axidraw-minikit-2,
https://shop.evilmadscientist.com/924). Smaller open designs: Lingdong Huang's Plotlet, a
postcard-area (6 x 4 inch) plotter with a $20.30 bill of materials built from three 28BYJ-48
geared steppers, an SG90 pen-lift servo, about 150 g of filament and an Arduino Nano or ESP32-S3
with BLE (https://github.com/LingDong-/plotlet); Bart Dring's tiny single-belt ESP32/Grbl plotter
(https://hackaday.com/2019/07/27/lack-of-space-is-no-longer-an-excuse-for-not-having-a-pen-plotter),
the "almost fits on your hand" drawing machine
(https://www.hackster.io/news/miniature-drawing-machine-almost-fits-on-your-hand-c0da2da8c28a) and
post-it sized machines (https://hackaday.com/2013/11/21/a-six-part-cnc-machine). Builders warn
against hobby servos for X/Y (https://community.robotshop.com/robots/show/two-servo-and-drawer-slide-pen-plotter);
micro lead-screw steppers from optical drives are the usual tiny actuator (unverified sizes).
A five-letter word is roughly 150 to 250 mm of pen path, so 5 to 15 s at modest speed (my
estimate). Handwriting models: Spatio-Temporal Handwriting Imitation turns an offline sample into
pen trajectories (https://arxiv.org/pdf/2003.10593); One-DM imitates a writer from one reference
sample (https://arxiv.org/html/2409.04004v2); DiffusionPen uses five
(https://www.arxiv.org/pdf/2409.06065); FW-GAN and a 2026 Buffalo report continue the one-shot to
six-shot line (https://arxiv.org/abs/2508.21040v1, https://cse.buffalo.edu/tech-reports/2026-43.pdf).
Most recent models output images, not strokes; for a plotter the practical route is to record
the performer's own strokes on a tablet and stitch or synthesise from those.
- *Magic relevance*: real marker ink, real pen pressure, the performer's real letterforms, on an
  ordinary business card or the face of a playing card. This removes the "that's a printout"
  theory that follows every thermal prediction.
- *Ethical and legal limit*: synthesise the performer's own hand, or print on cards. Imitating a
  spectator's or a third party's signature or handwriting on anything is forgery territory and is
  out of scope.
- *Give-aways*: stepper noise and vibration through a table; pen drying out between shows
  (cap-parking needed); 10 to 20 s of stall.

**Laser marking.** Portable galvo engravers reach 4,000 mm/s (xTool F1: 10 W 455 nm diode plus
2 W 1064 nm infrared, 115 x 115 mm field, 179 x 235 x 334 mm, 4.6 kg,
https://support.xtool.com/article/12, https://woodcraft.com/products/xtool-f1-portable-laser-engraver);
LaserPecker LP2 is a 5 W diode galvo unit with a 100 x 100 mm field at 6 to 600 mm/s, 194 x 154 x
236 mm (https://support.laserpecker.net/hc/en-us/articles/7322687094543-LP2-Buying-Guide). The
Dutch start-up Tocano showed "inkless" printing by carbonising the top layer of ordinary paper
with a 24 micron infrared spot (https://techcrunch.com/?p=1621213,
https://patents.google.com/patent/US9393804B2), which is a reminder that char on plain paper can
look like print. For packaging, DataLase sells laser-reactive coatings for paper, board, films
and foils that turn into high-contrast codes "instantly" under a laser with no ink
(https://www.datalase.com/; the page does not state wavelengths).
- *Capability*: non-contact marking of paper, card, wood, leather, fruit skin, toast, and (with
  the infrared source) bare metal; and the beam passes through glass and clear plastic.
- *Give-aways*: charring makes smoke and a campfire smell; fans are loud; galvo units are
  kilogram-scale. Marking *thermal* paper instead of charring plain paper only has to reach
  about 100 C rather than several hundred, so it should need far less energy and make no smoke
  (inference from the thermal-paper chemistry above; needs a bench test, since white coatings
  absorb visible light poorly).
- *Safety*: these are Class 4 sources once out of their enclosure. A hidden laser pointing up
  through a table toward faces is unacceptable without a full light-tight beam path, interlocks
  and a beam dump. Infrared beams are invisible and worse. Treat any open-beam idea as
  stage-crew-only engineering.

**UV exposure through a mask ("a printer with no moving parts").** A monochrome resin-printer LCD
is a cheap, high-resolution 405 nm mask. A 2025 Hackaday project replaced a resin printer's vat
with a lid and exposed cyanotype paper directly, but could not get below about 15 minutes
(https://hackaday.com/2025/02/22/cyanotype-prints-on-a-resin-3d-printer,
https://hackaday.io/project/202440-cyanoprinter); alt-process photographers report LCD contact
printing "works fine" with the LCD against the paper
(https://www.photrio.com/forum/threads/making-a-uv-projector-for-alt-process-prints.212710/post-2971364).
Faster chemistry exists in the literature: Yadong Yin's group made light-printable rewritable
paper from Prussian blue plus TiO2 nanoparticles (blue turns colourless under UV, legible for
more than five days, https://phys.org/news/2017-02-ink-required-paper.pdf,
https://patents.google.com/patent/US10534254), and a later Cu-doped TiO2 system is reported at
under 20 s to print, more than three days legible, more than 50 cycles and 90 micron resolution
(Wang, Yin and colleagues, as summarised in my search results; primary URL not opened,
https://www.escholarship.org/content/qt2wb412nw/qt2wb412nw.pdf?t=p1z7dt). Commercial photochromic
("sun-activated") inks and papers darken in seconds under 365 to 405 nm and fade in minutes
(unverified numbers; agent 8 covers chromic inks).
- *Magic relevance*: silent, flat, no head, no paper motion; exposure works through a clear cover
  sheet, a photo-frame glass or a plastic sleeve. Fading photochromic images give a prediction
  that *erases its own evidence*; Yin-type papers give days of legibility.
- *Limits*: cyanotype is too slow and needs a rinse; lab papers are not purchasable; stray
  daylight fogs the sheet.

**Electrochemical marking of metal.** In electroetching the workpiece is the anode of a DC
circuit and dissolves where electrolyte touches it (https://en.wikipedia.org/wiki/Electroetching).
Industrial "electro-etch" marking presses an electrolyte-soaked pad through a stencil onto steel
for a few seconds and leaves a black oxide or frosted mark; knife makers do it with a 12 V supply
and salt water (voltages and times unverified in this session). The stencil can be printed on
demand: Brother's STe-151 is a 24 mm x 3 m non-adhesive stencil tape with a thermally sensitive
layer, sold for $22 for P-touch label printers, described as a mask for "ink or special fluids"
in direct part marking (https://www.brother-usa.com/products/ste151). On coins: US law
(18 U.S.C. 331) is read as prohibiting only fraudulent alteration and the UK Coinage Act 1971
s.10 covers melting or breaking up, which is why penny presses are lawful in both; some
countries such as Canada differ (https://en.wikipedia.org/wiki/Elongated_coin). Old electrosensitive printers (the Sinclair ZX Printer burned aluminium off coated paper
with a stylus, https://en.wikipedia.org/wiki/ZX_Printer) show the paper version; it is noisy,
smelly and obsolete.
- *Magic relevance*: the only pocket-scale way found to put a permanent, chosen mark on a
  borrowed metal object. See concept 5.

**Zink and dye-sub.** Zink printers need no ink but take about 48 to 50 s for a 2 x 3 inch print
(https://www.expertreviews.co.uk/technology/printing-cameras/canon-zoemini-review,
https://www.digitalcameraworld.com/uk/reviews/canon-zoemini-2-mini-photo-printer-review), at
313 x 512 dpi (https://rtings.com/printer/reviews/canon/ivy-mini-photo-printer). Hackaday points
to FCC filings for internal photos (https://hackaday.com/2025/03/31/zink-is-zero-ink-sort-of).
Useful when the out must be a colour photograph (a "polaroid" of the chosen card or place) and a
minute of stall is available.

**Other marking channels (brief).**
- *Pressure*: carbonless paper carries micro-encapsulated dye on the back of one sheet and
  reactive clay on the front of the next; pen pressure bursts the capsules. A "self-contained"
  grade has dye and clay on the same face, so a single sheet marks itself under pressure with no
  ink on the stylus (https://en.wikipedia.org/wiki/Carbonless_copy_paper; the same page notes
  occasional skin irritation and a high bisphenol A content). Cholesteric "Boogie Board" film is
  written by pressure and erased electrically (unverified). Both let a blunt stylus write through
  a flexible cover.
- *Magnetism*: magnetophoretic boards (Magna Doodle: dark magnetic particles in honeycomb cells
  of opaque white liquid, pulled to the front by a magnet and to the back by the eraser bar,
  https://en.wikipedia.org/wiki/Magna_Doodle) and magnetic viewing film can be addressed through
  a non-ferrous wall; resolution is millimetres; the look is a toy.
- *Heat by conduction*: a resistor or PCB-trace matrix behind thin thermal paper, a thermochromic
  panel or a mirror (for condensation) is a display with no moving parts and 5 to 15 mm pixels
  (speculative; concept 4).
- *Impact*: braille embossers, dot-peen markers and numbering machines are loud and heavy. A
  self-inking band stamp whose number bands are turned by micro gearmotors is plausible and would
  give a genuine rubber-stamp impression (speculative, not found built).
- *Sand, salt, filings*: under-table magnet plotters (Sisyphus-style) take minutes and read as
  the phenomenon itself (level 1).

### 2.3 Sorting, selecting and dispensing engines

**Playing-card machines.**
- 3DprintedLife's open-source shuffler: card dispenser, Pi Zero camera with OpenCV reading each
  card as it is ejected, eight bins, three NEMA 17 steppers, about $200 in parts, code on GitHub;
  it can deal a truly random shuffle or a rigged order
  (https://www.hackster.io/news/rig-the-deck-so-you-always-win-with-this-card-shuffler-5db782b1b15f,
  https://www.tomshardware.com/news/rig-your-next-card-game-with-the-help-of-a-raspberry-pi,
  https://hackaday.com/2020/07/20/raspberry-pi-shuffler-is-computerized-card-shark). The
  repository (MIT licence, https://github.com/DDeGonge/Shuffle-o-matic) lists three NEMA 17
  steppers, an MG90S servo, a 600 rpm N20 gearmotor, three MGN9 rails of 95 to 135 mm, a
  Raspberry Pi, an Adafruit Feather and a custom PCB, and warns that it is poorly documented and
  "not a project for beginners". No throughput figure is published; a Hackaday commenter calls it
  "rather slow". With b bins a full sort needs ceil(log_b 52) passes: two passes with eight
  bins, so 104 card moves; at 1 to 2 cards per second that is one to two minutes (my estimate).
- Purdue "Smart Card Shuffler" (camera under the deck, phone-selected target order,
  https://engineering.purdue.edu/477grp10), Adelaide robot-arm sorters with a "new deck order"
  mode (https://projectswiki.eleceng.adelaide.edu.au/projects/index.php/Projects:2014S1-16_Automatic_Sorter_using_Computer_Vision),
  David Stern's Dave-o-Matic bridge dealer that reads cards to deal pre-set hands
  (https://www.hackster.io/news/david-stern-s-dave-o-matic-is-a-sneaky-bridge-dealing-bot-peeking-at-the-cards-for-pre-set-hands-977451688056),
  and a 3D-printed roller feeder that pulls single cards from the bottom of a stack
  (https://hackaday.com/2025/03/26/3d-printed-scanner-automates-deck-management-for-trading-card-gamers).
- Commercial trading-card sorters: TCG Machines PhyzBatch-9000 at 60 cards per minute average
  and 75 to 100 maximum with a 1,750-card hopper (https://tcgmachines.com/product,
  https://www.tcgmachines.com/blog/launch-day); TCGplayer Roca at 500 cards per hour in a
  36 x 30 inch frame (https://seller.tcgplayer.com/roca-sorter).
- Casino: IOActive showed in 2023 that the Deckmate 2 shuffler's internal camera exposes the full
  deck order and that its firmware can be hijacked through a USB port
  (https://ioactive.com/article/internal-camera-hacked-casino-card-shuffler-lets-you-look-at-the-cards/,
  https://www.tomshardware.com/news/raspberry-pi-enables-security-researchers-to-hijack-casino-card-shuffling-machine).
- *Assessment*: "stack a shuffled deck in about a minute" is real at shoebox size and 55 dB plus.
  It does not fit a card case. Its honest home in magic is (a) an openly present automatic
  shuffler, which already has a reason to whir, or (b) offstage preparation of many decks.
  "Know the order" (the camera half) miniaturises far better than "change the order" and belongs
  to the sensing agents.

**Dispensing 1 of N small objects.** I ran out of search budget before collecting sources on
pill carousels, capsule vendors, SMD tape feeders and coin hoppers (Open leads). First-principles
numbers (all my own estimates):
- A folded billet (50 x 30 mm slip folded to about 15 x 12 x 1.5 mm) occupies about 0.27 cm3.
  100 billets: 27 cm3, a third of a deck of cards. 1,000 billets: 270 cm3 plus pockets, about
  half a litre to a litre of mechanism.
- A reel of uncut paper is far denser than separate billets. 1,000 frames of 25 mm on 60 micron
  paper is 25 m and winds to a 45 mm diameter roll on a 12 mm core; 1,000 frames of 8 mm is 8 m
  and a 27 mm roll. Seek time at 300 mm/s from a mid-roll park position: 40 s worst case for the
  25 mm frames, 13 s for the 8 mm frames. A receipt-printer auto-cutter separates the frame.
- A stepped stack (each card or envelope offset 1 mm from the next so every item shows a lip)
  lets one finger on a lead screw address 52 items over 52 mm of travel in about a second.
- One coil per capsule (magnetic latch release) scales to perhaps 16 to 32 before wiring and
  size dominate; an XY picker scales to hundreds but is a table-sized device.

### 2.4 Assembly and transformation engines

- **Fast additive manufacturing.** Speed-tuned consumer FDM prints a Benchy in under 4 minutes
  from first layer, excluding heat-up and calibration (https://makerworld.com/models/1826151). A
  25 mm, 1.2 mm thick token with raised text is about 0.6 cm3, so 20 to 40 s of extrusion on a
  pre-heated machine (my estimate) plus motion overhead. Fans and steppers make it a backstage or
  inside-a-plinth engine with a chute, not a pocket one.
- **Volumetric printing.** Berkeley's CAL prints centimetre-scale parts in 30 to 120 s; xolo's
  Xube prints small parts in about 20 s and the 2024 Xube2 lists 6 mm/min and an 80 mm build
  volume, price on request; Readily3D's Tomolite prints "in a few tens of seconds" at 40 micron
  optical resolution, also quote-only; a sub-second result was reported in early 2026
  (https://3dprintingindustry.com/news/xolo-launches-new-xube%C2%B2-volumetric-3d-printer-technical-specifications-and-pricing-232600/,
  https://www.aniwaa.com/product/3d-printers/readily3d-tomolite/,
  https://hackaday.com/2026/02/25/sub-second-volumetric-3d-printing,
  https://www.3dnatives.com/en/notable-volumetric-3d-printing-projects-2026-10092026/amp/). Honest
  assessment: the speed is real and the object does form inside a closed vial, which is a
  beautiful plot, but the machines are laboratory instruments, the part comes out coated in
  uncured acrylate, and a hobby rebuild is a research project.
- **Single-layer resin "2.5D" tokens.** One long exposure through a mono LCD cures a flat relief
  token in tens of seconds (unverified cure depths). The part is wet with sensitising resin, so
  it only makes sense sealed inside a clear pouch or vial (speculative).
- **Laser engraving a borrowed object.** The 2 W infrared channel of a galvo engraver marks bare
  metal (xTool F1 above). Table-prop size, enclosed, tens of seconds (unverified time).
- **Folding, knotting, threading.** The research origami robot (Balkcom and Mason, ICRA 2004 and
  IJRR 2008) used a 4-DOF industrial arm open-loop for simple folds
  (https://www.ri.cmu.edu/publications/robotic-origami-folding-2). No small folding or knotting
  mechanism was found. Thermal paper curls by itself into a scroll, which is a free "fold".
- **Edible printing.** Ripples prints on drink foam in about 10 s; the EVEBOT FM1 in 20 to 40 s
  at 200 dpi (https://www.drinkripples.com/commercial-coffee-printer-buyers-guide/commercial-coffee-printer/,
  https://perfectdailygrind.com/2023/09/digital-coffee-beverage-printers-latte-art/). As visible
  reveal devices these belong to agent 12. As hidden engines, an edible-ink inkjet cartridge
  under a cloche or in a kitchen pass is the same swipe-print engine as above.
- **Coin and token presses, embossers, embroidery, badge presses.** Force (kN), noise or minutes;
  see Dead ends.

### 2.5 Brute-force media and information density

- **Microtext on paper.** Microprinting is conventionally text under 2 pt; laser printers reach
  about 1 pt (0.35 mm) reliably and 0.5 pt at the edge, and toner spread matters more than
  nominal dpi (https://en.wikipedia.org/wiki/Microprinting,
  https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/7270918). A three-digit number
  at 1 pt needs a cell of about 1.0 x 0.6 mm: all 1,000 numbers fit in 25 x 24 mm and read under
  a 10x loupe (my arithmetic).
- **Film photoplots.** University fabs and mask vendors sell letter-size film masks for $20 to
  $50 with 10 to 25 micron minimum features (up to 25,400 dpi plotters)
  (https://mtl.mit.edu/pipermail/labnetwork/2018-August/003228.html,
  https://wiki.nanofab.ucsb.edu/wiki/Tutorial_-_How_Photomasks_are_Made,
  https://vanderbilt.edu/vinse/facilities/instruments/photoplotter.php). At 25 micron features a
  5-pixel-high glyph is 0.125 mm tall; 1,000 three-digit numbers fit in about 16 x 8 mm, and one
  letter-size sheet yields hundreds of such chips.
- **Stanhope peep lenses.** A 2 x 2 mm microphotograph on the flat end of a tiny rod lens,
  magnified up to about 300x, readable by holding it to the eye; still made to order by a
  handful of craftspeople (https://en.wikipedia.org/wiki/Stanhope_(optical_bijou),
  https://www.cpbj.com/mechanicsburg-man-a-global-source-for-stanhope-lenses/). It is the
  historical "one frame of microfilm in a charm".
- **Microfiche and microdots as upper bounds.** Standard fiche hold 98 pages at 24x on a
  105 x 148 mm sheet; ultrafiche at 150x held 2,380 page images on a 3 x 5 inch sheet; silver
  film lasts centuries (https://en.wikipedia.org/wiki/Microform). A microdot is about 1 mm
  across, and Goldberg's 1925 process put a legible page in 0.01 mm2
  (https://en.wikipedia.org/wiki/Microdot). A thousand one-line outs is therefore a trivial load
  for a film chip the size of a lentil; the engineering problem is the viewer, not the storage.
- **Visual-cryptography overlays (the camouflaged index).** In the two-sheet scheme each sheet
  is random-looking noise and the stack shows the image at reduced contrast. Wikipedia notes
  that given one sheet, a "counterfeit" partner can be computed that combines with it "to
  produce any image at all" (https://en.wikipedia.org/wiki/Visual_cryptography). For a
  brute-force method that is the useful property: fix sheet A in advance, compute partners
  B1..BN for N messages, and every partner is indistinguishable noise.
- **Flexagons.** A hexahexaflexagon has six faces (15 reachable states on the ordinary one) and
  hexaflexagons exist "with any number of faces" (https://en.wikipedia.org/wiki/Flexagon), so one
  folded strip can hold a handful of messages reached by different flex sequences.
- **Lenticular and multi-condition printing.** Lenticular prints carry 2 to 5 clean flips (up to
  about 20 frames for animation) (https://en.wikipedia.org/wiki/Lenticular_printing,
  https://www.4over4.com/faqs/general/how-many-images-can-i-combine-in-a-single-lenticular-print,
  https://support.xtool.com/article/3802). Research and patents show two distinct images under
  white versus 365 nm UV, under red versus blue light, and several images by rotating a polariser
  (https://infoscience.epfl.ch/handle/20.500.14299/157014,
  https://www.photonics.com/Article.aspx?AID=16892, https://uspto.report/patent/grant/10889141,
  https://phys.org/news/2016-12-hidden-images-commercial-inkjet-printers.pdf).
- **Channel count for "one object, N outs, no mechanism"** (my tally; chromic chemistry is agent
  8's): visible; UV-fluorescent (1 to 2 bands); thermochromic at two or three thresholds; cold
  reveal; water reveal; lenticular angle (2 to 5); polariser angle (2 to 3); colour filter (2 to
  3); raking-light blind emboss; back-lit watermark; retroreflective (visible only in a flash
  photo); phosphorescent; breath/condensation; scratch-off; overlay with a revealer transparency
  (as many messages as there are revealers). In principle 10 or more; in practice 4 to 6 before
  crosstalk and before the list of "do this to the card" instructions becomes the tell.
- **Computed fold and dissection outs.** Erik and Martin Demaine's mathematical fonts include a
  hinged-dissection font in which one universal chain of 128 triangles folds into any letter or
  digit, a dissection font in which every letter rearranges into a 6 x 6 square, and a Tetris
  font in which every character uses the same seven pieces (https://erikdemaine.org/fonts/,
  https://erikdemaine.org/fonts/hinged/, https://erikdemaine.org/fonts/dissect,
  https://erikdemaine.org/papers/PuzzleFonts_G4G14/paper.pdf). This is a proof that "the same
  examinable pieces spell any outcome" is achievable by computation.
- **De Bruijn windows.** A de Bruijn sequence B(10,3) is 1,000 digits long (cyclically) and
  contains every three-digit string exactly once as a run of consecutive digits; the
  two-dimensional analogue is the de Bruijn torus, used for position encoding in the Anoto
  digital pen (https://en.wikipedia.org/wiki/De_Bruijn_sequence). Diaconis and Graham built card
  tricks on these sequences (unverified in this session). Printed as a strip, a window
  three digits wide shows a different number at every one-digit step, so 1,000 outs need 1,000
  digit pitches of travel rather than 3,000. At 1 mm digit pitch that is a 1 m tape (a tape
  measure, a ribbon, a lanyard) or a 40 x 25 grid of window positions over a 40 x 75 mm area.
- **Variable-data printing at audience scale** (prices: agent 13). The enabling fact is that 300
  to 1,000 unique sealed items now cost about as much as 300 to 1,000 identical ones.

### 2.6 Speed, noise, cover and self-check

- *Silent engines*: UV mask, heater matrix, electro-etch, swipe inkjet, pull-to-print thermal,
  optical index. *Quiet with care*: plotters on silent stepper drivers, thermal mechanisms inside
  padded cavities. *Loud*: card sorters, FDM, impact, lasers with fans.
- *Smell*: laser char (strong), solvent ink (mild), thermal (none), UV resin (acrylate, strong).
- *Standby*: cat printers and dealer printers idle for hours (Cosmos claims over 10 hours); inkjet
  nozzles dry out; pens dry out; thermal and UV engines have no wet parts.
- *Failure detection*: thermal jam (motor current or an encoder on the idler), inkjet misfire
  (invisible without a look), pen skip. A $5 camera module or a reflective sensor row that reads
  the finished mark before the reveal converts a public failure into a private one: the system
  buzzes the performer to go to the classical out. Plan every engine with a non-electronic out.

## 3. Capability primitives

1. *Now possible:* print any text or image 48 mm wide in under 1 s from a 67 x 18 x 30 mm, 28 g
   module, standby for hours. *Because:* commodity 2-inch thermal mechanisms and $20 BLE printers
   with open protocols. *Before:* $400 dealer units or a nail writer. *Primitives:* transform, delay.
2. *Now possible:* own the firmware of a prediction printer for under $30. *Because:*
   reverse-engineered cat-printer and Niimbot protocols. *Before:* closed dealer apps.
   *Primitives:* transform, control.
3. *Now possible:* print with no motor and no stall, the paper clocked past a fixed head by the
   hand that withdraws it (speculative). *Because:* cheap encoders plus swipe-printer practice.
   *Before:* motor noise covered by patter. *Primitives:* transform, conceal, erase the evidence.
4. *Now possible:* put a 3 mm dot-matrix line of text on almost any dry surface in one silent 1 s
   pass. *Because:* 12-nozzle thermal inkjet cartridges and open drivers. *Before:* impossible
   outside a factory. *Primitives:* transform, prove ordinariness (it is real date-coder output).
5. *Now possible:* write 5 letters in real marker ink in 5 to 15 s inside a 20 mm thick cavity.
   *Because:* micro plotters, silent stepper drivers. *Before:* swami gimmick, 2 to 3 shaky
   characters. *Primitives:* transform, prove ordinariness.
6. *Now possible:* reproduce the performer's own handwriting from one to five samples.
   *Because:* few-shot handwriting synthesis and stroke recovery. *Before:* pre-written outs
   only. *Primitives:* duplicate, prove ordinariness.
7. *Now possible:* mark paper sealed behind glass or clear plastic without opening it.
   *Because:* visible and UV light pass the wall; thermal and photochromic papers respond.
   *Before:* late loading through a trap. *Primitives:* transform, prove ordinariness (sealed).
8. *Now possible:* write inside a sealed paper envelope from outside by pressure alone
   (speculative). *Because:* carbonless chemistry plus a stylus plotter. *Before:* window
   envelopes, slits, switches. *Primitives:* transform, prove ordinariness.
9. *Now possible:* make a mirror or glass show a chosen symbol only when breathed on, then
   nothing (speculative). *Because:* PCB heater matrices at $25. *Before:* a fixed, pre-drawn
   breath message. *Primitives:* transform, delay, erase the evidence.
10. *Now possible:* permanently mark a borrowed steel or nickel object with a chosen word in 2 to
    5 s, silently, from a thumb-sized device (speculative for magic). *Because:* electro-etch
    marking. *Before:* engraving off stage, or switching for a duplicate. *Primitives:* transform.
11. *Now possible:* expose a chosen image onto light-sensitive paper in under 20 s with no moving
    parts through a 20 to 50 micron pixel mask. *Because:* resin-printer mono LCDs, fast
    photo-switching papers. *Before:* no equivalent. *Primitives:* transform, erase (fading types).
12. *Now possible:* carry 1,000 distinct readable messages in 16 x 8 mm for about $0.10.
    *Because:* $25 film photoplots at 10 to 25 micron. *Before:* 52 cards in two pockets.
    *Primitives:* conceal, control choice (cover every outcome).
13. *Now possible:* carry 1,000 full-size printed frames in a 45 mm roll and reach any one in
    under 40 s. *Because:* micro gearmotors, encoders, receipt cutters. *Before:* none.
    *Primitives:* swap, conceal.
14. *Now possible:* halve or third the travel of a "window that frames the right number".
    *Because:* de Bruijn sequences. *Before:* separate cells. *Primitives:* conceal.
15. *Now possible:* know each card and re-stack a shuffled deck to any order in one to two
    minutes for $200. *Because:* open-source camera shufflers. *Before:* a confederate or a deck
    switch. *Primitives:* know, move, control chance.
16. *Now possible:* give 300 to 1,000 audience members each a different sealed out for cents each.
    *Because:* variable-data digital print and mail-merge. *Before:* one envelope, one force.
    *Primitives:* control choice, delay (work done days before).
17. *Now possible:* make one printed card answer 4 to 6 different outcomes with no moving parts.
    *Because:* cheap UV, thermochromic, lenticular and polariser media. *Before:* two-way and
    four-way outs by wording. *Primitives:* conceal, transform.
18. *Now possible:* build a set of loose pieces that provably assemble into any of N words.
    *Because:* computational dissection and puzzle fonts. *Before:* anagram tiles.
    *Primitives:* prove ordinariness, control choice.
19. *Now possible:* detect a failed hidden print before the reveal. *Because:* $5 camera modules
    and on-device OCR. *Before:* hope. *Primitives:* know, tell.
20. *Now possible:* a colour photograph of anything named, made in about 50 s in a pocket.
    *Because:* Zink. *Before:* a stack of pre-printed photos. *Primitives:* transform.
21. *Now possible:* a solid shape formed inside a closed vial in under 2 minutes (lab only).
    *Because:* volumetric printing. *Before:* impossible. *Primitives:* transform.
22. *Now possible:* print on primed skin in 3 s with day-long cosmetic ink. *Because:* Prinker
    class devices. *Before:* soap-and-ash arm writing, fixed in advance. *Primitives:* transform.

## 4. Effect concepts

Level 2 means a hidden input that removes a known weakness of a classical method; level 3 means a
new method architecture. Noise budgets are estimates until measured.

### 1. Pull-to-print sleeve (level 3; speculative)
- *Effect*: a wallet, an envelope or a book has been in view from the start. After a free choice
  the performer (or the spectator) slides a card or a ticket out of it, and the choice is printed
  on it. There is no pause, no sound and nothing to press.
- *Method*: a 58 mm thermal line head (384 dots) is fixed across the mouth of the sleeve with a
  spring-loaded rubber idler roller as platen. There is no motor. A magnetic or optical encoder
  on the idler clocks the strobe lines as the hand pulls the thermal card out, in the same way a
  swipe inkjet clocks its nozzles. The choice arrives over BLE (from whatever input method is in
  use) before the pull starts.
- *Budget*: head-and-roller bar about 60 x 20 x 9 mm (estimate); cycle time zero beyond the pull;
  noise is card-on-leather. Pull speed must stay under roughly 100 mm/s, which is a normal
  withdrawal.
- *BOM*: head and roller from a $15 to $20 cat printer (or a Seiko low-energy head, which runs
  from a single 3.0 to 4.2 V cell but pulls up to 6 A peak, so strobe the 384 dots in blocks),
  AS5600-class encoder, ESP32-C3, MOSFET strobe drivers, a small high-discharge LiPo, thermal
  ticket stock. About $40. Difficulty: medium
  (strobe timing versus speed, contact pressure).
- *Risks*: uneven pull gives stretched print (the encoder corrects this); too little pressure
  gives grey print; a stalled pull over-burns a line. Because the object is a boarding pass,
  lottery ticket or receipt, thermal print is expected.
- *Novelty*: I found no magic product or maker project that prints during withdrawal. High.

### 2. Write-through envelope (level 3; speculative)
- *Effect*: a spectator checks a blank card, seals it in an envelope and signs across the flap.
  The envelope sits on the performer's clipboard or close-up pad. After the choice the spectator
  tears it open: the card now bears the choice in handwriting.
- *Method*: the card is self-contained carbonless stock, which has dye capsules and developer on
  the same face (or a coated-back/coated-front pair disguised as one card). A two-axis stylus plotter under the pad surface, or in the clipboard
  body, writes on the outside of the envelope with a 1.5 mm ball stylus through a thin flexible
  skin. Pressure develops the line on the card inside. No ink ever touches the envelope.
- *Budget*: plotter cavity about 80 x 50 x 15 mm; 8 to 15 s per word; noise under about 35 dB with
  silent stepper drivers (unverified). Stall is covered by the performer writing their own
  "impression" on a pad.
- *BOM*: two optical-drive lead-screw steppers or micro linear actuators, one solenoid or
  micro-servo for stylus lift, TMC2209 drivers, ESP32, LiPo, carbonless stock. $40 to $80.
  Difficulty: medium to hard (registration between envelope and plotter; stylus force).
- *Risks*: faint blind embossing on the envelope's outside (use a stiff, lightly textured
  envelope and a broad ball); carbonless paper also marks under a fingernail, so the spectator
  must seal it without heavy handling; the mirror-image problem does not arise because the
  stylus writes from the front.
- *Novelty*: carbon and impression devices are classical for *stealing* writing; I know of none
  that *writes into* a sealed envelope. High.

### 3. Light-through-glass late marking (level 3; hazardous, stage-crew engineering)
- *Effect*: a rolled slip has been sealed inside a corked glass bottle hanging in view since
  before the show. After the choice the bottle is broken open or uncorked by a spectator: the
  slip carries the choice.
- *Method*: the slip is thermal or photochromic paper with its coated side facing the glass. A
  small steered beam (two-mirror galvo or a two-servo mirror) housed in the stand or the hanging
  fixture writes through the glass. On thermal paper the mark is permanent and there is no char
  and no smoke (unverified power requirement; bench test needed). A speculative variant uses a
  near-infrared source through a visually opaque "IR-pass" acrylic box wall onto NIR-absorbing
  laser-markable coating.
- *Budget*: beam unit about 60 x 60 x 40 mm for a DIY two-mirror head (estimate); 2 to 10 s;
  silent apart from mirror tick.
- *BOM*: 405 nm module, two small galvos or servos, driver, enclosure. $60 to $250. Difficulty:
  hard.
- *Risks and safety*: an open laser path near an audience is the main objection. The beam path
  must be fully shrouded from emitter to glass, interlocked to the bottle's presence, power-limited
  to what thermal paper needs, and tested for reflections from the curved glass. If that cannot
  be guaranteed, use the UV-LED mask version (concept 7) instead, which has no collimated beam.
- *Novelty*: late marking through the wall of an honestly sealed transparent container. High.

### 4. Breath index mirror (level 3; speculative)
- *Effect*: a spectator names a card. She breathes on the performer's small mirror (or her own
  compact, switched in): in the fog the card's value and suit stand out as clear glass for two
  seconds, then vanish. The mirror is handed out; there is nothing on it.
- *Method*: behind a thin (1 mm) mirror sits a flexible PCB carrying a matrix of trace heaters,
  for example two 5 x 7 characters at 6 mm pitch. Chosen pixels are warmed a few degrees above
  the rest for 20 to 60 s. Condensation forms everywhere except the warm pixels. Nothing is
  written, so nothing remains.
- *Budget*: 1 to 2 mm added thickness plus a coin cell or thin LiPo in the frame; silent; 20 to
  60 s of preheat hidden in patter; image persists while the temperature difference lasts.
- *BOM*: flex PCB heater matrix ($25 from a prototype house), shift registers, microcontroller,
  acrylic or thin glass mirror. About $35. Difficulty: medium (lateral heat spread sets the pixel
  size; needs tuning for room temperature and humidity).
- *Risks*: dry rooms and warm mirrors fog poorly; blur on thicker glass; the unexamined frame is
  the weak point, so build it as a framed travel mirror with the electronics in the frame.
- *Novelty*: static breath messages (finger grease, anti-fog) are old. An addressable one appears
  to be new in magic. HCI researchers have built condensation displays (unverified; Open leads).

### 5. Etch swami: a nail writer for metal (level 2; speculative)
- *Effect*: a borrowed key or coin is held in the performer's fist while a spectator settles on a
  word or number. The object comes back with that word permanently darkened into the metal.
- *Method*: a thumb-tip gimmick holds a felt wick wetted with a benign salt electrolyte and wired
  to a 9 to 12 V stack (for example an A23 cell); the borrowed object is the other electrode
  through a finger clip or a second pad. Writing with the wick leaves a dark oxide line wherever
  it dwells. A higher-quality variant prints a stencil after the choice on Brother STe stencil
  tape in a P-touch printer (table or case scale, not pocket) and etches through it in one press
  of a few seconds.
- *Budget*: thumb-tip size for the freehand version; 5 to 10 s for two or three characters
  freehand; a few seconds per press plus a few seconds to print for the stencil version (all
  estimates); silent; a wipe on a hidden pad removes electrolyte.
- *BOM*: thumb tip, wick, A23 cell, fine wire ($10); optional P-touch printer and $22 stencil
  tape. Difficulty: easy electrically, hard as sleight.
- *Risks*: works on steel, nickel and cupronickel, poorly on brass and aluminium; leaves moisture;
  permanently marking someone's key needs their consent after the fact, so frame it as a souvenir;
  check local law on marking coins.
- *Novelty*: I know of no etch-based nail writer. Medium to high.

### 6. Ink after signature (level 2/3)
- *Effect*: before anything is chosen, a spectator signs the back of a blank business card, which
  is placed writing-side down under a glass tumbler on a small tray. After the choice she lifts
  the glass and turns the card over: the prediction is on the other side in marker, in the
  performer's handwriting, on the card she signed.
- *Method*: the tray is a 20 mm thick false-bottomed prop holding a micro pen plotter that writes
  upward through an aperture closed by a sliding shutter. The pen is a cut-down refill of the same
  marker the performer uses openly. The strokes are the performer's own recorded letterforms
  re-assembled by software, so the hand matches other writing in the act.
- *Budget*: tray 150 x 100 x 20 mm; 10 to 20 s per word; 35 to 45 dB (unverified), covered by
  music or by the performer writing a decoy on a pad. A reflective sensor row confirms ink was
  laid down before the shutter closes.
- *BOM*: micro XY stage, pen-lift servo, silent drivers, ESP32, LiPo, 3D-printed tray. $60 to
  $120. Difficulty: medium to hard (writing upward against gravity suits felt tips, not
  ballpoints).
- *Risks*: card registration over the aperture; the tray cannot be examined; ink bleed-through on
  thin stock.
- *Novelty*: plotters as visible performers exist (agent 12). A hidden plotter as a swami
  replacement with a signature-first convincer appears new.

### 7. Thousand-mask chip and light (level 3; speculative)
- *Effect*: a framed "blank photograph" or a card in a clear sleeve has been on the table
  throughout. After a number between 000 and 999 is chosen, the performer warms the frame between
  the hands: the number has appeared in the middle of the card.
- *Method*: brute force and micro-factory combined. A 20 x 20 mm chip of photoplotted film carries
  all 1,000 numbers as tiny transparent masks. A two-axis micro stage (10 mm travel per axis)
  brings one mask over a UV LED; a small lens projects it at readable size onto photochromic or
  fast photo-switching paper through the frame backing. The general-purpose alternative is a
  resin-printer mono LCD in contact with the sheet, which can show anything, not only the
  pre-made set.
- *Budget*: projector block about 30 x 30 x 25 mm, or a 6 mm thick LCD sandwich; 5 to 20 s
  exposure on fast media; silent.
- *BOM*: film photoplot ($25 for hundreds of chips), two micro linear steppers, 365 to 405 nm LED,
  lens, or a small mono LCD ($20 to $40, unverified price) and LED array. $50 to $90.
  Difficulty: medium.
- *Risks*: commercial photochromic images fade in minutes (use as a feature: the proof
  disappears) and are low-contrast purple or blue; ambient daylight exposes the whole sheet;
  permanent fast media are lab-only so far.
- *Novelty*: a print engine with no print head and no paper path. High.

### 8. The reel of real things (level 3)
- *Effect*: the prediction that comes out of the box is not a printout: it is a fortune-cookie
  slip, a strip of four photo-booth pictures, a foil-stamped lottery ticket or a line in fountain
  pen on laid paper.
- *Method*: brute force by overnight automation. A desk plotter or a print service makes all N
  outs (N up to about 1,000) in the genuine medium on one continuous roll. A two-spool transport
  with an encoder parks at mid-roll, seeks the right frame and a receipt-style cutter separates
  it. The roll, transport and cutter sit in a tea tin, a table leg or the base of a "fortune"
  machine.
- *Budget*: 45 mm roll plus take-up, about 110 x 60 x 60 mm overall for 1,000 frames of 25 mm;
  seek 13 to 40 s worst case; 45 to 50 dB while seeking (unverified), so seek during applause or
  music and cut on the quiet.
- *BOM*: two N20 gearmotors with encoders, cutter from a receipt mechanism, frame-mark sensor,
  microcontroller. $40 to $70 plus the roll. Difficulty: medium.
- *Risks*: mis-registration (print a machine-readable tick beside every frame and verify before
  cutting); seek noise; a long roll telescopes if tension is poor.
- *Novelty*: a motorised index of genuine-medium outs. I found none on sale.

### 9. The room is the index (level 3; logistics as method)
- *Effect*: one person is chosen by a genuinely random, examinable process (a thrown ball passed
  back three times). She reaches under her own seat and finds a sealed envelope naming her seat,
  what she is wearing "tonight" in general terms, and the word she is about to think of.
- *Method*: every seat has a different envelope produced by variable-data printing from the
  seating plan (and the ticketing list where names are known). The word is covered by a second
  brute-force layer inside the envelope: a multi-condition card (concept 12) or a classical
  equivoque. Nothing is forced and nothing is switched.
- *Budget*: no device; no cycle time; no noise; 300 seats at agent 13's unit prices.
- *Risks*: everyone else also has an envelope. Three ways to deal with that: make it the finale
  ("you all have one"), print the surplus in fading ink so that it is blank by the interval
  (agent 8), or hide the envelopes where only an instructed person will find them and have crew
  clear the room.
- *Novelty*: "under your chair" is old with one forced seat. Covering every seat honestly is new
  in economics rather than in principle. A street version (a sticker on every lamp post in four
  blocks, each naming its own corner) needs permission or removable media to stay legal.

### 10. Factory date code (level 2/3)
- *Effect*: a spectator picks any can from a sealed multipack that has been on the table all
  night, then names a date or a number. She turns the can over: the lot code jetted on the base,
  among the usual digits, is her number.
- *Method*: the cans start with blank bases (or bases cleaned of their code). The coaster or tray
  the chosen can is set on hides a 12-nozzle thermal inkjet cartridge on a short spring slide, so
  setting the can down and nudging it "to the centre" swipes it across the nozzles; an encoder or
  a simple time base clocks the dots. Quick-dry solvent ink is the same class used by real coders.
- *Budget*: coaster 110 mm across and about 45 mm deep for a standing cartridge (unverified
  cartridge size; a lying-down layout would be thinner); print in under 1 s; silent; 5 to 10 s
  drying before it is turned over.
- *BOM*: C6602-class cartridge ($20 to $40), InkShield-style driver, boost converter to about
  20 V, microcontroller, slide. About $70. Difficulty: medium.
- *Risks*: concave can bases put the surface out of nozzle range (choose flat-bottomed tins,
  jars with flat lids, egg boxes, matchboxes or cartons); nozzle drying between shows; faint
  solvent smell.
- *Novelty*: uses the audience's own belief that such codes are applied in a factory. High.

### 11. The shuffler that deals fair and stacks anyway (level 2)
- *Effect*: at a home card table the host's battery shuffler shuffles a borrowed, spectator-mixed
  deck; the host then calls every hand before it is turned.
- *Method*: an open-source camera shuffler re-skinned as a consumer shuffler reads each card and
  bins it to a planned order while appearing to randomise.
- *Budget*: about 30 x 20 x 15 cm; 60 to 120 s; 55 to 65 dB, which is what people expect of a
  shuffler.
- *BOM*: about $200 in printed parts, three steppers, Pi Zero and camera. Difficulty: hard
  (reliable single-card feeding of worn cards).
- *Risks*: the machine is the obvious suspect. It only works where a shuffler is socially normal
  and the magic happens later and elsewhere. Gambling use would be cheating; this is for
  demonstration only.
- *Novelty*: known in the maker and casino-security worlds, not as a magic prop. Medium.

### 12. Six-answer card (level 2; no mechanism)
- *Effect*: one printed card has been in the spectator's pocket all evening. Whichever of six
  drinks she orders, the card proves it: by a breath, a rub, the black light over the bar, a
  drop of water, a tilt, or a look through the performer's sunglasses.
- *Method*: one out per independent channel (visible microtext, UV fluorescent, thermochromic,
  hydrochromic, lenticular or raking-light emboss, polariser). The performer only needs to know
  which trigger to call for.
- *Budget*: one card; no cycle time; silent. $2 to $10 per card in small runs.
- *Risks*: the five unused answers remain on the card. Either keep the card, or choose channels
  that are hard to trigger by accident, or let the five others be a deliberate second climax.
- *Novelty*: each channel is known (agent 8); stacking them as a brute-force index is a modest
  step. Medium.

## 5. Dead ends and overhyped items

- **Volumetric "prints in seconds" as a hobby engine.** Real, fast and visually perfect for a
  "forms inside a sealed vial" plot, but quote-only instruments, sticky uncured parts, and no
  consumer route in 2026.
- **Cyanotype behind an LCD.** 10 to 15 minutes of exposure and a water rinse. Only usable as an
  installation that works while nobody watches.
- **Hidden coin or penny presses.** Rolling a design into a coin needs a geared press of several
  kilograms and makes noise; nothing hideable found.
- **Braille embossers, dot-peen and impact dot matrix.** 60 to 80 dB class and heavy (unverified
  figures).
- **Electrosensitive spark printing.** Obsolete media, ozone smell, buzz.
- **Charring plain paper with a hidden laser.** Smoke and smell reach the front row before the
  reveal; needs extraction, which needs a fan.
- **Zink for anything but a photograph.** 50 s per print and a recognisable "instant photo" look.
- **Card-case deck sorters.** Reading the deck fits in a case; re-ordering it does not, with any
  mechanism found.
- **1,000 separate physical billets in a pocket.** The volume is about half a litre before
  mechanism. Use a continuous roll, microtext or print-on-demand.
- **QR or NFC tags pointing to every outcome.** Cheap and unlimited, but the reveal is on a phone
  and the audience's first theory ("the website changed") is correct.
- **Hidden FDM printing in a pocket-scale prop.** Heat-up, fans and minutes; only viable as a
  backstage engine feeding a chute.
- **Embroidery, button-badge presses.** Minutes or a visible hand press.

## 6. Open leads

- **Sources I could not collect because web search was rate-limited part-way through**: pill
  carousels and capsule vendors, SMD tape feeders, coin hoppers, micro pick-and-place gantries
  with N20 motors, DIY card dealers with measured cards per second, penny-press force figures,
  electro-etch stencil tapes and etch pens, carbonless paper sensitivity, Boogie Board film,
  condensation displays in HCI (I recall a Peltier-array "Ketsuro-Graffiti" project, unverified),
  laser-markable NIR coatings (DataLase-type, unverified), handheld edible-ink printers, measured
  noise of plotters on silent drivers, thermal ticket stock suppliers, mono LCD prices.
- **Bench tests worth a weekend each**: (1) minimum 405 nm power to mark thermal paper through
  3 mm glass; (2) pull-to-print thermal with an encoder-clocked strobe; (3) stylus force needed
  to mark self-contained carbonless paper through a 100 gsm envelope without embossing it;
  (4) heater-matrix pixel size versus mirror thickness for breath reveal; (5) 9 V wick etching on
  common coins and keys.
- **Motorised band stamp**: a rubber date/number stamp whose bands are set by micro gearmotors,
  giving a genuine inked impression of a chosen number.
- **Thermal print through an envelope wall by conduction**: a thermal head pressed on the outside
  of a thin envelope with thermal card inside; resolution loss unknown.
- **Latent marks that self-develop**: marks that are invisible when made and appear minutes later
  (bruised fruit skin, slow-oxidising inks), giving a micro-factory with a built-in time delay.
- **Stroke-level few-shot handwriting synthesis for plotters**: most 2024 to 2026 models are
  image-based; a stroke model trained on one performer's tablet recordings is a small, tractable
  software project.
- **Dealer products not opened**: Ultra Prediction Table, Stop the Press (Vanishing Inc.),
  PITATA Pro app capabilities, the Electricks Cosmos integration page.
- **Self-loading containers**: a roller intake that pulls a card or slip from the lip of a wallet
  or box into its sealed-looking inner compartment in under half a second; I found no product and
  did not get to search patents.

## 7. Sources

Magic prior art
- https://www.vanishingincmagic.com/mentalism/pitata-smart-printer-mini/ - PITATA Smart Printer Mini listing (size, price; page returned 403, figures from search listing)
- https://vanishingincmagic.com/mentalism/smart-printer - PITATA Smart Printer listing
- https://alakazam.co.uk/products/smart-printer-by-pitata-magic - PITATA Smart Printer, UK dealer
- https://shop.52kards.com/products/cosmos-by-blackbox-magic-creations - Cosmos printer wallet, $450, integrations
- https://electricks.info/?p=24806 and https://electricks.info/?p=32672 - Electricks pages listing PeriPage and Cosmos printer integrations
- https://vanishingincmagic.com/mentalism/ultra-prediction-table - Ultra Prediction Table (not opened)
- https://www.penguinmagic.com/p/19078 and https://vanishingincmagic.com/card-magic/dex - Dex 52-card single-pocket index
- https://www.penguinmagic.com/reviewcomments.php?rid=84755 and https://www.penguinmagic.com/reviewcomments.php?rid=32691 - multiple-out wallet reviews mentioning Kolossal Killer
- https://vanishingincmagic.com/mentalism/spirit-slates-pro - mechanical spirit slates
- https://tricksupply.com/?p=267069 - Electricks Spirit electronic blackboards
- https://www.conjuringarchive.com/list/category/227 and https://www.conjuringarchive.com/list/category/2236 - headline and mail prediction indexes
- https://www.pegani.dk/en/products/mentalism/the-telegraph-chest---magic-wagon - Telegraph Chest
- https://www.lybrary.com/the-glass-box-headline-prediction-p-743506.html - Glass Box headline prediction
- https://trickshop.com/bally-prediction.html and https://trickshop.com/how-to-predict-headlines.html - Bally prediction; headline methods overview

Thermal printing
- https://sii-thermalprinters.com/mechanisms-and-components/low-voltage-thermal-printer-mechanisms/ltp02-245/ - Seiko 2-inch mechanism size, mass, speed
- https://sii.co.jp/sps/eg/product/oldproduct/ltpu245.html - Seiko LTPU245
- https://citizen-systems.com/en/products/printer/kiosk/mlt4281 - Citizen 58 mm mechanism with cutter
- https://www.aps-printers.com/product-category/mini-printer-mechanisms/ - APS mini mechanisms
- https://epson.eu/en_EU/products/retail/pos-printers/mobile-printers/tm-p20-series/p/14345 - Epson mobile printer noise 52.9 dB(A)
- https://github.com/rbaron/catprinter - cat printer BLE driver
- https://werwolv.net/blog/cat_printer - cat printer protocol reverse engineering
- https://deepwiki.com/NaitLee/Cat-Printer/1.2-supported-hardware - supported cat printer models
- https://learn.adafruit.com/ble-cat-thermal-printer-with-memento.md - Adafruit cat printer guide
- https://magazine.raspberrypi.com/articles/bluetooth-cat-thermal-printer-review - cat printer review, 16 pounds
- https://github.com/AndBondStyle/niimprint and https://github.com/kjy00302/niimprint - Niimbot label printer drivers
- https://www.bhphotovideo.com/c/product/1937602-REG/niimbot_1aa5e283401_d11h_1_2_portable_hd.html - Niimbot D11-H specs

Inkjet
- https://www.hp.com/sa-en/products/ink-toner/product-details/product-specifications/43339 - HP C6602A specifications
- https://www.homofaciens.de/technics-machines-printhead-hp6602_en.htm - driving the HP 6602 nozzles
- https://github.com/RazaGR/InkShield and https://makezine.com/2011/06/01/diy-open-source-inkjet-printer/ - InkShield
- https://hackaday.io/project/176931-hp-printer-cartridge-control-module and https://www.github.com/lichnost/PrintSpider_Arduino - PrintSpider cartridge driver
- https://www.cnx-software.com/2019/11/01/princube-smallest-handheld-smartphone-color-inkjet-printer-prints-on-anything/ - PrinCube specs
- https://techradar.com/news/worlds-smallest-color-printer-can-print-on-anything-including-your-skin - PrinCube launch price, weight
- https://en.techreviewer.de/mbrush-princube-test/ - MBrush/PrinCube review
- https://boingboing.net/2020/08/07/this-temporary-tattoo-printer.html/amp - Prinker 3 s print
- https://xatakaon.com/other-devices/this-is-prinker-a-painless-tattoo-printer-that-inks-your-skin-in-seconds - Prinker mechanism
- https://stacksocial.com/sales/prinker-m-mobile-digital-temporary-tattoo-printer - Prinker M price and yield

Plotters and handwriting
- https://shop.pimoroni.com/products/axidraw-minikit-2 and https://shop.evilmadscientist.com/924 - AxiDraw MiniKit 2
- https://github.com/LingDong-/plotlet - Plotlet
- https://hackaday.com/2019/07/27/lack-of-space-is-no-longer-an-excuse-for-not-having-a-pen-plotter - tiny ESP32 plotter
- https://www.hackster.io/news/miniature-drawing-machine-almost-fits-on-your-hand-c0da2da8c28a - miniature drawing machine
- https://hackaday.com/2013/11/21/a-six-part-cnc-machine - post-it sized plotter
- https://community.robotshop.com/robots/show/two-servo-and-drawer-slide-pen-plotter - servo plotter caution
- https://arxiv.org/pdf/2003.10593 - Spatio-Temporal Handwriting Imitation
- https://arxiv.org/html/2409.04004v2 - One-DM one-shot handwriting generation
- https://www.arxiv.org/pdf/2409.06065 - DiffusionPen
- https://arxiv.org/abs/2508.21040v1 - FW-GAN
- https://cse.buffalo.edu/tech-reports/2026-43.pdf - 2026 Buffalo report on few-shot handwriting

Laser, light and other marking
- https://support.xtool.com/article/12 and https://woodcraft.com/products/xtool-f1-portable-laser-engraver - xTool F1
- https://support.laserpecker.net/hc/en-us/articles/7322687094543-LP2-Buying-Guide - LaserPecker LP2
- https://techcrunch.com/?p=1621213 and https://patents.google.com/patent/US9393804B2 - Tocano inkless carbonisation printing
- https://hackaday.com/2025/02/22/cyanotype-prints-on-a-resin-3d-printer and https://hackaday.io/project/202440-cyanoprinter - cyanotype on a resin printer
- https://www.photrio.com/forum/threads/making-a-uv-projector-for-alt-process-prints.212710/post-2971364 - LCD contact printing for alt processes
- https://phys.org/news/2017-02-ink-required-paper.pdf and https://patents.google.com/patent/US10534254 - Yin group light-printable rewritable paper
- https://www.escholarship.org/content/qt2wb412nw/qt2wb412nw.pdf?t=p1z7dt - Yin group paper (not opened; source of the under-20 s figure per search summary)
- https://www.expertreviews.co.uk/technology/printing-cameras/canon-zoemini-review - Zink print time
- https://www.digitalcameraworld.com/uk/reviews/canon-zoemini-2-mini-photo-printer-review - Zink print time
- https://rtings.com/printer/reviews/canon/ivy-mini-photo-printer - Zink resolution
- https://hackaday.com/2025/03/31/zink-is-zero-ink-sort-of - Zink explainer
- https://en.wikipedia.org/wiki/ZX_Printer - electrosensitive printing

Card machines
- https://www.hackster.io/news/rig-the-deck-so-you-always-win-with-this-card-shuffler-5db782b1b15f - 3DprintedLife shuffler
- https://www.tomshardware.com/news/rig-your-next-card-game-with-the-help-of-a-raspberry-pi - same
- https://hackaday.com/2020/07/20/raspberry-pi-shuffler-is-computerized-card-shark - same
- https://engineering.purdue.edu/477grp10 - Purdue Smart Card Shuffler
- https://projectswiki.eleceng.adelaide.edu.au/projects/index.php/Projects:2014S1-16_Automatic_Sorter_using_Computer_Vision - Adelaide card sorter
- https://www.hackster.io/news/david-stern-s-dave-o-matic-is-a-sneaky-bridge-dealing-bot-peeking-at-the-cards-for-pre-set-hands-977451688056 - Dave-o-Matic
- https://hackaday.com/2025/03/26/3d-printed-scanner-automates-deck-management-for-trading-card-gamers - single-card roller feeder
- https://tcgmachines.com/product and https://www.tcgmachines.com/blog/launch-day - PhyzBatch-9000
- https://seller.tcgplayer.com/roca-sorter - Roca sorter
- https://ioactive.com/article/internal-camera-hacked-casino-card-shuffler-lets-you-look-at-the-cards/ - Deckmate 2 research
- https://www.tomshardware.com/news/raspberry-pi-enables-security-researchers-to-hijack-casino-card-shuffling-machine - same

Assembly and fabrication
- https://makerworld.com/models/1826151 - 3 min 52 s Benchy profile
- https://3dprintingindustry.com/news/xolo-launches-new-xube%C2%B2-volumetric-3d-printer-technical-specifications-and-pricing-232600/ - Xube2
- https://www.aniwaa.com/product/3d-printers/readily3d-tomolite/ - Tomolite
- https://hackaday.com/2026/02/25/sub-second-volumetric-3d-printing - sub-second volumetric printing
- https://www.3dnatives.com/en/notable-volumetric-3d-printing-projects-2026-10092026/amp/ - volumetric printing round-up
- https://www.ri.cmu.edu/publications/robotic-origami-folding-2 - origami-folding robot
- https://www.drinkripples.com/commercial-coffee-printer-buyers-guide/commercial-coffee-printer/ - Ripple Maker
- https://perfectdailygrind.com/2023/09/digital-coffee-beverage-printers-latte-art/ - beverage printers

Brute-force media
- https://en.wikipedia.org/wiki/Microprinting - microprinting limits
- https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/7270918 - microprinting patent
- https://mtl.mit.edu/pipermail/labnetwork/2018-August/003228.html - film mask prices and limits
- https://wiki.nanofab.ucsb.edu/wiki/Tutorial_-_How_Photomasks_are_Made - photomask tutorial
- https://vanderbilt.edu/vinse/facilities/instruments/photoplotter.php - 25,400 dpi photoplotter
- https://en.wikipedia.org/wiki/Stanhope_(optical_bijou) - Stanhope peeps
- https://www.cpbj.com/mechanicsburg-man-a-global-source-for-stanhope-lenses/ - present-day Stanhope maker
- https://en.wikipedia.org/wiki/Lenticular_printing - lenticular basics
- https://www.4over4.com/faqs/general/how-many-images-can-i-combine-in-a-single-lenticular-print - lenticular frame counts
- https://support.xtool.com/article/3802 - lenticular card guide
- https://infoscience.epfl.ch/handle/20.500.14299/157014 - EPFL two-image prints
- https://www.photonics.com/Article.aspx?AID=16892 - coloured-light hidden images
- https://uspto.report/patent/grant/10889141 - multiple hidden images by polariser
- https://phys.org/news/2016-12-hidden-images-commercial-inkjet-printers.pdf - hidden images with commercial inkjets
- https://erikdemaine.org/fonts/ , https://erikdemaine.org/fonts/hinged/ , https://erikdemaine.org/fonts/dissect , https://erikdemaine.org/papers/PuzzleFonts_G4G14/paper.pdf - Demaine puzzle fonts
