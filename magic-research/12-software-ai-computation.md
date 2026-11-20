# 12 - Software, AI, mathematics and computation as magic methods (2015 to 2026)

Slice: computation as a hidden method, with the result appearing in the physical world and no
phone or screen in the audience's view. Prices are as of late 2026 and come from the pages cited.

**Research-method note.** The shared web-search budget for this project ran out after my ninth
search. Everything after that was done by opening known primary pages directly (project pages,
GitHub READMEs, arXiv, vendor pages, Wikipedia). About 60 pages were opened. Anything I recall but
could not open or confirm is marked "(unverified)". Coverage of magic-trade prior art is therefore
thin; agent 2 and agent 3 should be treated as authoritative there.

**Level tags** used throughout (from the course correction): L1 = the phenomenon is the effect;
L2 = a hidden input that removes a weakness of a traditional method; L3 = a new method
architecture the audience never suspects.

---

## 1. Summary

- **The highest-value use of computation is before the show, not during it.** Search,
  optimisation and generation can produce stacks, forcing structures, book texts, anagram trees and
  thousands of indexed physical outs that no person would design by hand. At performance time
  there is no electronics at all, so the "a computer did it" theory has nothing to attach to.
  Williams and McOwan showed the pattern in 2014 (a simulated-annealing deck stack that beat
  Aronson's Simon-Eyes on average questions needed, 3.85 against 4.04); almost nobody has repeated
  it with 2026 solvers, LLMs and print-on-demand.
- **Diffusion "illusion" images are best understood as an outs compressor, not as a spectacle.**
  One printed, examinable object can now carry 2 to 4 full-quality pictures selected by rotation,
  viewing distance, colour of light, a second transparency, or re-assembly of jigsaw pieces. Code
  is MIT-licensed and runs on free-tier Colab (Visual Anagrams) or Colab notebooks (Diffusion
  Illusions).
- **Offline speech recognition is now small enough to hide in a prop and fast enough to act
  inside a sentence.** Vendor benchmarks put Moonshine streaming models at about 237 ms (tiny) to
  802 ms (medium) on a Raspberry Pi 5; an ESP32-S3 with Espressif's MultiNet recognises up to 300
  fixed phrases offline with no training. The performer never has to peek, pump or type.
- **For closed sets (52 cards, numbers, times) do not put an LLM in the loop.** A constrained
  vocabulary recogniser is faster and more reliable. LLMs and embedding models earn their place
  for open-ended answers: mapping "anything you can think of" to the nearest of several hundred
  prepared physical outs.
- **Batteryless NFC e-paper is the cleanest dynamic "print".** A 296 x 128 panel refreshes in about
  2 s powered only by the NFC field and is afterwards inert: no battery, no radio. It is thick as
  sold (12.4 mm board outline) and reads as e-ink at close range.
- **Ink, sand, flaps, clock hands and burn marks beat pixels.** A thermal printer costs about $50
  and prints 50 to 80 mm/s; a servo plotter costs about EUR 15; pen plotters make real ballpoint
  "handwriting" overnight. These are all much stronger as pre-show out factories than as live
  reveal machines, because live they are noisy and slow.
- **Human "free choices" are predictable to a useful, stated degree.** A 5-gram predictor of
  binary choices is right about 70% of the time; Google's Quick, Draw! set holds 50 million
  timed drawings in 345 categories. Confidence-gated commitment (only commit when the model is
  sure) is an unexploited architecture.
- **Cryptographic "proof I predicted this" can be faked with multiple outs.** Twelve PDFs sharing
  one MD5 hash were published as a mock election prediction in 2007; today colliding PDF or image
  pairs take seconds. This is theatre for a technical audience and must be framed as such.
- **Hobbyist dynamic projection mapping is still an order of magnitude slower than the lab.**
  DynaFlash runs at 1,000 fps with 3 ms delay; a consumer pipeline is 30 to 50 ms, which is 9 to
  15 mm of smear on a prop moving at 0.3 m/s. Use static or slow targets.
- **Real-time deepfakes, voice cloning, live image generation and AI songs work but are L1.**
  They read as "AI", need a screen or speaker, and raise consent problems. Keep them brief.

---

## 2. Catalog

### A. Generated images with hidden structure (printable)

**A1. Visual Anagrams (multi-view images).** At each denoising step the model estimates noise
for every "view" of the image, undoes the view, averages, and steps. Supported views in the code:
rotations by 90/180 degrees, flips, colour negation, skew, inner-circle rotation, jigsaw
rearrangement, patch and pixel permutation, and a "square hinge" view. Three- and four-view
examples are shown. It uses DeepFloyd IF (pixel-space, because latent models leave artefacts);
native output is 64 then 256 px, with an optional 1024 px upscale that only uses the first prompt.
- Refs: Geng, Park, Owens, CVPR 2024, https://arxiv.org/abs/2311.17919 ;
  https://dangeng.github.io/visual_anagrams ; code https://github.com/dangeng/visual_anagrams
  (MIT; free-tier and Pro Colab notebooks; the project page links a printable jigsaw PDF).
- Accessibility: free Colab or a 24 GB GPU (a reimplementation reports an RTX 3090 is enough);
  hosted version at https://replicate.com/chigozienri/visual-anagrams . Low-memory DeepFloyd notes:
  https://tmzh.github.io/post/2024-01-22-running-deep-floyd-with-limited-memory .
- Magic relevance: prediction, transformation. One print holds up to four outs chosen by which
  way up it is hung or handed over. No screen. Fully examinable. Weakness: 256 px native
  resolution limits print size to roughly A5 before it looks soft; image quality drops as views
  are added; a savvy viewer may know "AI ambigrams" exist, so do not let the turn be the climax.
- Prior magic use: none found. Hand-drawn ambigram and topsy-turvy predictions are old; this
  makes them on demand for any pair of subjects.

**A2. Factorized Diffusion (hybrid, colour-hybrid and motion-hybrid images).** Different prompts
drive different components of one image: low against high spatial frequency (changes with
distance or blur), greyscale against colour (changes when colour is removed, for example under
monochromatic light), and a motion-blur component. Triple hybrids are reported.
- Refs: Geng, Park, Owens, ECCV 2024, https://arxiv.org/abs/2404.11615 ;
  https://dangeng.github.io/factorized_diffusion . Foundation: Oliva, Torralba, Schyns, hybrid
  images (ACM TOG 2006), https://en.wikipedia.org/wiki/Hybrid_image .
- Magic relevance: a picture across the room is "a landscape"; in the hand it is the chosen
  card. The reverse direction is the useful one: the prediction is unreadable at arm's length and
  obvious from the back row or through frosted glass, a squint, or a deliberately defocused
  camera. Colour hybrids pair with a sodium or single-colour LED lamp (agent 5 covers lamps).
  Fully passive and examinable.

**A3. Diffusion Illusions (overlay, flip, folding and puzzle images).** Score distillation
optimises several "prime" images so that derived arrangements match target prompts. Types: flip;
rotation overlay (two sheets stacked, the top one rotated in 90 degree steps to give four
different pictures); hidden overlay (four innocent pictures stack to show a fifth); twisting
squares (hinged tiles that fold to a second picture); Parker puzzles. The authors report physical
fabrication and provide printable PDFs.
- Refs: Burgert, Li, Leite, Ranasinghe, Ryoo, SIGGRAPH 2024, https://arxiv.org/abs/2312.03817 ;
  https://diffusionillusions.com/ ; https://github.com/RyannDaGreat/Diffusion-Illusions (five
  Colab notebooks; hardware needs and licence not stated on the pages I opened).
- Magic relevance: the overlay types are a new kind of "two halves make a whole" prediction: two
  spectators each hold an innocent transparency for the whole act; stacked, they show the
  outcome, and the orientation of the stack selects one of four outs. Printing on inkjet
  transparency film costs cents per sheet. Agent 5 owns the optics (contrast when stacking).

**A4. ControlNet "QR Monster" hidden-pattern images.** A ControlNet steers Stable Diffusion so
the image's luminance follows a supplied pattern: a QR code, a word, a silhouette, a card pip.
Control strength trades readability against naturalness. The pattern is seen when squinting, from
far away, or in a thumbnail.
- Refs: https://huggingface.co/monster-labs/control_v1p_sd15_qrcode_monster (OpenRAIL++; v2
  improves scannability); SDXL version
  https://huggingface.co/monster-labs/control_v1p_sdxl_qrcode_monster ; IllusionDiffusion demo
  app https://huggingface.co/spaces/AP123/IllusionDiffusion/raw/main/app.py ; practical guide
  https://antfu.me/posts/ai-qrcode-101 .
- Accessibility: runs on any 8 GB consumer GPU or a free hosted space (unverified memory figure);
  full print resolution, unlike A1.
- Magic relevance: easiest route to "the word was in the painting all along". A scannable QR
  hidden in a picture needs a phone, so it is out of scope for the reveal itself.

**A5. 3D multi-view and mirror objects.** Illusion3D makes 3D shapes that read as different
pictures from different directions (https://arxiv.org/abs/2412.09625 ,
https://3d-multiview-illusion.github.io ). Mirror Illusion Art (Zhu et al., CVPR 2026,
https://arxiv.org/abs/2607.02015 , code https://github.com/zxp555/automia ) designs a printable
object whose reflection shows a different image from its front; reported design time is about 76 s
and 2.6 GB on one RTX 3090. JanusMesh (2026, https://huggingface.co/papers/2606.20563.md ) is a
zero-shot follow-up. A sculpture that has sat next to a mirror all evening is a two-out
prediction with no moving parts. Needs colour 3D printing for the textured versions (agent 13).

**A6. Other image tricks, briefly.** "Images that Sound" makes a picture that is also a playable
spectrogram (Chen, Geng, Owens, NeurIPS 2024, https://arxiv.org/abs/2405.12221 ,
https://ificl.github.io/images-that-sound ): a printed picture "played" by a scanner is L1 and
needs explaining. Photomosaics are a 1990s idea but now trivial to compute from an audience's own
photos overnight. Adversarial patches (Brown et al. 2017, https://arxiv.org/abs/1712.09665 ) make
a printed sticker force a classifier's output: only useful if the show contains an "honest AI
judge", which is itself a screen.

### B. Real-time AI in the show loop

**B1. On-device speech recognition as the secret assistant.** Options, smallest first:
- ESP32-S3 with Espressif ESP-SR: wake word, voice activity detection and MultiNet command
  recognition for up to 300 English or Chinese phrases, added as text with no retraining
  (https://github.com/espressif/esp-sr ). A complete listener is a thumb-sized board and a MEMS
  microphone, roughly $10 to $20 (unverified price).
- Vosk: 50 MB offline models with a streaming API and runtime-reconfigurable vocabulary, runs on
  Raspberry Pi (https://alphacephei.com/vosk/ ). sherpa-onnx adds streaming ASR, keyword
  spotting, VAD and speaker ID on Pi, Jetson and RK3588 boards
  (https://github.com/k2-fsa/sherpa-onnx ).
- Moonshine: streaming models that work while the person is still talking. Vendor benchmark on
  Pi 5, CPU only: tiny about 237 ms, small about 527 ms, medium about 802 ms; the same table gives
  faster-whisper tiny at about 5.9 s (the maintainers note their Pi figures may be pessimistic)
  (https://moonshine-voice.readthedocs.io/en/latest/moonshine-vs-whisper/ ,
  https://github.com/moonshine-ai/moonshine , MIT).
- whisper.cpp: tiny is 75 MiB on disk and about 273 MB RAM; has a streaming example that samples
  every 500 ms (https://github.com/ggml-org/whisper.cpp ). Whisper's fixed 30 s window makes true
  low latency awkward (WhisperKit paper, https://arxiv.org/html/2507.10860v1 ).
- Magic relevance: the *know* primitive with no performer action. Failure modes: room noise,
  applause, two people talking, accents, a spectator who whispers. Mitigations: restrict the
  vocabulary to the outcome set; make the performer repeat the choice aloud in a fixed carrier
  phrase ("so, the seven of clubs") as natural recap, which gives a known voice at known distance
  and pushes accuracy towards 100%; confirm by a silent haptic tick (agent 10) before committing.
  Legal note: process audio in RAM only and store nothing; always-listening devices can fall
  under recording-consent law.
- Prior use: phone apps listen in this way (agent 2). "SAM" (Vanishing Inc.) is sold on the
  point that the word is never spoken, to cancel the voice-recognition theory
  (https://www.vanishingincmagic.com/magic-apps/sam/ ). "AI Stooge" (Pavel Bach, listed at $60)
  steers a spectator's own ChatGPT (https://www.penguinmagic.com/p/S37976 ; page not openable).

**B2. LLMs and embeddings in the loop.** A cloud LLM call adds a network dependency and typically
0.3 to 1.5 s (unverified general figure). Local options: Raspberry Pi AI HAT+ 2 ($130, Hailo-10H,
8 GB on-board RAM, 1 to 1.5 billion parameter models such as Llama 3.2 1B and Qwen2.5 1.5B;
https://www.raspberrypi.com/news/introducing-the-raspberry-pi-ai-hat-plus-2-generative-ai-on-raspberry-pi-5/ ).
Useful jobs: (a) normalising messy speech into one of N outcomes when N is large or open;
(b) semantic nearest-neighbour from a free answer to the closest prepared out; (c) decision
support, choosing the next line of an equivoque tree; (d) generating personalised patter or a
"reading". On (d): cold-reading text from an LLM is fluent and Barnum-heavy; present it as
theatre, never as real psychic ability, and do not feed it scraped personal data.

**B3. Generative media on demand (L1; brief).** Real-time voice conversion (VCClient supports
RVC and Beatrice models, https://github.com/w-okada/voice-changer ); single-photo live face swap
(Deep-Live-Cam, AGPL, with built-in consent notices, https://github.com/hacksider/Deep-Live-Cam );
image generation above 100 frames per second on an RTX 4090 (StreamDiffusion with SD-turbo,
106 fps text-to-image, https://github.com/cumulo-autumn/StreamDiffusion ); songs with vocals from
a prompt, 3 s to 5 min (Eleven Music API, https://elevenlabs.io/docs/overview/capabilities/music ;
generation time not stated). All need a screen or speaker and all read as "AI". Their one strong
hidden use is audio: a cloned voice on an old telephone or radio prop. Cloning a real person's
voice or face needs that person's consent.

Per-item notes for a live room:
- *Voice conversion / cloning.* Screen: none, audio only. Latency: roughly 100 to 300 ms on a
  consumer GPU (unverified), fine for a "phone call" but audible as echo if the real voice is
  also heard. Use: the performer offstage speaks as "the spirit on the line", or a rotary
  telephone rings and a synthetic voice names the card (local TTS such as Piper runs on a Pi,
  https://github.com/rhasspy/piper ). Failure: feedback, and audiences in 2026 assume any
  disembodied voice can be synthetic.
- *Real-time face swap.* Needs a camera and a display, so it fails the no-screen goal. Its one
  defensible use is a fake "mirror" or "live relay" in an installation.
- *Instant picture of a thought.* Generation is no longer the bottleneck (under 1 s); the output
  device is. Sent to an instant-film printer or a plotter it becomes a physical artefact
  (section C). Failure: text-to-image misreads the concept; restrict to nouns.
- *Song about your word.* Tens of seconds of generation (unverified), cloud only. Playing it
  from a transistor radio or a music box prop helps, but it still reads as AI.
- *Agents that phone or message.* An LLM agent can place a call or send to a printer on a cue;
  in practice a fixed script fired by the recogniser is more reliable than an agent, and
  automated calls to third parties raise consent and telecom-rule problems.
- *Small local models.* ESP32-S3: fixed phrases only. Pi 5: streaming ASR plus a 1 to 1.5 B
  LLM with the $130 HAT. Jetson Orin Nano: ASR plus a larger LLM plus vision (unverified
  figures). Venue Wi-Fi is the commonest point of failure, so prefer fully local pipelines or
  the performer's own hotspot.

### C. Physical output devices (the reveal is matter, not pixels)

| Device | Speed | Noise | Size / cost | Disguise and comments |
|---|---|---|---|---|
| Thermal receipt printer | 50-80 mm/s, 48 mm print width | Loud buzz | 111 x 65 x 57 mm, $49.95 (Adafruit 597, now unstocked; clones common) https://www.adafruit.com/product/597 | A till, card reader, ticket machine, "fortune" box. Output is ordinary paper and can be kept. |
| Servo arm plotter | A postcard in minutes | Servo whine | About EUR 15 plus a Pi, https://www.brachiograph.art/ | Wobbly lines look hand-drawn, which helps. |
| Pen plotter (AxiDraw / NextDraw) | Fast enough for a signature in seconds (unverified) | Stepper hum | NextDraw from $949, https://bantamtools.com/collections/bantam-tools-nextdraw | Real ink with real pen pressure. Best used offstage to mass-produce outs. |
| Instant film printer | About 12-15 s print, about 90 s to develop (unverified) | Motor whirr | Instax Link printers can be driven from Python over Bluetooth: Mini 600 x 800 px, Square 800 x 800 px, https://github.com/javl/InstaxBLE | A real chemical photo. The development delay is free time misdirection. |
| Laser engraver | Seconds to minutes | Fan, smell, smoke | $200 to $800 (unverified) | Burn into wood, leather, toast. Class 4 hazard: see safety. |
| Sand table | Minutes per pattern | Near silent | DIY Dune Weaver, 25/45/75 cm, Raspberry Pi plus FluidNC and two NEMA 17 steppers, https://github.com/tuanchris/dune-weaver ; commercial https://sisyphus-industries.com/ | Furniture that is already "art". Slow: the drawing must start before the choice appears to be made. |
| Split-flap / flip-dot | About 1 s per character (unverified) | Loud clatter (that is the charm) | Open-source ESP32 split-flap, 52 flaps per module, https://github.com/scottbez1/splitflap ; Vestaboard https://www.vestaboard.com/ ; flip-dots hold state unpowered, https://flipdots.com/en/home/ | Reads as "a display", so it is a screen in spirit. Best as a venue fixture. |
| Batteryless NFC e-paper | About 2 s refresh plus transfer | Silent | 2.9 in, 296 x 128, black/white, 87.5 x 47.7 x 12.4 mm board, https://www.waveshare.com/wiki/2.9inch_NFC-Powered_e-Paper | No battery or radio afterwards. Needs a writer coil within centimetres and stillness during refresh. |
| Shelf-label e-paper | Tags poll about every 40 s | Silent | OpenEPaperLink firmware, ESP32 access point, 802.15.4, about 9 uA sleep, https://github.com/OpenEPaperLink/OpenEPaperLink (non-commercial licence) | A price tag is an innocent object. Latency rules out tight timing. |
| Light through veneer | Instant | Silent | Google's CHI 2022 work drove a 128 x 96 PMOLED through wood veneer, fabric and mirror film, 3.6 to 40 times brighter than AMOLED, https://research.google/blog/hidden-interfaces-for-ambient-computing/ ; hobby version is an LED matrix under 0.5 mm veneer (unverified) | The surface is examinable-looking wood until lit. Glowing text still says "electronics". |
| Quartz clock movement | One step per pulse, pulses about 31 ms, alternate polarity, one direction only, https://en.wikipedia.org/wiki/Lavet-type_stepping_motor | Faint tick | $5 movement plus a microcontroller | An honest clock all evening. Stock movements are too slow to slew far (see concept 6). |
| Electronic typewriter | About 10-15 characters/s (unverified) | Loud, theatrical | IBM Wheelwriter driven by an Arduino on its option bus, https://github.com/tofergregg/IBM-Wheelwriter-Hack ; "Ghostwriter" GPT typewriter (Sanjeev, 2022), https://www.arvindsanjeev.com/ghostwriter.html | A typewriter typing by itself is a classic spirit effect with a period-correct cause. |

Smart-home devices (lamps, speakers, a network printer already in the room) are reachable from
Home Assistant, MQTT or WLED's HTTP/JSON API (https://kno.wled.ge/ ). Using a venue's own devices
needs the owner's permission.

Other output devices from the brief, not separately verified in this session:
- *Label and Zink printers.* Small Bluetooth units; a Zink print takes roughly 40 to 60 s and has
  no development phase (unverified). A label printer inside a "parcel" prop can print the address
  label or customs slip after the choice.
- *3D printer as reveal.* Far too slow live (tens of minutes). Useful only when a long print is
  started with a hidden pause and resumes into one of several endings, or as a pre-show out
  factory.
- *Radio.* A milliwatt FM transmitter feeding a genuine vintage radio gives an examinable prop
  that "happens to be playing" generated speech or music. Unlicensed transmit power is tightly
  limited by law in most countries; check local rules.
- *Self-playing piano or music box.* Solenoid or MIDI player systems make an acoustic instrument
  play a named tune; loud, large and strong as an installation.
- *Old telephone.* A rotary set with a Pi inside can ring, read the dial, and speak. It has an
  innocent reason to make sound.
- *Mechanical counters, odometers, split-flap clocks.* Small steppers behind a genuine counter
  face; clicks are expected, so noise is cover.
- *Projected light.* See section D.

For a live reveal the ranking, by how little they suggest a computer, is roughly: clock hands
and counters, ink on paper, instant film, sand, typewriter, e-paper, flaps, lit veneer.

### D. Projection and spatial computing (brief; agent 5 owns hardware)

- Dynamic projection mapping: Ishikawa-Watanabe lab, DynaFlash at up to 1,000 fps with 3 ms
  delay, tracked by infrared-ink dot markers invisible to the audience (Narita, Watanabe,
  Ishikawa, VRST 2015 and IEEE TVCG 2016, http://ishikawa-vision.org/vision/DPM/index-e.html ).
  Lab-only. A hobbyist 120 Hz projector, IR camera and a GPU gives about 30 to 50 ms end to end
  (my estimate), fine for a prop lying on a table or a slowly turned hand, not for juggling.
- Calibration: Microsoft RoomAlive Toolkit (Kinect plus projectors, MIT,
  https://github.com/microsoft/RoomAliveToolkit ); MadMapper and TouchDesigner for mapping
  (unverified: Lightform, the hobby-friendly structured-light projector, closed in 2022).
- Laser-scanned pico projectors are always in focus on any surface at any distance, at the price
  of speckle (https://en.wikipedia.org/wiki/Handheld_projector ). One hidden in a prop can throw
  a small crisp image onto a palm, smoke, or the inside of a paper bag. This is the only
  projection tool in this list I would rate L2: the audience sees light, not a screen.
- Fake mirrors, video delay, live/recorded blending: established stage methods (Marco Tempest
  now foregrounds drone swarms, https://www.marcotempest.com/ ; Jamie Allan and Zach King are
  agent 3's). AR glasses on spectators: weak, because everyone knows glasses can show anything.
- Independent "shadows": a projector behind or above adds a dark shape (a projected shadow is
  simply an unlit region inside a lit field, so it needs the projector to be the key light). A
  depth camera or pose tracker lets the false shadow follow the performer and then diverge.
  Works at 30 to 60 fps because shadows are soft; the tell is the projector's black level and a
  second, real shadow from room light, so the room must be dark.
- Fake window or mirror: a display behind a two-way mirror, or a camera-fed "mirror" with a
  delay or edit. Modern capture-to-display latency of about 50 to 100 ms (unverified) is
  noticeable in a mirror when someone waves; parallax is wrong for every viewer but one. Best
  for a glance, not for study.
- Video delay loops: a "live" camera relay that is in fact delayed or pre-recorded remains a
  strong stage principle and is now a few lines in OBS or TouchDesigner; the screen is openly
  part of the staging, so it only suits stage contexts.
- Pepper's ghost and telepresence: optics belong to agent 5; the software contribution is
  real-time keying and depth-matched rendering.

### E. Computer vision as assistant (brief; agent 10 owns sensing)

- Hand tracking: MediaPipe gives 21 3D landmarks per hand in about 17 ms on a Pixel 6 CPU
  (https://developers.google.com/edge/mediapipe/solutions/vision/hand_landmarker ). A finger
  snap, a count on the fingers, or a pointing direction becomes an invisible cue with no remote
  in the hand.
- Tiny vision on a $10 to $20 board: ESP-WHO on ESP32-S3-EYE and ESP32-P4 does face detection and
  recognition, pedestrian detection and QR decoding (https://github.com/espressif/esp-who ).
- Card recognition from an overhead or edge camera, handwriting OCR of a spectator's pad, and
  tracking a shell game or Rubik's cube are all standard fine-tuning jobs in 2026 (unverified in
  detail). The software point is what happens next: see F6.
- Handwriting and drawing from an overhead camera: vision-language models read a word or
  identify a sketch in about 1 s in the cloud; lighting, glare from glossy pads and the writer's
  hand occluding the page are the failure modes. A near-infrared camera and lamp remove the
  dependence on stage lighting (agent 10).
- Gaze: webcam gaze estimation is accurate to a few degrees (unverified), enough to tell which
  of four or five well-separated objects someone looked at longest from about 1 m, not which
  card in a spread. Fragile with glasses and head turns. Treat as a probability input to outs.
- Shell game and cup tracking: multi-object tracking at 30 fps follows cups a human loses; it
  lets the performer "fail" honestly and still know. Rubik's cube: six face views give the
  state; a solver gives a 20-move solution instantly, useful for cube-matching effects.
- Depth cameras give body pose and table occupancy regardless of lighting, at the cost of an
  IR projector that phone cameras can sometimes see.

### F. Mathematics, search and optimisation as method

**F1. Classical structures** (foundations; Diaconis and Graham, *Magical Mathematics*, 2011).
- de Bruijn sequences: a cyclic sequence over k symbols in which every window of length n appears
  exactly once, k^n long; the same idea is used for rotary position sensing
  (https://en.wikipedia.org/wiki/De_Bruijn_sequence ). In magic: five consecutive colours
  identify a position in 32 cards; six cover 52.
- Gilbreath principle: one riffle after a reversed deal preserves block structure; the "ultimate"
  form says the top j cards stay distinct modulo j for every j
  (https://en.wikipedia.org/wiki/Gilbreath_shuffle ). This is the model of a shuffle that looks
  fair but is constrained.
- Kruskal count: two walkers on a random sequence, each stepping by the value they land on,
  usually merge; for 52 cards Wikipedia cites above 90% (classic analyses give about 85%
  depending on court-card values) (https://en.wikipedia.org/wiki/Kruskal_count ; Lagarias, Rains,
  Vanderbei 2001, arXiv math/0110143).
- Fitch Cheney five-card trick and its 124-card bound, Hamming-code "one lie allowed" number
  cards, on-the-fly magic squares, faro group theory (all unverified here; standard literature).
  In brief: Cheney's trick has an assistant choose which of five cards to hide and order the
  other four to encode it (first published 1950; the same scheme works up to a 124-card deck,
  Kleber 2002). Hamming(7,4) cards let a performer identify a number from seven yes/no answers
  even if one answer is a lie, and say which. Eight perfect out-faros restore a 52-card deck, and
  in/out faro sequences move the top card to any position by its binary expansion. A magic square
  for any named total above about 21 is a four-line mental algorithm.
- Computation aids built on these: memorised-deck arithmetic (position of any card, cut needed
  for any-card-at-any-number), day-of-week for any date, and stack-to-stack transitions by a
  planned sequence of faros and cuts are all trivial for software and can be cued to the
  performer; the mathematics also gives the error-tolerant codes agent 10 needs for marking.
- Perfect-hash book tests: choose a hash from (page, line) to a short code so that a normal
  book's words at the forced positions are all distinguishable; this indexes an unprepared,
  real, purchasable book and is a pure search problem.

**F2. Computer-discovered tricks.** Williams and McOwan (QMUL), "Magic in the machine", Frontiers
in Psychology 2014: a genetic algorithm (NSGA-II) designed a geometric-vanish jigsaw around
measured perceptual thresholds; simulated annealing found a cyclic deck order identified with
fewer questions than a published human design and placed likeable cards where people pick them.
The jigsaw sold out two runs of a London magic shop
(https://www.frontiersin.org/articles/10.3389/fpsyg.2014.01283/full ). A 2017 follow-up mined
web text with word2vec to find strong word-picture associations; it worked for 128 of 143 people
(https://spectrum.ieee.org/ai-helps-magicians-perform-mind-reading-tricks ).
- What 2026 adds: SAT/ILP solvers, cheap brute force, and LLMs that can write the constraint
  model. Problems that are now an evening's work: stacks that satisfy several independent tricks
  at once; stacks that keep an identifying property after one genuine riffle; minimal-depth
  progressive anagram trees over any word list (a decision-tree optimisation); grid or clock
  "walk" forces where every legal path ends on one cell; spelling forces for the specific
  names of the people who will be in the room; equivoque scripts enumerated so every branch reads
  naturally.
- Accessibility: a laptop. Performance uses no electronics. This is L3 by construction.

**F3. Brute-force outs and indexing.** Per-card custom decks cost about $17 for one deck, every
face and back individually printable (https://www.makeplayingcards.com/design/custom-blank-card.html ).
Single-copy paperbacks cost a few dollars (Lulu; exact price not confirmed,
https://www.lulu.com/pricing ). A pen plotter writes a few hundred real-ink predictions overnight.
Computation generates the artefacts, guarantees uniqueness, and computes the index so the right
one is reachable in one move.

**F4. Models of human choice.** Aaronson's oracle predicts the next of two keys from the last
five presses and is right about 70% of the time, 70 to 80% for most students
(https://github.com/elsehow/aaronson-oracle ). Quick, Draw! has 50 million drawings in 345
categories with stroke order, timing and country (CC BY 4.0,
https://github.com/googlecreativelab/quickdraw-dataset ). Known folk regularities (7 from 1 to 10,
37 from 1 to 100, ace of spades and queen of hearts as most-named cards: Olson, Amlani and
Rensink 2012) are unverified here and should be re-measured on your own audiences. Hit rates in
this area are 25 to 70%, so it must always be paired with outs.

**F5. Simulation and computational design of gimmicks.** Spin-It (Bächer, Whiting,
Sorkine-Hornung, Bickel, SIGGRAPH 2014) optimises hidden interior voids so an arbitrary 3D-printed
shape spins stably about a chosen axis
(https://la.disneyresearch.com/publication/spin-it-optimizing-moment-of-inertia-for-spinnable-objects/ ).
The same idea gives objects that balance where they should not, dice with a designed bias, and
tops that always stop pointing one way, all with a solid-looking exterior. For calibration of
expectations: a real coin lands same-side-up 50.8% of the time over 350,757 flips (Bartoš et al.
2023, https://arxiv.org/abs/2310.04153 ), so physics alone gives nothing; the gimmick must.

**F6. Real-time decision support.** Once the full state is known (deck order from a camera or
marked deck; choices so far), a solver can search in milliseconds for the strongest outcome
reachable by natural actions: a cut depth, whose name to spell, which pile to deal. This turns a
genuinely shuffled deck into raw material for "jazz" magic. Output is one short cue to the
performer (agent 10 covers the channel).

### G. Data, records and "proof"

- **Hash commitments with outs.** Stevens, Lenstra and de Weger published an MD5 hash in 2007 as
  a "prediction" of the 2008 US election, backed by twelve PDFs with the same hash, one per
  candidate; a chosen-prefix collision took under two days on a PlayStation 3
  (https://marc-stevens.nl/research/hashclash/Nostradamus/ ). Today: FastColl takes seconds,
  UniColl 7 to 40 minutes, chosen-prefix about 72 core-hours, and precomputed tricks make two
  different-looking PDFs, PNGs, JPGs or MP4s with one MD5 instantly
  (https://github.com/corkami/collisions ). SHA-1: the 2017 SHAttered pair cost about 6,500
  CPU-years (https://shattered.io/ ), but its prefix can be reused to make same-SHA-1 PDFs with
  different embedded JPEGs instantly. SHA-256: no. Chameleon hashes give the committer a trapdoor
  for collisions by design (Krawczyk and Rabin, https://eprint.iacr.org/1998/010 ). Blockchain
  timestamps (https://opentimestamps.org/ , free) honestly prove a file existed, but say nothing
  about how many other files you also stamped.
- **Editable or schedulable records.** Git commit dates are whatever the author sets; DNS TXT
  records keep no public history; a QR code can redirect anywhere later; many scheduled or
  deleted social posts amount to multiple outs. These deceive third parties and platforms beyond
  the room and can breach platform terms. Keep such "proofs" inside the frame of the show and say
  afterwards that it was a trick.
- **Fabricated artefacts.** Image and text models can produce a convincing "1970s snapshot",
  "old newspaper page" or "telegram". As invented theatrical props this is fine. It becomes
  forgery or third-party deception when it copies a real masthead, official seal, ID, currency or
  a real person's likeness or handwriting, or when it leaves the venue presented as genuine.
- **Personalisation from public information.** Technically trivial, ethically the same as hot
  reading. Use only what the booker or the person supplied for the purpose.
- **Search-engine and Wikipedia forces.** Existing apps do this on the spectator's phone
  (agent 2). They are screen magic by definition.
- **Mailed and sealed predictions with dynamic content.** A parcel posted days ahead with a
  genuine postmark, containing NFC e-paper (updated through the cardboard at the moment of
  opening) or a tiny thermal or label printer that prints on a wake signal, separates the
  apparent time of the prediction from the real one by days. The postmark is honest; only the
  contents are late. Battery life is the constraint for anything active: a sleeping ESP32 with a
  wake receiver lasts weeks on a coin cell (unverified).
- **Time-stamped media.** File metadata, EXIF dates and "sent" times are all editable and prove
  nothing; audiences increasingly know this.

### H. Show control

QLab (macOS; sound, video, light and show-control cues, version 5.6,
https://qlab.app/ ) is the standard for cue stacks; WLED accepts Art-Net, sACN, MQTT and JSON on a
$5 ESP32; ggwave sends 8 to 16 bytes/s over sound including a 15 kHz near-ultrasonic mode on ESP32
and phones (https://github.com/ggerganov/ggwave ). Solo performers fire cues by foot switch, a
spoken trigger word (B1), a tracked gesture (E), or elapsed time. Whole-room effects (every lamp
dims, the sound moves around the audience, the house music changes to the named song) are L1 as
spectacle but valuable as cover: a lighting or sound cue fired by the recogniser hides motor
noise and draws eyes away at exactly the moment a device acts. QLab 5.5 added object-based
spatial audio, so a voice can be placed at a spectator's shoulder with an ordinary speaker ring.

### I. Keeping "a computer did it" out of the audience's mind

Principles that recur across the catalog:
1. **Pre-electronic output.** Ink, film, sand, clock hands, burn marks and typed characters are
   not associated with computers. Pixels, LEDs and speakers are.
2. **No visible input.** Ambient recognition, gesture cues and fixed timing remove the tell of a
   performer touching a device. The moment of input should coincide with a natural recap.
3. **Separate cause and effect in time.** Slow devices (plotter, sand table, film) should finish
   before the audience believes the choice was final, or long after attention has moved.
4. **Custody.** The object that changes should be in a spectator's hands or in plain view the
   whole time, and should be inert and ordinary afterwards (paper, film, a batteryless tag).
5. **Offer a wrong theory.** A visible pencil, a conspicuous handling of the envelope or some
   sleight of hand gives suspicion somewhere harmless to go. The technology cancels "he switched
   it"; the handling cancels "it's electronic".
6. **Move the computation offstage.** A method computed last week leaves nothing to detect.
7. **Mask actuation.** Applause, music stings, a clattering typewriter or the venue's air
   handling cover motors and relays.

---

## 3. Capability primitives

1. *Now possible:* know a spoken card, number or time within 0.25 to 0.8 s, offline, from a
   hidden $15 to $100 device. *Because:* Moonshine, Vosk, ESP-SR. *Before:* peeks, pumping,
   confederates, or typing on a phone. *Primitives:* know.
2. *Now possible:* map any free spoken answer to the nearest of about 500 prepared outs in under
   1 s. *Because:* ASR plus embeddings or a small LLM. *Before:* forces, or a narrow question.
   *Primitives:* know, control choice.
3. *Now possible:* one printed sheet holding 2 to 4 full pictures, selected by rotation, distance,
   light colour or overlay. *Because:* multi-view diffusion. *Before:* an index of separate
   envelopes or crude ambigrams. *Primitives:* conceal, swap (without swapping), prove ordinariness.
4. *Now possible:* a jigsaw whose same pieces assemble into two different pictures. *Because:*
   Visual Anagrams jigsaw view. *Before:* geometric vanishes only. *Primitives:* transform.
5. *Now possible:* a solid object whose mirror image or side view is a second chosen picture,
   designed in about 76 s. *Because:* Mirror Illusion Art, Illusion3D. *Before:* hand-sculpted
   shadow art. *Primitives:* conceal, prove ordinariness.
6. *Now possible:* a 200-page book of readable, all-different prose in which every page obeys a
   hidden rule. *Because:* LLM text plus a typesetting constraint solver plus one-off printing.
   *Before:* book tests with repeated pages or word lists. *Primitives:* control choice, prove
   ordinariness.
7. *Now possible:* a deck order that satisfies several independent tricks and survives a real
   riffle, found in minutes. *Because:* SAT/ILP and annealing. *Before:* decades of hand design.
   *Primitives:* control chance, know.
8. *Now possible:* the provably shallowest anagram or question tree for any outcome list.
   *Because:* decision-tree optimisation. *Before:* hand-built trees for fixed lists.
   *Primitives:* know.
9. *Now possible:* 300 real-ink "handwritten" predictions or drawings overnight for the cost of
   paper. *Because:* pen plotters and stroke data. *Before:* nail writers, a few pre-written
   outs. *Primitives:* duplicate, delay.
10. *Now possible:* 52 or more different custom-printed cards, each one of a kind, for about
    $17 a deck. *Because:* per-card digital printing. *Before:* gaff cards from a fixed
    catalogue. *Primitives:* duplicate, conceal.
11. *Now possible:* change printed-looking content inside a sealed container in about 2 s and
    leave no power source behind. *Because:* NFC-powered e-paper. *Before:* billet switches,
    carbon impressions. *Primitives:* transform, delay, erase the evidence.
12. *Now possible:* predict a person's next binary choice at about 70%, and know when the
    prediction is strong. *Because:* n-gram predictors. *Before:* intuition and psychological
    forces. *Primitives:* control choice.
13. *Now possible:* predict how a person will draw a named thing (orientation, stroke order) from
    50 million examples. *Because:* Quick, Draw! *Before:* guesswork. *Primitives:* control choice.
14. *Now possible:* a published cryptographic fingerprint that matches any of 2 to 12 documents.
    *Because:* MD5 collision tooling. *Before:* a sealed envelope held by a trusted person.
    *Primitives:* delay, swap.
15. *Now possible:* trigger any cue from a finger gesture seen by a camera, about 17 ms.
    *Because:* MediaPipe. *Before:* thumb remotes, foot switches, offstage operators.
    *Primitives:* tell.
16. *Now possible:* given a genuinely shuffled, known deck, find the best available miracle in
    milliseconds. *Because:* search. *Before:* memorised stacks that cannot be shuffled.
    *Primitives:* know, control chance.
17. *Now possible:* a real chemical photograph of anything, about 15 s after it is decided.
    *Because:* Bluetooth instant-film printers driven from Python. *Before:* pre-shot Polaroid
    outs. *Primitives:* transform, delay.
18. *Now possible:* a printed object with a hidden interior that spins, balances or rolls in a
    designed way. *Because:* mass-distribution optimisation plus 3D printing. *Before:* lead
    weights and trial and error. *Primitives:* control chance, prove ordinariness.
19. *Now possible:* typed, plotted or printed text appearing with no operator, from a $10
    microcontroller. *Because:* hackable typewriters, plotters and printers. *Before:* hidden
    assistants, threads. *Primitives:* move, tell.
20. *Now possible:* a crisp image thrown on any nearby surface from a matchbox-sized source with
    no focusing. *Because:* laser-scanned pico projection. *Before:* slide gobos. *Primitives:*
    transform.
21. *Now possible:* a prop personalised to one audience (names, dates, in-jokes woven into a
    printed puzzle, programme or book) in one night. *Because:* LLMs plus print on demand.
    *Before:* weeks and a print run. *Primitives:* prove ordinariness, control choice.
22. *Now possible:* an invented period artefact (photo, clipping, letter) in an hour.
    *Because:* image and text models. *Before:* a prop-maker. *Primitives:* prove ordinariness.
23. *Now possible:* sub-second, silent machine-to-machine cueing through the room's own sound
    system at 15 kHz. *Because:* ggwave. *Before:* radio remotes. *Primitives:* tell.
24. *Now possible:* a wooden or fabric surface that shows nothing until lit from behind.
    *Because:* thin veneers over bright matrices. *Before:* smoked glass. *Primitives:* conceal.

---

## 4. Effect concepts

**1. The computed novel (L3).**
*Effect:* a spectator takes a worn paperback from a stack, opens anywhere, reads silently; the
performer names the word, then the sentence. Every page is different and it reads as a real book.
*Method:* the book is written for the trick. An LLM writes continuous pastiche prose under
constraints, and a typesetting script fixes page breaks, so that the first long word on each page
comes from a list of 20 to 30 words arranged in a solver-minimised progressive anagram tree (about
4 letter guesses, at most one "no"). A second layer: the page number hashes to the word by a rule
the performer can do mentally (for example digit sum modulo list position), so if the page number
is glimpsed or named, no fishing is needed.
*BOM:* laptop, one-off paperback printing (a few dollars; unverified), tea and sandpaper for
ageing. *Difficulty:* software moderate, no hardware. *Risks:* LLM prose that reads oddly near
the constrained words; fix by constraining only the first line. *Novelty:* book tests with
all-different pages exist commercially (unverified); a generated, re-themable, personalised one
with a provably minimal tree appears new.

**2. Semantic outs: "draw anything" (L3).**
*Effect:* a spectator thinks of any simple object and says it aloud only at the end. A folded
ballpoint sketch, in a wallet on the table from the start, is that object.
*Method:* a pen plotter prepares about 300 real-ink sketches on identical slips, covering the
most-drawn objects, drawn the way people most often draw them (orientation and proportions from
Quick, Draw! strokes). They sit in an index (classic pocket index, or a thin motorised carousel:
agent 13). A hidden recogniser hears the word; an embedding lookup picks the nearest sketch and
cues the pocket number by haptic pulses. Near misses are theatrically acceptable ("a cottage" for
"my gran's house").
*BOM:* servo plotter (EUR 15) or borrowed AxiDraw-class plotter, Pi 5 ($80), microphone, a
vibration motor. Under $200. *Difficulty:* moderate. *Risks:* coverage; measure it by asking 100
people first. Honest estimate: 300 outs cover perhaps 70 to 85% of answers (unverified), so
restrict the category ("an animal", "something in a kitchen") to push that up.
*Novelty:* indexes are old; the semantic mapping and plotted real-ink outs are new.

**3. Two strangers, one picture (L2).**
*Effect:* at the start two spectators each receive a framed abstract print on clear film to hold.
After a free choice among four options, they stack their frames and the abstract shapes resolve
into a detailed picture of the choice.
*Method:* Diffusion Illusions rotation overlay: two transparencies give four different pictures
at the four relative rotations. The frames are square and unmarked; the performer controls the
relative rotation when "helping" to align them. Nothing is switched and both sheets can be kept.
*BOM:* Colab time, inkjet transparency film, two acrylic frames. Under $30. *Difficulty:* easy.
*Risks:* overlay contrast depends on print density (test prints needed); four outs only, so the
choice must be forced to four or framed as four. *Novelty:* high as a prediction format.

**4. The puzzle that changes its mind (L3, speculative).**
*Effect:* a small boxed jigsaw is assembled by spectators early in the show and shows a wrong
prediction. Later, after the pieces are tipped back into the box and shaken, a different
spectator assembles it and it shows the right one. Same pieces, nothing added.
*Method:* a Visual Anagrams jigsaw image: the same 16 or so pieces assemble into picture A or
picture B. People assemble by picture, so telling them what they are making steers the layout.
Print on card and laser-cut, or order a custom photo puzzle with the authors' piece template.
*BOM:* GPU time, printed card, laser cutting ($20 to $40). *Difficulty:* moderate; the cut must
match the template. *Risks:* 256 px native resolution; pieces fit in several places, so assembly
may wander. *Novelty:* I found no magic use.

**5. The listener and the envelope (L2).**
*Effect:* a sealed, signed envelope is given to a spectator before anything is chosen. A card,
word or date is decided with no force. The spectator opens the envelope: the printed ticket
inside names it. The performer never writes, types, or touches a phone.
*Method:* the "ticket" is a batteryless NFC e-paper panel laminated into a luggage tag, museum
label or boarding-pass wallet. A hidden recogniser (B1) hears the performer's recap. The writer
coil lives in a close-up pad, clipboard or book that the envelope rests on for 3 to 5 s. After
that there is no power anywhere in the envelope.
*BOM:* NFC e-paper module (about $20 to $30, unverified), ST25R3911B-class writer board, Pi or
ESP32-S3, pad. $80 to $150. *Difficulty:* moderate to hard (thinning the module; coil range).
*Risks:* e-ink looks like e-ink within 30 cm, so present it as a parlor piece and frame the
insert as a "label"; the stock module is 12 mm thick and must be re-housed; the object must be
still during refresh. *Novelty:* e-ink prediction props exist (agent 2); the fully hands-off,
batteryless-in-custody version may not.

**6. The clock agrees (L2).**
*Effect:* someone names the time of an important moment in their life. The ordinary wall clock
that has been telling the right time all evening now shows it.
*Method:* a dial with two independently driven concentric hands (dual-shaft automotive gauge
steppers as used in hobby "clock of clocks" builds; unverified part) behaves as an honest clock
until the recogniser hears a time; the hands then slew silently in about 1 s during a moment of
misdirection. A stock quartz movement cannot do this: it steps once per pulse in one direction,
so a 6-hour move is 21,600 steps.
*BOM:* stepper, ESP32, Pi or ESP32-S3 listener, clock case. $60 to $120. *Difficulty:* moderate.
*Risks:* someone watching the clock at the wrong moment. *Novelty:* stopped-watch effects are
common; a room clock driven by overheard speech less so.

**7. Confidence-gated "free will" test (L3).**
*Effect:* a spectator hides a coin in either hand again and again; the performer loses and wins
casually, then announces that the *next* one is written down. It is right.
*Method:* each result is logged by a toe switch or by camera. An n-gram predictor tracks the
spectator; the performer gets a cue only when the model's confidence for the next choice passes
a threshold. The written commitment is made only then. A two-way out covers the residual miss.
*BOM:* ESP32, toe switch, vibration motor. $20. *Difficulty:* easy hardware; the work is testing
thresholds on real people. *Risks:* baseline accuracy is about 70%; gated accuracy is unknown
until measured, and some people are unpredictable. *Novelty:* the gating idea appears new in
magic.

**8. Jazz deck (L3).**
*Effect:* a borrowed-looking deck is really shuffled by spectators. The performer then does a
string of impossible locations and coincidences that differ every show.
*Method:* agent 10's hardware supplies the full order. A solver searches for the strongest
outcomes reachable with one cut and a natural deal or spell: a spectator's name spelling to a
named card, four of a kind at chosen positions, a poker deal. The performer hears one short
instruction. Sleight of hand covers the gaps.
*BOM:* whatever reads the deck, plus a Pi. *Difficulty:* software moderate. *Risks:* cue
complexity; restrict to five or six move types. *Novelty:* deck-reading apps report positions
(agent 2); opportunistic search over effects is, as far as I know, unbuilt.

**9. Solver-built table (L3).**
*Effect:* the audience's own objects are laid out; spectators make free moves ("move as many
steps as letters in your name", "remove any one you are not on"); all end on the one object
predicted in ink before they arrived.
*Method:* for the actual set of objects and names present, a search tool finds a layout and
instruction script for which every legal path converges (a designed Kruskal-type or parity
force), and rejects scripts that look contrived. The performer needs only the layout.
*BOM:* laptop or phone used offstage. *Difficulty:* easy to moderate. *Risks:* instructions
people mis-follow; the tool should prefer robust scripts. *Novelty:* the principle is classic; a
per-audience generator is new.

**10. The fingerprint in the programme (L2, niche).**
*Effect:* for a technical audience: a 32-character fingerprint printed in the event programme
weeks ago matches a document that names tonight's outcome.
*Method:* multi-way MD5 collisions (the Nostradamus construction) or instant colliding PDF pairs.
*BOM:* a desktop for hours to days. *Risks:* any cryptographer will say "MD5" at once, which is
why the 2007 authors used it as a warning. Frame as a puzzle and reveal that it is one.
*Novelty:* demonstrated by cryptographers, not used in magic to my knowledge.

**11. Typewriter medium (L1/L2).**
*Effect:* an old electric typewriter on a side table types a line about the spectator's choice.
*Method:* option-bus hack plus the listener. Period-correct noise is the misdirection for the
electronics. *BOM:* used Wheelwriter-class machine ($50 to $150, unverified), Arduino Nano.
*Risks:* reads as a machine doing a machine thing; strongest as an unattended installation.

Levels: concepts 1, 2, 4, 7, 8, 9 are L3; 3, 5, 6, 10 are L2; 11 is L1/L2.

---

## 5. Dead ends and overhyped items

- **LLM as the visible mind-reader.** The audience's model of an LLM is "it knows everything",
  so nothing it does is impossible. Hidden use only.
- **Live image generation, deepfake video and AI songs as the reveal.** Screen or speaker bound,
  instantly attributed to AI, and dated within a year.
- **Whisper-class large models on a Pi.** Seconds of lag; use streaming or fixed-vocabulary
  recognisers.
- **Shelf-label e-paper for timed reveals.** A roughly 40 s polling interval is fatal on stage.
- **Stock quartz clock movements for a time reveal.** One direction, one step per pulse.
- **Hobbyist dynamic projection mapping on fast props.** 30 to 50 ms lag is visible.
- **Coin-flip physics.** A 0.8 percentage point bias is not a method.
- **Adversarial patches and "images that sound".** They need a machine in view to mean anything.
- **Live laser engraving near an audience.** Smoke, smell, fan noise and a Class 4 beam. Pre-burn
  the outs instead.
- **SHA-256 or blockchain "prediction proofs" with a single honest file.** They prove only that
  you can pre-commit; the method still has to come from somewhere else.
- **AR glasses on spectators.** Everyone knows a headset can show anything.
- **Scheduled or deleted social posts as predictions.** Works, but it deceives the public record
  and third parties, and platforms mark edits.

## 6. Safety, legal and ethical flags

- Diode laser engravers are Class 4: eye injury from reflections, fire, toxic fumes from leather
  and plastics. Enclose and vent; never run near an audience. Laser pico projectors: never aim at
  faces.
- Hidden microphones: process on-device, keep nothing, and check local recording-consent law.
- Voice cloning and face swapping of real people need consent; insightface models bundled with
  face-swap tools are non-commercial.
- Fabricated documents: invented props only; no real mastheads, seals, IDs, currency or
  signatures; do not let them circulate as genuine.
- Do not present cold reading, personalisation or prediction as real psychic or forecasting
  ability. The same multiple-outs structure is the basis of stock-tip and betting scams.

## 7. Open leads

- Measure real coverage curves: how many outs cover what fraction of answers for "draw anything",
  "name an animal", "a place you love" (Quick, Draw! plus a small live survey).
- Build and benchmark a fixed-vocabulary listener in a noisy room; I found no published
  accuracy figures for 52-card vocabularies at 3 to 5 m.
- Whether a bare e-paper panel with an NFC harvesting chip can be made under 1.5 mm thick.
- Whether Visual Anagrams jigsaws survive physical cutting and human assembly without guidance.
- Search for existing computed book tests, progressive-anagram generators, and solver-designed
  stacks in the magic trade press (not reachable in this session).
- Dual-shaft gauge steppers for silent clock hands: part numbers, noise, slew rate.
- Gilbreath-robust multi-purpose stacks by SAT: is there a 52-card order that supports three
  named effects after one real riffle?
- LLMs as a cheap proxy for human choice distributions (they reproduce human number biases;
  unverified).
- Instax, Zink and dye-sub timings and whether development can be made to look like "the image
  arriving" (agent 5).

## 8. Sources

Opened unless noted "seen in search results" or "not openable".

- https://arxiv.org/abs/2311.17919 - Visual Anagrams paper (CVPR 2024); seen in search results
- https://dangeng.github.io/visual_anagrams - Visual Anagrams project page, views and printable jigsaw
- https://github.com/dangeng/visual_anagrams - code, DeepFloyd IF, Colab notebooks, MIT
- https://replicate.com/chigozienri/visual-anagrams - hosted Visual Anagrams; seen in search results
- https://tmzh.github.io/post/2024-01-22-running-deep-floyd-with-limited-memory - DeepFloyd memory notes; seen in search results
- https://arxiv.org/abs/2404.11615 - Factorized Diffusion (ECCV 2024); seen in search results
- https://dangeng.github.io/factorized_diffusion - project page; seen in search results
- https://en.wikipedia.org/wiki/Hybrid_image - hybrid images background
- https://arxiv.org/abs/2312.03817 - Diffusion Illusions paper (SIGGRAPH 2024); seen in search results
- https://diffusionillusions.com/ - illusion types, printable PDFs, Colab links
- https://github.com/RyannDaGreat/Diffusion-Illusions - notebooks
- https://huggingface.co/monster-labs/control_v1p_sd15_qrcode_monster - QR Monster ControlNet model card
- https://huggingface.co/monster-labs/control_v1p_sdxl_qrcode_monster - SDXL version; seen in search results
- https://huggingface.co/spaces/AP123/IllusionDiffusion/raw/main/app.py - IllusionDiffusion app; seen in search results
- https://antfu.me/posts/ai-qrcode-101 - practical QR-art guide; seen in search results
- https://arxiv.org/abs/2412.09625 and https://3d-multiview-illusion.github.io - Illusion3D; seen in search results
- https://arxiv.org/abs/2607.02015 and https://github.com/zxp555/automia - Mirror Illusion Art (CVPR 2026); seen in search results
- https://huggingface.co/papers/2606.20563.md - JanusMesh; seen in search results
- https://arxiv.org/abs/2405.12221 and https://ificl.github.io/images-that-sound - Images that Sound; seen in search results
- https://arxiv.org/abs/1712.09665 - Adversarial Patch
- https://github.com/espressif/esp-sr - offline wake word and 300-phrase command recognition
- https://alphacephei.com/vosk/ - Vosk offline ASR
- https://github.com/k2-fsa/sherpa-onnx - streaming ASR, keyword spotting on embedded boards
- https://github.com/moonshine-ai/moonshine - Moonshine streaming ASR
- https://moonshine-voice.readthedocs.io/en/latest/moonshine-vs-whisper/ - Pi 5 latency table; seen in search results
- https://github.com/ggml-org/whisper.cpp - model sizes, streaming example
- https://arxiv.org/html/2507.10860v1 - WhisperKit on-device ASR paper; seen in search results
- https://www.raspberrypi.com/news/introducing-the-raspberry-pi-ai-hat-plus-2-generative-ai-on-raspberry-pi-5/ - $130 local LLM HAT
- https://github.com/rhasspy/piper - local TTS (archived Oct 2025, moved to OHF-Voice/piper1-gpl)
- https://github.com/w-okada/voice-changer - real-time voice conversion client
- https://github.com/hacksider/Deep-Live-Cam - real-time face swap and its consent notes
- https://github.com/cumulo-autumn/StreamDiffusion - real-time image generation benchmarks
- https://elevenlabs.io/docs/overview/capabilities/music - music generation API
- https://www.adafruit.com/product/597 - thermal receipt printer specifications and price
- https://www.brachiograph.art/ - EUR 15 servo plotter
- https://bantamtools.com/collections/bantam-tools-nextdraw - pen plotter prices
- https://github.com/javl/InstaxBLE - Python control of Instax Link printers
- https://github.com/tuanchris/dune-weaver - DIY sand table
- https://sisyphus-industries.com/ - commercial sand tables
- https://github.com/scottbez1/splitflap - open-source split-flap display
- https://www.vestaboard.com/ - commercial split-flap
- https://flipdots.com/en/home/ - flip-dot displays
- https://www.waveshare.com/wiki/2.9inch_NFC-Powered_e-Paper - batteryless NFC e-paper specifications
- https://github.com/OpenEPaperLink/OpenEPaperLink - shelf-label firmware and latency
- https://research.google/blog/hidden-interfaces-for-ambient-computing/ - displays through wood and fabric (CHI 2022)
- https://en.wikipedia.org/wiki/Lavet-type_stepping_motor - quartz clock motor drive
- https://github.com/tofergregg/IBM-Wheelwriter-Hack - typewriter as printer
- https://www.arvindsanjeev.com/ghostwriter.html - GPT typewriter
- http://ishikawa-vision.org/vision/DPM/index-e.html - 1,000 fps dynamic projection mapping
- https://github.com/microsoft/RoomAliveToolkit - projector-camera calibration
- https://en.wikipedia.org/wiki/Handheld_projector - laser pico projectors
- https://www.marcotempest.com/ - Marco Tempest
- https://developers.google.com/edge/mediapipe/solutions/vision/hand_landmarker - hand tracking latency
- https://github.com/espressif/esp-who - vision on ESP32-S3/P4
- https://en.wikipedia.org/wiki/De_Bruijn_sequence - de Bruijn sequences
- https://en.wikipedia.org/wiki/Gilbreath_shuffle - Gilbreath principle
- https://en.wikipedia.org/wiki/Kruskal_count - Kruskal count
- https://www.frontiersin.org/articles/10.3389/fpsyg.2014.01283/full - Williams and McOwan 2014
- https://spectrum.ieee.org/ai-helps-magicians-perform-mind-reading-tricks - 2017 QMUL association trick
- https://www.qmul.ac.uk/news/latest-news/2014/se/magic-tricks-created-using-artificial-intelligence-for-the-first-time.html - QMUL press release; seen in search results
- https://www.makeplayingcards.com/design/custom-blank-card.html - per-card custom decks
- https://www.lulu.com/pricing - print-on-demand books (price not shown)
- https://github.com/elsehow/aaronson-oracle - binary-choice predictor, about 70%
- https://github.com/googlecreativelab/quickdraw-dataset - 50 million drawings
- https://arxiv.org/abs/2310.04153 - 350,757 coin flips
- https://la.disneyresearch.com/publication/spin-it-optimizing-moment-of-inertia-for-spinnable-objects/ - Spin-It
- https://marc-stevens.nl/research/hashclash/Nostradamus/ - twelve PDFs, one MD5 "prediction"
- https://github.com/corkami/collisions - hash collision tooling and timings
- https://shattered.io/ - SHA-1 collision
- https://eprint.iacr.org/1998/010 - chameleon hashing
- https://opentimestamps.org/ - blockchain timestamps
- https://qlab.app/ - show control
- https://kno.wled.ge/ - WLED
- https://github.com/ggerganov/ggwave - data over sound
- https://www.vanishingincmagic.com/magic-apps/sam/ - SAM app; seen in search results
- https://www.penguinmagic.com/p/S37976 - AI Stooge; seen in search results, not openable
