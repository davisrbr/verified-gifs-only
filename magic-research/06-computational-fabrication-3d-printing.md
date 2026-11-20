# 06 - Computational fabrication and 3D printing as magic method infrastructure

Slice: SIGGRAPH / UIST / CHI / TEI / SCF / Eurographics fabrication research, 2014 to 2026, plus
consumer printer materials and practice, as sources of magic props and methods.

Level labels used below: level 1 means the phenomenon itself is the effect; level 2 means a hidden
input to a traditional method; level 3 means a method structure that could not exist before. The
"Capability primitives" section is an extra, kept from a mid-project request that was later
withdrawn.

Research note: the shared web-search budget ran out after 14 searches, so most checking was done by
opening known primary pages directly. Anything I could not open or see in a search result is marked
**(unverified)**. Prices are as seen in late 2026. Numbers labelled "my estimate" are my own
arithmetic, not from a source.

## 1. Summary

- **The field offers two kinds of transfer.** Direct showpieces (shadow art, lenticular objects,
  asymmetric spinning tops, caustic windows, ambiguous cylinders) are buildable and catalogued in
  section G. The same papers also contain a quieter tool: optimisers that set an object's mass,
  centre of mass and inertia tensor through hidden internal voids while the outside does not
  change (Make It Stand, Spin-It, buoyancy optimisation). Used backwards, they make a gimmicked
  object match a genuine one in the hand.
- **A consumer printer now spans a 20x density range in one object**: foamed LW-PLA at 0.40 to
  0.48 g/cm3, PLA at 1.24, iron PLA at 1.85, tungsten filament at 8.0 to 9.2, and a 48x range with
  an inserted tungsten slug (19.3). Weight, balance point and "heft" are free design variables.
- **Chance can be biased with nothing to find.** "Putting Rigid Bodies to Rest" (SIGGRAPH 2025)
  computes the probability of every resting face of any convex shape with no simulation, and its
  inverse mode designs solid, homogeneous dice with chosen non-uniform probabilities. Code, a
  Blender plugin and STL files are public. Hidden weights in a normal cube give only a modest bias
  (my estimate: about 22% against 13% for opposite faces), so geometry is the stronger lever.
- **One-piece mechanisms remove the classic tells.** Metamaterial mechanisms (a door latch printed
  as one block), bistable signal-propagating cells (a printed combination lock), compliant flexures
  and print-in-place joints have no screws, no assembly seam and no backlash rattle.
- **Layer lines are camouflage.** A parting plane or programmed break plane that follows a layer
  boundary is one line among hundreds. Printed objects are also now socially ordinary (fidget toys,
  phone stands), which gives a gimmick an innocent reason to look printed.
- **"Black to the eye, clear to a camera" is a cheap wall material.** Infrared-transmitting PLA
  (about $5.86 per 100 g) passes about 45% of near-infrared per mm and 0 to 15% of visible light.
  A $20 NoIR camera reads through 1.08 mm of it at up to 250 cm. This is a hidden *know* channel
  through an apparently opaque solid wall.
- **Fracture surfaces can be duplicated.** A torn or broken edge is magic's standard proof of
  identity. Resin printers reproduce a designed "random" fracture surface on any number of copies,
  so the proof can be faked. I found no prior use of this.
- **Brute force is nearly free.** A 6 x 6 x 1.5 mm resin token is 0.054 cm3; a thousand different
  ones use 54 cm3 of resin, about $2 of material (my estimate). Every outcome can be pre-made.
- **Pause-and-insert makes sealed objects with contents that could not have been put there**:
  magnets, coins, NFC tags, steel balls, liquids. PrusaSlicer documents the workflow, including
  the warning that loose magnets jump to the print head.
- **Limits that matter:** desktop FDM holds roughly ±0.5% (floor ±0.5 mm), desktop resin ±0.5%
  (floor ±0.10 mm). Resin needs 0.4 mm supported walls, so a printed shell over a US quarter comes
  out about 0.8 mm oversize and 20 times too light. Metal coin shells remain a machining job.
  Printing wins on objects that are already moulded plastic.

## 2. Catalog

### A. Mass, balance, inertia, rolling and landing

**A1. Internal-void optimisation of mass properties (Make It Stand, Spin-It, buoyancy)**
- What: given a surface mesh, the methods voxelise the interior and solve for which voxels to fill
  so that the centre of mass falls over a chosen support (Make It Stand), the largest principal
  moment of inertia aligns with a chosen spin axis (Spin-It), or the object floats at a chosen
  waterline and pose (Wang and Whiting). Spin-It extends to deformation and to two materials when
  voids alone are not enough.
- References: Prévost, Whiting, Lefebvre, Sorkine-Hornung, SIGGRAPH 2013
  (https://igl.ethz.ch/projects/make-it-stand/, beta source and Windows binary, non-commercial);
  Bächer, Whiting, Bickel, Sorkine-Hornung, SIGGRAPH 2014
  (https://visualcomputing.ist.ac.at/publications/2014/SpinIt/); Wang and Whiting, Computer
  Graphics Forum 35(2) 2016 (https://diglib.eg.org/handle/10.1111/cgf12810); a student
  re-implementation on libigl (https://github.com/MultiW/make-it-balance).
- Accessibility: hobbyist. For simple props no optimiser is needed: CAD reports mass, centroid and
  inertia tensor, and slicer modifier meshes set infill per region.
- Magic relevance (level 2 and 3): *prove ordinariness* and *control chance*. A hollowed gimmick
  can be trimmed back to the genuine object's mass, balance point and swing feel. The reverse use
  gives objects that stand, roll back, float or sink in ways the outside does not predict
  (physical anomaly, spectator failure). Tells: tap tone and flex of thin walls.
- Prior use: weighted "balancing" novelties and loaded dice are old; I found no magic product
  using computed interior design.

**A2. Density palette on a consumer printer**
- LW-PLA (ColorFabb): 1.21 to 1.43 g/cm3 unfoamed, 0.403 to 0.476 foamed, foaming from about
  230 C, parts up to 65% lighter, €26.49 a spool (https://colorfabb.com/lw-pla-natural).
- Iron PLA (Proto-pasta): about 1.85 g/cm3, ferromagnetic, can be rusted, mildly abrasive, $9 per
  100 g (https://proto-pasta.com/products/magnetic-iron-pla).
- Tungsten filament (Rapid 3DShield): 8.00 to 9.20 g/cm3 printed, 93.6% tungsten, 0.8 mm hardened
  nozzle, $716.99 per 0.5 kg after 2026 tungsten price rises
  (https://shop.thevirtualfoundry.com/products/rapid-3dshield-tungsten-filament). Too expensive
  for bulk; a tungsten or steel insert at a pause is the practical route.
- Magic relevance: same outside, mass anywhere from one third to seven times normal. Two objects
  can share mass and centre of mass but differ 3x in moment of inertia (rim-loaded against
  centre-loaded disc, my estimate), a difference felt only when the object is twirled. Iron PLA
  gives attraction to a magnet with no discrete slug to find or rattle.

**A3. Resting-pose probability and dice design**
- What: the resting probability of each face equals the area of a cell on the Gauss map divided
  by 4 pi, computed geometrically. The inverse solver moves vertices of a convex shape to hit
  target face probabilities. Validated with resin-printed dice.
- References: Baktash, Sharp, Zhou, Crane, Jacobson, ACM TOG 44(4), SIGGRAPH 2025
  (https://hbaktash.github.io/projects/putting-rigid-bodies-to-rest/index.html); code
  (https://github.com/hbaktash/resting-rigid-bodies) with a `convex_dice` inverse mode.
- Accessibility: hobbyist; C++ build plus any resin printer.
- Magic relevance (level 3): *control chance* in a solid, homogeneous object that can be cut open.
  Tabletop gaming has made odd polyhedral dice ordinary, and nobody can judge the fairness of an
  unfamiliar shape by eye. The model assumes negligible momentum, so hard throws on hard tables
  will deviate; test by rolling. Entertainment use only.
- Related: the first working monostable tetrahedron (Almádi, Dawson, Domokos 2025,
  https://arxiv.org/abs/2506.19244) needed 1 mm carbon tubes and a 14.15 g/cm3 tungsten carbide
  core. A homogeneous Gömböc needs 0.01 mm precision (https://www.gomboc.eu/en/). Both are beyond
  a hobby printer as homogeneous objects, but a self-righting shape with a hidden weight is easy.

**A4. Trajectoids: programmed rolling paths (brief, level 1 to 2)**
- A 1-inch steel ball sits in a printed shell whose surface is trimmed so the body rolls along a
  chosen periodic path down a slight incline (test sphere must roll at 0.5 degrees). Python code
  and a Colab are public, but the final boolean was done in 3ds Max.
- References: Sobolev et al., Nature 620, 310-315 (2023)
  (https://www.nature.com/articles/s41586-023-06306-y.pdf;
  https://github.com/yaroslavsobolev/trajectoids;
  https://techxplore.com/news/2023-09-trajectoids-desired-path.html).
- Magic relevance: the lumpy shape announces itself, and paths zig-zag and sometimes escape. The
  principle (a heavy core inside a light shell decides where it goes) is more useful hidden: a
  smooth ball with an offset core that curves to a predictable spot.

**A5. Tops, yo-yos and classic dynamics toys**
- Spin-It's demonstrations are asymmetric tops and yo-yos (a break-dancing figure, animals) that
  spin steadily about an axis that looks wrong, because voids move the principal axis. Classic
  mechanics toys print well with a designed interior: the rattleback (spins one way, reverses the
  other), the tippe top (inverts itself), the oloid and sphericon (wobbling rollers), the
  uphill roller with an offset weight, and self-righting figures. I did not open sources on these
  classic toys this session (unverified, well-known physics).
- Accessibility: hobbyist; any FDM printer. Rattlebacks need a smooth base and an accurate inertia
  asymmetry, so expect a few iterations.
- Magic relevance: physical anomaly and spectator failure. A top that only the performer can keep
  upright, or a rattleback that "refuses" to spin in the direction a spectator chooses, are short
  close-up pieces. A hidden-weight version in an ordinary-looking object (a bottle cap, a pebble,
  a spoon-rest) is stronger than a visibly odd shape. Tells: the audience may know the toys.
- Prior use: rattlebacks and tippe tops have long been sold as novelties and science toys.

### B. Mechanisms with no seams, screws or rattles

**B1. Metamaterial mechanisms and mechanical logic**
- What: a block of printed cells, some rigid and some "shear cells", acts as a mechanism. Shown: a
  door latch converting handle rotation to bolt travel, pliers, a pantograph and a walker, each
  one piece. Digital Mechanical Metamaterials adds cells with embedded bistable springs that pass
  a mechanical signal to neighbours and compute simple logic; the example is a combination lock.
  MetaSense adds capacitive sensing by printing conductive cell walls (5 mm cells still readable,
  about 4.8 fF swing).
- References: Ion et al., UIST 2016 (https://hpi.de/baudisch/projects/metamaterial-mechanisms.html,
  online editor and Thingiverse files); Ion, Wall, Kovacs, Baudisch, CHI 2017
  (https://hpi.de/baudisch/projects/digital-mechanical-metamaterials.html); Ion's dissertation
  (https://publishup.uni-potsdam.de/files/42986/ion_diss.pdf); Gong et al., UIST 2021
  (https://hcie.csail.mit.edu/research/metasense/metasense.html).
- Accessibility: hobbyist with TPU or a flexible resin; cell grids look like infill, not like a
  normal object, so they belong inside a skin.
- Magic relevance (level 2 and 3): *hold / release*, *move*, *delay*. A lock, latch or load
  chamber with zero parts, nothing to unscrew and nothing loose to rattle survives handling.
  Bistable cells store energy and release it on a light trigger: a mechanical one-shot.
- Prior use: none found.

**B2. Compliant, print-in-place and tendon mechanisms**
- Working numbers: resin moving-part clearance 0.5 mm, assembly fit 0.2 mm, push fit 0.1 mm
  (https://www.hubs.com/knowledge-base/how-design-parts-sla-3d-printing/). FDM: bridges under
  5 mm are clean, overhangs to 45 degrees need no support, vertical pins under 5 mm are weak
  (https://www.hubs.com/knowledge-base/how-design-parts-fdm-3d-printing/). FDM print-in-place
  gaps of 0.2 to 0.3 mm are common practice (unverified).
- Also in the literature: computational design of linkage-and-gear characters driven by one input
  (Coros et al., SIGGRAPH 2013,
  https://la.disneyresearch.com/publication/computational-design-of-mechanical-characters/);
  telescoping structures that collapse a curved shape into nested shells (Yu, Crane, Coros,
  SIGGRAPH 2017, unverified); printed hydraulics (MacCurdy et al., arXiv 1512.03744, needs a
  modified inkjet printer, so lab-only).
- Magic relevance: curved internal channels for a pull thread or air line can be printed inside a
  solid-looking part, which a drill cannot do. Water-soluble supports (PVA, BVOH) free an enclosed
  mechanism through a pinhole (general practice, unverified numbers).

**B2b. Deployable, telescoping, origami, kirigami and auxetic structures**
- What: structures that pack small and open large. Telescoping structures nest curved shells
  (Yu, Crane, Coros 2017, unverified). Print-in-place collapsing swords and telescoping wands are
  common hobby models (unverified). Auxetic and kirigami sheets expand in two directions at once.
  Self-folding sheets are in C2. Under-extruded printed textiles are in section G.
- Accessibility: hobbyist. Thin telescoping shells want 0.3 to 0.5 mm clearance per stage on FDM
  and a taper so stages lock by friction.
- Magic relevance: production and transformation. A printed appearing wand or cane costs under $2
  against a spring-steel one, though it is thicker when collapsed and extends by a flick, not by
  spring. Auxetic panels could make a small flat object grow visibly when pulled. Tells: stage
  lines on the extended object, plastic sound.
- Prior use: appearing canes and collapsing props are classic; printed versions exist as toys.

**B3. Gravity, inertia and spin locks (puzzle-box practice)**
- What: a captive ball or slider blocks a lid unless the box is tilted in sequence, tapped, or
  spun. Known in puzzle design; printing lets the ball be sealed in at a pause with no assembly
  seam.
- Magic relevance (level 2): spectator failure with no magnet to detect and no electronics. Tell:
  rattle, which a TPU bumper or a drop of grease reduces.

### C. Internal structure that changes behaviour

**C1. Programmed break, tear and separation**
- FDM parts are weakest between layers. A one-layer modifier region with reduced bonding sets
  where a part snaps, and the snap plane is hidden among layer lines. I could not verify published
  strength ratios this session; treat the commonly quoted "Z strength about half of XY" as
  unverified and test coupons.
- Two parts printed separately with matched surfaces and tacked together separate exactly along a
  designed surface, which may be rough and random-looking.
- Magic relevance (level 3): *duplicate* and *erase the evidence*. See concept 3.

**C2. Self-folding PLA (Thermorph, 4DMesh)**
- What: flat sheets printed with deliberate residual stress fold into 3D shapes in hot water. PLA's
  glass transition is 60 to 65 C. Software compiles a mesh to a printable flat sheet in seconds.
- References: An et al., CHI 2018 (https://morphingmatter.org/projects/thermorph;
  https://www.cs.cmu.edu/news/2018/cheap-3-d-printer-can-produce-self-folding-materials); Wang et
  al., UIST 2018 (https://morphingmatter.org/projects/4dmesh).
- Magic relevance: a plastic stirrer that bends itself in a hot drink is level 1. Hidden use: a
  latch that releases when the prop is put into hot water (*delay*). Hand heat is not enough.
  Smart-material detail belongs to agent 7.

**C3. Sound when tapped or swiped**
- Shape can be optimised for a target struck tone (Bharaj et al., SIGGRAPH Asia 2015,
  http://www.cs.columbia.edu/cg/zoolophone/). Internal cavities can be optimised as acoustic
  filters and give objects a tapping signature (Li et al., SIGGRAPH 2016,
  http://www.cs.columbia.edu/cg/lego/). Notch patterns swiped with a nail give a decodable ID via
  one contact microphone (Harrison, Xiao, Hudson, UIST 2012,
  https://chrisharrison.net/index.php/Research/AcousticBarcodes).
- Magic relevance: *prove ordinariness* (a hollow shell tuned or filled so it does not sound
  hollow) and *know* (identical-looking objects told apart by ear or a hidden microphone).

**C4. Buoyancy**
- Computed floating pose and waterline (A1). Speculative addition: a water-soluble plug that lets
  a floating object flood and sink minutes later (*delay*); dissolution time needs testing.

### D. Sealed objects and embedded contents

**D1. Pause-and-insert**
- PrusaSlicer inserts an M601 pause at any layer for magnets and nuts. Magnets must fit tightly or
  be glued, or they jump to the print head
  (https://help.prusa3d.com/article/insert-pause-or-custom-g-code-at-layer_120490).
- Magic relevance: *conceal*, *prove ordinariness*. A solid block containing a coin, a ball, a
  folded note, a tag or a liquid, with no seam because there never was one. Heat-sensitive inserts
  sit under a 200 C nozzle pass, so recess them and bridge over.
- Prior use: impossible-object souvenirs are an old tradition; printed "coin in block" files exist
  on model sites (unverified).

**D2. Hidden tags and see-through walls**
- InfraredTags: IR-transmitting PLA from 3dk.berlin, about $5.86 per 100 g, 45% near-IR
  transmission per mm. Shell 1.08 mm, air-gap code 2.00 mm; minimum marker 9 mm (6 mm with two
  materials); ArUco decode in about 6 ms; Raspberry Pi NoIR camera about $20; read distance to
  250 cm. Spools vary and need calibration. (Dogan et al., CHI 2022,
  https://hcie.csail.mit.edu/research/infraredtags/infraredtags.html;
  https://news.mit.edu/2022/invisible-labels-identify-track-objects-0128.)
- BrightMarker: fluorescent filament from DIC, excitation 763 nm, any colour except black ABS,
  $148 camera module. Filament is not retail, so lab-only for now
  (https://hcie.csail.mit.edu/research/brightmarker/brightmarker.html).
- AirCode: sub-surface air pockets read with a projector and camera by separating scattered light;
  PolyJet printer and lab optics (Li et al., UIST 2017, https://arxiv.org/abs/1707.05754;
  http://www.cs.columbia.edu/cg/aircode/). Lab-only.
- G-ID: identifies individual prints from slicer settings alone. Bottom-layer line angle and width
  give 204 distinguishable instances by phone camera, 17,136 with backlit infill (Dogan et al.,
  CHI 2020, https://hcie.csail.mit.edu/research/gid/gid.html). LayerCode hides a barcode in layer
  thickness (Maia et al., SIGGRAPH 2019, http://www.cs.columbia.edu/cg/layercode/). StructCode
  does the same in laser-cut finger joints
  (https://hcie.csail.mit.edu/research/structcode/structcode.html).
- Magic relevance (level 2 and 3): the important idea is the wall, not the tag. A box, cup or lid
  that looks like solid black plastic is a window for a hidden camera or reflectance sensor.
  G-ID's coarse version needs no camera: eight bottom-line angles are readable by eye as a marking
  system that is part of how the object was made. Camera and electronics detail: agents 5 and 14.

**D3. Conductive and passive sensing**
- Conductive PLA: 2.0 to 3.5 kilohm per 10 cm of 1.75 mm filament, about 10 kilohm across 10 mm
  printed, $7 per 50 g (https://proto-pasta.com/products/conductive-pla). Enough for capacitive
  touch (CapriCate, Schmitz et al. UIST 2015, unverified).
- Passive wireless: printed gears and springs that modulate backscatter to a Wi-Fi receiver, and
  data stored in magnetised filament read by a phone magnetometer (Iyer et al., SIGGRAPH Asia
  2017, https://printedwifi.cs.washington.edu/). Research-grade.
- Magic relevance: *tell*. A touch point with no button, click or wire: the performer's finger on
  an ordinary-looking spot is the switch.

### E. Duplicates, shells and passing as mass-produced

- **Tolerances**: desktop FDM ±0.5% with a ±0.5 mm floor, desktop resin ±0.5% with a ±0.10 mm
  floor, industrial resin floor ±0.01 mm, SLS and MJF ±0.3 mm
  (https://www.hubs.com/knowledge-base/dimensional-accuracy-3d-printed-parts/). Resin: supported
  wall 0.4 mm, unsupported 0.6 mm, embossed detail 0.1 mm high, engraved 0.4 mm, drain holes
  3.5 mm.
- **Coin shell arithmetic**: a US quarter is 24.26 mm x 1.75 mm, 5.67 g, 119 reeds
  (https://en.wikipedia.org/wiki/Quarter_(United_States_coin)), so reed pitch is 0.64 mm, within
  resin resolution. A 0.4 mm resin shell is 25.06 mm across and about 0.3 g (my estimate). It
  fails on weight, sound and coldness. Routes to metal (plating, lost-resin casting, service metal
  printing) belong to agent 13. Replica currency has legal limits; check local law.
- **Where printing passes**: objects that are already moulded plastic. Bottle caps, dice, poker
  chips, pen caps, game pieces, lighter bodies, earbud cases, pill bottles, toy bricks.
- **Finish**: seams placed on layer lines or hidden under "fuzzy skin" texture; textured build
  plates give a moulded-looking base; scarf seams in current slicers, and solvent-smoothable PVB
  filament (both unverified this session); primer and paint on resin. Full-colour texture transfer
  onto 3D shapes by computational hydrographics (Zhang et al., SIGGRAPH 2015,
  http://www.cs.columbia.edu/cg/hydrographics/) and computational thermoforming (Schüller et al.,
  SIGGRAPH 2016, https://igl.ethz.ch/projects/thermoforming/) are buildable but fiddly.
- **Alternative**: make the prop openly printed. A printed box or desk toy needs no excuse.
- Prior use: model sites carry re-creations of classic plastic tricks, for example a glue-free
  coin vanish and switch box (https://makerworld.com/en/models/251925), a finger guillotine
  (https://makerworld.com/models/1367291) and a 2021 round-up of ten tricks
  (https://all3dp.com/2/3d-printed-magic-tricks-3d-models/). These are copies of old gimmicks,
  not new methods.

### F. Surface micro-texture, friction and fits

- FDM surfaces have ridges at the layer pitch (0.1 to 0.3 mm), so friction differs along and
  across layers; ironing and plate texture change it again. I found no measured coefficients this
  session.
- Cilllia prints hair-like pillars at 50 micrometre resolution for grip, directional actuation
  and sensing (Ou et al., CHI 2016, https://tangible.media.mit.edu/project/cilllia/), on a
  high-end printer.
- Speculative, for testing: sawtooth micro-ratchets (0.1 to 0.2 mm pitch in resin) so that two
  tiles slide one way and lock the other; a durable version of the rough-and-smooth principle for
  plastic tiles, chips and coasters.
- Fits: a "tolerance ladder" of ten sockets in 0.05 mm steps prints in under an hour and finds the
  interference that gives the wanted holding force. Friction holds, air-damped slow-closing lids
  and suction fits then need no mechanism. Air-cushion fits probably need resin plus hand lapping.

### G. Appearance and optics by fabrication

Mostly level 1 uses. Optics hardware detail belongs to agent 5.

**G1. Lenticular Objects (view-dependent surfaces on 3D shapes)**
- What: lenses of 2 to 5 mm are printed over a computed colour pattern so the object shows a
  different image from each direction. Lens geometry is 2:1:1 (diameter : radius : base height),
  usable range 83.6 degrees, image spot 0.6 mm or larger, up to 19 viewpoints for upward-facing
  lenses, 2 to 5 images in the applications. Printed on a Stratasys J55 in clear and CMY resins,
  then varnished. The lenses add about 3 mm to the surface.
- Reference: Zeng, Deng, Zhu, Wessely, Kilian, Mueller, UIST 2021
  (https://hcie.csail.mit.edu/research/lenticularobject/lenticular-object.html).
- Accessibility: the printer is not consumer-class. The page suggests a separately printed lens
  shell for consumer printers. The cheap route for flat props is bought lenticular sheet over an
  inkjet interlaced print (unverified).
- Magic relevance: transformation and prediction. A message only visible from above (performer's
  view) and plain from the side (spectator's view) is a private cue card on an ordinary object.
  A colour or symbol change as an object is turned is visible as lens bumps at close range.

**G2. Barrier-grid animation (FabObscura)**
- What: a striped barrier over an interlaced image shows different frames as the barrier slides,
  rotates or as the viewer moves. The tool treats barrier patterns as functions, supports nesting
  two animations, and outputs image files, so an inkjet printer and transparency film suffice.
- Reference: Sethapakdi et al., UIST 2025
  (https://hcie.csail.mit.edu/research/fabobscura/fabobscura.html).
- Accessibility: hobbyist, a few dollars.
- Magic relevance: transformation. A coaster or box lid whose picture changes when a sleeve is
  slid or a lid is turned. Close-up or installation. The striped look is recognisable.

**G3. Caustic windows**
- What: a clear slab with a computed relief focuses light into a picture. One documented build is
  a 10 cm acrylic square with 2 mm of relief, image at 0.2 m, from a flashlight or the sun; CNC
  roughing 10 minutes, finishing 90 minutes, sanding and polishing 30 minutes; MIT-licensed Julia
  code.
- References: https://mattferraro.dev/posts/caustics-engineering (after Yue et al. 2014);
  Schwartzburg et al., SIGGRAPH 2014 (unverified this session).
- Accessibility: hobbyist with a CNC router or a milling service. Resin printing needs heavy
  polishing to be optically smooth.
- Magic relevance: prediction and identification. A "plain" clear paperweight or glass coaster
  that projects the chosen card when a phone torch shines through it. Needs a point source, a
  set distance and dim light. The slab looks faintly rippled.

**G4. Shadow art, multi-view objects and ambiguous cylinders**
- What: one sculpture casts up to three different shadows (Mitra and Pauly, SIGGRAPH Asia 2009,
  https://graphics.stanford.edu/~niloy/research/shadowArt/shadowArt_sigA_09.html). Sugihara's
  ambiguous cylinders look like circles from one side and squares in a mirror, best seen from
  about 45 degrees above, with free STL files in two sizes
  (https://www.isc.meiji.ac.jp/~kokichis/ambiguousc/ambiguouscylindere.html;
  https://all3dp.com/ambiguous-cylinder-illusion-melt-brain/). Multi-view wire art and perforated
  lampshades that project images are related (unverified).
- Accessibility: hobbyist; any printer.
- Magic relevance: transformation. They work from one viewpoint, so they suit video, a single
  seated spectator, or an installation with a fixed mirror. A printed clump that casts the chosen
  card's shadow under a phone torch is a workable parlour reveal with a forced card.

**G5. Structural colour by build-plate transfer**
- What: printing onto a double-axis diffraction grating sheet (13,500 lines per inch) transfers
  the grating to the first layer. Bed 60 C, first layer 0.18 mm, works with PLA, ABS and flexible
  filament, strongest on dark colours, needs flat areas of 5 mm or more. Single-axis sheets did
  not transfer.
- References: https://learn.adafruit.com/3d-printing-on-diffraction-grating-sheets;
  https://hackaday.com/2022/02/13/3d-printing-rainbows.
- Accessibility: off-the-shelf, a few dollars for the sheet.
- Magic relevance: mostly decorative. It makes a printed face look like a factory hologram
  sticker, which helps a prop pass as a commercial product.

**G6. Lithophanes, filament painting, hidden and dual images**
- What: thickness-coded translucent prints show an image when backlit. HueForge computes stacked
  filament layers that give multi-colour images without a multi-material printer
  (https://shop.thehueforge.com/).
- Accessibility: off-the-shelf.
- Magic relevance: a plain white tile, box wall or lampshade that shows an image only with light
  behind it is a cheap delayed reveal (prediction). Thin embossing of 0.1 mm on resin gives marks
  that show only under raking light.

**G7. Polarisation images (Polagons)**
- What: laser-cut cellophane layers (0.023 to 0.053 mm) between polarisers change colour with
  polariser angle and are clear without them (Sethapakdi et al., CHI 2023,
  https://hcie.csail.mit.edu/research/polagons/polagons.html).
- Magic relevance: a clear window that shows a picture only through polarised glasses, or marks
  only the performer can see. Agent 5's territory.

**G8. Pointers**
- Printed light pipes route light through a solid print to any surface (Willis et al., UIST 2012,
  https://la.disneyresearch.com/wp-content/uploads/printedoptics-paper.pdf). Needs clear
  material; on consumer resin, short pipes work and long ones lose light.
- Photochromic recolouring (PhotoChromeleon): a coating of three dyes is set by a projector and a
  365 nm lamp; 24 minutes to 2 hours per recolour, fades in 5 to 26 hours indoors
  (https://hcie.csail.mit.edu/research/photochromeleon/photochromeleon.html). Too slow live;
  usable to prepare a one-night custom object. Agent 7's territory.
- Full-colour surfaces by computational hydrographics and thermoforming are in section E.
- Printed textiles: under-extruded PLA makes a tulle-like fabric on a $250 printer (Forman et
  al., UIST 2020, https://www.media.mit.edu/projects/defextiles/overview/). Possible use: gauze,
  nets and pockets printed in one piece with rigid frames.

### H. Material tricks on consumer printers

- **Foaming and dense filaments**: see A2. An object that feels far too light or too heavy for
  its size is a physical anomaly on its own, and the size-weight mismatch can make a spectator
  misjudge which of two objects is "the heavy one".
- **Soluble supports (PVA, BVOH)**: allow enclosed moving parts and captive objects with no
  access hole larger than a drain pinhole. Needs a multi-material printer; dissolving takes hours
  (unverified numbers).
- **Flexible TPU skins**: a rigid core co-printed under a soft skin hides hinges and buttons, and
  gives living hinges that do not show a pin.
- **Clear resin and clear FDM**: resin polishes to transparency with sanding and a clear coat;
  FDM stays hazy. Enough for light pipes, windows and liquid-filled props.
- **Glow, thermochromic and UV colour-change filaments**: off-the-shelf (unverified, no supplier
  page opened). Thermochromic prints change colour near body temperature, so a held object
  changes in the hand; UV-reactive prints change in sunlight or under a hidden UV LED. The effect
  is slow (seconds) and widely known from novelty mugs.
- **Low-melt and wax filaments**: polycaprolactone softens near 60 C (unverified). Use: parts
  that release or reshape in hot water.
- **Printing on fabric**: clamping mesh fabric into a paused print bonds plastic through the
  weave (Rivera et al., CHI 2017, unverified). Use: rigid gimmicks anchored invisibly to cloth,
  such as pockets, holders and stiffeners inside a handkerchief or bag.
- **Multi-material inlay**: two-colour first layers give flush printed-looking text and pips, so
  dice faces, card indices and labels need no paint.
- **Finishing**: see section E.

### I. Impossible objects and captive parts

- **What printing gives directly**: closed interlocked rings and chains with no join, a ball
  inside a cage it cannot pass through, an arrow through a hole smaller than its head, nested
  spheres, a bolt captive in a block. These print in place on any FDM printer with 0.3 mm gaps.
- **Sealed contents**: pause-and-insert (D1) puts a real coin, a die or a folded card in a clear
  or opaque block.
- **Magic relevance**: penetration and physical anomaly. A printed linked pair of solid rings is
  a give-away souvenir that "proves" a linking effect after a switch: the spectator examines two
  separate rings, the performer links them, and the linked pair handed out has no gap because it
  was printed linked. Ring-on-rope and "how did that get in there" objects work the same way.
  The weakness is that a printed object invites the explanation "it was printed that way", so the
  switch must be clean and the rings should look like something else (cast metal finish, wood
  grain filament, or an everyday item such as key-ring loops or bangles).
- **Prior use**: impossible bottles and captive-ball carvings are a long tradition; printed
  versions are common on model sites (unverified, not opened).

## 3. Capability primitives

1. *Now possible:* set mass anywhere from 0.33x to 7x of solid PLA with an unchanged exterior.
   *Because:* LW-PLA 0.40 to 0.48, tungsten filament 8.0 to 9.2 g/cm3. *Before:* drilled and
   plugged lead. *Primitives:* conceal, prove ordinariness.
2. *Now possible:* match a gimmick's mass, centre of mass and inertia to the real object within
   printer tolerance. *Because:* CAD mass properties plus per-region infill, Make It Stand style
   optimisers. *Before:* trial and error. *Primitives:* prove ordinariness, swap.
3. *Now possible:* two visually identical objects with equal mass and balance but about 3x
   different rotational inertia. *Because:* rim against centre loading. *Before:* marks or weight
   differences that a spectator can also find. *Primitives:* know.
4. *Now possible:* a solid one-material die whose chosen face comes up at a designed rate.
   *Because:* resting-probability solver with inverse design (2025). *Before:* loads and shaved
   faces found by inspection. *Primitives:* control chance, prove ordinariness.
5. *Now possible:* compute any object's resting-pose probabilities in seconds before printing.
   *Because:* same solver. *Before:* thousands of test throws. *Primitives:* control chance.
6. *Now possible:* a latch, lock or release with zero separate parts and zero backlash.
   *Because:* metamaterial shear cells, flexures, bistable cells. *Before:* pins, springs and
   screws that rattle and show. *Primitives:* hold/release, prove ordinariness.
7. *Now possible:* a one-shot mechanical trigger that stores spring energy and fires on a light
   touch, printed in place. *Because:* bistable cells. *Before:* mousetrap-style assemblies.
   *Primitives:* hold/release, move.
8. *Now possible:* thread or air channels following any 3D curve inside a solid-looking part.
   *Because:* additive build, soluble supports. *Before:* straight drilled holes only.
   *Primitives:* move, conceal.
9. *Now possible:* a solid block containing an object with no seam anywhere. *Because:*
   pause-and-insert (M601). *Before:* glued halves, cast resin. *Primitives:* conceal, prove
   ordinariness, delay.
10. *Now possible:* a break that always happens in the same place and leaves the same surface.
    *Because:* layer-bond control and matched printed surfaces. *Before:* pre-scored or pre-cut
    props with visible lines. *Primitives:* control choice, erase the evidence.
11. *Now possible:* N copies of a "unique" fracture surface, accurate to about 0.1 mm.
    *Because:* resin printing of a designed rough surface. *Before:* impossible; the torn corner
    was proof. *Primitives:* duplicate, swap.
12. *Now possible:* a parting line hidden among 100 to 300 identical layer lines. *Because:* FDM
    surface texture. *Before:* seams hidden by pattern, paint or misdirection. *Primitives:*
    conceal.
13. *Now possible:* a wall opaque to eyes and about 45% transparent per mm to an 850 to 940 nm
    camera, for about $6 per 100 g. *Because:* IR-transmitting PLA. *Before:* tinted acrylic
    windows that look like windows. *Primitives:* know.
14. *Now possible:* mark individual copies by manufacturing parameters only (204 codes by camera,
    a handful by eye). *Because:* G-ID bottom-line angle and width. *Before:* scratches, dots,
    one-way patterns. *Primitives:* know.
15. *Now possible:* 1,000 different engraved tokens for about $2 of resin. *Because:* resin
    printing, 0.4 mm engraved detail, scripted CAD. *Before:* a few hand-made outs. *Primitives:*
    control choice, duplicate.
16. *Now possible:* a prop carrying tonight's spectator's name or date, moulded in, made
    overnight. *Because:* parametric CAD plus multi-colour flush inlay. *Before:* engraving
    services, days. *Primitives:* prove ordinariness, delay.
17. *Now possible:* holding force tuned from "falls out" to "needs a pull" by dimension alone, in
    0.05 mm steps. *Because:* tolerance ladders at cents per test. *Before:* shimming, wax,
    magnets. *Primitives:* hold/release.
18. *Now possible:* a ferromagnetic part with no slug, shim or seam. *Because:* iron PLA.
    *Before:* embedded steel discs. *Primitives:* hold/release, conceal.
19. *Now possible:* a touch-sensitive area with no button or moving part. *Because:* conductive
    PLA co-printed in the wall. *Before:* foil pads and wires. *Primitives:* tell.
20. *Now possible:* release triggered by 60 to 65 C water with no electronics. *Because:* PLA
    glass transition and printed-in stress. *Before:* wax links. *Primitives:* delay,
    hold/release.
21. *Now possible:* a thin shell over a plastic object with 0.4 mm walls and 0.1 mm fit.
    *Because:* resin printing. *Before:* vacuum forming or machining. *Primitives:* duplicate,
    conceal, swap.
22. *Now possible:* identical-looking objects with different tap or shake sounds by internal
    geometry. *Because:* cavity and shape design (Acoustic Voxels, Zoolophone). *Before:* loose
    rattles. *Primitives:* know, tell.
23. *Now possible:* an object that floats at a chosen angle and waterline. *Because:* buoyancy
    optimisation. *Before:* ballast by trial. *Primitives:* control chance, conceal.
24. *Now possible:* a disposable gimmick per performance at $0.10 to $1. *Because:* PLA at about
    2 cents a gram. *Before:* gimmicks too costly to destroy. *Primitives:* erase the evidence.

## 4. Effect concepts

**1. The honest die (level 3).** *Effect:* a spectator rolls an odd-shaped gaming die; the
performer's prediction matches three times running. The die is given away. *Method:* shape
designed with the resting-rigid-bodies inverse solver so one face rests at 60% or more; solid
resin, nothing inside. A second, fair-looking sibling shape allows a switch-free "now you try"
failure if its favoured face differs. Combine with equivoque for misses. *BOM:* resin printer or
print service, under $5. *Difficulty:* moderate (build the solver, iterate with roll tests).
*Risks:* real rolls with spin deviate from the model; face count against bias trade-off.
*Novelty:* high; I found no magic use of computed geometric bias.

**2. Weight-matched shell family (level 2).** *Effect:* none by itself; it is an upgrade to any
shell, hollow or loaded prop (chips, caps, dice, game pieces). *Method:* print the gimmick in
LW-PLA, add a tungsten or steel trim insert at a pause so mass and balance equal the genuine
object's within 0.1 g. *BOM:* LW-PLA €26, tungsten scraps. *Difficulty:* easy. *Risks:* LW-PLA
surface is matte and slightly rough. *Novelty:* medium; the principle is old, the precision is new.

**3. The duplicated break (level 3).** *Effect:* a spectator snaps a corner off a plaster-like
token and keeps it. The token is destroyed or vanishes, then turns up sealed somewhere impossible;
the spectator's corner fits it exactly. *Method:* tokens are printed in two parts with a designed
random-looking mating surface and tacked with a weak bond, so the "break" is predetermined. A
second token with the identical surface was loaded hours earlier. *BOM:* resin, filler primer,
under $3 a set. *Difficulty:* moderate; the finish must hide the tack line. *Risks:* tack line
visibility; fit must feel like a real break (print the mating faces rough). *Novelty:* high.

**4. See-through-black dice cup (level 3).** *Effect:* a spectator shakes borrowed dice under an
opaque black cup; the performer, across the room, names the total. *Method:* the cup's crown is
1 mm IR-transmitting PLA over a NoIR camera module with 940 nm LEDs; the rest is ordinary black
filament of matching sheen. Readout to the performer is agent 14's slice. *BOM:* IR PLA $6, camera
board $20 to $30, battery. *Difficulty:* moderate to hard. *Risks:* sheen mismatch between
filaments, a thick crown, pips with poor IR contrast. *Novelty:* medium-high; electronic dice
exist, reading ungimmicked dice through a "solid" wall I did not find.

**5. Inertial marking (level 3, speculative).** *Effect:* five identical sealed boxes, one holding
a borrowed ring, are mixed by spectators; the performer finds it by picking each up once. Scales
would show equal weights. *Method:* the ring carrier sits at the centre in one box and dummy
masses sit at the rim in the others, with equal totals and balance. A small wrist twist feels the
difference. *BOM:* PLA and steel shot, $5. *Difficulty:* easy to build, needs practice. *Risks:*
human sensitivity to inertia needs testing. *Novelty:* high as far as I could find.

**6. Self-sealing one-way block (level 3).** *Effect:* a signed coin vanishes and is found inside
a solid printed block that has to be broken open. *Method:* a spring-loaded printed plug, textured
with the same layer lines, closes a load port flush and latches irreversibly on a bistable
flexure. The block has a programmed break plane so it opens cleanly. One block per show.
*BOM:* PLA, about $0.50 each. *Difficulty:* hard (flush plug, reliable latch). *Risks:* plug
outline visible under raking light; place it on a layer line or under fuzzy skin. *Novelty:*
medium; it is the nest of boxes rebuilt as a consumable.

**7. Thousand-out token index (level 3).** *Effect:* any three-digit number named aloud is found
engraved on a tiny tile inside a sealed pill bottle the spectator has held. *Method:* 1,000
engraved resin tiles in a printed belt index with two-digit tactile addressing; the bottle has a
weight-matched shell base for loading. *BOM:* resin $2, printed index. *Difficulty:* hard (index
design and handling). *Risks:* retrieval time, miscounts. *Novelty:* medium; indexes are classic,
this size was not practical by hand.

**8. Gravity-sequence lock (level 2).** *Effect:* a small box that spectators cannot open, though
the performer opens it at once, and it can be examined for as long as they like. *Method:* a
sealed-in ball in a printed maze frees the lid only after a tilt sequence. No magnet, no power.
*BOM:* PLA and a steel ball, $1. *Difficulty:* easy. *Risks:* rattle; persistent spectators may
open it by chance. *Novelty:* low to medium; common in puzzles, rare in magic sets.

**9. Seamless touch cue (level 2).** *Effect:* no visible action; the performer starts or stops a
hidden device by resting a finger on a plain part of a prop. *Method:* conductive PLA co-printed
under a 0.4 mm skin, read by a capacitive input. *BOM:* conductive PLA $7, microcontroller.
*Difficulty:* moderate. *Risks:* false triggers from spectators' hands. *Novelty:* medium.

**10. Hot-drink release (level 2).** *Effect:* a stirrer left in a spectator's hot tea slowly
bends, or a sealed capsule dropped into it opens to release a prediction. *Method:* printed-in
stress (Thermorph) or a PLA latch that softens above 60 C. *BOM:* PLA. *Difficulty:* moderate
tuning. *Risks:* scalding water near spectators; drinks cooler than 60 C do nothing. *Novelty:*
medium; the bend alone is level 1.

**11. Rattle on command (level 2).** *Effect:* three sealed boxes, one rattles; the spectator
never finds it. *Method:* every box holds a ball that parks silently in a pocket depending on how
the box is first tilted when lifted. One piece, sealed, examinable. *BOM:* $2. *Difficulty:* easy.
*Risks:* a spectator finding the tilt by accident. *Novelty:* medium; replaces the hidden
sleeve rattle.

**12. Backlit tile reveal (level 1).** *Effect:* a plain white tile shows the chosen card when a
phone torch is held behind it. *Method:* lithophane; 52 tiles or a forced card. *BOM:* PLA, cents.
*Difficulty:* easy. *Risks:* the image is faintly visible as relief on the back; print it relief
side inward in a two-wall tile. *Novelty:* low.

**13. Linked for keeps (level 1 to 2).** *Effect:* two solid bangles examined by a spectator are
linked in her hands and given to her to keep, with no gap or join. *Method:* three rings: two
separate, one pair printed linked, in a wood-fill or metal-finish filament; a switch under cover
of the linking move. *BOM:* under $2 a set. *Difficulty:* easy print, needs a good switch.
*Risks:* "it was printed like that"; disguise the material. *Novelty:* low to medium; a cheap
give-away finish for a classic.

**14. The disobedient top (level 1).** *Effect:* a small figure spins upright on one toe for the
performer and falls over at once for everyone else; or a top shaped like a lopsided object spins
dead steady. *Method:* Spin-It style interior design; for the failure version, two look-alike
figures with different interiors, or a rattleback base. *BOM:* PLA, a metal tip. *Difficulty:*
moderate tuning. *Risks:* reads as a science toy. *Novelty:* low.

**15. Shadow of the chosen card (level 1).** *Effect:* a tangle of printed plastic casts a
shapeless shadow, then, turned to one angle under a phone torch, the shadow is the spectator's
card. *Method:* shadow-art volume with one meaningful and two abstract projections, forced card.
*BOM:* PLA. *Difficulty:* easy. *Risks:* needs a single small light source and a wall. *Novelty:*
low to medium.

Eleven of the fifteen are level 2 or 3.

## 5. Dead ends and overhyped items

- **Homogeneous Gömböc or monostable polyhedra on a hobby printer**: 0.01 mm precision or exotic
  density ratios. Use a hidden weight instead.
- **Printed metal-looking coin shells**: wrong weight, sound and temperature.
- **Hidden weights in standard cubic dice**: bias is modest unless the die is mostly hollow.
- **AirCode, BrightMarker, InfraStructs, printed hydraulics, PolyJet lenticular objects**: need
  lab printers, non-retail filament or projector rigs.
- **Trajectoids as shown**: the shape gives the game away and the paths wander.
- **Ambiguous cylinders and shadow art live**: one viewpoint only.
- **PhotoChromeleon-style recolouring**: tens of minutes in a dark box, fades in hours.
- **Tungsten filament for bulk weight**: about $1,400 per kg; use inserts.
- **Acoustic tags by tapping in a noisy room**: lab-validated only; the reading hardware is not
  described on the project pages.

## 6. Open leads

- Measured friction of FDM and resin micro-textures, and whether sawtooth surfaces give one-way
  slip between tiles or cards. I found no data this session.
- Layer-bond strength against slicer settings, for calibrated break forces.
- Human sensitivity to moment of inertia in small handheld objects (for concept 5).
- Viscoelastic bistable shells as electronics-free timers (seconds to minutes), unverified.
- Soluble-plug delays (PVA, BVOH) with measured dissolution times.
- Computational telescoping structures (Yu, Crane, Coros 2017), CapriCate, AirTouch, Blowhole,
  Lamello, Print-A-Sketch, Medley, multi-view wire art and perforated lampshades: known to me but
  not opened this session.
- Embedding everyday objects in prints and printing onto existing manufactured objects (Encore,
  Reprise, RetroFab, unverified): a route to gimmicking a genuine object rather than replacing it.
- Metal routes for shells (plating, casting, service printing): agent 13.

## 7. Sources

Opened this session:
- https://igl.ethz.ch/projects/make-it-stand/ - Make It Stand project page, code and models
- https://visualcomputing.ist.ac.at/publications/2014/SpinIt/ - Spin-It abstract and paper link
- https://hbaktash.github.io/projects/putting-rigid-bodies-to-rest/index.html - resting-pose paper
- https://github.com/hbaktash/resting-rigid-bodies - code, including inverse dice design
- https://arxiv.org/abs/2506.19244 - Building a monostable tetrahedron
- https://www.gomboc.eu/en/ - Gömböc, 0.01 mm precision claim
- https://github.com/yaroslavsobolev/trajectoids - trajectoid code and build notes
- https://techxplore.com/news/2023-09-trajectoids-desired-path.html - trajectoid coverage
- https://colorfabb.com/lw-pla-natural - LW-PLA densities and price
- https://proto-pasta.com/products/magnetic-iron-pla - iron PLA
- https://proto-pasta.com/products/conductive-pla - conductive PLA resistance
- https://shop.thevirtualfoundry.com/products/rapid-3dshield-tungsten-filament - tungsten filament
- https://shop.thevirtualfoundry.com/collections/metal-filaments - metal filament prices
- https://hpi.de/baudisch/projects/metamaterial-mechanisms.html - metamaterial mechanisms
- https://hpi.de/baudisch/projects/digital-mechanical-metamaterials.html - mechanical logic cells
- https://hcie.csail.mit.edu/research/metasense/metasense.html - sensing in metamaterials
- https://la.disneyresearch.com/publication/computational-design-of-mechanical-characters/
- https://arxiv.org/abs/1512.03744 - Printable Hydraulics
- https://morphingmatter.org/projects/thermorph - Thermorph
- https://morphingmatter.org/projects/4dmesh - 4DMesh
- https://www.cs.cmu.edu/news/2018/cheap-3-d-printer-can-produce-self-folding-materials
- https://en.wikipedia.org/wiki/Polylactic_acid - PLA density and glass transition
- http://www.cs.columbia.edu/cg/zoolophone/ - shape optimised for struck tone
- http://www.cs.columbia.edu/cg/lego/ - Acoustic Voxels project page
- https://la.disneyresearch.com/publication/acoustic-voxels/ - Acoustic Voxels summary
- https://chrisharrison.net/index.php/Research/AcousticBarcodes - Acoustic Barcodes
- https://help.prusa3d.com/article/insert-pause-or-custom-g-code-at-layer_120490 - pause and insert
- https://hcie.csail.mit.edu/research/infraredtags/infraredtags.html - InfraredTags numbers
- https://hcie.csail.mit.edu/research/brightmarker/brightmarker.html - BrightMarker
- http://www.cs.columbia.edu/cg/aircode/ - AirCode
- https://hcie.csail.mit.edu/research/gid/gid.html - G-ID
- http://www.cs.columbia.edu/cg/layercode/ - LayerCode
- https://hcie.csail.mit.edu/research/structcode/structcode.html - StructCode
- https://printedwifi.cs.washington.edu/ - printed wireless objects
- https://www.hubs.com/knowledge-base/how-design-parts-sla-3d-printing/ - resin design limits
- https://www.hubs.com/knowledge-base/how-design-parts-fdm-3d-printing/ - FDM design limits
- https://www.hubs.com/knowledge-base/dimensional-accuracy-3d-printed-parts/ - tolerances
- https://en.wikipedia.org/wiki/Quarter_(United_States_coin) - quarter dimensions
- http://www.cs.columbia.edu/cg/hydrographics/ - computational hydrographic printing
- https://igl.ethz.ch/projects/thermoforming/ - computational thermoforming
- https://tangible.media.mit.edu/project/cilllia/ - Cilllia printed hair
- https://hcie.csail.mit.edu/research/lenticularobject/lenticular-object.html - Lenticular Objects
- https://hcie.csail.mit.edu/research/fabobscura/fabobscura.html - FabObscura
- https://hcie.csail.mit.edu/research/polagons/polagons.html - Polagons
- https://hcie.csail.mit.edu/research/photochromeleon/photochromeleon.html - PhotoChromeleon
- https://mattferraro.dev/posts/caustics-engineering - caustic window build and code
- https://graphics.stanford.edu/~niloy/research/shadowArt/shadowArt_sigA_09.html - Shadow Art
- https://www.isc.meiji.ac.jp/~kokichis/ambiguousc/ambiguouscylindere.html - Sugihara, with STLs
- https://learn.adafruit.com/3d-printing-on-diffraction-grating-sheets - grating transfer
- https://shop.thehueforge.com/ - HueForge
- https://www.media.mit.edu/projects/defextiles/overview/ - DefeXtiles

Seen in search results, not opened:
- https://history.siggraph.org/?p=108355 - Make It Stand record
- https://diglib.eg.org/handle/10.1111/cgf12810 - Buoyancy Optimization paper record
- https://github.com/MultiW/make-it-balance - student re-implementation
- https://www.nature.com/articles/s41586-023-06306-y.pdf - trajectoids paper (paywalled)
- https://news.mit.edu/2022/invisible-labels-identify-track-objects-0128 - InfraredTags news
- https://news.mit.edu/2023/enhancing-3d-object-tracking-invisible-tagging-system-0815
- https://arxiv.org/abs/1707.05754 - AirCode preprint
- https://publishup.uni-potsdam.de/files/42986/ion_diss.pdf - Ion dissertation
- https://la.disneyresearch.com/wp-content/uploads/printedoptics-paper.pdf - Printed Optics
- https://all3dp.com/ambiguous-cylinder-illusion-melt-brain/ - printable ambiguous cylinder
- https://hackaday.com/2022/02/13/3d-printing-rainbows - grating transfer notes
- https://all3dp.com/2/3d-printed-magic-tricks-3d-models/ - ten printable tricks (body not readable)
- https://makerworld.com/en/models/251925 - printed coin box (page returned 403 when opened)
- https://makerworld.com/models/1367291 - printed finger guillotine
