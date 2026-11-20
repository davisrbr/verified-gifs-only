# 05 - Optics, photonics and display technology (2015-2026) as sources of magic methods

Research note. The shared web-search budget for this project ran out after my first 14 searches,
so most of this report rests on (a) those searches, (b) about 60 direct page fetches of primary
pages, and (c) my own background knowledge. Anything in category (c) that I could not confirm on a
page is marked **(unverified)**. Several supplier sites could not be reached from this session
(listed at the end). Prices are as seen in late 2026.

Following the course correction, the catalog is in two parts. Part A (long) treats optics as
hidden infrastructure: who can see what, from where, in which band, and what can be made to
disappear at arm's length. Part B (short) covers the level-1 spectacles: cloaks, aerial images,
volumetric displays.

---

## 1. Summary

- **The most useful optical capability for a magician is selective visibility, not spectacle.**
  Cheap parts now let a builder decide, per surface, which observer (performer, one spectator, a
  camera, nobody) can read it, by polarisation, wavelength, angle or position of the light source.
- **Polarisation gives a private, full-resolution display channel for about $20.** An LCD with its
  front polariser peeled off looks like a blank white light panel; anyone wearing ordinary
  polarised sunglasses sees the full image. Google used a stacked version at I/O 2015. I found no
  sign that magic uses this as a prompter.
- **"Looks opaque, passes infrared" is now a filament and a print setting.** IR-transmitting PLA
  costs about $6 per 100 g; a 1.1 mm wall hides a code, sensor, LED or camera completely (MIT
  InfraredTags, CHI 2022). Likewise, black printed with carbon (K) and black printed as a C+M+Y
  mix match by eye and separate under near-IR, which banknotes exploit.
- **Paper-looking displays with no battery exist off the shelf.** A 2.9 inch NFC-powered e-paper
  panel is $27.99, has no battery, is powered and rewritten by a phone held against it, and holds
  its image indefinitely. It reads as print, not as a screen.
- **Displays can hide behind real materials.** Google's "Hidden Interfaces" (CHI 2022) drives a
  PMOLED through 0.2 to 1.6 mm of wood veneer, textile, acrylic or mirror film; the surface looks
  untouched when off.
- **Ultra-black paint moved from lab to craft shop.** Musou Black (about 99.4% absorption, EUR 25
  per 100 ml) and Black 4.0 (maker claims 99%+, GBP 49.99 per 150 ml) bring black art down from
  stage distance toward arm's length; the limit is now durability, not darkness.
- **Total internal reflection is a mirror with no silvering and no edge.** Inside a clear acrylic
  block, an air gap perpendicular to the viewing face is a perfect mirror at every viewing angle
  (critical angle 41.8 degrees), and it switches off when the gap is flooded with water. That
  allows the mirror principle inside an object that looks like solid clear plastic.
- **Caustic "magic windows" are hobbyist-buildable** with open code (Ferraro, MIT licence) and a
  hobby CNC or resin printer. They are level 1 on their own; they become interesting when cheap
  enough to make one per outcome.
- **Cloaks, aerial images and volumetric displays are mostly weak for live magic.** Each has a
  narrow working geometry, visible apparatus, and an audience that immediately says "hologram" or
  "screen". AIRR floating images are the most buildable (about $150 to $300) and the most honest
  about being dim.
- **Hazards in this slice:** lasers (anything scanned, anything above 5 mW, all 405 nm), UV LEDs
  at 365 nm, the 48 to 65 V AC drivers for PDLC film, and fragile glass optics near spectators.

---

## 2. Catalog

### Part A - Optics as hidden infrastructure

#### A1. Polarisation as a private channel

**What it is.** An LCD forms its image between two polarisers. Remove the front one and the panel
shows uniform white; the image is still there, encoded as polarisation state, and reappears through
any linear polariser. Google's I/O 2015 version stacked a stripped LCD in front of a normal one, so
the naked eye saw ordinary content and a polarising badge revealed a second image. Separately,
clear birefringent films (cellophane, stretched packing tape) are invisible on their own but show
strong colours between two polarisers, and a rotated analyser inverts or swaps the colours. Security
printing uses the same trick for "latent images" revealed by a polariser.

**References.** Hackaday, "Trick Google Used Hides Secret Messages On LCD Screens", 2015,
https://hackaday.com/2015/07/15/trick-google-used-hides-secret-messages-on-lcd-screens/ ;
Hackaday polariser tag (stress polariscope 2022, transparent LCD 2020, Pe Lang art 2017),
https://hackaday.com/tag/polarizer/ ; Instructables "Privacy Monitor Hacked From an Old LCD
Monitor" (title only loaded), https://www.instructables.com/Privacy-monitor-made-from-an-old-LCD-Monitor/ ;
latent images in security printing, https://en.wikipedia.org/wiki/Security_printing .

**Accessibility.** Hobbyist. A discarded monitor or a $15 to $40 small IPS panel, a craft knife and
solvent; polarised sunglasses $10 to $20. Peeling polarisers destroys some panels (the Hackaday
builder lost several).

**Magic relevance (level 2, primitives: tell, know, conceal).** A cue screen in full view that
only the performer can read: it presents as a lamp, lightbox sign, "broken" photo frame or softbox.
The analyser can be sunglasses, a tinted "loupe", or a strip of polariser film on spectacle lenses
(polariser film looks like a neutral grey tint of roughly 40% transmission **(unverified
figure)**). The reverse use: any ordinary LCD in the room (TV, monitor, phone, tablet) emits
polarised light, so clear tape marks stuck on it are invisible to everyone except someone looking
through a polariser. Weaknesses: spectators with polarised sunglasses; glossy surfaces near
Brewster's angle partially analyse the light, so a glass tabletop can show a ghost of the hidden
image; the white panel must have a reason to be there.

**Prior use in magic.** I found none documented. The hacker community has known it since about
2011.

#### A2. Wavelength selectivity: things that match by eye and differ in the near-IR or UV

**What it is.** Human vision ends near 700 nm; silicon sensors work to about 1000 nm. Many dyes
that look black are transparent beyond 750 nm, while carbon black absorbs throughout. Results:

- *IR-transmitting plastic.* MIT's InfraredTags prints the object body in IR-transmitting PLA
  (3dk.berlin, about $5.86 per 100 g) that looks slightly translucent black. A shell of 1.08 mm
  hides air-gap or ordinary-PLA code bits behind it. A $20 Raspberry Pi NoIR camera with two
  940 nm LEDs reads a 6 to 9 mm marker from up to 250 cm, decoding in 6 to 14 ms.
- *NIR-fluorescent plastic.* BrightMarker (UIST 2023) embeds a 0.15 mm layer of NIR-fluorescent
  ABS under a 0.3 to 1.2 mm coloured shell; excitation about 760 nm, emission about 775 nm, read
  through an 830 nm long-pass filter at 60 fps with 99%+ decode on moving objects. The marker and
  the excitation light are both invisible. The filament is a speciality product (DIC Corp.).
- *K versus CMY black in print.* Wikipedia's security-printing article shows a EUR 50 note under
  700 nm and 1000 nm light: colours that look identical in the CMYK print separate, and some
  vanish. Any printer or print service that lets you choose "K only" versus "rich/composite black"
  is in principle an IR-contrast printer, provided its K is carbon pigment (true for most laser
  toner and pigment inks; many dye blacks are IR-transparent) **(the pigment/dye rule is from
  memory, unverified here; test each printer with a NoIR camera)**.
- *Cold mirrors.* A dielectric cold mirror reflects visible light and transmits IR, so a "mirror"
  can have an IR camera or beam behind it (https://en.wikipedia.org/wiki/Cold_mirror).
  IR-transmitting black acrylic sheet (the material of TV-remote windows) is sold by plastics
  suppliers **(unverified here; no supplier page reached)**.
- *UV fluorescence, phosphorescence, upconversion.* Invisible UV-fluorescent inks, afterglow inks
  and multi-wavelength fluorescence are standard security features (same Wikipedia page).
  Upconversion ("anti-Stokes") phosphors that turn 980 nm into visible green are sold as IR
  detector cards and powders **(unverified here)**.

**References.** Dogan et al., "InfraredTags", CHI 2022,
https://hcie.csail.mit.edu/research/infraredtags/infraredtags.html ; Dogan et al., "BrightMarker",
UIST 2023, https://hcie.csail.mit.edu/research/brightmarker/brightmarker.html ;
https://en.wikipedia.org/wiki/Security_printing .

**Accessibility.** Hobbyist; $10 to $60 for filament, NoIR camera, 850/940 nm LEDs. 940 nm is
fully invisible; 850 nm shows a faint red glow at the emitter.

**Magic relevance (levels 2 and 3, primitives: know, tell, conceal, prove ordinariness).** This
removes the window, hole or seam that every sensing gimmick used to need. A sealed, glossy black
3D-printed object can contain an IR remote receiver, a break-beam, a camera or status LEDs with no
visible aperture and no radio. A printed prop can carry a machine-readable identity that survives
visual inspection, UV lamps and the "riffle test". The sensing side (cameras, decoding) belongs to
agent 10; the materials side is here. Giveaways: IR PLA is slightly translucent against a bright
light, so shells need tuning; phone cameras see 850 nm and often 940 nm, so a spectator filming
may catch emitters.

**Prior use.** Card cheats' "luminous readers" (greenish ink on red backs read through red-tinted
glasses or contact lenses) and "video-luminous" marks read by camera and filter are the direct
ancestors (https://en.wikipedia.org/wiki/Card_marking). IR-marked decks sold to cheats exist
**(unverified here)**.

#### A3. Metamerism and tunable LED lighting

**What it is.** Two surfaces with different reflectance spectra can match under one illuminant and
differ under another (illuminant metameric failure); inkjet prints are especially prone. The
overt art version is Carnovsky's RGB series (from 2010): three superimposed images printed in
cyan, magenta and yellow, each isolated by red, green or blue light. The covert version is new:
smart bulbs can produce "white" either from a broadband phosphor channel or from mixed narrow R, G
and B channels. Both look white on a white wall, but they render a metameric ink pair differently.

**References.** https://en.wikipedia.org/wiki/Metamerism_(color) ; Carnovsky RGB,
https://www.carnovsky.com/RGB.htm . I could not search for papers on designed metameric pairs
under LED illumination; treat the covert version as my own proposal.

**Accessibility.** Hobbyist. RGBW smart bulb $15 to $40 **(unverified price)**, an inkjet printer,
a camera. Pairs can be found by brute force: print a few hundred patches, photograph under both
lighting states, let a script pick pairs that match in one and differ most in the other.

**Magic relevance (level 3, primitives: transform, delay, conceal, erase the evidence).** The
developer for a hidden image becomes the room lighting, which nobody examines. Writing can appear
on an examined poster, card or wall with nothing touching it, and vanish again. Risks: RGB-mixed
white has poor colour rendering, so faces and clothes shift noticeably if the whole room switches;
restrict it to one spot lamp over the prop. Observer metamerism means a few spectators (and all
cameras) will see a faint difference in the "matched" state.

**Prior use.** Red-filter decoders and luminous readers are the classical narrow-band reveal. I
know of no use of tunable-spectrum room lighting as a method.

#### A4. Angle-selective and position-selective surfaces

- **Micro-louvre light-control ("privacy") film.** Microscopic slats pass light only near the
  normal; laptop makers build it in (HP SureView, Lenovo PrivacyGuard)
  (https://en.wikipedia.org/wiki/Monitor_filter). Typical cut-off is about 30 degrees each side
  of normal, and phone-sized sheets cost about $10 **(both unverified here)**. Capability: a
  screen or printed panel that exists for one seat only; or a slot or cavity whose interior is
  black from every oblique angle.
- **Lenticular sheet.** A printed interlaced image under cylindrical lenses shows different images
  at different angles. Flip images need a large angle change, 3D needs many views with small
  changes; inkjet-and-laminate at home is established practice, with phasing and ghosting as the
  usual defects (https://en.wikipedia.org/wiki/Lenticular_printing). Lenticular optics can now be
  printed into objects (Hackaday 2021, 2025, and MIT's ShiftLens sliding indicators, 2026:
  https://hackaday.com/tag/lenticular/ ; details belong to agent 6). Capability: a flat surface
  0.3 to 0.6 mm thick **(unverified thickness)** that shows the audience one thing and the
  performer, standing off-axis, another.
- **Retroreflective marks.** Glass-bead or prismatic retroreflectors return light toward its
  source, so they look bright only to an observer almost in line with the lamp; traffic
  engineering uses a 0.2 degree observation angle as its test geometry
  (https://en.wikipedia.org/wiki/Retroreflector). Clear retroreflective sprays marketed as
  invisible in daylight exist (Albedo100 "Invisible Bright" **(unverified; product page did not
  load)**). Capability: a mark that only a viewer or camera with a co-located light can see,
  readable across a room.
- **Recessed apertures.** A 1 mm LED or fibre end at the bottom of a 20 mm deep matt-black bore
  is visible only within about 3 degrees of the bore axis (simple geometry). A free, zero-cost
  "tell" channel aimed at one pair of eyes.
- **Barrier grids and moire.** Scanimation (Rufus Butler Seder, from 2007) slides a striped
  acetate over an interlaced print to play six or more frames
  (https://en.wikipedia.org/wiki/Barrier-grid_animation_and_stereography). As a method rather
  than an effect: an interlaced print is unreadable noise until the matching grid lies on it, so
  the grid (a "plain" striped card sleeve, a comb, a window blind) is a physical decryption key.

**Magic relevance (level 2, primitives: tell, know, conceal).** These let information sit in plain
sight on the working surface. They also hide depth: a louvre film over a gap turns it into a
uniform dark line from all but one direction.

#### A5. Ultra-black coatings

**What it is.** Vantablack (carbon nanotube forest, up to 99.965% absorption) is export-controlled
and licensed exclusively to one artist for art use. The accessible substitutes are acrylic paints
with a very rough microstructure: Musou Black (Koyo Orient Japan), reported at up to 99.4%
absorption, and Stuart Semple's Black 4.0, which the maker claims absorbs "at least 99%" (99.6%
in its FAQ). User reviews consistently rank Musou as darker than Black 3.0/4.0; I found no
controlled measurement. For comparison, black velvet, the classical black-art material, is
usually quoted near 1 to 2% reflectance and ordinary matt black paint near 5% **(unverified)**.

**Prices seen.** Musou Black: EUR 25 per 100 ml, EUR 235 per litre; Musou Black Fabric KIWAMI from
EUR 25; flock sheets from EUR 16 (https://www.musoublack.com/). Black 4.0: GBP 49.99 per 150 ml,
covering about 2 square metres (https://culturehustle.com/products/black-3-0-the-worlds-blackest-black-acrylic-paint-150ml).
The Drive overview: https://www.thedrive.com/guides-and-gear/whats-the-blackest-black-paint.md .
Vantablack numbers: https://en.wikipedia.org/wiki/Vantablack .

**Limits.** Both paints are fragile. Black 4.0's own page warns that it scuffs, takes
fingerprints, cannot be varnished (any topcoat adds shine and destroys the effect) and cracks on
fabric; Musou is reported as even easier to rub off **(unverified)**. They are for surfaces
nobody touches.

**Magic relevance (level 2, primitives: conceal, prove ordinariness).** Black art works when two
blacks cannot be told apart. Dropping reflectance from about 2% to about 0.6% roughly triples the
lighting level or halves the distance at which a black gimmick against a black ground stays
invisible (my estimate, not a measured claim). Uses: wells and servantes in close-up mats, thin
rod supports, thread, edges of mirrors and glass, the inside of "empty" boxes, 3D-printed
gimmicks whose layer lines would otherwise catch light. A painted disc reads as a hole; a real
hole reads as a painted disc.

**Prior use.** Black art is 19th-century stage practice (Kellar is named in Hopkins 1897, per
https://en.wikipedia.org/wiki/Black_light_theatre ; Max Auzinger is usually credited as
originator **(unverified)**). Magicians do discuss Musou Black for wells and tables
**(unverified; no product page checked)**.

#### A6. Thin mirrors, beam splitters and anti-reflection glass

**What it is.** Three parts fix the three classical giveaways of mirror methods.

- *The edge.* A glass mirror shows a bright line at its edge. Alternatives: first-surface mirror
  on thin glass; metallised polyester film; and 3M Enhanced Specular Reflector film from LCD
  backlights, a non-metallic multilayer film about 65 micrometres thick with over 98% reflectance
  **(unverified here; figures from memory)**. A film mirror stretched on a printed knife-edge
  frame has an edge thinner than a hair.
- *The reflection off the front window.* Ordinary glass reflects about 4% per surface
  **(unverified, standard optics)**. Picture-framing "museum glass" has double-sided
  anti-reflection coating: under 1% reflection, over 97% transmission, 2.5 mm thick
  (https://tru-vue.com/solution/museum-glass/). A pane of it in front of a dark interior is close
  to invisible, and it removes the glint that betrays Pepper's ghost glass.
- *The beam splitter.* Teleprompter glass is the standard hobby beam splitter (used in the AIRR
  builds below). 70/30 and 60/40 sheets in glass and acrylic are sold cut to size **(supplier
  page returned an error; prices unverified)**.

**Magic relevance (level 2, primitives: conceal, swap, transform).** Mirror boxes, mirror glasses,
the Sphinx table and Pepper's ghost are 1860s methods (Pepper and Dircks 1862; a 45-degree pane,
a hidden lit "blue room", matt-black surroundings: https://en.wikipedia.org/wiki/Pepper%27s_ghost).
Their failure at close range is entirely about edges, glints and mismatched blacks. Thin film
mirror plus ultra-black edge paint plus AR glass makes a matchbox-scale Sphinx or a card-case
Pepper's ghost plausible at 50 cm. A miniature Pepper's ghost with a small OLED as the hidden
"room" gives a visible transformation inside a clear-fronted box with no screen in the line of
sight.

#### A7. Index matching and total internal reflection

**What it is.** A transparent solid disappears in a liquid of the same refractive index: Pyrex in
cooking or mineral oil, polyacrylamide hydrogel beads in water, and FEP fluoropolymer (index close
to water's 1.33) in water are the standard cases **(indices from memory; the Exploratorium page
for the Pyrex demonstration would not load)**. The opposite extreme is total internal reflection
(TIR): light inside acrylic or glass hitting an air boundary beyond 41.8 degrees is reflected
100%. A consequence worth spelling out: inside a rectangular block with index above 1.414, any
air-gap plane perpendicular to the face you are looking through acts as a perfect mirror at every
viewing angle. TIR is "frustrated" when something of similar index touches the surface within a
few wavelengths, which is why fingerprint ridges show on a wet glass
(https://en.wikipedia.org/wiki/Total_internal_reflection). Against water the critical angle for
acrylic rises to about 63 degrees (computed from n = 1.49 and 1.333), so flooding an air gap turns
a mirror into a window.

**Accessibility.** Hobbyist: clear acrylic, CNC or laser cutting, flame or solvent polishing,
clear casting resin; FEP film, tube and heat-shrink are cheap industrial stock **(unverified
prices)**.

**Magic relevance (levels 2 and 3, primitives: conceal, hold/release, transform, prove
ordinariness).** (a) Seams, partitions, holders and threads that vanish in a glass of liquid; the
classical glass disc in water is the ancestor. (b) A mirror compartment inside a "solid clear
block" with no silvering to scratch and no mirror edge. (c) A switch: an optical state change
caused by wetting, with no moving parts. Constraint: like every mirror method, what the TIR face
shows is a reflection of the block's own sides, so sides and back must match (frosted or uniform).

#### A8. Image relays: making a thing appear where it is not

- **Coherent fibre bundles.** Ulexite ("TV rock") carries an image from one polished face to the
  other along natural fibres, so the image appears to sit on the top surface
  (https://en.wikipedia.org/wiki/Ulexite). Synthetic fibre-optic faceplates, tapers and rigid
  "image conduit" rods do the same with far better resolution; conduit can be heat-bent to carry
  an image round a corner. Edmund Optics sells them **(product page returned 403; price roughly
  tens to low hundreds of dollars, unverified)**.
- **GRIN rod arrays.** Radial gradient-index rods are used as relay lenses in endoscopes and, in
  arrays, in scanners and photocopiers (https://en.wikipedia.org/wiki/Gradient-index_optics).
  A scanner's contact-image-sensor strip contains a lens array that forms an upright 1:1 image a
  few millimetres away **(working distance unverified)**: a salvageable flat relay.
- **Dihedral corner reflector plates (ASKA3D, Parity Mirror).** A passive plate of crossed
  micro-mirrors forms a real image in the air at the same distance in front as the object is
  behind. Sold to integrators; no price found. (See B2.)
- **Concave mirror pairs ("Mirage" toy).** Two facing paraboloids lift a real image of a small
  object to the opening. Old, cheap, well known **(unverified details)**.

**Magic relevance (level 2, primitives: know, conceal, transform).** A relay with no electronics
is a peek device that has no battery, makes no sound and emits nothing: the underside of a die,
coin or card is carried to a spot only the performer looks at. Faceplates make something beneath
a surface look printed on the surface, the reverse of what a spectator assumes. Relays also make
a thin prop look deep (the image of a cavity elsewhere) or a deep prop look thin.

#### A9. Switchable transparency

- **PDLC film.** Milky when unpowered, clear when driven; the article describes it as in effect a
  capacitor between two plastic layers (https://en.wikipedia.org/wiki/Smart_glass). Material
  cost is about $25 to $60 per square foot in cost guides seen in search results; small samples
  with drivers sell on marketplaces **(unverified)**. Typical drive is 48 to 65 V AC, switching
  in well under a second, with residual haze when clear **(unverified figures)**. Important: the
  off state scatters light; it does not block it. An object touching the film is still visible;
  one 5 cm behind it is a blur.
- **Liquid-crystal shutters.** Adafruit's large LC light valve: $7.50, 88.5 x 34.5 mm aperture,
  clear-grey to at least 95% blocking between 1 V and 4 V, near-zero current
  (https://www.adafruit.com/product/3330). Auto-darkening welding-lens cells are a larger cheap
  source **(unverified)**.
- **Electrochromic and suspended-particle glass.** Slow (seconds to minutes) tinting; printed
  electrochromic segment displays (Ynvisible) are thin, flexible, ultra-low-power "printed
  e-paper" with an Arduino kit (https://www.ynvisible.com/).

**Magic relevance.** As the visible effect (a frosted box clears to show a production) PDLC is
level 1 and reads as "smart glass" to anyone who has seen an office meeting room. As hidden
infrastructure it is better: a diffuser that is the back wall of a prop until the moment a camera
or the performer needs to see through it; an LC shutter as a silent, 5 V, no-moving-parts cover
over a hidden image, light path or sensor window. **Hazard:** PDLC drivers deliver tens of volts
AC; insulate edges and bus bars.

#### A10. Displays that do not look like displays

- **NFC-powered e-paper.** Waveshare 2.9 inch passive NFC e-paper: $27.99, 296 x 128 px, no
  battery, powered and written by a phone or NFC reader, 2 s refresh plus transfer time
  (https://www.waveshare.com/2.9inch-nfc-powered-e-paper.htm). Bistable: the image stays with no
  power.
- **Electronic shelf labels.** OpenEPaperLink is open firmware for retail e-paper tags over
  802.15.4 from an ESP32 access point; tags idle at about 9 microamps and check in every 40 s or
  more (https://github.com/OpenEPaperLink/OpenEPaperLink). Surplus tags are a few dollars each
  **(unverified)**.
- **Hidden-until-lit.** Olwal and Dementyev (Google, CHI 2022) show a 128 x 96 PMOLED through
  0.2 mm mirror film up to 1.6 mm basswood, 5 to 40 times brighter through the material than
  AMOLED for sparse content; thick basswood passes little light
  (https://research.google/blog/hidden-interfaces-for-ambient-computing/).
- **Transparent displays.** Small transparent OLED modules are sold to hobbyists (SparkFun,
  Waveshare) **(pages not reachable; unverified)**; large transparent OLED and micro-LED panels
  are commercial signage, far over budget **(unverified)**. DIY: replacing an LCD's reflector
  makes it partly see-through (Hackaday 2020, via the polariser tag page).
- **Pressure-written cholesteric LCD tablets** (the $5 to $20 "LCD writing tablet"): written by
  pressure, erased by one voltage pulse **(unverified; page did not load)**. A writing surface
  with a remote erase line is the "erase the evidence" primitive in sheet form.

**Magic relevance (level 3, primitives: transform, delay, swap, prove ordinariness).** E-paper is
the first display that passes for a printed label at arm's length: no glow, full viewing angle,
readable in sunlight. With NFC power the object contains no battery to find and nothing to charge.
Giveaways: the refresh flashes black and white for a second or two, so the update must happen out
of sight; the panel is rigid glass with a visible border; its "white" is light grey, so real
printed surroundings must be matched to it.

#### A11. Light as trigger, power, data and pen

**What it is.** A photodiode or 38 kHz IR receiver module behind an IR-pass wall (A2) gives a
sealed object a command input with no antenna, pairing or radio signature; a $1 IR LED in a ring,
pen or lamp is the transmitter **(component prices unverified)**. Small solar cells can
trickle-charge a sealed prop through a clear or IR-pass window. Light can also write. MIT's
Photo-Chromeleon (UIST 2019) coats objects with mixed cyan, magenta and yellow photochromic dyes,
activates them with UV and selectively erases them with a projector's red, green and blue;
textures take 24 minutes to 2 hours to write and fade over 5 to 26 hours indoors
(https://hcie.csail.mit.edu/research/photochromeleon/photochromeleon.html ; the dye chemistry is
agent 8's). Faster and cruder: a 405 nm laser pointer writes instantly on strontium-aluminate
glow paint and the trace fades in minutes **(unverified, common toy behaviour)**.

**Magic relevance (level 3, primitives: tell, delay, transform, erase the evidence).** Remote
state change of a surface or mechanism through a transparent or IR-pass barrier, with nothing
attached to the object. **Hazards:** 405 nm and all scanned lasers are eye hazards even at 5 mW;
never direct a beam toward seating; public laser displays are regulated in many countries. UV LEDs
at 365 nm need eye protection during building.

#### A12. Engineered light patterns

- **Computational caustics.** A clear slab with a gently sculpted face (about 2 mm relief over
  10 x 10 cm) projects an image when light passes through. Schwartzburg, Testuz, Tagliasacchi and
  Pauly (SIGGRAPH 2014) used optimal transport to get high contrast including true black; EPFL
  spin-off Rayform takes a few custom projects a year, in acrylic, glass or polished metal. Matt
  Ferraro's 2021 write-up and MIT-licensed Julia code (286 stars), following Yue et al. 2014,
  made it a hobby project: a quarter-inch ball-nose bit, 10 minutes roughing, 90 minutes
  finishing, 30 minutes hand sanding and polishing. Moritz von Sivers made a caustic clock dial
  with a resin printer (2025). A flat liquid-crystal version (Hufnagel et al., Optica 2022) is
  lab-only and polarisation-dependent. Fabrication research belongs to agent 6.
  Refs: https://infoscience.epfl.ch/record/201509 ; https://rayform.ch/ ;
  https://mattferraro.dev/posts/caustics-engineering ;
  https://github.com/MattFerraro/causticsEngineering ;
  https://hackaday.com/2021/08/23/math-optics-and-cnc-combine-to-hide-secret-images-in-acrylic/ ;
  https://hackaday.com/2025/01/20/innovative-clock-uses-printed-caustic-lens/ ;
  https://physicstoday.aip.org/news/magic-window-uses-liquid-crystals-to-project-images .
  Magic relevance: an examinable object carrying an image nobody can see in it. The image is
  fixed, needs a small bright source at the design distance, and the slab is visibly wavy. The
  ancestor is the East Asian bronze "magic mirror" **(unverified)**.
- **Specular (scratch) holograms.** Circular-arc scratches on plastic give glints that float in
  depth under a point light (Beaty 1990s; Brand's computed version, Applied Optics 2011):
  https://en.wikipedia.org/wiki/Specular_holography . Compass-and-acrylic cost; invisible under
  diffuse light, which makes it a covert mark revealed by a phone torch.
- **DIY holography.** Litiholo's self-developing film needs no chemicals: 20-plate 2 x 3 inch kit
  $239.99, about 5 minute exposures; large-format bundles $499.99 to $769.99; full-colour kit
  $589.99 (https://www.litiholo.com/hologram-kits.html). A reflection hologram is a film that
  shows real depth and parallax of a scene that is not there.
- **Diffractive elements and metasurfaces.** Cheap laser "star cap" gratings are diffractive
  optical elements; custom patterns and catalogue metalenses are sold by optics houses at lab
  prices **(unverified; no supplier page reached)**. No hobby route to custom metasurfaces found.
- **Structural colour.** Printing on diffraction-grating film transfers an iridescent surface to
  a 3D print **(unverified)**; an angle-dependent finish, of limited method value.

### Part B - Level-1 spectacles (brief)

#### B1. Passive cloaks

- **Rochester cloak** (Choi and Howell, Optics Express 22, 29465, 2014): four ordinary lenses.
  The demonstration used 50 mm achromats, f1 = 200 mm and f2 = 75 mm, pairs spaced f1 + f2. The
  hidden region is a doughnut around the axis (the centre cannot be cloaked), viewing is good to
  a few degrees and the mathematics to about 15. It is a metre-long tube you look down, with
  edge effects. https://arxiv.org/abs/1409.4705 ;
  https://www.rochester.edu/newscenter/watch-rochester-cloak-uses-ordinary-lenses-to-hide-objects-across-continuous-range-of-angles-70592/ ;
  Harvard demonstration notes, https://sciencedemonstrations.fas.harvard.edu/presentations/paraxial-ray-optics-cloaking .
- **Lenticular "invisibility shields"** (Invisibility Shield Co., 2022; Hyperstealth "Quantum
  Stealth" **(page unavailable, unverified)**): a sheet of vertical cylindrical lenses smears the
  background sideways, so a vertical object behind the middle is replaced by a blur of what is
  beside it. Launch prices GBP 49 (21 x 31 cm) and GBP 299 (65 x 95 cm); 2.0 range up to a
  6 x 4 ft panel. A DIY polycarbonate build (Hackaday 2021) worked "only from certain viewing
  angles", best against bold horizontal patterns, with motion still visible. It hides nothing
  horizontal, blurs rather than shows the background, and is obviously a ridged plastic sheet.
  https://www.iflscience.com/real-invisibility-shield-created-by-british-startup-63223 ;
  https://hackaday.com/2021/01/25/lenticular-lens-makes-things-invisible/ .
- **Digital integral cloaking** (Choi and Howell, Optica 2016 **(unverified; page blocked)**) and
  **retroreflective projection camouflage** (Tachi lab, 2003 **(unverified; rate-limited)**)
  need cameras, displays or projectors and one viewing position.

Verdict: none hides an object from a free-moving audience. The useful residue is the lenticular
sheet as a cheap one-axis diffuser that turns anything behind it into horizontal streaks.

#### B2. Aerial (mid-air) images

- **AIRR** (Yamamoto, Tomiyama and Suyama, Optics Express 22, 26919, 2014, as cited in patents):
  display, 45-degree beam splitter, retroreflective sheet; a real image forms mirror-symmetric
  to the display. Maker builds: Markus Mierse (IEEE Spectrum, Nov 2024: 7 inch screen, Oralite
  3010 sheeting at about $90 for 77 cm x 1 m, three $5 time-of-flight sensors for touch; "dim"
  but fine indoors) and Moritz von Sivers' floating clock (Oralite Superlens 3000, teleprompter
  glass). Polarised variants recycle light (Tokuda's pAIRR page).
  https://spectrum.ieee.org/diy-scifi-aerial-display ;
  https://hackaday.com/2023/05/10/clever-optics-make-clocks-digits-float-in-space ;
  https://ytokuda.github.io/projects/floating-display ;
  https://www.jstage.jst.go.jp/article/isj/56/4/56_341/_article/-char/en .
- **ASKA3D plates**: passive, flat 2D image at plate-to-display distance; sold as plates to
  integrators; used in Japanese convenience-store checkouts; a maker holochess table (2025)
  "works from only one viewing angle". https://displaydaily.com/aska3d-is-not-just-pepper-s-ghost/ ;
  https://hackaday.com/2025/05/08/let-the-wookie-win-with-this-diy-holochess-table/ .
- **Pepper's ghost** with stage foils and scrims (Musion Eyeliner foil; Hologauze, "price on
  request" from Gerriets; ShowTex PepperScrim): https://en.wikipedia.org/wiki/Pepper%27s_ghost ;
  https://www.gerriets.com/uk/special-3d-projection-gauze-holo-gauze ;
  https://hackaday.com/tag/peppers-ghost/ .

Verdict: a floating image is a display, and audiences say so. The one method use is as a relay
(A8): the "image" is of a real object, so a real borrowed ring can appear to hover where a hand
passes through it.

#### B3. Volumetric and light-field displays

- Acoustic trap display (Hirayama, Martinez Plasencia, Masuda, Subramanian, Nature 575, 320,
  2019): a levitated bead scanned at up to 8.75 m/s. https://link.springer.com/article/10.1038/s41586-019-1739-5
- Photophoretic trap display (Smalley et al., Nature 553, 486, 2018): 10 micrometre points,
  centimetre-scale line drawings. https://link.springer.com/10.1038/nature25176
- Femtosecond laser plasma voxels (Ochiai et al., 2015): about 1 cubic centimetre, lab lasers.
  https://arxiv.org/abs/1506.06668
- Hobby swept-volume and fog displays (spinning LED panels, a "bubblegram" glass block scanned by
  a laser projector, mist with multi-view projection): https://hackaday.com/tag/volumetric-display/ .
- Looking Glass Go light-field frame, about $299, up to 100 views
  (https://techcrunch.com/2024/08/08/looking-glass-new-lineup-includes-a-300-phone-sized-holographic-display/).
- Multi-view signage: Misapplied Sciences "Parallel Reality" shows different content to "a
  hundred or more viewers" at once; not purchasable (https://www.misappliedsciences.com/).
- LED persistence-of-vision "hologram fans" are cheap and loud **(unverified prices)**.

Verdict: lab-only or obviously apparatus. The multi-view idea (different people see different
things on one surface) is the valuable part, and A1 and A4 deliver it for a few dollars.

#### B4. Camera-versus-eye and active illumination

Rolling-shutter cameras and PWM-driven LEDs let a light source carry content that cameras record
and eyes do not (Columbia's DisCo, Jo, Gupta and Nayar, 2016 **(unverified; page did not
load)**). 940 nm emitters behind IR-pass plastic are black to the eye and bright to many phone
cameras. Useful for video-only work, and a risk for every IR method in A2. Laser projectors,
galvos and high-speed dynamic projection mapping (Ishikawa-Watanabe lab) are agent 12's.

---

## 3. Capability primitives

1. *Now possible:* a full-resolution cue display in open view that only a person in polarised
   glasses can read. *Because:* LCD with front polariser removed, about $20. *Before:* earpieces,
   crib sheets, memorisation. *Primitives:* tell, know.
2. *Now possible:* invisible marks on any existing LCD screen, read through a polariser.
   *Because:* clear birefringent tape on a polarised emitter. *Before:* not possible.
   *Primitives:* tell, conceal.
3. *Now possible:* a sealed black object with a 1.1 mm wall that passes 850/940 nm, so sensors,
   emitters and cameras need no window. *Because:* IR-transmitting PLA at about $6 per 100 g.
   *Before:* holes, grilles, cloth panels. *Primitives:* know, tell, prove ordinariness.
4. *Now possible:* machine-readable codes 6 to 9 mm wide inside a printed object, read at up to
   2.5 m in 6 to 14 ms. *Because:* InfraredTags. *Before:* visible marks or RFID.
   *Primitives:* know.
5. *Now possible:* covert markers under a coloured (not black) 0.3 mm skin, tracked at 60 fps.
   *Because:* NIR-fluorescent filament and an 830 nm long-pass filter. *Before:* not possible.
   *Primitives:* know.
6. *Now possible:* two printed blacks that match by eye and differ in near-IR, from an ordinary
   printer or print service. *Because:* carbon K versus composite CMY. *Before:* specialist
   luminous inks. *Primitives:* know, prove ordinariness.
7. *Now possible:* a hidden image developed and erased by switching a lamp between two whites.
   *Because:* illuminant metamerism plus RGBW smart bulbs. *Before:* chemical developers, heat,
   UV torches. *Primitives:* transform, delay, erase the evidence.
8. *Now possible:* a surface showing content only within about 30 degrees of one direction.
   *Because:* micro-louvre film, about $10. *Before:* shielding with the hands or body.
   *Primitives:* tell, conceal.
9. *Now possible:* one flat surface, under 1 mm thick, showing the audience one image and the
   performer another. *Because:* home-made lenticular flips. *Before:* double-faced props.
   *Primitives:* tell, swap.
10. *Now possible:* a mark that is bright only to an eye or camera within a degree or so of a
    lamp. *Because:* clear retroreflective coatings. *Before:* daub and juice read at close range.
    *Primitives:* know.
11. *Now possible:* a light signal visible in a 3 degree cone. *Because:* an LED or fibre in a
    deep black bore. *Before:* thumper or earpiece. *Primitives:* tell.
12. *Now possible:* a black surface reflecting about 0.6% instead of about 2%, by brush.
    *Because:* Musou Black, EUR 25 per 100 ml. *Before:* velvet and stage distance.
    *Primitives:* conceal.
13. *Now possible:* a 98%+ mirror about 65 micrometres thick with no visible edge.
    *Because:* multilayer reflector film (unverified figures). *Before:* 2 to 3 mm glass mirror
    with a bright edge. *Primitives:* conceal, swap.
14. *Now possible:* a front window with under 1% reflection. *Because:* AR-coated framing glass,
    2.5 mm. *Before:* 8% reflection that betrays every glass front. *Primitives:* conceal.
15. *Now possible:* a perfect mirror inside a clear solid, with nothing to scratch or see.
    *Because:* total internal reflection at an internal air gap (41.8 degrees for acrylic).
    *Before:* silvered mirrors in opaque props. *Primitives:* conceal, prove ordinariness.
16. *Now possible:* turning that mirror into a window, with no moving parts, by flooding a gap.
    *Because:* critical angle rises to about 63 degrees against water. *Before:* flaps and
    slides. *Primitives:* release, transform.
17. *Now possible:* solid partitions, holders and filaments that vanish in water or oil.
    *Because:* FEP, hydrogel, borosilicate index matching. *Before:* a glass disc.
    *Primitives:* conceal, hold.
18. *Now possible:* carrying an image round a corner inside a prop with zero electronics.
    *Because:* coherent fibre conduit and GRIN arrays. *Before:* mirror shiners with strict
    angles. *Primitives:* know.
19. *Now possible:* a "printed" label that rewrites itself in about 2 s and contains no battery.
    *Because:* NFC-powered e-paper, $27.99. *Before:* switches, multiple outs, nail writers.
    *Primitives:* transform, delay, prove ordinariness.
20. *Now possible:* a wall-mounted "printed" sign updated by radio, running months on a coin
    cell. *Because:* electronic shelf labels with open firmware. *Before:* assistants.
    *Primitives:* transform, delay.
21. *Now possible:* glowing text through 0.2 to 1.6 mm of real wood, cloth or mirror, invisible
    when off. *Because:* high-brightness PMOLED or LED matrices. *Before:* stencils and bulbs.
    *Primitives:* transform, conceal.
22. *Now possible:* a silent 5 V shutter, 88 x 34 mm, 95% blocking, no moving parts.
    *Because:* LC light valve, $7.50. *Before:* mechanical flaps. *Primitives:* conceal, release.
23. *Now possible:* a wall that is a diffuser or a window on command. *Because:* PDLC film.
    *Before:* curtains. *Primitives:* conceal, know.
24. *Now possible:* a command channel into a sealed object with no radio. *Because:* IR receiver
    behind IR-pass plastic. *Before:* magnets, threads, RF. *Primitives:* tell, delay.
25. *Now possible:* writing on a surface from metres away through glass, the trace gone in
    minutes. *Because:* 405 nm light on phosphorescent or photochromic coatings.
    *Before:* not possible. *Primitives:* transform, delay, erase the evidence.
26. *Now possible:* an examinable clear object that carries a hidden picture, one per outcome,
    for about a dollar of resin each. *Because:* open caustic-design code and resin printing.
    *Before:* one hand-made prop. *Primitives:* conceal, control of choice by brute force.
27. *Now possible:* a 0.2 mm film that shows real depth and parallax. *Because:* self-developing
    hologram film, about $12 a plate. *Before:* built false perspective. *Primitives:* conceal.

---

## 4. Effect concepts

Levels refer to the brief: 1 = phenomenon is the effect, 2 = hidden input to a classical method,
3 = new method architecture. Eleven of the twelve are level 2 or 3.

### 4.1 The lamp that only the performer can read (level 2)

*Effect.* Any mentalism routine needing fed information: a spectator's drawing, a word, a stack
position, a running cue sheet. Nothing is worn in the ear and the performer never looks at a
phone.
*Method.* A lightbox sign, softbox lamp or framed "light panel" on stage is a polariser-stripped
LCD driven by a hidden Pi or phone. The audience sees a white light. The performer's polarised
sunglasses or tinted spectacles decode it. An assistant, a camera or software feeds the content.
*BOM.* Used monitor or 10 inch panel $0 to $40, Pi Zero $15, diffuser, polarised glasses $15.
About $60.
*Difficulty.* Low; the risk is destroying a panel while peeling.
*Risks.* Spectators in polarised sunglasses (outdoor shows); reflections from glass and water;
phone photos through a polarising clip. Contrast drops at steep angles.
*Novelty.* The physics is 15-year-old hacker lore; I found no magic use. Medium to high.

### 4.2 The room light is the developer (level 3, speculative)

*Effect.* A printed poster, menu or sealed photograph is examined at the start and is ordinary.
Later, untouched, it carries a line of writing naming the chosen item; later still the writing
is gone.
*Method.* The writing is printed in an ink mix that matches its background under a lamp's
phosphor-white channel and separates under the same lamp's RGB-mixed white. A spot lamp over
the object changes channel on cue. Pairs are found by printing a patch chart and letting a
script choose.
*BOM.* RGBW bulb or LED engine $20 to $60, inkjet, camera. Under $100.
*Difficulty.* Medium; the work is calibration, repeated per printer and paper.
*Risks.* Imperfect matches visible to some eyes and to cameras; colour rendering shift on nearby
skin; only modest contrast (a tint difference, not black on white).
*Novelty.* High as a method. Unproven until someone measures real pairs.

### 4.3 Print-on-demand props with an infrared identity (level 2 to 3)

*Effect.* Fifty-two identical sealed envelopes, or a deck printed by a commercial card printer,
pass any visual or UV inspection, yet the performer names which is which from across the room.
*Method.* The artwork uses K-only black for some elements and composite black for others; they
match by eye and differ at 850 to 940 nm. A NoIR camera with IR LEDs in a prop or bag reads them.
Because it is ordinary artwork, a print service produces it at catalogue price. Sensing details:
agent 10.
*BOM.* Print order $15 to $40; Pi NoIR camera $20; IR LEDs and filter $10.
*Difficulty.* Medium. A test sheet is needed first: services may convert blacks, and not every K
is carbon.
*Risks.* The two blacks may differ slightly in gloss or tone; phone cameras see the IR lamps.
*Novelty.* The principle is banknote practice; using consumer print services to get it is, as
far as I know, new.

### 4.4 The object with no way in (level 3)

*Effect.* A solid-looking glossy black block, box or figurine is examined, sealed in a bag and
held by a spectator; it later proves to have "known" something, or releases, lights or moves on
cue.
*Method.* The shell is IR-transmitting PLA. Inside: an IR receiver for commands from an LED in
the performer's ring or a lamp; a break-beam or reflective sensor looking out through the wall
to detect a hand, a card laid on top or a lid opening; optionally a camera. No holes, no window,
no radio.
*BOM.* IR PLA $6, microcontroller $5, IR receiver and LEDs $3, cell $5. About $25.
*Difficulty.* Medium; shell thickness must be tuned so nothing shows against a bright light.
*Risks.* Strong sunlight swamps IR sensors; the shell is slightly translucent if held to a lamp;
"it's electronic" remains the default theory for a black box, so pair it with a sleight that
appears to do the work.
*Novelty.* Medium to high; the material is three years old in the research literature.

### 4.5 The label that was always printed (level 3)

*Effect.* A bottle with a paper-looking label, a museum-style placard or a luggage tag has been
in view all along. Its printed text names the freely chosen city.
*Method.* The text area is an NFC-powered e-paper panel behind a real printed surround matched
to its grey. A phone or NFC reader under the table top, in the performer's palm or in the bottle
stand writes the outcome in a few seconds while the object is covered or turned. It then holds
the image with no power and no battery inside.
*BOM.* Panel $28, printed surround, phone. About $35.
*Difficulty.* Low to medium; an app or reader script, and colour matching.
*Risks.* The refresh flash must be hidden; the panel is rigid and has a border; a spectator who
knows shelf labels may recognise the look. Reduce this by showing only a small window (a number,
one word) inside real print.
*Novelty.* E-paper prediction devices exist in the trade **(unverified)**; battery-free and
embedded in real print is, I believe, less explored.

### 4.6 The TIR vault (level 3, speculative)

*Effect.* A clear plastic block with frosted sides, obviously empty and solid, is dropped into a
glass of water. A folded banknote or ring is now visible sealed inside it.
*Method.* The block contains a wedge-shaped air cavity with its apex toward the viewing face and
walls at 60 degrees to the line of sight. In air, both walls reflect totally for viewers within
about 28 degrees of straight on (my calculation for n = 1.49), showing the frosted sides, so the
block looks uniformly clear. A capillary channel lets water into the gap: the critical angle
rises to about 63 degrees and the walls become windows. This is the mirror box with no mirror.
*BOM.* Acrylic or cast resin $10 to $20, polishing supplies; CNC or careful sawing.
*Difficulty.* High: internal faces need optical polish and must stay clean and dry.
*Risks.* Narrower angle range from one side; background seen through the block must be uniform;
condensation in the gap; untested.
*Novelty.* High. TIR concealment is a known physics demonstration; I know of no magic prop
built on a switchable internal TIR face.

### 4.7 The peek with nothing in it (level 2)

*Effect.* A spectator sets a die, or a coin heads or tails, under a small cup or inside a turned
wooden box. The performer knows the state every time. The prop can be scanned for electronics;
there are none.
*Method.* A bent coherent fibre conduit or a salvaged GRIN lens strip set into the base carries
the image of the object's underside to a 3 to 6 mm spot on the rim, under a dark resin "inlay"
that only shows the image at close range and the right angle.
*BOM.* Conduit or scanner strip $10 to $80, resin, a 3D-printed or turned body.
*Difficulty.* Medium; aligning and disguising the output end.
*Risks.* Dim image in low light (it relays ambient light only); small field of view; the output
spot can be noticed.
*Novelty.* Optical peeks are old; fibre relays for them may exist in high-end props
**(unverified)**. The scanner-strip source is, I think, new.

### 4.8 Close-range mirror box, rebuilt (level 2)

*Effect.* A matchbox-sized clear-fronted case is shown empty at 50 cm, covered for a second, and
holds the signed coin.
*Method.* The classical 45-degree mirror with three upgrades: a stretched film mirror on a
knife-edge printed frame, the edge and all interior dead surfaces in ultra-black paint, and an
AR-coated front pane so the window itself has no glint.
*BOM.* Reflector or first-surface film $10 to $20, Musou Black EUR 25, offcut of museum glass
$10 to $20 from a framer, printed body.
*Difficulty.* Medium; keeping film flat and paint untouched.
*Risks.* Ultra-black paint rubs off; film mirrors wrinkle with heat; lighting must not strike
the mirror edge-on.
*Novelty.* Low as a principle, real as an improvement: it moves a stage method to close-up.

### 4.9 A caustic for every outcome (level 2)

*Effect.* A spectator names any card. The performer picks up a clear plastic token from a bowl of
identical ones, shines a phone torch through it, and the card's image appears on the table.
*Method.* Fifty-two resin-printed 40 mm caustic lenses, indexed by position, from the open code.
Each is a few millilitres of resin. A drop of glycerine or oil on the sculpted face flattens the
optical relief (close index match **(unverified indices)**), so a token can be shown projecting
nothing, then wiped.
*BOM.* Clear resin $30 to $40, printer time, polishing or clear-coat.
*Difficulty.* Medium; small printed lenses need a clear-coat dip to project cleanly.
*Risks.* Low image quality at this size; needs dim light and a fixed distance.
*Novelty.* Medium. The single magic window is known; the brute-force index is the new part.

### 4.10 Light-written, self-erasing prediction (level 3, speculative)

*Effect.* A blank white card sealed in a clear box glows with the chosen word when the lights
dim. Minutes later, examined in the light, it is blank.
*Method.* The card is coated with phosphorescent paint under a white topcoat. A hidden 405 nm
laser with a two-axis scanner, aimed down at the table from a lamp fitting, draws the word in a
fraction of a second during a moment of cover.
*BOM.* 5 mW 405 nm module $10, hobby galvo set or two mirror servos $40 to $100, glow paint $10.
*Difficulty.* High; aiming, registration and safety enclosure.
*Risks.* **Laser eye hazard**: beam path must be enclosed or strictly downward and away from
faces. 405 nm is visible as dim violet on the card while writing. Venue laser rules apply.
*Novelty.* High.

### 4.11 The on-axis mark (level 2)

*Effect.* Five identical sealed envelopes or cups are mixed by spectators on a stage. The
performer, metres away, knows which holds the object.
*Method.* A dab of clear retroreflective coating on one item. A small LED beside the performer's
eye line, on a spectacle frame or beside a camera lens, makes the mark glint for that viewpoint
only. With an IR LED and camera it is invisible to everyone.
*BOM.* Retroreflective spray or beads in clear varnish $15 to $25, LED $1.
*Difficulty.* Low.
*Risks.* Spectators directly in line with any strong light source (a phone flash) see it; the
coating can alter surface sheen.
*Novelty.* Medium; a cheat's principle with a longer range.

### 4.12 Floating image of a real borrowed object (level 1)

*Effect.* A borrowed ring placed in a small box appears hovering above the lid; fingers pass
through it.
*Method.* A retroreflector and beam-splitter relay (AIRR) or a concave mirror pair images the
real ring, lit inside the box.
*BOM.* Retroreflective sheet $90 (enough for many), teleprompter glass offcut, LEDs. About $120.
*Risks.* Dim, limited viewing zone, recognisably "an optical toy". Included for completeness.

---

## 5. Dead ends and overhyped items

- **Invisibility shields and Quantum Stealth.** One-axis smear. They hide a standing person
  against a plain background from a distance and are themselves a large, obvious ridged sheet.
- **Rochester cloak.** A bench of lenses with a doughnut-shaped hidden zone and a few degrees of
  tolerance. A demonstration, not a method.
- **Acoustic, photophoretic and plasma volumetric displays.** Lab instruments drawing
  centimetre-scale figures; the plasma version needs femtosecond lasers.
- **Smartphone "hologram" pyramids and LED hologram fans.** Universally recognised.
- **Light-field frames (Looking Glass).** Beautiful, but unmistakably a screen in a thick frame.
- **PDLC as the effect.** Known from offices and hotel bathrooms; and its opaque state only
  blurs, so anything near the film shows through.
- **Vantablack.** Not purchasable for this use; the paints are close enough.
- **Stage hologram foils and gauzes.** Priced on request, need a stage, a pit or rig and
  controlled lighting.
- **Metasurfaces and custom diffractive optics.** No hobby fabrication route found.
- **Photo-Chromeleon-style reprogrammable colour.** Tens of minutes to write; too slow for
  performance, though usable as a pre-show or overnight process.

## 6. Open leads

- **Holographic false bottom.** A Litiholo reflection hologram of an empty tray interior, laid
  as the tray's visible "bottom", might show convincing depth over a hidden load space. Needs a
  point light, and colour and brightness will not match reality; the test costs one $240 kit.
- **Measured reflectance** of Musou Black, KIWAMI fabric, Black 4.0 and velvet under the same
  conditions; I found maker claims and reviews only.
- **Which consumer printers and card-printing services keep K-only and composite black
  distinct**, and how the two look at 850 and 940 nm.
- **Designed metameric pairs for RGBW bulbs**: whether literature exists (I could not search),
  and how large a contrast is reachable with inkjet inks.
- **3M ESR film and micro-louvre film**: confirm thickness, reflectance, cut-off angles and
  hobby sources.
- **ASKA3D and Parity Mirror plate prices**, and the "AiRWitch" DIY floating-display kits
  mentioned on Tokuda's page.
- **Cholesteric writing-tablet film** with segmented or remote erase as a self-erasing writing
  surface.
- **Welding-helmet LC cells** as large cheap shutters; switching speed and clear-state tint.
- **Magic-trade prior art** for all of Part A. I could not search dealers or forums, so every
  novelty judgement above is provisional.

## 7. Sources

Opened or seen in search results during this work:

1. https://arxiv.org/abs/1409.4705 - Choi and Howell, paraxial ray optics cloaking.
2. https://www.rochester.edu/newscenter/watch-rochester-cloak-uses-ordinary-lenses-to-hide-objects-across-continuous-range-of-angles-70592/ - Rochester cloak build notes.
3. https://sciencedemonstrations.fas.harvard.edu/presentations/paraxial-ray-optics-cloaking - Harvard demonstration of the cloak.
4. https://www.iflscience.com/real-invisibility-shield-created-by-british-startup-63223 - Invisibility Shield sizes, prices, mechanism.
5. https://hackaday.com/2021/01/25/lenticular-lens-makes-things-invisible/ - DIY lenticular shield and its limits.
6. https://hackaday.com/tag/lenticular/ - 3D-printed lenticular work, ShiftLens (2026).
7. https://en.wikipedia.org/wiki/Lenticular_printing - effect types, manufacture, defects.
8. https://en.wikipedia.org/wiki/Barrier-grid_animation_and_stereography - scanimation history.
9. https://spectrum.ieee.org/diy-scifi-aerial-display - Mierse AIRR build with parts and costs.
10. https://hackaday.com/2023/05/10/clever-optics-make-clocks-digits-float-in-space - von Sivers floating clock.
11. https://ytokuda.github.io/projects/floating-display - polarised AIRR and DIY kit mention.
12. https://www.jstage.jst.go.jp/article/isj/56/4/56_341/_article/-char/en - Yamamoto group AIRR review (2017).
13. https://displaydaily.com/aska3d-is-not-just-pepper-s-ghost/ - ASKA3D plate explanation.
14. https://hackaday.com/2025/05/08/let-the-wookie-win-with-this-diy-holochess-table/ - maker use of an ASKA3D plate.
15. https://en.wikipedia.org/wiki/Pepper%27s_ghost - history, geometry, modern stage versions.
16. https://hackaday.com/tag/peppers-ghost/ - small Pepper's ghost builds.
17. https://www.gerriets.com/uk/special-3d-projection-gauze-holo-gauze - Hologauze, price on request.
18. https://link.springer.com/article/10.1038/s41586-019-1739-5 - Hirayama et al., acoustic trap display.
19. https://link.springer.com/10.1038/nature25176 - Smalley et al., photophoretic trap display.
20. https://arxiv.org/abs/1506.06668 - Ochiai et al., femtosecond laser aerial graphics.
21. https://hackaday.com/tag/volumetric-display/ - hobby volumetric displays 2025-2026.
22. https://techcrunch.com/2024/08/08/looking-glass-new-lineup-includes-a-300-phone-sized-holographic-display/ - Looking Glass Go price.
23. https://www.misappliedsciences.com/ - Parallel Reality multi-view claim.
24. https://hackaday.com/2015/07/15/trick-google-used-hides-secret-messages-on-lcd-screens/ - stacked LCD hidden image.
25. https://hackaday.com/tag/polarizer/ - polariser projects list.
26. https://www.instructables.com/Privacy-monitor-made-from-an-old-LCD-Monitor/ - privacy monitor (title only loaded).
27. https://en.wikipedia.org/wiki/Security_printing - IR, UV, latent-image and OVI features.
28. https://hcie.csail.mit.edu/research/infraredtags/infraredtags.html - InfraredTags, CHI 2022.
29. https://hcie.csail.mit.edu/research/brightmarker/brightmarker.html - BrightMarker, UIST 2023.
30. https://hcie.csail.mit.edu/research/photochromeleon/photochromeleon.html - Photo-Chromeleon, UIST 2019.
31. https://en.wikipedia.org/wiki/Cold_mirror - visible-reflecting, IR-transmitting mirrors.
32. https://en.wikipedia.org/wiki/Card_marking - luminous and video-luminous readers.
33. https://en.wikipedia.org/wiki/Metamerism_(color) - illuminant and observer metamerism.
34. https://www.carnovsky.com/RGB.htm - RGB layered prints.
35. https://en.wikipedia.org/wiki/Monitor_filter - privacy filters.
36. https://en.wikipedia.org/wiki/Retroreflector - bead and prismatic retroreflection, observation angle.
37. https://www.musoublack.com/ - Musou Black paint, fabric and flock prices.
38. https://culturehustle.com/products/black-3-0-the-worlds-blackest-black-acrylic-paint-150ml - Black 4.0 price, claims, handling.
39. https://www.thedrive.com/guides-and-gear/whats-the-blackest-black-paint.md - Musou 99.4% figure.
40. https://en.wikipedia.org/wiki/Vantablack - absorption, licensing, export control.
41. https://en.wikipedia.org/wiki/Black_light_theatre - black art history and lighting.
42. https://tru-vue.com/solution/museum-glass/ - AR glass reflection and transmission.
43. https://en.wikipedia.org/wiki/Total_internal_reflection - critical angles, frustrated TIR.
44. https://en.wikipedia.org/wiki/Ulexite - natural fibre-optic image transfer.
45. https://en.wikipedia.org/wiki/Gradient-index_optics - GRIN rods in scanners and endoscopes.
46. https://en.wikipedia.org/wiki/Smart_glass - PDLC, SPD, electrochromic behaviour.
47. https://engineerfix.com/how-much-does-smart-film-cost/ - PDLC film cost guide (seen in search results).
48. https://www.adafruit.com/product/3330 - LC light valve specifications and price.
49. https://www.ynvisible.com/ - printed flexible e-paper displays and kit.
50. https://www.waveshare.com/2.9inch-nfc-powered-e-paper.htm - battery-free NFC e-paper.
51. https://github.com/OpenEPaperLink/OpenEPaperLink - open firmware for shelf labels.
52. https://research.google/blog/hidden-interfaces-for-ambient-computing/ - displays through wood, textile, mirror.
53. https://infoscience.epfl.ch/record/201509 - Schwartzburg et al., high-contrast caustic design.
54. https://rayform.ch/ - commercial caustic design, materials, process.
55. https://mattferraro.dev/posts/caustics-engineering - hobby caustic window write-up.
56. https://github.com/MattFerraro/causticsEngineering - open caustic design code.
57. https://hackaday.com/2021/08/23/math-optics-and-cnc-combine-to-hide-secret-images-in-acrylic/ - coverage of the magic window.
58. https://hackaday.com/2025/01/20/innovative-clock-uses-printed-caustic-lens/ - resin-printed caustic lens.
59. https://physicstoday.aip.org/news/magic-window-uses-liquid-crystals-to-project-images - flat liquid-crystal magic window.
60. https://en.wikipedia.org/wiki/Specular_holography - scratch and specular holograms.
61. https://www.litiholo.com/hologram-kits.html - self-developing hologram kit prices.

Not reachable from this session (claims depending on them are marked unverified):
invisibilityshield.co (host not allowed), hyperstealth.com (503), telepromptermirror.com (503),
edmundoptics.com (403), exploratorium.edu (405), hackster.io (403), opg.optica.org (blocked),
aska3d.com, sparkfun.com and tachilab.org (safety check rate-limited), albedo100.com (404),
cave.cs.columbia.edu (empty page).
