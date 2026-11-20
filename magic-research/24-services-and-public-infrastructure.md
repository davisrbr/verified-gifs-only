# 24. On-demand services and public infrastructure as method and reveal channels

Prices and lead times are as of late 2026 (pages opened 20 November 2026) unless marked. Anything
marked "(unverified)" is recalled from memory or seen only in a search snippet and was not
confirmed on a primary page. The shared web-search budget ran out part-way through this task, so
several lines of inquiry rest on directly opened pages only; gaps are listed in section 6.

## 1. Summary

- **The outside world is now an API with a one-unit minimum.** A postcard costs $0.91 by API
  (Lob), a phone number $1.15 a month (Twilio), an 8-second play on a roadside billboard cents
  (Blip), a one-off printed book $2.30 to print (KDP), a one-off deck $16.95 (MPC), a courier
  $8 to $10 (Uber Direct, DoorDash Drive), a tasked 50 cm satellite photograph about $200 to
  $300 (SkyFi). The television-budget "prediction out in the world" is a hobby-budget item.
- **The binding constraint is lead time and approval, not money.** Almost nothing physical can be
  made to exist in under an hour. Mail takes 5 to 7 business days, print-on-demand 4 to 9 days,
  billboard creative 1 to 3 business days to approve. Only telephony, messaging, pre-approved
  screens, couriers and (probably) same-day photo counters respond inside a performance.
- **So the natural architecture is "stage many, select live".** Pay for N genuine pre-placed outs
  days ahead (envelopes, lockers, caches, approved creatives, phone numbers) and let the live
  choice pick one. Out capacity per channel is in the table in 2.8.
- **Live-triggered channels suit transposition and transmission plots, not prediction plots.**
  Anything ordered after the choice carries an order time on a receipt, label or log. Frame it as
  "it is appearing over there now", never as "it was always there".
- **Honest timestamps prove "existed before", never "the only one".** OpenTimestamps, Wayback
  captures, notarisation, copyright registration and domain creation dates are all genuine and
  cheap or free, and all are compatible with making fifty-two of them. The strongest commitment
  is therefore one the spectator has physically held (posted mail), because siblings cannot hide
  in their hands. The cleverest structure found: distribute the siblings across the audience.
- **Third-party fulfilment is a "prove ordinariness" machine.** A gimmicked book or stacked,
  marked deck that the spectator bought themselves from Amazon or a card printer's shop, and
  that the performer never touches, is a new method architecture. This is the single most
  transferable finding.
- **Public telemetry turns "chance" into knowledge.** Aircraft overhead (OpenSky, free, 5 to 10 s
  resolution), the fleet number and licence plate of the next bus (GTFS-realtime), ISS passes ten
  days ahead, and above all stream latency (a "live" stream is 15 to 78 s in the past) give the
  performer facts about the public world minutes or seconds before the audience.
- **Real-time voice agents make every owned phone number a collaborator** for $0.07 to $0.30 a
  minute with sub-second response; inbound calls only (outbound automated calls need consent).
- **Independent strangers are the best witnesses.** A geocache with fourteen months of dated
  finder logs, or a parcel with carrier tracking from another city (alternate-reality-game
  craft), is evidence no prop can supply. The secret work happens the day before, off-stage.
- **Clean lines:** do not back-date listings, plant false notices, edit reference sites, disguise
  a trick as a commercial advert to a sign owner, call people with an automated voice without
  consent, or mine guests' private data. Every concept below runs on the performer's own
  accounts, openly supplied guest information, and paid or willing open collaborators.

## 2. Catalog

### 2.1 Programmable physical output at a distance

**Self-serve digital billboards (Blip).** Blip sells single 8-second plays ("blips") on roadside
digital signs through a web dashboard: pick individual signs on a map, set days and times of day,
set a daily budget (no contract; the help page mentions both a $5 and a $20 daily floor), pay only
for plays won. Plays are quoted "as low as $0.01", typically $0.01 to $0.50 depending on sign and
time (search snippet). Slots are allocated by "digital auctions every 10 minutes". Creative goes
through Blip moderation ("typically completed within 90 minutes during business hours") and then
the sign owner ("usually 1 to 3 business days"; another Blip page says "up to 48 business
hours", and that Blip cannot speed it up). 2,700 to 3,500+ screens in the US, depending on the
page. Sources: https://www.blipbillboards.com/ ,
https://help.blipbillboards.com/get-started-with-blip ,
https://www.blipbillboards.com/blog/outdoor-billboard-advertising/ .
*Accessibility:* off-the-shelf, $5 to $50 for a stunt; US-centric.
*Magic relevance:* the classic "it's on the billboard" reveal for the price of a coffee.
Multiple creatives can be approved in advance and rotated, so the out capacity is whatever the
owner will approve; switching which creative runs is a dashboard action, but the 10-minute
auction cycle means the reveal lands 10 to 20 minutes after the choice, not on a finger-snap.
*Unknowns:* whether owners approve cryptic personal creatives, and the real latency between
editing a campaign and the next play. Both need a $20 test. *Ethics:* submit creatives as what
they are (a personal message), not as a fake advert.
Other routes: a Times Square operator has sold 15-second public slots through an app for about
$40 (unverified; the operator's site redirected to an unrelated domain today and was not
followed). AdQuick, Vistar-connected resellers, JCDecaux and Clear Channel self-serve were not
verified. Taxi-top, cinema and stadium screens are sold by quote; treat as out of hobby range.

**Mail by API.** Lob's free Developer plan prints and posts a postcard from $0.905 and a letter
from $0.828 per piece, fully variable per piece. The piece is handed to USPS no earlier than two
business days after the API call; First Class takes "typically 5 to 7 business days". Tracking
events arrive by webhook: In Transit, In Local Area, **Processed for Delivery** ("should reach
the mailbox within one business day"), Delivered. Sources: https://www.lob.com/pricing ,
https://help.lob.com/print-and-mail/getting-data-and-results/tracking-your-mail .
Handwrytten writes cards with pen-holding robots: $3.75 retail per card plus postage at the USPS
rate, down to $1.19 on business plans, API on business plans
(https://www.handwrytten.com/pricing/). PostGrid is a Lob equivalent (pricing page did not
expose numbers). USPS Informed Delivery, free to recipients, emails a greyscale image of the
address side of each letter-sized piece on the morning it is due
(https://www.usps.com/manage/informed-delivery.htm).
*Magic relevance:* (a) a spectator-held, third-party-carried commitment for about a dollar;
(b) fully unique per recipient, so twelve guests can hold twelve different sealed things;
(c) the performer knows, to the day, when a remote person's letter lands ("know" primitive for
telephone or video-call work). Machine-franked API mail usually carries a permit imprint rather
than a dated postmark (unverified for Lob specifically); a real stamp, as on robot-handwritten
cards, gets cancelled, which is the dated evidence a routine wants.

**Print-on-demand, one unit, by API.** Printful: no stated minimum, fulfilment "2 to 5 business
days", then 3 to 4 business days flat-rate or 1 to 3 express in the US; the Orders API accepts a
print-file URL per order item, so every unit can be different
(https://www.printful.com/shipping , https://developers.printful.com/docs/). Categories include
shirts, posters, mugs, puzzles and playing cards. MakePlayingCards: "No minimum order required.
Buy 1 deck for $16.95", each card individually customisable front and back
(https://www.makeplayingcards.com/design/custom-blank-card.html). The Game Crafter prints single
decks and game components (pricing page did not render; a 2020 maker post quotes about $6.17 for
a 52-card deck with box, https://www.patreon.com/posts/32873289 , dated). Amazon KDP prints a
24 to 110 page black-ink paperback for a fixed $2.30, or $1.00 plus $0.012 a page above that,
and sells it through Amazon's own storefront and delivery
(https://kdp.amazon.com/en_US/help/topic/G201834340). Lulu has a print API (price calculator did
not render). Gelato (403), Printify, Blurb, Moo, Zazzle and Sticker Mule were not verified.
*Magic relevance:* covered by agents 13 and 19 as gimmick manufacture; the point for this slice
is the **delivery chain**. The item can be shipped by the printer straight to the spectator, a
venue, or a pickup point, so the performer never touches it.

**Newspapers.** Newspaper Club prints real newsprint tabloids, broadsheets and minis with "No
minimum order ... from 1 copy", "from our press to your door in 2 to 8 working days" (UK 1 to 7),
shipped from the UK with US duties prepaid (https://www.newspaperclub.com/ ,
https://www.newspaperclub.com/choose/orders-and-delivery/delivery). Single-copy price did not
load; recalled as roughly £20 to £30 delivered (unverified). Historic Newspapers sells genuine
original papers from a named date from $39.99, "5 days from order to your door"
(https://www.historic-newspapers.com/). Real classified ads: the Star Tribune's 2026 rate book
closes liner ads two to three days before the run date; a small weekly charges $15 for 15 words;
another small paper wants copy five business days ahead (rate cards via search:
https://cdn.startribunecompany.com/wp-content/uploads/2026/03/ClassifiedRB_2026_0213.pdf ,
https://westernwaynenews.com/advertise/ ).
*Magic relevance:* a personal, forced-outcome prediction in a genuine local paper costs $15 to
$50 and needs 2 to 5 days' notice; a facsimile "paper from your birthday" with altered small ads
costs about the same and gives total control. A real ad must be a true personal notice, not a
false announcement.

**Food and small personalised goods.** Custom fortune cookies: minimum 50, individually wrapped,
five different messages included, $0.74 each at 50 to 99 (search snippet), 3 to 5 business days
plus shipping, and a $35 option to sort specific messages for specific guests
(https://www.fancyfortunecookies.com/Articles.asp?ID=355). The Ripple Maker prints any image on
a coffee, beer or cocktail foam in under 10 seconds, driven from a cloud portal and app; it is a
commercial bar machine, so the route is a café that owns one, as an open collaborator
(https://www.drinkripples.com/). Printed-image cakes, personalised sweets, engraved items,
temporary tattoos by post and personalised postage stamps exist but could not be priced today
(sites failed to load or search budget exhausted).

**Couriers and helpers.** DoorDash Drive API: $9.75 for a delivery within 5 miles, plus $0.75 a
mile to 15 (https://developer.doordash.com/en-US/docs/drive/overview/pricing_payment). Uber
Direct: from $7.99 a delivery, no monthly minimum, delivery "in under 2 hours, on the same day,
or scheduled up to 30 days in advance"; 81% of orders completed within 45 minutes in 2023
(https://merchants.ubereats.com/us/en/services/uber-direct/). Both are merchant products; an
individual needs a business-style account. Task marketplaces supply a person for an hour (rates
not verified; recalled as $25 to $50 an hour).
*Magic relevance:* a sealed object arriving at the door within a chosen window, carried by an
obviously independent courier. Timing is a window of tens of minutes, not a cue. A paid helper
must be an open collaborator who knows it is a magic trick.

**Sky-scale channels.** Skywriting is quoted from about $2,500 a message upward (marketing-blog
figures via https://www.thepricer.org/how-much-does-skywriting-cost/ ; an operator page,
https://www.vanwagneraerial.com/ , says only that it depends on length, location and date).
Drone shows and laser hire are by quote and not verified. Outside the brief's budget.

### 2.2 Programmable communication

**Telephony.** Twilio US: a local number is $1.15 a month; inbound calls $0.0085 a minute,
outbound $0.014; conference $0.0018 per participant-minute; answering-machine detection $0.0075
a call; **ConversationRelay** (speech in, text to your code, speech out) $0.07 a minute
(https://www.twilio.com/en-us/voice/pricing/us). SMS is $0.0083 a segment plus $0.003 to $0.005
carrier fee; MMS $0.022; business-style registration (A2P 10DLC) applies to application-sent
texts (https://www.twilio.com/en-us/sms/pricing/us).
**Real-time voice agents.** 2026 vendor roundups put an all-in phone agent at $0.07 to $0.30 a
minute, and one benchmark gives a median response latency of 680 ms, 1,180 ms at the 95th
percentile (search snippets; vendor sources such as
https://inworld.ai/resources/voice-agent-cost-per-minute-2026 and
https://www.assemblyai.com/blog/ai-voice-agent-pricing , not independently verified). The
cost structure is explained in
https://thenextweb.com/news/the-economics-of-a-voice-agent-what-a-minute-of-conversation-actually-costs .
*Magic relevance:* the "phone a stranger who names your card" plot ("The Wizard"; marketed app
versions exist, unverified) no longer needs a briefed friend at home. One person can own 20 to
50 numbers, each answered by a different convincing persona, each either hard-wired to one
outcome (the number is the out) or fed the outcome silently by the performer's pocket input.
*Deception properties:* the too-perfect theory is "that was your friend" or "that was a bot".
Counter with choice among many numbers found on physical objects, and with a persona who is busy,
slightly irritated and off-script. *Legal:* keep it inbound. Automated or artificial-voice
outbound calls to people who have not consented are restricted in the US (TCPA) and elsewhere.

**Calendar invitations, shared documents, scheduled messages.** Organiser-side edits propagate
into an invitation the guest accepted days ago; scheduled messages can be queued and cancelled.
These live on phone screens, which the commissioner dislikes, and belong to agent 12. One
structural point matters here: **cancellable schedules**. Queue N outputs for a fixed minute and
cancel N-1 after the choice, so that at reveal time the performer does nothing at all. This works
for scheduled texts and emails, pre-approved billboard campaigns (pause), and scheduled couriers.

**E-ink shelf labels as "printed" signage.** OpenEPaperLink is open firmware for surplus
electronic shelf labels: an ESP32 access point pushes images over 802.15.4; tags sleep at about
9 µA and check in every 40 seconds or more; a flashed 4.2 inch, 400 x 300, black-white-red tag
was $24 on Tindie, and raw surplus tags have sold for around €9
(https://github.com/OpenEPaperLink/OpenEPaperLink ,
https://www.tindie.com/products/electronics-by-nic/42-epaper-tag-for-openepaperlink ,
https://hackaday.com/2019/02/25/e-ink-price-tags-fall-off-store-shelves-onto-your-workbench).
A tag behind a mount in a frame reads as a printed card, with no glow, and changes while nobody
looks, 40 to 90 seconds after a command. Pointer only: agents 12 and 22 own in-room devices.

### 2.3 Public records and timestamps: what is honestly possible

| Mechanism | Cost | What it genuinely proves | Sibling visibility |
|---|---|---|---|
| OpenTimestamps (hash anchored in Bitcoin) | free, no account | this exact file existed before time T | none: stamps are unindexed |
| RFC 3161 timestamp authority | free to cheap | same, on the authority's word | none |
| Wayback "Save Page Now" | free | this URL showed this content at capture time (14-digit timestamp) | captures are listed per site; use unrelated hosts |
| Online notarisation | $25 first seal, 24/7, minutes | this person signed this page on this date | none |
| US copyright registration | $45 single author | a work with this title was filed on this date | public catalogue searchable by claimant |
| Domain registration | about $1 to $15 a year | the name was created on this date (registry record) | guessable sibling names can be looked up |
| Posted mail with a cancelled stamp | $1 to $5 | this sealed item passed through the post around this date | none, if the spectator holds it |
| Geocache or tracked book with public logs | about $10 | strangers found this container on these dates | none |

Sources: https://opentimestamps.org/ ; https://en.wikipedia.org/wiki/Trusted_timestamping ;
https://help.archive.org/help/save-pages-in-the-wayback-machine/ ;
https://archive.org/help/wayback_api.php ; https://www.notarize.com/pricing ;
https://www.copyright.gov/about/fees.html ; https://www.geocaching.com/play/guidelines .

**Structure of a multiple-out method built on genuine commitments.** Make K real, dated
commitments, one per outcome; after the choice, surface exactly one. Nothing false is told to
any platform. It works to the extent that (1) the channel has no public index that lists the
siblings, (2) the sibling names cannot be guessed and tried, and (3) the path by which the
spectator reaches the right one looks unforced. OpenTimestamps is technically perfect on (1) and
(2), since anyone can stamp a million files for nothing, and for that reason it proves nothing
to an informed spectator. This is the "publish every outcome, delete the misses" social-media
prediction, which tech-literate audiences already suspect. Three defences:
- **Spectator-held commitments.** One posted envelope in one person's hands has no room for
  siblings. The method then has to be a force, a controlled outcome, or a hidden late change
  inside the envelope (delayed inks and self-erasing evidence: agents 8 and 17).
- **Siblings distributed across the audience.** Every guest holds one sealed, posted envelope;
  each is a different out (concept 4.2).
- **Commit to a key, not an outcome.** A posted string of letters "decoded" by a short keyword
  revealed on the night can decode to anything, because the keyword is chosen afterwards: the
  out index shrinks from 52 objects to 52 memorised words. Speculative; agent 23's slice.

**Timelock encryption.** drand, a distributed beacon run by the League of Entropy, lets anyone
encrypt to a future round; nobody, the sender included, can decrypt until the network publishes
that round's signature (quicknet rounds every 3 s per the tlock documentation, search snippet).
Tools: tlock, tlock-js, and a public web app at https://timevault.drand.love/
(https://docs.drand.love/docs/timelock-encryption/). It proves no late change to a ciphertext
the spectator already holds; it does not prove there was one ciphertext.

**Random beacons and lotteries are unpredictable. Say so.** NIST's beacon publishes a signed,
time-stamped, hash-chained 512-bit pulse (reference cadence once a minute); drand is "publicly
verifiable, unbiased and unpredictable" (https://csrc.nist.gov/projects/interoperable-randomness-beacons ,
https://docs.drand.love/docs/overview/). Their use in magic is the reverse of prediction: a
public, obviously fair random source to drive a selection whose every outcome is covered.
Lottery "predictions" are late loading or camera work, not prediction (2.7).

**Requires deceiving a platform or the public; avoid.** Setting a false earlier publication date
on a self-published book or post; editing a reference site; false classified or death notices;
fake reviews or map entries; forged commit dates presented as a host's record; submitting a
prediction to a sign owner disguised as an advert for a non-existent business.

### 2.4 Places that hold an object for you

- **Amazon Locker.** Pickup by a 6-digit code or QR sent by email or text; three calendar days
  to collect; anyone holding the code can open the door (university locker guides say to forward
  the email to whoever collects). Only Amazon-fulfilled orders can go in; you cannot deposit your
  own object. Sources: https://en.wikipedia.org/wiki/Amazon_Locker ,
  https://www.aboutamazon.com/news/operations/how-to-use-amazon-locker ,
  https://www.kings.uwo.ca/kings/assets/File/depts/finance/Central%20Services/Amazon%20Locker%20Instructions%20and%20FAQs.pdf .
  Use: a specific stock item (a book, a deck, a toy), or a self-published book, waiting in a
  steel box across town that the performer has visibly never been near. Carrier lockers that
  accept your own parcel (locker-to-locker services in the UK and Europe) and named-recipient
  hold-at-counter services were not verified today.
- **Luggage storage.** Bounce: from $6.95 a day, "32,000+ storage spots across 4,000+ cities",
  collected by showing the booking confirmation to shop staff (https://bounce.com/). Whether a
  third party may collect was not confirmed; ask the shop openly.
- **Smart key boxes and locks.** igloohome's "algoPIN" codes are computed offline like a bank
  token: one-time codes are valid for a 24-hour window and die after one use; API from $2 per
  lock per month; hardware roughly €135 for a deadbolt at one reseller
  (https://www.igloohome.co/pricing ,
  https://docs.seam.co/latest/device-and-system-integration-guides/igloohome-locks/creating-igloohome-offline-access-codes).
  A $12 mechanical combination box does the same job with no evidence of electronics.
- **Geocaches.** A cache is published after volunteer review (allow several days), must be
  161 m from other caches, must hold a logbook, must be meant to last three months or more, with
  landowner permission and no commercial or cause-promoting content
  (https://www.geocaching.com/play/guidelines). Its public page then accumulates dated logs from
  strangers. This is the only cheap channel where **independent third parties timestamp the
  performer's container for free**.
- **Staff as open collaborators.** A restaurant, hotel desk or cloakroom that has been asked to
  hold an envelope "for a guest who will ask for it" is the oldest version and still the most
  reliable. Alternate-reality-game designers also used shops and cafés as pick-up points (2.7).

### 2.5 Data that is knowable or controllable

- **Stream latency.** Standard HLS runs about 15 to 30 s behind, low-latency HLS 2 to 8 s,
  WebRTC under 0.5 s (https://www.dacast.com/blog/hls-streaming-protocol/). The same vendor
  reports streams of the February 2025 Super Bowl running 26 to 78 s behind the field (search
  snippet). Betting has a name for exploiting venue-to-broadcast delay: courtsiding
  (https://en.wikipedia.org/wiki/Courtsiding). Anyone with a faster path to the same event
  (broadcast radio, a data feed, a lower-latency stream) is living tens of seconds in the
  audience's future.
- **Aircraft.** OpenSky's free REST API returns callsign, ICAO address, origin country,
  position, altitude, speed and heading for a bounding box, at 10 s resolution anonymously and
  5 s with an account, 400 to 4,000 queries a day
  (https://openskynetwork.github.io/opensky-api/rest.html).
- **Buses, trams and trains.** GTFS-realtime feeds carry, per vehicle, a rider-visible `label`
  and `license_plate`, its position and current stop, and per stop a predicted arrival time
  with an explicit uncertainty (https://gtfs.org/documentation/realtime/reference/). The number
  painted on the next bus is public several stops before it arrives.
- **Satellites and the Sun.** Heavens-Above gives 10-day pass predictions for the ISS and other
  bright satellites (https://www.heavens-above.com/). The Sun moves 15 degrees an hour, 0.25
  degrees a minute, so a sunbeam through a 5 mm hole crosses a wall 3 m away at about 13 mm a
  minute: a free pointer that reaches a pre-marked spot at a computed minute. Solar position
  algorithms are accurate to a small fraction of a degree (reference page unreachable).
- **Commissioned satellite imagery.** SkyFi sells tasked optical images to anyone with a card:
  "starting at $200"; a 2025 price sheet lists 31 to 50 cm imagery at $12 per km² with a 25 km²
  minimum ($300), priority $24 per km²; you set a capture window and acceptable cloud cover and
  are refunded if the image is cloudier or not captured; delivery about 48 hours after capture
  (https://www.skyfi.com/pricing , https://www.skyfi.com/faqs ,
  https://learn.skyfi.com/?p=506 ). A reseller notes direct SkySat tasking minimums of $15,000
  (https://apollomapping.com/blog/an-update-on-skysat-tasking-pricing-and-video-capabilities),
  so marketplaces are the only hobby route. At 50 cm per pixel a legible letter needs strokes
  about 1 m wide and 5 m tall (my estimate). Free Sentinel-2 imagery is 10 m per pixel every 5
  days (https://en.wikipedia.org/wiki/Sentinel-2): a marker would need to be 50 m across.
- Tides, timetables, eclipses and sunrise times are public and exact but everyone knows it; they
  are cues and timers, not mysteries.

### 2.6 Personalisation at speed, with consent

Between an RSVP and a dinner a week later, using only what the guest supplies (name, birthday,
a favourite book, a photograph they send), one person can commission: a robot-handwritten card
($3.75 plus stamp); a one-off deck with their face on the court cards ($16.95); a facsimile
newspaper from their birth date on real newsprint (2 to 8 working days), or the genuine paper
($39.99, 5 days); a paperback "novel" with their name in the text ($2.30 to $4 to print); a
jigsaw, mug or shirt through a print API (4 to 9 days); 50 fortune cookies sorted per guest.
Privacy line: ask openly ("for the place cards"). Do not harvest social media.

### 2.7 Prior art

- **Covering every outcome with people.** Derren Brown's *The System* (2008) appeared to give a
  woman a run of winning horse-racing tips; the reveal was that he "used different people to
  cover all possible outcomes" (https://en.wikipedia.org/wiki/Derren_Brown). This is the
  distributed-siblings architecture at television scale.
- **Lottery prediction.** Brown's 2009 live lottery stunt showed the "prediction" only after the
  draw (legally he could not show it before), offered a wisdom-of-crowds explanation that
  mathematicians dismissed, and is widely theorised to be split-screen camera work
  (https://en.wikipedia.org/wiki/Derren_Brown:_The_Events ,
  https://www.cs4fn.org/magic/derrenbrown.php). Late loading, not prediction.
- **Prediction carried on the body for years.** David Blaine has described a playing-card
  prediction tattooed in ink visible only under a certain light, made long before use
  (https://www.geo.tv/latest/598782-magician-david-blaine-admits-to-forgetting-about-one-invisible-tattoo).
- **Working magicians' advice** still lists the local newspaper front page, a sports result or
  lottery numbers on live radio as the standard publicity predictions
  (https://www.oneahead.com/p/magicians-the-time-is-now). Billboard and headline reveals by
  other television magicians are recalled but could not be verified today (unverified).
- **Alternate-reality games have the deepest craft.** *The Beast* (2001) used faxes, fake ads
  and voicemail. *I Love Bees* (2004) published 210 GPS coordinates with time codes that turned
  out to be payphones that would ring; a live actor took some calls and improvised; about 9,000
  people took part physically; earlier-game veterans were recruited with posted jars of honey.
  *Year Zero* (2007) left USB drives in concert washrooms.
  (https://en.wikipedia.org/wiki/I_Love_Bees , https://en.wikipedia.org/wiki/Alternate_reality_game).
  A cake with a ringing phone inside, collected from a bakery under a given name, is recalled
  from the 2007 *Dark Knight* campaign (unverified).
- **Mailed-object experiences.** The Mysterious Package Company (238,000+ experiences sold) posts
  weathered documents, period magazine pages, sealed packets and props in staged mailings;
  Emily Short's review notes that postal delay itself becomes the pacing and that opening a
  sealed thing destructively carries a "transgressive thrill"
  (https://www.mysteriouspackage.com/ ,
  https://emshort.blog/2016/06/29/mysterious-package-company-and-narrative-of-objects/).
  *Ten Parcels* (2020) sent ten hand-addressed boxes over months, and used **tracking numbers
  and different shipping origins** (Los Angeles, Philadelphia, Amityville) as part of the fiction
  (https://www.noproscenium.com/ten-parcels-and-the-intimacy-of-objects-in-the-time-of-quarantine/).
  A hobbyist's mailed "feelie" box cost €4.60 a unit before postage
  (https://intfiction.org/t/murder-in-the-mail-feelie/12992).
- Transferable techniques: the return address and carrier tracking page are part of the prop;
  pace by post; let the recipient break a seal; have a live human (now an agent) on the phone;
  send the audience to a place at a time rather than bringing the thing to them.

### 2.8 Scale and cost model

| Channel | Minimum cost | Lead time | Unique per unit? | Live trigger from pocket? | Approval or failure risk | Practical outs |
|---|---|---|---|---|---|---|
| Posted card or letter (API) | $0.83 to $5 | 7 to 10 days | yes | no | postal delay | 1 per recipient; N recipients |
| Billboard play (Blip) | cents; $5 to $20 a day | 1 to 3 business days approval, then about 10 min cycles | yes, per creative | yes (campaign switch; untested) | owner rejection; lost auction | 5 to 20 approved creatives |
| Print-on-demand item | $2 to $30 | 4 to 9 days | yes | no | misprint, delay | pages or parts within one item |
| Facsimile newspaper | about £20 to £30 (unverified) | 2 to 8 working days | yes | no | customs | dozens (small ads) |
| Real classified ad | $15 to $50 | 2 to 5 days | n/a | no | desk may refuse odd copy | 1 |
| Courier drop | $8 to $15 | 45 min to 2 h, or scheduled | yes | yes | arrival window is loose | 1 to 3 (cancel the rest) |
| Owned phone number plus agent | $1.15 a month plus $0.07 to $0.30 a minute | minutes to set up | yes | yes (and needs none if the number is the out) | "it's a bot" | 20 to 50 numbers |
| Text message | about $0.012 | seconds | yes | yes | registration, filtering | unlimited, but it is a screen |
| Lock box, cache, cloakroom, luggage desk | $0 to $12 each | hours to a day | yes | no | theft, weather, staff error | 4 to 10 across a venue or district |
| Amazon Locker | price of item | 1 to 5 days; held 3 days | stock items only | no | locker full, item delayed | 2 to 4 |
| Timestamps (OTS, Wayback, notary) | free to $25 | minutes to hours | yes | no | none | unlimited, and worthless to a sceptic for that reason |
| Tasked satellite image | $200 to $300 | days to weeks, weather | yes | no | cloud | 1 |

## 3. Capability primitives

1. *Now possible:* for $0.91 and 7 to 10 days, make a unique printed card appear in a named
   person's letterbox, carried by the post. *Because:* Lob-class mail APIs. *Before:* hand-post
   it yourself, with your own handwriting and local postmark. *Primitives:* delay, prove
   ordinariness, duplicate.
2. *Now possible:* for about $5 each, twelve different "handwritten" sealed cards in twelve
   guests' hands a week ahead. *Because:* pen-robot services with APIs. *Before:* an evening of
   forgery. *Primitives:* duplicate, conceal (siblings), delay.
3. *Now possible:* know to within one business day when a remote person's letter lands.
   *Because:* "Processed for Delivery" webhooks; Informed Delivery. *Before:* guess.
   *Primitives:* know.
4. *Now possible:* for under $1 a play and 1 to 3 business days of approval, put a chosen image
   on a specific roadside billboard at a chosen time of day. *Because:* per-play self-serve
   signage. *Before:* four-figure campaign minimums. *Primitives:* tell, transform (public space).
5. *Now possible:* hold 5 to 20 pre-approved billboard images and choose which runs within about
   10 to 20 minutes of a live decision (untested). *Because:* dashboards and 10-minute auctions.
   *Before:* impossible. *Primitives:* control choice (outs), delay.
6. *Now possible:* for $2.30 to $4 and 1 to 2 weeks, a real paperback with a barcode, sold and
   delivered by a major retailer, with any text on any page. *Because:* KDP, Lulu. *Before:* a
   $500 short run, or rebinding. *Primitives:* prove ordinariness, control choice.
7. *Now possible:* a gimmicked deck, in any order, that the spectator orders from a third-party
   printer and receives sealed, never touched by the performer. *Because:* one-deck print shops.
   *Before:* every gaffed deck came from the magician's pocket. *Primitives:* prove ordinariness,
   know.
8. *Now possible:* every copy of a printed thing different, at no extra cost, tracked by order
   number. *Because:* per-order print files. *Before:* identical runs. *Primitives:* know,
   duplicate.
9. *Now possible:* for about £25 and a week, a newsprint newspaper carrying any date, with any
   small ad on any page. *Because:* single-copy digital newsprint. *Before:* 1,000-copy minimum.
   *Primitives:* prove ordinariness, conceal (outs in dense text).
10. *Now possible:* for $40 and 5 days, the genuine newspaper from a guest's birth date.
    *Because:* archive retailers. *Before:* dealers and luck. *Primitives:* prove ordinariness.
11. *Now possible:* for $37 to $72, fifty wrapped fortune cookies with up to five (or
    guest-sorted) messages, in about a week. *Because:* custom confectioners. *Before:*
    re-stuffing cookies with tweezers. *Primitives:* conceal, prove ordinariness.
12. *Now possible:* for $8 to $10, an independent courier brings a sealed object to a door
    within 45 minutes to 2 hours of a pocket trigger, or in a window booked up to 30 days ahead.
    *Because:* delivery-as-a-service. *Before:* a friend with a car. *Primitives:* move, delay.
13. *Now possible:* for $1.15 a month each, own any number of real phone numbers, each answered
    in under a second by a different improvising voice. *Because:* telephony APIs and real-time
    voice models. *Before:* one briefed friend, one number. *Primitives:* tell, control choice.
14. *Now possible:* queue N timed outputs and cancel N-1 silently, so the reveal fires with the
    performer's hands empty. *Because:* cancellable scheduled sends, pausable campaigns, bookable
    couriers. *Before:* an assistant backstage. *Primitives:* delay, control choice, erase.
15. *Now possible:* for nothing, a third-party-verifiable proof that a file existed before a
    date, for as many files as you like, with no list of them anywhere. *Because:*
    OpenTimestamps. *Before:* a notary per document. *Primitives:* delay, conceal (siblings).
16. *Now possible:* give a spectator a file that nobody on Earth, you included, can open before
    a chosen second. *Because:* drand timelock encryption. *Before:* a sealed envelope and trust.
    *Primitives:* delay, prove ordinariness.
17. *Now possible:* for $25 in ten minutes at any hour, a notary's dated seal on any page.
    *Because:* remote online notarisation. *Before:* office hours. *Primitives:* prove
    ordinariness.
18. *Now possible:* for about $10 and a few weeks, a container in a public place whose presence
    since a given date is attested by strangers' dated logs. *Because:* geocaching's listing and
    log system. *Before:* "trust me, it's been there for months". *Primitives:* prove
    ordinariness, delay, swap (off-stage, the day before).
19. *Now possible:* for the price of the item, a specific object waiting in a steel locker
    across town, opened by a 6-digit code that can be handed to anyone, for 3 days. *Because:*
    parcel lockers. *Before:* a confederate shopkeeper. *Primitives:* hold, delay.
20. *Now possible:* for $7 a day or a $12 box, a held object at any of 32,000 shops, or behind a
    one-time code. *Because:* luggage-storage networks, offline-code locks. *Before:* station
    lockers. *Primitives:* hold, conceal (spatial outs).
21. *Now possible:* know what a "live" stream will show 15 to 78 s before the room does.
    *Because:* HLS latency against radio and data feeds. *Before:* satellite-delay tricks known
    to broadcasters only. *Primitives:* know, delay.
22. *Now possible:* know the flight number, origin and registration of the aircraft that will be
    overhead in 3 to 5 minutes. *Because:* free ADS-B APIs. *Before:* nothing. *Primitives:* know.
23. *Now possible:* know the fleet number and plate of the next bus, and its arrival to within
    a stated uncertainty, several stops out. *Because:* GTFS-realtime. *Before:* nothing.
    *Primitives:* know, control chance.
24. *Now possible:* for $200 to $300 and days to weeks, an independent photograph from orbit of
    a ground marker 15 to 30 m across. *Because:* satellite-tasking marketplaces. *Before:*
    government customers only. *Primitives:* prove ordinariness, tell.
25. *Now possible:* a sign that reads as printed card and silently changes within 40 to 90 s,
    for $10 to $25, running for years on coin cells. *Because:* reflashed shelf labels.
    *Before:* glowing screens. *Primitives:* transform, erase.
26. *Now possible:* an image printed on the surface of a guest's drink in under 10 seconds, sent
    from an app, at a café that owns the machine. *Because:* foam printers. *Before:* latte art.
    *Primitives:* tell.

## 4. Effect concepts

Levels: 1 = the phenomenon is the effect; 2 = hidden input to a classical method; 3 = new
architecture. Nine of the eleven are level 2 or 3.

### 4.1 The seven-second past (level 3)

*Effect.* Friends are watching a match, a race or a live draw on the television. Before each
decisive moment the performer writes on a card, dates it to the second from the on-screen clock,
and hands it to someone. The card is right, repeatedly. They keep the cards.
*Method.* The room watches an ordinary streaming app, 15 to 60 s behind the event. A phone in
the performer's pocket follows a faster source (broadcast radio commentary, a low-latency data
feed, a different stream) and passes events to a wrist tap or bone-conduction cue (agents 10 and
21). The performer writes openly, in plain sight, before the room sees it.
*Bill of materials.* Phone, existing haptic or audio cue device, a script watching a feed. $0 to
$50. *Difficulty.* Low to moderate: measure both delays on the day; they drift.
*Risks.* Someone has a faster feed or a phone buzzing with score alerts (ask for phones in a
bowl "so nobody spoils it"); the host switches to broadcast television. Do not use it to bet.
*Novelty.* The principle is known in betting; no magic use was found. Believed new as a
structured routine.

### 4.2 Twelve envelopes, one year (level 3)

*Effect.* Every guest received a hand-addressed card in the post a week ago, with a request to
bring it sealed. At dinner one guest makes a free choice among twelve things (twelve wines on a
list, twelve months, twelve guests). The performer names one guest: "You've had mine since
Tuesday." That guest tears open their own stamped, cancelled envelope. It names the choice. The
rest go, still sealed, into a tin "to be opened at next year's dinner".
*Method.* The audience is the index. Twelve different robot-handwritten cards go out through the
API, one outcome each; the performer memorises who holds what. Next year's opening is a second
show: each remaining card also carries a line that will be true then (a toast, a place setting).
*Bill of materials.* 12 cards at about $4 to $5 posted: $50 to $60. *Difficulty.* Low.
*Risks.* A guest forgets or opens theirs (post two per household; make the inner card harmless
out of context: "It will be the Rioja. Open nothing else."); two guests compare afterwards, so
the tin matters. Late post: send ten days ahead and watch tracking.
*Novelty.* Distributed outs exist in stage mentalism (envelopes under chairs); posted,
audience-held, cancelled-stamp outs with a year-long second act were not found.

### 4.3 The cache that was always there (level 3 evidence, level 2 method)

*Effect.* A word or card is chosen at home. The spectator is given coordinates. On their own
phone the listing shows a geocache hidden fourteen months ago, found by twenty-three strangers,
several mentioning "the little sealed tube marked for someone called M". They walk there
alone, find it, break the wax, and read their choice. They keep the tube.
*Method.* The cache is genuine and long-lived. A dummy sealed tube has always been in it, so
strangers' logs honestly describe it. The outcome is forced (any classical force), or the tube
is exchanged by the performer the afternoon before for one of a few prepared outs, which is the
whole secret action, done a day early with nobody present.
*Bill of materials.* Container, logbook, tubes, wax: $10. Months of patience.
*Difficulty.* Low. *Risks.* Cache muggled or soaked; a finder opens the tube (the dummy says
only "not yet"). Stay within the listing guidelines: a real cache, with permission, no
promotion. *Novelty.* Not found in magic literature searched; believed new.

### 4.4 Wrong number (level 2 to 3)

*Effect.* A bowl of real-looking business cards and takeaway menus "collected over the years".
The spectator thinks of a card, picks any one, and dials it on their own phone, on speaker. A
harassed florist answers, is talked into playing along, and names the card.
*Method.* Every number in the bowl is the performer's. All route to one voice-agent backend with
a different persona per number. The thought-of card reaches the server from a pocket input
(agent 10), or, with no electronics on the performer, each number is hard-wired to one card and
the performer steers which card the spectator takes from the bowl after the card is named
(a 20 to 30 out index disguised as clutter). The agent stalls naturally for two sentences while
the input lands. The spectator keeps the business card; the number still answers next week.
*Bill of materials.* 25 numbers at $1.15 for one month, calls at about $0.15 a minute, printing:
about $50. *Difficulty.* Moderate (prompting and latency tuning). *Risks.* "It's a bot": keep
calls under 40 s, add shop noise, let the persona be wrong once about something else. Inbound
only. *Novelty.* The plot is a century old; many simultaneous numbers, each a persistent
believable person with no human helper, is new.

### 4.5 The book you bought yourself (level 3)

*Effect.* The invitation says: "Bring a paperback. If you have nothing, this one is cheap," with
an ordinary retail link. At dinner the guest opens their own copy, delivered by the retailer,
to any page; the performer, across the room, tells them the word they are looking at, then the
sentence.
*Method.* The performer wrote and published the book months ago under a pen name. It is a
classical book-test text (restricted first words, or a long-word index the performer has
memorised, or a page-number-to-word rule) printed and delivered by the retailer. The supply
chain proves ordinariness. A deck version: the guest orders "a nice deck" from a public
print-shop listing; it arrives stacked and marked.
*Bill of materials.* $0 to publish; guest pays about $6 to $8, or the performer gifts copies.
*Difficulty.* Writing a readable gimmicked book is the real work; an LLM helps (agent 12).
*Risks.* A guest brings a different book (carry a second method); someone searches the author.
Publish honestly: real date, real pen name, no false claims in the listing.
*Novelty.* Gimmicked book-test books are standard dealer items; having the spectator source it
from a neutral retailer was not found and is believed new at hobby scale.

### 4.6 Small ads from the day you were born (level 2 to 3)

*Effect.* The birthday guest is handed the newspaper from the day they were born. They are asked
to think of any card, then to turn to the small ads on a named page. One reads: "LOST, between
the station and the canal, the queen of hearts. Finder please hold until [tonight's date] and
give to [their name]."
*Method.* A facsimile on real newsprint, built from archive scans, with a classified page that
is the performer's. Fifty-two (or, after a narrowing force, eight) ads each mention a card in
passing ("bridge set, wants jack of clubs") scattered over three dense pages; the performer
knows where each is and directs "page 14, third column, near the bottom". Sold as a keepsake;
the density of real small print hides the siblings from a casual reread.
*Bill of materials.* One newspaper copy, about £25 (unverified), a week's lead. A genuine
original ($39.99) can be shown first and exchanged for the facsimile. *Difficulty.* Layout
work. *Risks.* A careful rereader finds two card ads; reduce outs, vary wording.
*Novelty.* Multiple-out newspaper predictions are old; a single-copy personalised facsimile was
not affordable before.

### 4.7 Eight seconds of sky (level 3; must be tested)

*Effect.* Walking to the bar, a friend names one of the group. Fifteen minutes later the
roadside sign opposite shows, for eight seconds, "IT WAS ALWAYS GOING TO BE PRIYA". They
photograph it.
*Method.* One creative per person was approved days earlier. A pocket action enables the one
campaign for that sign with a generous bid, and the group is walked into view during the next
auction windows. *Bill of materials.* $5 to $20. *Difficulty.* Low technically; high in
logistics. *Risks.* Owner rejects creatives; auction lost; 10-minute granularity; needs a Blip
sign near home. A backup reveal is essential. *Novelty.* Billboard reveals are television
staples; a live multiple-out one run by one person for $20 is new if the latency holds.

### 4.8 The 20:11 from Lisbon (level 2)

*Effect.* In the garden the performer writes something, folds it under a glass, and says,
"Wait." Minutes later a plane crosses overhead. The paper gives its origin city, flight number
and the registration painted on it, which the guests then look up themselves.
*Method.* A script polls a free ADS-B API for aircraft whose track will pass within a kilometre
in 3 to 6 minutes and whispers the details (earpiece or a glance at a watch). A bus-stop version
uses the transit feed's vehicle label.
*Bill of materials.* $0. *Difficulty.* Low. *Risks.* Guests know flight-tracking apps exist, so
the writing must clearly precede any sign of the plane, and the performer's phone should be
visibly on the table, face down; stronger with a week-old posted card naming the scheduled
flight and tonight's writing adding the registration. *Novelty.* Small; a good opener.

### 4.9 Fortune for the table (level 2)

*Effect.* Cookies arrive with the bill. Each guest's fortune addresses them by name; one
predicts the dessert its owner chose ten minutes ago; the "lucky numbers" on another match the
serial number of the note its owner has been guarding all evening.
*Method.* Guest-sorted custom cookies ordered a week ahead, handed out by an open-collaborator
waiter in seat order. Named fortunes are consent-based personalisation; the dessert is a menu
force or a five-message out set; the banknote is a classical switch. The factory wrapper carries
the conviction. *Bill of materials.* 50 cookies about $40 plus the $35 sorting fee and shipping.
*Difficulty.* Low. *Risks.* Seating changes; broken cookies (order spares).
*Novelty.* Fortune-cookie loads are old; sealed, factory-made, per-guest ones are newly cheap.

### 4.10 The photo counter (level 3; details unverified)

*Effect.* A guest draws a doodle on a napkin and keeps it. The performer "sends it out". An hour
later a courier rings the bell (or the group passes a print counter) with a sealed envelope
bearing the guest's name: a glossy print of the doodle.
*Method.* A concealed camera (agent 22) captures the doodle; a pocket trigger submits it to a
same-day print or courier pipeline. Present it as transmission happening now, because the label
will show the order time. *Bill of materials.* $10 to $25 per performance.
*Difficulty.* Moderate. *Risks.* Same-day photo ordering by API and third-party pickup rules
were not verified; arrival is a window, so it must be a running thread through the evening.
*Novelty.* Believed new in this form.

### 4.11 Seen from orbit (level 1 to 2)

*Effect.* For a significant birthday: a framed, provider-stamped satellite image of the
family's field, dated last week, with the guest's "freely chosen" word laid out in white.
*Method.* A force, 60 m of white fabric, landowner permission, and a $200 to $300 tasking order
with a cloud-cover refund. *Risks.* Weather, weeks of slack needed, legibility at 50 cm.
*Novelty.* New to hobbyists; the method is nothing but a force, so keep it for sentiment.

## 5. Dead ends and overhyped items

- **Blockchain or archive timestamps as proof.** Genuine, free, and exactly as convincing as
  "I made fifty-two". The audience able to verify one is the audience that knows the trick.
- **Predicting beacons and lotteries.** Unpredictable by design. Every lottery routine is late
  loading, a switch or camera work.
- **Depositing your own object in an Amazon Locker.** Not possible; only their parcels go in.
- **Skywriting, drone shows, cinema and stadium screens.** Four figures and up, weather and
  permits. Not a hobby channel.
- **Anything on-demand as a prediction.** Receipts, labels, order emails and tracking pages all
  carry the order time.
- **Billboard on a finger-snap.** Auction cycles and approval make it a 10 to 20 minute, 1 to 3
  day channel.
- **Outbound AI calls or texts to guests' phones.** Consent and registration rules, spam
  filtering, and it ends on a phone screen.
- **Public payphones and shop phones** (the *I Love Bees* technique): not owned, out of scope.
- **Sentinel-class free satellite imagery.** 10 m pixels; a marker would be the size of a
  football pitch.
- **Back-dated listings, planted reference edits, fake notices.** Deceive a platform or the
  public, break terms, and are discoverable. Not needed.
- **ISS passes and tide tables as mysteries.** Too widely known; use as timers.

## 6. Open leads

- A $20 Blip experiment: do sign owners approve cryptic personal creatives, and how many minutes
  from campaign switch to first play?
- Same-day photo and print counters with online ordering: order-to-ready time, whether a named
  third party can collect, and what the label reveals. Not verified today.
- Carrier lockers that accept your own parcel (locker-to-locker), named-recipient hold-at-counter
  services, poste restante: price, hold time, ID rules.
- Does Lob mail carry a dated mark? Does a third-party print shop ship a deck in file order?
  Both decide whether concepts 4.2 and 4.5 work as written.
- Personalised postage stamps by country; temporary tattoos by post; printed cakes; engraved
  items with rush options: all unpriced here.
- Single-copy price lists for Newspaper Club, The Game Crafter and Lulu (pages needed scripts).
- Measured, same-day delay between broadcast radio, terrestrial television and each major
  streaming app for one event, to size concept 4.1.
- "Commit to a key, not an outcome" with posted ciphertext (agent 23), and grille-style decodes.
- Sunbeam-as-pointer: a pre-surveyed room where sunlight selects an object at a computed minute.
- Self-serve screens outside the US, and the Times Square public-slot service.
- Costs and practice of small immersive-theatre companies that run phone-call and mail shows.

## 7. Sources

Opened directly:
- https://www.blipbillboards.com/ - Blip home: no minimum, 8 s plays, from $0.01.
- https://help.blipbillboards.com/get-started-with-blip - moderation times, 10-minute auctions.
- https://www.blipbillboards.com/blog/outdoor-billboard-advertising/ - 3,500+ screens, dayparts.
- https://www.lob.com/pricing - postcard $0.905, letter $0.828, $0 plan.
- https://help.lob.com/print-and-mail/getting-data-and-results/tracking-your-mail - events, timing.
- https://www.handwrytten.com/pricing/ - robot-handwritten card prices, API.
- https://www.usps.com/manage/informed-delivery.htm - morning greyscale mail previews, free.
- https://www.twilio.com/en-us/voice/pricing/us - numbers, per-minute rates, ConversationRelay.
- https://www.twilio.com/en-us/sms/pricing/us - SMS and MMS rates, carrier fees.
- https://thenextweb.com/news/the-economics-of-a-voice-agent-what-a-minute-of-conversation-actually-costs - voice-agent cost structure.
- https://www.newspaperclub.com/ - newsprint from 1 copy, 2 to 8 working days.
- https://www.newspaperclub.com/choose/orders-and-delivery/delivery - delivery rules.
- https://www.printful.com/shipping - 2 to 5 business days fulfilment, shipping times.
- https://developers.printful.com/docs/ - Orders API, per-item print files.
- https://www.makeplayingcards.com/design/custom-blank-card.html - 1 deck $16.95, per-card art.
- https://www.thegamecrafter.com/make/pricing - component pricing (partially rendered).
- https://kdp.amazon.com/en_US/help/topic/G201834340 - paperback print-cost formula.
- https://www.lulu.com/pricing - print API exists (calculator not rendered).
- https://www.historic-newspapers.com/ - original dated newspapers from $39.99.
- https://www.fancyfortunecookies.com/Articles.asp?ID=355 - custom cookie minimums and timing.
- https://www.drinkripples.com/ - drink-surface printer, under 10 s a print.
- https://developer.doordash.com/en-US/docs/drive/overview/pricing_payment - $9.75 base delivery.
- https://merchants.ubereats.com/us/en/services/uber-direct/ - from $7.99, scheduling.
- https://opentimestamps.org/ - free blockchain timestamping.
- https://en.wikipedia.org/wiki/Trusted_timestamping - what timestamps prove.
- https://help.archive.org/help/save-pages-in-the-wayback-machine/ - Save Page Now.
- https://archive.org/help/wayback_api.php - capture timestamps.
- https://docs.drand.love/docs/timelock-encryption/ - timelock encryption, tools, assumptions.
- https://docs.drand.love/docs/overview/ - drand guarantees.
- https://csrc.nist.gov/projects/interoperable-randomness-beacons - NIST beacon format.
- https://www.notarize.com/pricing - $25 online notarisation, 24/7.
- https://www.copyright.gov/about/fees.html - $45 and $65 registration fees.
- https://www.geocaching.com/play/guidelines - cache placement rules.
- https://en.wikipedia.org/wiki/Amazon_Locker - code, three-day limit.
- https://bounce.com/ - luggage storage from $6.95 a day.
- https://www.skyfi.com/pricing and https://www.skyfi.com/faqs - tasking from $200, refunds.
- https://en.wikipedia.org/wiki/Sentinel-2 - 10 m, 5-day revisit, free.
- https://openskynetwork.github.io/opensky-api/rest.html - aircraft state API and limits.
- https://gtfs.org/documentation/realtime/reference/ - vehicle label, plate, arrival uncertainty.
- https://www.heavens-above.com/ - 10-day satellite pass predictions.
- https://www.dacast.com/blog/hls-streaming-protocol/ - streaming latency figures.
- https://en.wikipedia.org/wiki/Courtsiding - exploiting venue-to-broadcast delay.
- https://github.com/OpenEPaperLink/OpenEPaperLink - shelf-label firmware.
- https://www.tindie.com/products/electronics-by-nic/42-epaper-tag-for-openepaperlink - tag spec, $24.
- https://en.wikipedia.org/wiki/Derren_Brown - The System, The Events.
- https://en.wikipedia.org/wiki/I_Love_Bees - payphones, coordinates, live operator.
- https://en.wikipedia.org/wiki/Alternate_reality_game - The Beast, Year Zero and others.
- https://emshort.blog/2016/06/29/mysterious-package-company-and-narrative-of-objects/ - mailed-object craft.
- https://www.noproscenium.com/ten-parcels-and-the-intimacy-of-objects-in-the-time-of-quarantine/ - Ten Parcels.
- https://www.mysteriouspackage.com/ - product range, 238,000+ sold.

Seen in search results (snippet only):
- https://www.blipbillboards.com/blog/effective-billboard-advertising-10day/ - budgets.
- https://learn.skyfi.com/?p=506 and https://skyfi.com/files/SkyFi_Pricing_2025.pdf - 25 km² minimum, $12 per km².
- https://apollomapping.com/blog/an-update-on-skysat-tasking-pricing-and-video-capabilities - $15,000 minimum.
- https://www.igloohome.co/pricing - API from $2 per lock per month.
- https://docs.seam.co/latest/device-and-system-integration-guides/igloohome-locks/creating-igloohome-offline-access-codes - offline one-time codes.
- https://www.aboutamazon.com/news/operations/how-to-use-amazon-locker - locker pickup.
- https://www.kings.uwo.ca/kings/assets/File/depts/finance/Central%20Services/Amazon%20Locker%20Instructions%20and%20FAQs.pdf - code can be given to another person.
- https://inworld.ai/resources/voice-agent-cost-per-minute-2026 and https://www.assemblyai.com/blog/ai-voice-agent-pricing - voice-agent cost ranges.
- https://hackaday.com/2019/02/25/e-ink-price-tags-fall-off-store-shelves-onto-your-workbench - surplus shelf labels.
- https://cdn.startribunecompany.com/wp-content/uploads/2026/03/ClassifiedRB_2026_0213.pdf - classified deadlines.
- https://westernwaynenews.com/advertise/ - $15 for 15 words.
- https://www.thepricer.org/how-much-does-skywriting-cost/ and https://www.vanwagneraerial.com/ - skywriting cost.
- https://www.patreon.com/posts/32873289 - 2020 Game Crafter deck price.
- https://intfiction.org/t/murder-in-the-mail-feelie/12992 - €4.60 feelie box.
- https://en.wikipedia.org/wiki/Derren_Brown:_The_Events and https://www.cs4fn.org/magic/derrenbrown.php - lottery stunt.
- https://www.geo.tv/latest/598782-magician-david-blaine-admits-to-forgetting-about-one-invisible-tattoo - tattoo prediction.
- https://www.oneahead.com/p/magicians-the-time-is-now - publicity predictions.
- https://timevault.drand.love/ - timelock web app (named in drand docs).
