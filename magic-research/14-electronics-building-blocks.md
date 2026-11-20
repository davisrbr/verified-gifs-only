# 14. Electronic building blocks for hidden gimmicks (parts bin, late 2026)

Scope: what can be embedded in a coin, card, pen, ring, die, book, mat, shoe or sleeve, with part
numbers, sizes and prices. Sensing *methods* are agent 10's, fabrication services agent 13's,
smart-material actuators agent 7's, haptics on spectators agent 11's; they get pointers only.

**How to read the evidence marks.** The shared web-search budget for the whole project ran out
after my first 14 searches, so most checking was done by opening supplier and primary pages
directly. Marks used throughout:

- **[V]** = I opened the page in this session (November 2026) and the number comes from it.
- **[S]** = the number appeared in a search-result summary; I did not open the page.
- **(unverified)** = recalled from memory, not confirmed this session. Treat as a lead, check
  before ordering.

Prices are single-unit, as of late 2026.

---

## 1. Summary

- **The battery, not the chip, sets the size of every gimmick.** A complete Bluetooth computer is
  now 2.45 x 2.25 x 0.42 mm (nRF54L15 CSP [V]) or 1.7 x 2.0 x 0.33 mm (DA14531 WLCSP, $0.81 [V]);
  a general MCU is 1.6 x 0.86 mm (TI MSPM0C1104 [V]). The thinnest stocked LiPo is 0.4 mm but
  22 x 55 mm for 25 mAh at $15 [V]. Design the power first.
- **The most useful move is to take the battery out of the handled object entirely.** Three
  proven ways: 13.56 MHz NFC harvesting (15 mW from NTAG I2C plus [V], "up to 30 mW" from NTAG 5
  boost [V], a few mA from ST25DV [S]); cheap loosely coupled induction (Adafruit 5 V coil kit:
  LEDs light 0 to 80 mm above a 70 mm, 0.5 mm thick coil, $14.95 with ten receivers [V]); and Qi
  (40 x 29 mm receiver, 5 V 500 mA, contact range only [V]).
- **Standby is solved.** An AirTag idles at 2.3 µA, about 11 years on a CR2032 [V]. A 45 nA RTC
  (RV-3028-C7, 3.2 x 1.5 x 0.8 mm [V]) or a 35 nA power-gating timer (TPL5111 [V]) plus a 0.54 µA
  hall switch in a 1.4 x 1.1 mm package (DRV5032 [V]) lets a prop sleep for years on a 12 mm coin
  cell and act once at a set time or on a magnet pass.
- **Logic is nearly free, so it can be thrown away.** Padauk PMS150C is $0.033 [V], CH32V003 is
  $0.14 to $0.28 on LCSC [S], an addressable RGB LED 1.1 x 1.1 x 0.33 mm is $0.05 to $0.09 [S].
  A burnable or bin-able "sense and signal once" unit is well under $1 in parts; the coin cell is
  the largest cost and the only real disposal hazard.
- **Credit-card thickness (0.76 mm) holds a full computer; playing-card thickness (0.3 mm) holds
  only a passive tag.** Two-layer flex is 0.11 mm [V], wafer-level chips are 0.33 to 0.42 mm,
  the thinnest cells 0.4 to 0.5 mm, a flexible e-paper panel 0.3 mm [V]. A "thick card" (two
  cards laminated, about 0.6 mm) is the realistic smart playing card.
- **Silent actuation exists but is weak; strong actuation is loud.** Electromagnet release,
  shape-memory wire, flex-PCB coils and piezo pumps (Bartels BP7 under 50 dB, 30 x 15 x 3.8 mm,
  2 g [V]) are quiet. Solenoids (80 g at 3 mm, 1.1 A, audible click [V]), geared motors and
  servos are not. Rank by noise before force when designing for close-up.
- **RF does not come out of a solid metal coin or ring; magnetism does.** Skin depth in brass is
  about 0.035 mm at 13.56 MHz and microns at 2.4 GHz, but about 4 mm at 1 kHz (my calculation,
  section 2.6). Metal props should talk with magnets, hall sensors and low-frequency coils, or
  have a non-metal window, as AirTag and Oura do.
- **Existence proofs are everywhere and mostly open.** Pixels dice put an nRF52, LEDs, 60 mAh
  cell, 10 mm charge coil and accelerometer on a folded flex in a 16 mm die [V]; the Oura Ring 5
  has a 10.2 to 10.5 mAh cell on a flex in titanium [S]; a $20 Colmi R02 ring is a ready-made
  accelerometer-plus-BLE finger controller with an open protocol [V]; Chipolo Card is a 2.4 mm
  tracker with a two-year cell [V].
- **Good prototyping paths:** Seeed XIAO boards (21 x 17.8 mm; ESP32-C6 $5.20 [V], nRF54L15
  $9.90 [S], ESP32-S3 Sense with camera and mic $18.90 [V]), then shrink to an 8 x 8 x 1 mm SiP
  (Insight SiP ISP1507 [V]) or 7.8 x 8.8 x 1.3 mm module (Fanstel BC832, $5.74 at 1k [V]), then
  to bare WLCSP on flex only if needed.
- **Best new architectures from this slice:** batteryless sealed props powered from the mat;
  time-delayed props that act days after the performer has left; disposable instrumented
  environment objects; and one-shot hold-and-release pellets under half a gram.

---

## 2. Catalog (by function)

### 2.1 Brains and radios

**Capability:** a radio-linked computer that fits anywhere a coin cell fits, for $1 to $10, and a
logic-only controller for 3 to 30 cents.

| Part | Size (mm) | Price | Notes | Design-in |
|---|---|---|---|---|
| Seeed XIAO ESP32-C6 | 21 x 17.8 | $5.20 [V] | Wi-Fi 6, BLE 5, 802.15.4; LiPo charger on board; 15 µA deep sleep [V] | Trivial (USB-C, Arduino, ESPHome) |
| Seeed XIAO nRF54L15 / Sense | 21 x 17.8 | $9.90 / $15.99 [S] | BLE 6, Thread, Zigbee; Sense adds IMU and mic | Easy (Zephyr/nRF Connect SDK; steeper than Arduino) |
| Seeed XIAO ESP32-S3 Sense | 21 x 17.8 (15 tall with camera board) | $18.90 [V] | OV5640/OV3660 camera, mic, SD slot | Easy |
| ESP32-C6-MINI-1 / -1U | 13.2 x 16.6 x 2.4 / 13.2 x 12.5 x 2.4 [V] | about $2 to $3 (unverified) | C3-MINI-1 and H2-MINI-1 share the outline (unverified) | Moderate (own PCB, reflow) |
| ESP32-C3 "SuperMini" boards | about 22.5 x 18 | $2 to $3 AliExpress (unverified) | Cheapest Wi-Fi/BLE/ESP-NOW board | Trivial |
| Raytac MDBT42V (nRF52832) | 6.4 x 8.4 x 1.75 | EUR 4.45 DigiKey [S] | Chip antenna, 20 GPIO, pre-certified | Moderate (LGA pads) |
| Fanstel BC832 (nRF52832) | 7.8 x 8.8 x 1.3 | $5.74 at 1k; BC832-p from $6.88 in 10-packs [V] | 50 m line of sight | Moderate |
| Insight SiP ISP1507 (nRF52832) | 8 x 8 x 1.0 | (not checked) | Antenna, both crystals, DC/DC in package; vendor suggests ISP2454 for new designs [V] | Moderate (fine LGA) |
| KAGA FEI ES4L15BA1 (nRF54L15) | 8.55 x 3.25 x 1.0 | (not found) | Antenna included; pen- and ring-shaped footprint [S] | Hard to buy in ones |
| Ezurio BL54L15µ | 6.3 x 7.9 x 1.75 | dev kit $80 [S] | Smallest nRF54L module with antenna per vendor [S] | Moderate |
| Murata Type 2NR (nRF54L15) | 7.4 x 7.0 x 1.0 | (not found) | [S] | Moderate |
| nRF54L15 bare chip | CSP 2.45 x 2.25 x 0.42; QFN40 5 x 5 x 0.85 [V] | about $2 to $3 (unverified) | RX 3.4 mA, TX 4.8 mA at 0 dBm, sleep 0.7 to 2.9 µA; BLE Channel Sounding ranging [V] | Hard (0.3 mm pitch, RF layout) |
| nRF52805 bare chip | WLCSP 2.48 x 2.46 [V] | about $1.5 (unverified) | Used in GoDice [S] | Hard |
| Renesas DA14531 | WLCSP 1.7 x 2.0 x 0.328; module 12.5 x 14.5 x 2.8 | $0.81 chip [V] | Runs from 1.1 V, so one silver-oxide or printed cell, no boost; TX 3.5 mA; made for sub-30 mAh cells [V] | Hard as chip, easy as module |
| RP2040 / RP2350 | QFN 7 x 7 (unverified) | about $1 (unverified) | No radio; best for USB tricks, PIO signal generation, CircuitPython | Easy on a board |
| WCH CH32V003 | QFN20 3 x 3; SOP8 | $0.14 to $0.28 LCSC [S]; "under $0.10" is a volume claim [V] | 32-bit RISC-V, 16 kB flash, 2 kB RAM, one-wire debug | Easy (open toolchain ch32fun, unverified) |
| TI MSPM0C1104 | DSBGA 1.6 x 0.861; WSON 2 x 2 [V] | about $0.16 to $0.20 at 1k (unverified) | Cortex-M0+, 16 kB flash, 12-bit ADC, shutdown 200 nA [V] | Hard in DSBGA, easy in WSON |
| Padauk PMS150C | SOP8 / SOT23-6 | $0.033 [V] | One-time programmable, 1 kword, 64 bytes RAM; fine for "wake, wait, pulse" | Moderate (odd tools) |
| ATtiny (10/85/1616) | SOT23-6 to QFN20 | $0.5 to $1.5 (unverified) | Now dearer than CH32V003; keep for existing Arduino code | Easy |
| STM32C011 / G031 WLCSP | about 1.7 x 1.4 / 1.9 x 2.1 (unverified) | about $0.5 to $1 | Mainstream tools | Hard in WLCSP |

**Radio links, by use.**

- **433/315 MHz ASK remotes** (SYN115 transmitter, SYN480R or RXB6 receiver, EV1527 learning
  key-fobs; $1 to $3 a pair, unverified). Believed to be the workhorse of commercial magic
  remotes (unverified). Simple and long-range, but unencrypted, one-way and easily jammed by any
  other fob in the room. Use only with rolling or checksummed codes of your own.
- **ESP-NOW** (Espressif's connectionless 2.4 GHz protocol; payloads to about 250 bytes,
  millisecond latency, no router; unverified from docs). The practical default for performer to
  prop links between ESP32 boards.
- **BLE**: the default for anything a phone or watch must talk to. A beacon is the cheapest
  "tell" channel. BLE Channel Sounding in nRF54L15 [V] gives distance between two of your own
  nodes without UWB.
- **Nordic proprietary 2.4 GHz** (up to 4 Mbps on nRF54L15 [V]): lowest latency for thumpers.
- **Sub-GHz LoRa** (Fanstel lists SX1262 and LR2021 modules [V]; Seeed Wio-E5 about 12 x 12 mm,
  unverified): through walls and across buildings at tens of bits per second. Useful for
  "the object acts when I text it from another city" builds.
- **Infrared** (38 kHz TSOP-class receivers under $1, unverified): line of sight, invisible,
  immune to RF congestion; a dark-red window or a thin white plastic shell passes it.
- **UWB**: Qorvo DWM3000 module is 23 x 13 x 2.9 mm, $28.34 at RFMW [S], and Qorvo states it is
  interoperable with Apple U1 and U2 [S]. Apple's own page says an accessory must implement the
  Nearby Interaction accessory protocol on an NI-enabled chipset, with specs downloadable [V].
  In practice that means your own iPhone app running a session; you cannot piggyback on Find My
  precision finding (unverified). Between two of your own DW3000 nodes you get roughly 10 cm
  ranging (unverified). Too big for a coin, fine for a deck box or book.
- **BLE beacons**: coin-cell beacon tags with an accelerometer or button cost $3 to $10 on
  AliExpress (unverified) and need no hardware work; the nRF52805 is the chip Nordic lists for
  beacons and disposable devices [V]. A beacon that changes its advertisement when moved is the
  quickest way to make an ordinary object report that it was picked up.
- **AirTag-class tags**: AirTag is nRF52832 + U1 + BMA280 accelerometer on a 26 mm board, 3.3 mm
  tall without battery [V]. OpenHaystack runs Find My advertising on ESP32 or nRF51 boards but
  is experimental, needs a Mac with a Mail plugin, and reports lag up to 30 minutes [V].

**NFC, the most important radio for magic** because it carries power and data to a batteryless
object:

- **Plain tags** (NTAG213/215/216 stickers and bare inlays, cents each, unverified; about
  0.1 to 0.2 mm thick, unverified). Identify which object is on which spot of a mat.
- **Dynamic tags with harvesting**: NXP NTAG I2C plus (NT3H2111/2211) outputs up to 15 mW on
  VOUT, has a field-detect pin that can wake a host, 64-byte SRAM pass-through at 40 kbit/s, in
  SO8 or TSSOP8 [V]. NXP NTAG 5 boost: "regulated up to 30 mW", two PWM outputs and two GPIOs
  that work with no MCU at all, active load modulation for tiny antennas when a supply is
  present [V]. ST25DV04K/16K: ST's AN4913 shows roughly 0.7 to 2.9 mA from the V_EH pin
  depending on field strength with a class-1 antenna [S]; current depends heavily on antenna and
  distance, and a custom small antenna may deliver almost nothing [S]. Adafruit ST25DV16K
  breakout $3.95 [V].
- **NFC "system" chips**: Infineon NAC1080 (landing page exists [V]; from memory it is a
  Cortex-M0 with NFC front end, harvesting and an H-bridge, sold for batteryless locks that a
  phone both powers and opens, unverified). The closest thing to a one-chip batteryless
  *actuator*. Worth a deep look.
- **Readers**: PN532 breakout (Adafruit $39.95 [V]; red AliExpress boards $3 to $5,
  unverified); PN5180 and ST25R3916 boards for ISO 15693 and more field (unverified).
  Rule of thumb (my estimate): read and power range is about one reader-antenna diameter for a
  card-sized tag, and 1 to 3 cm for a 10 mm tag coil, so a mat reader wants a 6 to 10 cm loop
  and the prop wants the largest coil that fits.
- **Flipper Zero** ($169 [V]) is the fastest way to sniff and emulate NFC, 125 kHz RFID, IR and
  sub-GHz remotes while prototyping (capabilities beyond price unverified this session).

### 2.2 Power

**Capability:** run for years, or run with no battery at all.

**Cells.**

| Type | Example | Size (mm) | Capacity | Price | Notes |
|---|---|---|---|---|---|
| Ultra-thin LiPo | PowerStream PGEB0042255 | 0.4 x 22 x 55 | 25 mAh | $15 [V] | Stocked; custom shapes need tooling and 2,000 pieces [V] |
| Ultra-thin LiPo | PowerStream PGEB042923 | 0.45 x 29 x 23 | 10 mAh | spec only [V] | Card-corner size |
| Ultra-thin LiPo | PowerStream 0.5 mm range | 0.5 x 40 x 18 to 0.5 x 43 x 38 | 10 to 45 mAh | $10 [V] | Vendor says 0.5 mm cells can be bent into a cylinder [V] |
| Ultra-thin LiPo | Grepow GRP0425025 / GRP0422055 | 0.5 x 25 x 25 / 0.5 x 22.5 x 55.5 | 9 / 22 mAh | quote | 1C rated only [V] |
| Thin primary Li | Powersolve | down to 0.4 | (n/a) | quote | [S] |
| Printed zinc | Zinergy | "paper-thin" | custom | quote | No lithium; can be bent, pierced or cut without fire risk; roll-to-roll custom [V]. Molex thin-film cells similar (unverified) |
| Coin, primary | CR2032 | 20 x 3.2 | 225 mAh | $0.3 to $1 | Keep pulses under 10 to 15 mA or add a capacitor [S] |
| Coin, primary | CR2016 / CR1220 / CR1216 | 20 x 1.6 / 12.5 x 2.0 / 12.5 x 1.6 | about 90 / 35 / 25 mAh (unverified) | cents | The coin- and chip-sized options |
| Silver oxide | SR626 / SR416 | 6.8 x 2.6 / 4.8 x 1.6 | about 28 / 8 mAh (unverified) | $0.5 | 1.55 V: pairs with DA14531 (1.1 V min [V]) |
| Small LiPo pouch | "301012", "401215" class | 3 x 10 x 12 and up | 20 to 60 mAh (unverified) | $2 to $4 | Pixels die uses 60 mAh [V] |
| Curved LiPo | Oura Ring 5 cell | ring arc | 10.2 to 10.5 mAh [S] | n/a | Proof that ring cells exist; hard to buy in ones |
| Pin cell | Panasonic CG-320 class | about 3.6 dia x 20 | about 15 mAh (unverified) | n/a | For pens and wands |
| Solid-state SMD | TDK CeraCharge, ITEN | 1812 chip size | about 100 µAh (unverified) | $1 to $3 | Reflowable; enough to ride through a pulse, not to run a radio |
| Supercapacitor | Seiko CPH3225A; Murata DMH | 3.2 x 2.5 x 0.9; about 20 x 20 x 0.4 (both unverified) | 11 mF; 35 mF | $1 to $5 | Buffer for burn-wire or radio pulses from a weak source |

Coin-cell pulse limits matter: TI's SWRA349 found 30 mA peaks cost only about 9 percent capacity
against 15 mA peaks, but the cell must stay under roughly 30 ohm internal resistance to survive
them; Duracell rates 10 mA for 1 s and 3 mA continuous [S]. Anything that fires a heater, motor
or solenoid from a coin cell needs a storage capacitor.

**No battery in the prop.**

- **Loose induction (the "LED lights in the spectator's hand" kit).** Adafruit 5140: a 5 V driver
  with a 70 mm outer, 65 mm inner, 0.5 mm thick coil and ten LED-plus-inductor receivers, sensing
  distance 0 to 80 mm, $14.95 (out of stock when checked) [V]. The 24 V large-ring version is
  reported to work to about 30 cm with large receivers and 9 cm with small ones when centred
  [S]; Jameco lists the large kit at $37.25 [S]. The receivers have no chip and no battery. A
  0.5 mm coil vanishes under a close-up pad. The same field can feed a rectifier, a capacitor
  and a cents MCU instead of an LED, which is the interesting use.
- **NFC harvesting**: 15 to 30 mW at centimetres, with data, as in 2.1. From a performer-owned
  reader this is dependable. From a spectator's phone it is not: phones poll in short bursts,
  antenna positions vary, and Waveshare's batteryless NFC e-paper lists Samsung and Google
  phones as unsupported [V].
- **Qi**: 5 V at 500 mA from a 40 x 29 mm receiver whose chip is 1.3 mm tall [V], but only at a
  few millimetres. Good for charging a deck box or book on a "coaster", not for powering at a
  distance. Pixels dice charge through a 10 mm, 7 µH coil [V].
- **Resonant power across 2 to 5 cm** with more than LED-level power: I could not verify
  hobby-grade kits beyond the two above. Cheap XKT-series transmitter/receiver pairs claim
  5 V at hundreds of mA at about 1 cm (unverified). Open lead.

**Harvesting, realistic numbers (all unverified rules of thumb):** indoor photovoltaic about
10 µW per cm² at office light; body-heat thermoelectric 10 to 30 µW per cm² of skin; a pressed
kinetic switch (EnOcean ECO 200 class, not recommended for new designs [V]) about 100 to
200 µJ per press, enough for one radio packet. None of these moves anything. They only keep a
sleeping logic circuit alive or send one message.

**Wake-up and standby parts.**

| Function | Part | Size (mm) | Current | Source |
|---|---|---|---|---|
| Wake on magnet | TI DRV5032 hall switch | 1.4 x 1.1 (X2SON) | 0.54 µA at 5 Hz sampling; thresholds from 3.4 mT | [V] |
| Wake on magnet, lower power | Coto RedRock RR122 TMR | about 1.4 x 1.4 (unverified) | hundreds of nA or less (unverified; page blocked) | - |
| Wake on motion or tap | Bosch BMA400 | 2 x 2 x 0.95 | 0.8 µA auto-wake; tap detect under 8 µA | [V] |
| Wake at a date and time | Micro Crystal RV-3028-C7 | 3.2 x 1.5 x 0.8 | 45 nA; alarm, timer, plus or minus 1 ppm | [V] |
| Wake every N seconds | TI TPL5111 | 2.9 x 2.8 | 35 nA; 100 ms to 2 h | [V] |
| Wake on NFC field | NTAG I2C plus FD pin | SO8/TSSOP8 | zero (field powered) | [V] |
| Zero-current wake | reed switch, tilt ball | 5 to 10 long | 0 | (unverified sizes) |

Arithmetic: a CR1216 (about 25 mAh) feeding 1 µA total lasts about 2.8 years; a CR2032 at the
AirTag's 2.3 µA lasts about 11 years [V]. Self-discharge, not the electronics, is the limit.

**Disguised charging contacts:** pogo pads as rivets, eyelets, a ring's inner band, a pen clip
and tip, the brass ferrule of a pencil, or no contacts at all (Qi coil or 10 mm coil as in
Pixels). Magnetic pogo connectors add steel and attract; note it for examinable props.

### 2.3 Sensing parts (pointer level; methods are agent 10's)

| Class | Smallest practical parts | Price | Note |
|---|---|---|---|
| IMU | LSM6DS3TR-C, BMI270 (about 2.5 x 3 x 0.8, unverified); BMA400 2 x 2 x 0.95 [V] | $2 to $5 | XIAO "Sense" boards include one |
| Magnetometer | MMC5603 (sub-1 mm WLCSP, unverified), LIS3MDL, MLX90393 | $1 to $6 | |
| Hall / TMR | DRV5032 1.4 x 1.1 [V]; DRV5053/5055 analog (unverified) | $0.3 to $1 | |
| Capacitive touch | TTP223 (cents), AT42QT1010, MPR121, ESP32 touch pins (all unverified) | $0.05 to $3 | Works through 1 to 3 mm of plastic, cloth or card |
| Time-of-flight | VL53L0X/L4CD/L5CX (about 4.4 x 2.4 x 1, unverified); VL6180X | $3 to $12 | Needs an IR-clear window |
| Colour / light | TCS34725, VEML7700, AS7341, APDS-9960 (unverified) | $2 to $10 | |
| MEMS mic | ICS-43434, PDM mics about 3.5 x 2.65 x 1 (unverified) | $1 to $3 | |
| Camera | OV2640/OV5640 modules about 8 x 8 x 6 (unverified); XIAO ESP32-S3 Sense $18.90 [V]; 3.9 mm USB endoscopes $15 to $30 (unverified); OmniVision OVM6948 0.65 mm class is not hobby-buyable (unverified); global-shutter OV9281 mono modules and "NoIR" (no IR-cut filter) modules for 850/940 nm work, $15 to $40 (unverified) | | Smallest easy wireless camera is the XIAO; global shutter matters for cards in motion |
| Thermal | MLX90640 24 x 32 px, $74.95, 25.7 x 17.7 mm board [V]; FLIR Lepton 3.5 160 x 120, 11.5 x 12.7 x 6.9 mm, $172 [V]; 256 x 192 USB modules about $100 to $200 (unverified) | | |
| mmWave | Hi-Link LD2410 24 GHz, 7 x 35 mm, 5 m range, $3.20 [V]; LD2450 tracking, Infineon BGT60 (unverified) | $3 to $25 | Sees through cloth, wood and mats |
| Force / weight | HX711 plus bar or thin-film load cells ($1 to $8, unverified); FSR 400 series; Velostat sheet 280 x 280 x 0.1 mm, $4.95 [V]; flex sensors about $10 (unverified) | | Velostat is the cheap way to make a whole mat pressure-sensitive |
| EMG | MyoWare 2.0, 37.6 x 35.9 mm, $43.50, raw/rectified/envelope out; retired in favour of DEV-27924 [V] | | Performer control, section 2.7 |

### 2.4 Actuation parts

**Capability framing:** every actuator is a point on a force, stroke, noise and standby-power
chart. Noise figures below are my estimates at about 30 cm in a quiet room unless marked; nobody
publishes them, and measuring a table of them with a phone sound meter is a cheap, useful job.

| Actuator | Example part | Size / mass | Output | Drive | Noise (est.) | Price |
|---|---|---|---|---|---|---|
| Electromagnet (hold, then release) | Adafruit P20/15 | 20 dia x 15 | 2.5 kg hold on flat steel | 5 V, 0.22 A while holding | Silent hold; faint tick on release | $7.50 [V] |
| Electropermanent magnet | OpenGrab EPM class (unverified) | about 40 x 40 x 16 | kg-class hold at zero power; flips on a pulse | high-current pulse | Tick | $40 to $50 (unverified) |
| Burn-through release | SMD resistor or nichrome on a nylon thread | under 0.2 g | Releases whatever the thread holds (newtons) | 0.2 to 1.5 A for about 1 s (unverified hobby practice) | Silent; faint smell | cents |
| Shape-memory wire | Flexinol 100 to 150 µm (agent 7) | wire | 1 to 3 N, 3 to 5 percent stroke (unverified) | 0.2 to 0.4 A, about 1 s | Silent | $5 to $10 per metre |
| Flex or rigid PCB coil on a magnet | Carl Bugeja FlexAR (flex, about EUR 2) and Flexar 12L (2 mm rigid) [S] | 0.13 to 0.3 mm flex [S] | millinewtons; flaps, taps, nudges; ran 100 million cycles [S] | 23 ohm coil, to 65 Hz [S] | Silent below audio rates | cents once ordered |
| Voice coil | salvaged phone camera autofocus or HDD arm (unverified) | 8 x 8 x 3 and up | 0.05 to 1 N, 0.3 to 10 mm | DC current | Silent | $1 to $10 |
| Piezo micropump | Bartels BP7 | 30 x 15 x 3.8, 2 g | 9 ml/min water or 35 ml/min air; 450 / 140 mbar | 50 mW plus driver | Under 50 dB [V] | about EUR 30 to 60 plus driver (unverified) |
| Piezo microblower | Murata MZB1001T02 | about 20 x 20 x 1.85 (unverified) | at least 0.7 l/min, 1.42 kPa | 15 Vpp at 24 to 27 kHz | Sold as silent (ultrasonic drive) [V] | about $20 to $40 (unverified) |
| LRA | 8 to 10 mm coin LRA plus DRV2605L ($7.95 [V]) | 8 to 10 dia x 2 to 3.5 | Sharp tap at 175 to 235 Hz [V] | AC at resonance | Quiet in the hand, loud on a table | $1 to $3 (unverified) |
| ERM coin motor | Adafruit 1201 | 10 dia x 2.7, 0.9 g | 11,000 rpm buzz | 60 mA at 3 V | Audible buzz | $1.95 [V] |
| Mini solenoid | Adafruit 2776 | 20 long, 12.6 g | 80 g at 3 mm | 5 V, 1.1 A | Sharp click, clearly audible | $4.95 [V] |
| Latching / lock solenoid | small bistable and door-latch types (unverified) | 10 to 30 long | holds at zero power | 3 to 12 V pulse | Click | $2 to $10 |
| 6 mm planetary gearmotor | Pololu 2357 (26:1) | 6 dia x about 25 total, 1.2 g | 2500 rpm, 0.1 kg-cm stall at 6 V | 35 to 400 mA | Whine; louder at high ratios | $19.95 [V]; AliExpress equivalents $2 to $5 (unverified) |
| Sub-micro servo | 3.7 g class (Pololu 1053, discontinued; FEETECH FS0307 successor) | 20.2 x 8.5 x 20.2 | 0.4 kg-cm, 0.07 s per 60 degrees | 4.8 to 6 V | Whine plus gear chatter | $5 to $10 [V for specs] |
| 1.5 to 2 g linear servo | Goteck/Spektrum class (unverified) | about 15 x 8 x 20 | about 100 g over 8 mm | 3.7 V | Whine | $5 to $15 |
| Micro linear actuator | Actuonix PQ12 (page blocked) | about 15 x 21.5 x 36, 15 g; 20 mm stroke; 18 to 50 N; about 55 dB at 45 cm (all unverified) | | 6 or 12 V | Clearly audible | about $80 to $100 (unverified) |
| Slider stepper | camera and optical-drive lead-screw steppers (unverified) | 15 to 40 long | 20 to 80 mm travel, low force | 2-phase driver | Tick or hum by drive | $1 to $3 |
| Air pump / valve | 3 to 6 V diaphragm pumps and solenoid valves (unverified) | 27 dia x 60 | litres per minute | 0.2 to 0.5 A | Loud (60 dB class) | $3 to $8 |
| Peristaltic pump | 3 to 12 V hobby heads with silicone tube (unverified) | about 30 x 30 x 50 | 20 to 100 ml/min, self-priming, holds liquid when stopped | 0.2 to 0.4 A | Rhythmic hum and roller thump | $8 to $25 |
| Micro valve | 3 V latching and proportional micro solenoid valves, 6 to 10 mm (unverified) | 8 x 8 x 20 | gates air or liquid; latching types hold at zero power | pulse | Faint click | $5 to $30 |
| Mist | Seeed Grove Water Atomization, 105 kHz disc | board plus about 16 mm disc | cold mist from a wetted wick | 5 V, 2 W, 65 V peak on disc | Faint hiss | $10.90 [V] |
| Thread reel | 6 mm gearmotor plus printed spool (invisible thread reels are the existing magic form, unverified) | 8 x 30 | grams of pull | 3 V | Whine; use low ratio and slow PWM | $5 to $20 |
| Speaker / exciter | Bone conduction transducer | 14 x 21.5, 9.6 g | 1 W; turns a table, box or glass into the speaker | small class-D amp | n/a | $8.95 [V] |
| Heat | PCB trace heaters, 0603 resistors, polyimide film heaters, PTC discs, nichrome (unverified) | 0.1 mm and up | 40 to 300 °C | 0.1 to 2 A | Silent | cents to $5 |
| Cooling | TEC1-12706 40 x 40 Peltier (unverified) | 40 x 40 x 3.8 | tens of °C below ambient | 2 to 6 A | Silent (needs a heat sink) | $3 |
| Ultrasound | 40 kHz 10 or 16 mm cans (Murata MA40S4S class, unverified) | 10 dia x 7 | inaudible carrier | 10 to 20 Vpp | Inaudible | $1 to $5 |
| Laser | 3 to 6 mm 650 nm modules under 5 mW (unverified) | 6 x 10 | dot or line | 3 V | Silent | $1 to $5 |
| Flip dot | single electromagnetic flip-dot elements (unverified) | 10 to 15 mm | bistable disc | short pulse | Loud click | $2 to $5 each |
| Fog on cue | vape-coil micro foggers (agent 7 or chemistry slices) | 10 x 30 | glycol puff | 3.7 V, 2 to 5 A | Hiss | $5 to $30 |

**Muscle-wire alternatives** (pointer to agent 7): for the same "silent pull of a few
millimetres" job, consider a DC voice coil, a flex-PCB coil on a magnet, a wax or paraffin
thermal actuator, a bimetal strip on a trace heater, or a spring held by a burn-through thread.
All avoid the SMA problems of slow reset and heat next to skin.

**Silent ranking for close-up (quietest first, with typical force):** electromagnet or
electropermanent release (kg hold); burn-through thread (newtons, one shot); shape-memory wire
(1 to 3 N); flex-PCB coil on magnet (mN); DC voice coil (0.05 to 1 N); piezo pump or blower
(mbar); LRA held in a soft mount; slow-driven stepper; geared motor and servo; ERM; solenoid;
diaphragm pump. Anything in the lower half needs music, patter or distance.

**Safety:** heaters, burn wires and flash-paper igniters (glo-plugs) are fire sources; drive them
through a firmware time limit and a hardware fuse or PTC, never straight from a LiPo. Piezo and
EL drivers carry 65 to 150 V. Strong magnets pinch, erase hotel keys and are dangerous near
implanted devices. Class 3R and above lasers must never face an audience.

### 2.5 Light and display parts

| Part | Size | Price | Use and caveats |
|---|---|---|---|
| SK6805-EC10 addressable RGB | 1.1 x 1.1 x 0.33 mm | $0.05 to $0.09 LCSC [S] | Thinnest addressable pixel; EC15 (1.5 mm) is easier to place [S] |
| 0402 / 0201 single-colour LEDs | 1.0 x 0.5 / 0.6 x 0.3, 0.2 to 0.35 thick (unverified) | about 1 cent | Fit under a card face or in a coin edge |
| Flexible LED filament ("nOOds") | 300 mm long, silicone coated | $4.50 [V] | 3 V, 50 mA recommended; a glowing line that bends |
| UV / IR LEDs | 0603 to 5 mm | cents to $1 | 365 to 395 nm for hidden inks, 850/940 nm for cameras (agent 10) |
| Side-glow fibre, light guides | 0.25 to 3 mm | $1 per metre (unverified) | Carries light from a hidden LED to a seam-free surface |
| EL wire, tape, panel | 1 to 2.3 mm wire; 0.2 to 0.5 mm panel (unverified) | $5 to $15 | Needs about 100 V AC inverter that whines at 1 to 2 kHz |
| EL paint | sprayed electroluminescent coating systems, Lumilor class (unverified) | installer-priced | Makes an arbitrary 3D surface glow; multi-layer spray process, same high-voltage inverter; not a hobby kit as far as I know |
| Thin backlights / light guides | 0.4 to 1 mm edge-lit LED light-guide panels from phone and keypad backlights; laser-dotted acrylic (unverified) | $1 to $10 | An evenly lit area under paper or card from one or two side LEDs |
| Laser-scanning MEMS projector modules | focus-free laser pico engines (unverified; several makers have left the market) | $150 to $400 | Always in focus on any surface, but dim and a laser-safety item |
| Micro OLED 0.42 in (72 x 40), 0.49, 0.66, 0.91, 0.96 in | glass about 1.2 to 1.5 mm thick (unverified) | $2 to $6 (unverified) | Peek displays in a pen cap, ring box or watch; never for the audience side |
| Transparent OLED 1.51 in | 128 x 64, module 42 x 27 mm | $19.99 Waveshare [V] | Visible as a device; a level-1 "phenomenon" part |
| Flexible e-paper 2.13 in | 59.2 x 29.2 x **0.3 mm**, 212 x 104, 2 s full / 0.3 s partial refresh | $11.99, marked discontinued [V] | Bistable: holds its image with no power, so the driver can be removed. Under a matte film it reads as print |
| NFC-powered e-paper 2.13 in | 65.35 x 40.05 mm, 250 x 122 | $23.99 [V] | No battery at all; rewritten in about 2 s plus transfer by phone or ST25R3911B reader [V] |
| E-paper badge | Badger 2040: 2.9 in on RP2040, 85.6 x 48.7 x 10 mm; discontinued, RP2350 successor [V] | about $20 to $30 (unverified) | Fast prototyping |
| Printed electrochromic segments | Ynvisible (product page not reachable; unverified) | kits about EUR 50 to 100 (unverified) | About 0.3 mm, under 3 V, microwatts, slow (about 1 s), looks like printed ink changing |
| Cholesteric "Boogie Board" film | salvaged from $10 writing tablets (unverified) | | Pressure-written, erased by one pulse; "erase the evidence" at a button press |
| DLP pico projector | TI DLPDLCR2000EVM, 54 x 76 mm board, up to 30 lm [V] | about $99 (unverified) | Too dim outside a dark room |
| Laser galvo set | 20 kpps galvo pairs (unverified) | $70 to $120 | Laser-safety heavy; stage only |
| Flip-dot, nixie, VFD | modules (unverified) | $20 to $200 | Style, not concealment |
| PDLC switchable film | A5 samples plus 48 to 60 V AC driver (agent 7) | $15 to $40 | |

### 2.6 Thin and flexible construction

**Thickness budget.** JLCPCB flex: 1-layer 0.07 or 0.11 mm, 2-layer 0.11, 0.12 or 0.2 mm;
polyimide, FR4 or 0.1 to 0.3 mm stainless stiffeners; 3 mil traces on thin copper [V]. Add the
tallest part:

| Target | Thickness available | What fits |
|---|---|---|
| Playing card (about 0.3 mm) | 0.3 | A bare NFC/RFID inlay only. RFID playing cards for televised poker are the existence proof (unverified this session). No battery, no packaged chip. |
| "Thick card" (two cards laminated, about 0.6 mm) | about 0.4 after skins | 0.07 mm flex + SK6805-EC10 (0.33) or DA14531 WLCSP (0.328 [V]) + 0201 passives. NFC-harvested or mat-induction powered; no cell unless a 0.4 to 0.45 mm cell sits beside the flex in a cut-out. |
| Credit card (0.76 mm) | about 0.55 | Full BLE system: 0.11 flex + nRF54L15 CSP (0.42 [V]) with a 0.4 to 0.5 mm cell alongside, 0.3 mm flexible e-paper [V], dome switches. Display payment cards and Chipolo-type cards (2.4 mm, two-year cell [V]) show the range. |
| Coin (1.5 to 2.5 mm; US half dollar 30.6 x 2.15 mm, unverified) | 1.0 to 1.8 inside a shell | 0.4 mm rigid PCB + 1 mm SiP + CR1216 or SR-type cell beside it, hall switch, LED, LRA will not fit under about 2 mm. |
| Poker chip (39 x 3.3 mm) | about 2.5 | Almost anything small: 8 x 8 x 1 SiP, CR1220/CR2016, IMU. A 10 mm coin motor is 2.7 mm thick [V], which leaves only 0.3 mm per skin, so use a thinner LRA or a flex coil. |
| Pen (6 mm bore) | 6 dia x 100 | Pin cell or 2 to 3 stacked SR/LR cells, KAGA 8.55 x 3.25 x 1 module [S] or a 5 mm-wide custom board, 6 mm gearmotor [V], 4 to 6 mm LRA, IR LED, 0.42 in OLED in the cap. |
| Ring | about 2 x 6 mm cross-section around the finger | Oura-class flex and 10 mAh curved cell [S]; or NFC tag only (passive). |
| Die (16 mm) | about 12 mm cube inside | Pixels: nRF52810, RGB LEDs, 60 mAh cell, 10 mm coil, accelerometer, hall sensor on folded flex [V]. |

**Existence proofs worth studying.**

- **AirTag**: 26 mm board, three antennas laser-structured onto one plastic part at the board
  edge, the case itself is the speaker diaphragm driven by a voice coil, 2.3 µA idle [V]. The
  "case as speaker" idea transfers directly: any thin plastic prop skin can be the sounder.
- **Pixels dice**: open firmware and software (GameWithPixels on GitHub [S]); the Hackaday log
  admits early prototypes were biased, with one face landing about 15 percent more often, fixed
  by centring the battery and adding lead tape [V]. Balance is a real, testable problem for any
  loaded-with-electronics prop.
- **GoDice** use the nRF52805 [S]. **Oura Ring 5**: Ambiq Apollo3 Blue, flex board and cell
  fill the ring, titanium inside and out, epoxy-sealed and unrepairable [S]. Gen 2 and 3
  teardowns by Becky Stern [S].
- **Colmi R02 ring**: about $20, accelerometer, heart-rate and SpO2 sensors, a UART-like BLE
  service with 16-byte packets and no pairing or keys [V]. A cheap finger-worn motion input with
  no hardware work, and a warning that such devices are trivially spoofable.
- **Musical greeting cards, LED business cards, display credit cards, Tile Slim** (unverified):
  proofs that a 0.8 to 2.5 mm laminated sandwich survives pockets.

**Printed and textile electronics.** Conductive pens and paints (Bare Conductive), the Voltera
desktop circuit printer, conductive thread and sew-on parts (all unverified this session) are
good for touch pads, switch contacts, coils and sleeve wiring. Sheet resistance is too high for
motors or radios. Velostat (0.1 mm, $4.95 for 280 x 280 mm [V]) between two foil or
conductive-fabric layers makes a silent pressure switch of any shape.

**Potting.** Clear or pigmented epoxy and UV resin make a prop solid, hide seams and stop
rattles; Oura is the model [S]. Costs: no repair, no battery change (so use harvesting or
wireless charging), heat during cure can damage LiPo cells, and resin shifts the weight. Tune
weight and balance with tungsten putty or lead tape, as Pixels did [V].

**RF inside metal (my calculation, standard skin-depth formula; resistivity of brass taken as
6.5e-8 ohm-m).** Skin depth is about 4 mm at 1 kHz, 0.36 mm at 125 kHz, 0.035 mm at 13.56 MHz
and about 3 µm at 2.4 GHz. So a 0.3 mm brass shell stops NFC and Bluetooth completely, attenuates
125 kHz RFID heavily, and is transparent to static magnets and to slow coil signalling under a
few kHz. Known fixes: put the antenna on a non-metal face (Oura's inner surface, AirTag's plastic
half); a slot or gap in the metal so it does not form a shorted turn; a ferrite sheet between
coil and metal for NFC; or abandon RF and signal with a magnet, a hall sensor and a low-frequency
coil in the mat.

### 2.7 Wearable control for the performer

- **Triggers:** toe and heel switches (a dome switch or Velostat patch under the insole, read by
  a XIAO at the ankle); a ring with a hidden dome switch; a $20 Colmi ring used as a gesture
  input [V]; capacitive pads sewn in a sleeve or pocket (MPR121 class, unverified); a bite
  switch (medical "sip and puff" style, unverified); EMG from a forearm or calf with MyoWare
  ($43.50 [V]) so a muscle tense with no visible motion is the button; smartwatch apps as a
  socially invisible button and haptic screen (Wear OS and watchOS both let an app read the
  crown, buttons and IMU and play haptic patterns; open watches such as Bangle.js and
  PineTime are easier to script; all unverified this session). Silent buttons: tactile dome
  switches under silicone, capacitive pads, or a hall switch and a magnet on the opposite
  finger, since ordinary tact switches click audibly at close range.
- **Return channel:** an LRA with DRV2605L ($7.95 [V]) taped to skin for coded taps; bone
  conduction ($8.95 [V]) behind the ear under hair for speech. Commercial magic versions
  (thumpers, PeekSmith-type displays, SB Watch) exist (unverified; vendor site blocked my
  fetch).
- **Reliability practice (engineering judgement, not sourced):** two independent triggers for
  any critical cue; a dead-man timeout so a stuck switch cannot fire a heater or run a motor
  forever; defined link-loss behaviour (a prop that hears nothing for N seconds goes to a safe,
  innocent state); acknowledgement back to the thumper for every command; a pre-show self-test
  that reports battery voltage and link quality as a haptic code; a physical "arm" step so
  nothing fires in the pocket; fixed channels chosen away from venue Wi-Fi.

### 2.8 Reference designs and open hardware to copy

- Carl Bugeja: flex PCB actuators, PCB motors, Flexar 12L with Altium files, Gerbers and CC
  BY-SA datasheet [S].
- Pixels dice firmware and apps [S][V]; GoDice as a commercial comparison [S].
- OpenHaystack for Find My advertising [V].
- colmi_r02_client for a hackable smart ring [V]; Memfault's smart-ring development series [S].
- Adam Catley's AirTag reverse engineering for low-power board design [V].
- Flipper Zero for NFC, RFID, IR and sub-GHz exploration [V].
- CircuitPython on XIAO and RP2040 boards, ESPHome on ESP32 for no-code sensors and triggers,
  ESP-NOW examples from Espressif (all unverified this session).
- Open thumpers and open BLE HID rings: I could not search for these after the budget ran out.
  Open lead.

### 2.9 What fits in X

| Host | Usable space | Brain / radio | Power | Sense | Act / show | Main tell |
|---|---|---|---|---|---|---|
| Coin (24 to 31 mm, 1.75 to 2.15 mm) | 20 dia x 1.2 | WLCSP MCU or 8 x 8 SiP; RF needs a slot or plastic face | CR1216, SR cells, or none (magnet only) | Hall, IMU | LED at edge, flex coil | Ring test: a hollow coin sounds dead; weight |
| Playing card (0.3 mm) | whole face x 0.15 | NFC inlay only | Field | Identity | none | Stiffness, snap sound, show-through |
| Thick card (0.6 mm) | whole face x 0.4 | WLCSP MCU/BLE on 0.07 flex | NFC or induction; 0.4 mm cell in cut-out | Touch, tilt | 0201/EC10 LEDs, electrochromic patch | Thickness in a squared deck, edge view |
| Credit-card (0.76 mm) | 80 x 50 x 0.55 | nRF54L15 CSP, DA14531 | 0.4 to 0.5 mm LiPo 10 to 45 mAh | Touch, IMU, NFC | Flexible e-paper, LEDs | Flex stiffness, seam at edge |
| Pen (6 mm bore) | 6 dia x 100 | KAGA-type sliver module, custom 5 mm board | Pin cell, stacked SR cells | IMU, touch, IR | 6 mm gearmotor, LRA, IR LED, 0.42 in OLED | Does it still write; weight and rattle |
| Ring | arc 2 x 6 mm | Apollo/nRF on flex, or NFC tag | 10 mAh curved cell or field | IMU, PPG | LRA is too big; LED | Thickness; metal blocks RF |
| Die (16 mm) | 12 mm cube | nRF52810/54L15 | 60 mAh LiPo plus 10 mm coil, or NFC harvest | IMU, hall | 6+ RGB LEDs | Balance bias, sound on wood |
| Deck box | 90 x 65 x 2 walls, or a false half | XIAO or ESP32-C6-MINI | 100 to 400 mAh LiPo, Qi | NFC reader, camera, ToF, mic | LRA, servo, exciter | Weight, wall thickness |
| Book | pages hollowed, 10 to 30 mm | Raspberry Pi Zero class or ESP32-S3 | 1 to 5 Ah | Camera, mmWave, NFC, load cells | Speaker, projector, motors | Stiff block of pages, weight |
| Table mat / close-up pad | 400 x 300 x 3 to 6 | ESP32-S3, several readers | USB pack at the edge | NFC reader coils, hall/TMR arrays, Velostat, mmWave, load cells | Induction coil 0.5 mm, PCB coil arrays, exciters, heaters | Cable, stiffness, warmth |
| Shoe | insole 3 to 8 mm, heel cavity | XIAO at ankle or in heel | 100 to 500 mAh | FSR, Velostat, IMU | LRA return channel | Squeak, flex fatigue, sweat |
| Sleeve / jacket | lining | XIAO, conductive thread | flat LiPo in a pocket | Capacitive pads, EMG, IMU | Thread reel, SMA, blower | Wire strain, washing |

---

## 3. Capability primitives

1. *Now possible:* a sealed prop with no battery and no port that computes and reports when it
   sits within 1 to 3 cm of a mat. *Because:* NTAG I2C plus harvesting 15 mW with a field-detect
   wake pin [V]. *Before:* charge ports, dead batteries, or no electronics. *Primitives:* know,
   tell, prove ordinariness.
2. *Now possible:* light or power a chipless, batteryless receiver up to 8 cm above a 0.5 mm
   coil hidden in a pad, for $15. *Because:* loose induction kits [V]. *Before:* wires, or a
   battery in the prop. *Primitives:* transform, conceal, prove ordinariness.
3. *Now possible:* a prop sleeps 2 to 10 years and wakes when a magnet passes within a few
   centimetres. *Because:* 0.54 µA hall switch in 1.4 x 1.1 mm [V], coin cell. *Before:* reed
   switch plus bulky battery, or always-on drain measured in days. *Primitives:* delay, hold,
   know.
4. *Now possible:* a prop acts at a chosen minute weeks or months ahead, accurate to seconds.
   *Because:* 45 nA RTC with alarm, plus or minus 1 ppm [V]. *Before:* clockwork, or the
   performer present. *Primitives:* delay.
5. *Now possible:* "sense, decide, signal once" for under $1 and under 1 g, disposable.
   *Because:* 3-cent to 28-cent MCUs [V][S], 1-cent LEDs, cents NFC inlays. *Before:* every
   electronic gimmick was a $50 to $500 keepsake. *Primitives:* know, tell, erase the evidence.
6. *Now possible:* know which of N identical paper objects is on which spot, through cloth, with
   nothing but a 0.15 mm sticker in each. *Because:* NFC inlays and $3 to $40 readers [V].
   *Before:* marks, peeks, stooges. *Primitives:* know.
7. *Now possible:* hold several newtons with zero power and release silently on a one-second
   pulse, in under 0.5 g. *Because:* burn-through or SMA release driven by a cents MCU and a
   supercapacitor. *Before:* pull threads, wax, assistants. *Primitives:* hold/release, delay.
8. *Now possible:* a full Bluetooth computer 0.42 mm tall, so a 0.76 mm card can sense touch
   and tilt and report. *Because:* nRF54L15 CSP [V], 0.11 mm flex [V], 0.4 mm cells [V].
   *Before:* thick "electronic cards" that could not be handed out. *Primitives:* know, tell,
   prove ordinariness.
9. *Now possible:* change printed-looking information on a surface 0.3 mm thick with no power
   afterwards. *Because:* flexible bistable e-paper [V], NFC-powered e-paper [V].
   *Before:* pre-printed outs, nail writers. *Primitives:* transform, swap, control choice.
10. *Now possible:* 2.5 kg of magnetic holding from a 20 x 15 mm, $7.50 part switched by a
    logic pin. *Because:* commodity electromagnets [V]. *Before:* mechanical latches, PK
    magnets that never let go. *Primitives:* hold/release.
11. *Now possible:* move air or liquid at millilitres per minute from a 2 g, 3.8 mm thick pump
    under 50 dB. *Because:* piezo micropumps [V]. *Before:* squeeze bulbs, loud diaphragm pumps.
    *Primitives:* move, transform.
12. *Now possible:* turn any panel, glass or box into a loudspeaker with a hidden 14 x 21 mm
    part. *Because:* bone-conduction exciters at $9 [V]; AirTag does this with its own shell
    [V]. *Before:* visible speakers. *Primitives:* conceal, tell.
13. *Now possible:* detect a hand or body through a tabletop, mat or wall to 5 m for $3.20.
    *Because:* LD2410 24 GHz radar [V]. *Before:* cameras with a line of sight.
    *Primitives:* know.
14. *Now possible:* a pressure-sensing surface of any shape, 0.3 mm thick, for $5.
    *Because:* Velostat [V]. *Before:* discrete switches. *Primitives:* know.
15. *Now possible:* finger-motion input from a $20 ring that looks like jewellery, with an open
    protocol. *Because:* Colmi R02 class rings [V]. *Before:* custom ring switches.
    *Primitives:* tell, control.
16. *Now possible:* a muscle tense with no visible movement as a trigger. *Because:* $40 EMG
    front ends [V]. *Before:* toe switches, visible presses. *Primitives:* tell.
17. *Now possible:* a 16 mm die that knows its face and survives handling. *Because:* open
    Pixels design on folded flex [V]. *Before:* expensive closed "electronic dice".
    *Primitives:* know, prove ordinariness.
18. *Now possible:* signal through a solid brass shell. *Because:* magnets, hall sensors and
    sub-kHz coils pass where radio cannot (calculation in 2.6). *Before:* plastic "metal-look"
    props. *Primitives:* know, tell, prove ordinariness.
19. *Now possible:* a 1.1 mm pixel of any colour for 5 to 9 cents, on one data wire. *Because:*
    SK6805-EC10 [S]. *Before:* three wires per colour, 5 mm LEDs. *Primitives:* transform.
20. *Now possible:* a paper-thin battery that can be cut, pierced or binned without fire risk.
    *Because:* printed zinc cells [V]. *Before:* lithium cells that must never be crushed or
    burned. *Primitives:* erase the evidence, conceal. (Custom-order only.)
21. *Now possible:* two of your own nodes measure their separation to about 10 cm (UWB) or
    sub-metre (BLE Channel Sounding) (accuracy figures unverified). *Because:* DW3000 [S],
    nRF54L15 [V]. *Before:* signal-strength guesses. *Primitives:* know.
22. *Now possible:* 100 ms-latency private links with no router for $2 a node. *Because:*
    ESP-NOW on ESP32-C3/C6 (unverified figures). *Before:* 433 MHz one-way fobs.
    *Primitives:* tell.
23. *Now possible:* a 0.2 mm, silent, solid-state actuator printed as part of the circuit.
    *Because:* flex-PCB coils against a small magnet, 100 million cycles [S]. *Before:* motors
    and linkages. *Primitives:* move.
24. *Now possible:* object tracking from a 26 mm board that idles at 2.3 µA for a decade.
    *Because:* AirTag-class design [V]. *Before:* GPS trackers lasting days.
    *Primitives:* know, delay. (See dead ends for limits.)

---

## 4. Effect concepts

Levels follow the brief: 1 = phenomenon is the effect, 2 = hidden input to a classical method,
3 = new architecture.

**4.1 The sealed die with nothing inside to run down (level 2).**
*Effect:* a spectator rolls an ordinary-looking resin die under a cup; the performer names the
number every time. The die can be handled for as long as anyone likes, tonight or in five years.
*Method:* the die holds a 12 mm coil, NTAG I2C plus (15 mW harvest [V]), an accelerometer and a
cents MCU, fully potted. It is dead until it sits on the close-up pad, where a reader coil
powers it, reads the up face and taps the result to an LRA on the performer. No battery, no
charging, no "it stopped working".
*BOM:* custom 2-layer flex ($10 to $30 for a batch), NT3H2111 ($1), BMA400 ($2), MCU ($0.3),
PN532 or ST25R reader ($5 to $40), XIAO ($5), LRA and driver ($10). About $60.
*Difficulty:* hard (coil tuning in a small volume, potting, balance). *Risks:* range under a
cup may be only 1 to 2 cm; balance bias as Pixels found [V]. *Novelty:* electronic dice exist;
a batteryless, permanently sealed one I believe is new to magic (unverified).

**4.2 The week-later kicker (level 3).**
*Effect:* at the end of a trick the spectator keeps a small sealed block (resin, wood or a
sealed envelope in a frame) with their signed coin or card inside, face up. The performer says
"look at it again at nine on Sunday". At that time the coin is found tails up, or the folded
card has opened.
*Method:* RV-3028 alarm (45 nA [V]) wakes a cents MCU once. It pulses a flex coil against a
tiny magnet on a pivoted insert, or burns a thread holding a spring flap. CR1216 lasts years.
Nothing is transmitted and the performer is long gone.
*BOM:* RTC $2, MCU $0.3, cell $0.3, flex coil or 0603 burn resistor, printed housing. Under $10
a unit, so it can be given away.
*Difficulty:* moderate. *Risks:* the giveaway contains a coin cell (make it inaccessible, never
give to households with small children, say so in the design); a one-shot cannot be rehearsed
on the same unit. *Novelty:* delayed giveaways exist in chemical form; an electronic timed
giveaway at this cost I have not seen (unverified).

**4.3 The table that knows what was touched, with nothing to find (level 3).**
*Effect:* at a dinner table the performer, back turned, names which sugar packet, coaster or
matchbook each guest picked up, in order.
*Method:* each object is a disposable: an NFC inlay only (read by coils under the cloth), or
for tables you do not control, a $1 beacon made of a cents MCU, 433 MHz or BLE transmitter, a
tilt or hall wake and a CR1220, glued inside a coaster or matchbook. Objects are consumed,
pocketed or binned; nothing is recovered and nothing needs to be.
*BOM:* inlays about $0.2 each; beacon coasters $1 to $3 each; receiver XIAO $5; thumper $10.
*Difficulty:* easy (NFC) to moderate (beacons). *Risks:* coin cells in disposable items are a
waste and ingestion hazard, so never in or near food items themselves, and prefer the passive
NFC version. *Novelty:* RFID-tagged props are known in mentalism (unverified); treating the
electronics as consumable set-dressing is the new part.

**4.4 One-shot release pellet (level 2).**
*Effect:* any classical effect that needs something to let go at a distance with no one near
it: a ring drops off a ribbon in a sealed jar, a card rises, a banner unrolls, a borrowed key
turns on a spectator's palm when a spring lets go.
*Method:* a 6 x 4 x 3 mm pellet: hall switch (wake on the performer's magnet) or IR receiver,
MSPM0 or CH32V003, a supercapacitor or small LiPo, and a burn resistor across a nylon thread.
Zero holding power, silent, under 0.5 g, fires once.
*BOM:* under $3. *Difficulty:* moderate (tiny hand soldering, or order assembled).
*Risks:* heat and a faint smell at the burn point; coin cells cannot supply the pulse, so size
the capacitor (0.1 F at 3 V is about 0.45 J). Fire safety applies. *Novelty:* burn-wire releases
are standard in small satellites and theatre pyrotechnics; a sub-gram addressable version for
close-up is, I think, unexploited (unverified).

**4.5 The spectator's hand as the socket (level 2).**
*Effect:* a borrowed ring, placed on a spectator's palm, makes a tiny bulb (or a sealed capsule
they hold) glow only when they think of the right word; it is dark in everyone else's hand.
*Method:* the "bulb" is a chipless coil-and-LED receiver [V]. The transmitter coil is not in the
table but in the performer's sleeve or a book held nearby, switched by a toe switch. Sleight of
hand gives the "which hand" structure; the electronics only supply a glow that has no battery to
find. Combine with a classical switch so the examined bulb is a real, dead filament bulb.
*BOM:* $15 kit, a 5 V boost and LiPo in the sleeve, toe switch. About $30.
*Difficulty:* easy. *Risks:* range falls fast off-axis; an LED glow invites "it's electronic",
which is why the examined object must be genuinely inert. *Novelty:* wireless LEDs are known
in craft and some magic props (unverified); the sleeve-borne coil and the inert duplicate are
the method work.

**4.6 Print that rewrites itself, then loses its driver (level 3).**
*Effect:* a prediction on a paper luggage tag, sealed in a clear pouch from the start and held
by a spectator, is correct for a freely named word.
*Method:* the "paper" is a 0.3 mm flexible e-paper panel [V] under a matte laminate printed
with paper texture, on an NFC-harvesting driver (as in Waveshare's batteryless tag [V]). It is
rewritten in two seconds while the pouch rests on a book containing the reader. E-paper is
bistable, so the image stays with no power. For a cleaner finish the driver flex is a tear-off
tab removed when the tag is "cut from the string".
*BOM:* panel $12, NFC e-paper tag $24 as a donor, reader $10 to $40, ESP32 $5. About $60 to $90.
*Difficulty:* hard (making e-paper pass as paper at inches is the whole problem).
*Risks:* contrast and surface sheen; 212 x 104 pixels limits type size; too-perfect if anyone
suspects a screen, so let it be seen blank first and never refresh in view (the flash of a full
refresh is a tell). *Novelty:* e-paper predictions exist commercially in device-shaped form
(unverified); disguising it as a tagged scrap with no battery is the step.

**4.7 Heat writing from under the pad (level 3, speculative).**
*Effect:* a blank slip, folded by the spectator and left on the pad under their own hand, bears
a two-digit number when opened.
*Method:* the slip is thermal receipt paper. Under the pad cloth lies a 0.6 mm PCB of trace
heaters laid out as large seven-segment digits. The chosen segments are pulsed to about 90 °C
for a few seconds. There is nothing in the slip.
*BOM:* custom heater PCB $10 to $20, MOSFETs, ESP32, 2 Ah pack. About $40.
*Difficulty:* moderate. *Risks:* heat spreads through cloth and folds, so digits will be large
and soft-edged; warmth can be felt by the hand; a folded slip prints through all layers.
Untested. Burn and fire care. *Novelty:* I know of no prior use (unverified).

**4.8 The pen that is the whole control system (level 2).**
*Effect:* none by itself; it removes pockets, wires and bulges from any mentalism act.
*Method:* a working marker with a 5 mm-wide board: BLE module (8.55 x 3.25 mm class [S]), IMU
for gesture cues, a touch pad under the clip as a silent button, an LRA at the grip as the
return channel, a 0.42 in OLED under the cap as a peek, IR LED at the tail to trigger props.
Pin cell or two SR cells.
*BOM:* about $40 in parts plus a custom board. *Difficulty:* hard (mechanical packaging).
*Risks:* LRA is audible if the pen rests on a table. *Novelty:* partial versions exist
commercially (unverified); an open design does not seem to (unverified).

**4.9 Brass coin, magnet language (level 2).**
*Effect:* an examinable solid-feeling coin signals heads or tails and which hand, with no
plastic and no radio.
*Method:* accept that RF cannot leave brass. The coin shell holds only a diametrically
magnetised disc on one side of centre; all electronics are in the mat or on the wrist (hall or
TMR arrays, agent 10). The contribution from this slice is the negative result: put nothing
active in metal. *BOM:* $5 to $30. *Difficulty:* easy. *Novelty:* low; magnet-sensing coins
exist. Included because it is the right architecture.

**4.10 Phone as an unwitting battery (level 3, uncertain).**
*Effect:* a spectator lays their own phone on the sealed envelope "as a paperweight". Inside,
an ink patch changes or an LED-lit window appears.
*Method:* an ST25DV or NTAG 5 tag harvests from the phone's background NFC polling and drives an
electrochromic segment or LED. *Risks:* background polling is bursty and phone-dependent;
harvest may be far below the 15 to 30 mW bench figures, and iPhone and Android behave
differently (Waveshare lists whole brands as unsupported even with an app [V]). Needs a bench
test on ten phones before any design work. *Novelty:* high if it works.

Seven of ten are level 2 or 3 with unseen technology (4.1 to 4.4, 4.6, 4.7, 4.8); 4.5 is
borderline level 1 to 2.

---

## 5. Dead ends and overhyped items

- **Bluetooth or NFC inside a closed metal coin or ring.** Physics, not engineering (2.6).
- **Hiding Find My or AirTag-class tags on a spectator.** Phones raise unknown-tracker alerts,
  OpenHaystack lags up to 30 minutes [V], and covertly tracking a person is unethical and in
  many places illegal. Use only on your own props.
- **UWB "precision finding" of your prop from a spectator's iPhone.** Needs your app and the
  accessory protocol [V]; nothing happens on a stock phone.
- **Body-heat, piezo or indoor-solar harvesting to move anything.** Microwatts. Fine for
  keeping a clock alive, useless for actuation.
- **Qi across a tabletop.** Millimetres only. Use loose induction or NFC instead.
- **Ultra-thin LiPo as a general answer.** 10 to 25 mAh, 1C rated [V], $10 to $15 each [V],
  easily creased, and a punctured lithium cell is a fire in someone's hand. Prefer field power
  for anything a spectator bends.
- **Solenoids, diaphragm pumps and ERM motors at close-up.** The sound is the tell.
- **EL wire and panels in quiet rooms.** Inverter whine, and about 100 V AC.
- **Pico projectors.** 30 lumens [V] loses to room light; reads as a screen.
- **Transparent OLED and flexible AMOLED.** Recognisable as displays at a glance; level-1 only.
- **Conductive ink for power circuits.** Too resistive; keep to touch pads and coils.
- **ATtiny as the "cheap" MCU.** It is now several times the price of a CH32V003 [S].
- **Electronics in anything edible or burnable in the hand.** Coin cells are a lethal
  ingestion hazard and lithium cells must not be burned. Only passive items (an NFC inlay in a
  paper billet that is burned in a tray, nothing in food) are defensible, and even those should
  be in the wrapper, not the food.

**What gives hidden electronics away (examinability checklist):** weight (grams matter in a
card or coin), stiffness and the sound of a card snapped or a coin dropped, a dull ring from a
hollow metal shell, warmth after use, motor or inverter noise, a seam where a shell closes,
light leaking through thin stock, magnets picking up paper clips, balance bias in dice, and a
0.6 mm card felt in a squared deck. X-rays are not a performance risk.

---

## 6. Open leads

- Infineon NAC1080/NGC1081: confirm it can harvest, compute and drive a small motor or SMA from
  a reader field with no battery.
- NTAG 5 boost with a sub-10 mm antenna in a ring or coin edge slot (AN12339 antenna guide [V]).
- Bench-measure harvest from idle phones (concept 4.10) and from a 1 W ST25R3916 reader through
  a close-up pad at 1, 2 and 3 cm.
- Higher-power resonant links at 2 to 5 cm (6.78 MHz class) and the cheap XKT modules: real
  delivered power versus gap.
- A measured dB-at-30-cm table for every actuator in 2.4; nobody publishes one.
- Printed zinc batteries in sample quantities (Zinergy [V], Molex, Imprint Energy): who sells
  ten pieces.
- Ynvisible electrochromic kits: current price, thickness and whether custom shapes can be
  ordered in ones.
- RFID playing cards used in broadcast poker: tag type, thickness, who sells decks.
- Open-source thumpers, mentalism remotes and BLE HID rings; Electricks' scripting for their
  remotes (site blocked my fetch).
- Thermal print heads or heater PCBs under a pad (concept 4.7): quick test with receipt paper.
- BLE Channel Sounding accuracy on nRF54L15 as a "how far is the prop from me" sensor.
- Carl Bugeja's measured force figures for flex and 12-layer coils (in his videos, not the
  logs I could read).

---

## 7. Sources

Opened this session [V]:

- https://www.adafruit.com/product/5140 - small inductive coil and 10 wireless LED kit, 5 V, specs and price
- https://www.adafruit.com/product/1201 - 10 mm vibrating disc motor
- https://www.adafruit.com/product/2305 - DRV2605L haptic driver
- https://www.adafruit.com/product/1674 - bone conduction transducer
- https://www.adafruit.com/product/2776 - mini push-pull solenoid, 5 V
- https://www.adafruit.com/product/3872 - 5 V electromagnet, 2.5 kg
- https://www.adafruit.com/product/1901 - Qi receiver module
- https://www.adafruit.com/product/4701 - ST25DV16K NFC EEPROM breakout
- https://www.adafruit.com/product/364 - PN532 NFC breakout
- https://www.adafruit.com/product/4407 - MLX90640 thermal camera breakout
- https://www.adafruit.com/product/5503 - nOOds flexible LED filament
- https://www.adafruit.com/product/1361 - Velostat pressure-sensitive sheet
- https://www.pololu.com/product/2357 - 6 mm sub-micro planetary gearmotor
- https://www.pololu.com/product/1053 - 3.7 g sub-micro servo (discontinued)
- https://www.seeedstudio.com/Seeed-Studio-XIAO-ESP32C6-p-5884.html - XIAO ESP32-C6
- https://www.seeedstudio.com/XIAO-ESP32S3-Sense-p-5639.html - XIAO ESP32-S3 Sense
- https://www.seeedstudio.com/Grove-Water-Atomization-v1-0.html - ultrasonic atomiser module
- https://www.espressif.com/en/products/modules - ESP32-C6 module dimensions
- https://www.nordicsemi.com/Products/nRF54L15 - packages, currents, Channel Sounding
- https://www.nordicsemi.com/Products/nRF52805 - WLCSP size
- https://www.renesas.com/en/products/wireless-connectivity/bluetooth-low-energy/da14531-smartbond-tiny-ultra-low-power-bluetooth-51-system-chip - DA14531 sizes and price
- https://www.insightsip.com/products/bluetooth-smart-modules/isp1507 - 8 x 8 x 1 mm nRF52832 SiP
- https://www.fanstel.com/bt832-1 - BC832 module size and price, module family list
- https://www.ti.com/product/MSPM0C1104 - 1.6 x 0.861 mm MCU
- https://www.ti.com/product/TPL5111 - 35 nA power-gating timer
- https://www.ti.com/product/DRV5032 - sub-µA hall switch
- https://www.ti.com/tool/DLPDLCR2000EVM - DLP2000 pico projector EVM
- https://www.microcrystal.com/en/products/real-time-clock-rtc-modules/rv-3028-c7 - 45 nA RTC
- https://www.bosch-sensortec.com/products/motion-sensors/accelerometers/bma400/ - BMA400 wake currents
- https://www.nxp.com/products/rfid-nfc/nfc-hf/connected-nfc-tags/ntag-ic-plus-2k-nfc-forum-type-2-tag-with-ic-interface:NT3H2111_2211 - NTAG I2C plus, 15 mW harvesting
- https://www.nxp.com/products/rfid-nfc/nfc-hf/ntag-for-tags-and-labels/ntag-5-boost-nfc-forum-compliant-ic-bridge-for-tiny-devices:NTAG5-BOOST - NTAG 5 boost, 30 mW
- https://www.infineon.com/part/NAC1080 - NAC1080 landing page (details not readable)
- https://developer.apple.com/nearby-interaction/ - Apple UWB accessory requirements
- https://www.powerstream.com/thin-lithium-ion.htm - ultra-thin LiPo list and prices
- https://www.grepow.com/shaped-battery/ultra-thin-battery.html - 0.5 mm cells
- https://www.zinergy-power.com/ - printed non-lithium batteries
- https://jlcpcb.com/capabilities/flex-pcb-capabilities - flex thickness and stiffeners
- https://www.waveshare.com/2.13inch-nfc-powered-e-paper.htm - batteryless NFC e-paper
- https://www.waveshare.com/2.13inch-e-paper-d.htm - 0.3 mm flexible e-paper
- https://www.waveshare.com/1.51inch-transparent-oled.htm - transparent OLED
- https://shop.pimoroni.com/products/badger-2040 - e-paper badge
- https://www.murata.com/en-us/products/mechatronics/fluid/overview/lineup/microblower_mzb1001t02 - piezo microblower
- https://www.bartels-mikrotechnik.de/en/micropumps/ - BP7 piezo micropump
- https://www.precisionmicrodrives.com/linear-resonant-actuators-lras - LRA basics
- https://www.hlktech.net/index.php?id=988 - LD2410 radar module
- https://groupgets.com/products/flir-lepton-3-5 - Lepton 3.5 price and size
- https://www.sparkfun.com/products/21265 - MyoWare 2.0 muscle sensor
- https://adamcatley.com/AirTag.html - AirTag reverse engineering
- https://github.com/seemoo-lab/openhaystack - OpenHaystack
- https://github.com/tahnok/colmi_r02_client - Colmi R02 ring client
- https://hackaday.io/project/28377-pixels - Pixels dice build log and parts
- https://gamewithpixels.com/ - Pixels dice product site
- https://chipolo.net/en-us/products/chipolo-card-spot - 2.4 mm card tracker
- https://flipper.net/ - Flipper Zero price
- http://cpldcpu.com/2019/08/12/the-terrible-3-cent-mcu/ - survey of 3-cent MCUs
- https://www.cnx-software.com/2022/10/22/10-cents-ch32v003-risc-v-mcu-offers-2kb-sram-16kb-flash-in-sop8-to-qfn20-packages/ - CH32V003 launch
- https://www.enocean.com/en/product/eco-200/ - kinetic harvester (status only)
- https://hackaday.io/project/159936-flexible-pcb-actuator/log/181176-how-small-can-my-flexible-pcb-actuator-get - Bugeja log (no numbers on page)

Seen in search results, not opened [S]:

- https://www.lcsc.com/product-detail/C5299908.html - CH32V003F4U6 pricing
- https://www.lcsc.com/product-detail/C22394946.html - SK6805-EC10 size and pricing
- https://www.lcsc.com/product-detail/C2890035.html - SK6805-EC15
- https://www.nordicsemi.com/Nordic-news/2024/11/KAGA-FEI-ES4L15BA1-module-integrates-nRF54L15-SoC - 8.55 x 3.25 x 1 mm module
- https://www.ezurio.com/product/bl54l15-micro-series-bluetooth-le-802-15-4-nfc - BL54L15µ
- https://www.murata.com/en-us/news/connectivitymodule/bluetooth/2025/0623 - Murata Type 2NR
- https://www.digikey.fr/en/products/detail/raytac/MDBT42V-512KV2/16896690 - Raytac MDBT42V price
- https://www.hackster.io/news/seeed-studio-packs-ble-6-0-thread-matter-zigbee-and-more-into-the-new-xiao-nrf54l15-429ae1490e7a - XIAO nRF54L15 prices
- https://www.seeedstudio.com/blog/2025/07/30/meet-seeed-studio-xiao-nrf54l15-sense-the-ultra-low-power-platform-with-multi-protocol-connectivity/ - XIAO nRF54L15
- https://www.qorvo.com/products/p/DWM3000 - DWM3000 UWB module, Apple interoperability claim
- https://rfmw.com/products/detail/dwm3000-qorvo/681949/ - DWM3000 price
- https://www.st.com/resource/en/application_note/dm00329035-energy-harvesting-delivery-impact-on-st25dvxxx-behavior-during-rf-communication-stmicroelectronics.pdf - ST AN4913 harvesting currents
- https://community.st.com/t5/st25-nfc-rfid-tags-and-readers/how-much-power-can-be-harvested-via-stm-nfc-dynamic-tags-e-g/td-p/822426 - ST forum on harvest variability
- https://TI.com/lit/pdf/swra349 - coin cells and peak current
- https://www.duracell.com/wp-content/uploads/2021/06/CR2032CH_225mAh.pdf - CR2032 pulse rating
- https://www.nxp.com/docs/en/application-note/AN14664.pdf - coin-cell peak current guidance
- https://eepower.com/new-industry-products/powersolve-thin-lithium-polymer-primary-cells-can-be-produced-down-to-0-4mm/ - 0.4 mm primary cells
- https://www.batteryspace.com/ultra-thin-rechargeable-cells.aspx - 0.4 mm cells
- https://core-electronics.com.au/small-inductive-coil-and-10-wireless-led-kit-5v.html.md - induction kit distances
- https://www.jameco.com/z/5141-Adafruit-Industries-Large-Inductive-Coil-and-10-Wireless-LED-Kit-24V_2522943.html - large coil kit price
- https://adafruit.com/product/5572 - large wireless LED packs
- https://www.androidauthority.com/oura-ring-5-teardown-3680320/ - Oura Ring 5 teardown summary
- https://www.notebookcheck.net/Oura-Ring-5-teardown-reveals-ARM-chip-384-KB-RAM-and-impossible-repairs.1326712.0.html - Oura Ring 5
- https://beckystern.com/2022/04/17/oura-ring-teardown-gen-3-and-gen-2 - Oura Gen 2/3 teardown
- https://interrupt.memfault.com/blog/smart-ring-development-part-1 - smart ring development notes
- https://github.com/GameWithPixels/DiceFirmware/ - Pixels firmware
- https://www.nordicsemi.com/News/2022/08/Particulas-GoDice-employs-Nordics-nRF52805-SoC - GoDice internals
- https://hackaday.io/project/159936-flexible-pcb-actuator - Bugeja flex PCB actuator
- https://hackaday.com/2023/06/01/flexible-actuator-flaps-for-100000000-cycles-without-failure - flex actuator endurance
- https://cdn.shopify.com/s/files/1/0766/9855/0605/files/Flexar_12L_Datasheet_Rev1.6.pdf - Flexar 12L datasheet
- https://www.hackster.io/news/carl-bugeja-demonstrates-five-applications-of-the-12-layer-pcb-actuator-kit-2838f868c87a - Flexar 12L applications

Pages that refused or were missing (claims from them are marked unverified): actuonix.com/pq12
(403), cotorelay.com RR122 (403), product.tdk.com CeraCharge (403), electricks.info (403),
molex.com thin-film batteries (503), murata.com DMH supercapacitor (404), ynvisible.com kit
page (404), tahnok.github.io (empty).
