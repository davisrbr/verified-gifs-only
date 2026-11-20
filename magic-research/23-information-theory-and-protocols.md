# 23 - Information theory, coding, cryptography and protocols as method structure

Slice: results from information theory, coding theory, cryptography, combinatorics and theoretical
computer science that can become the hidden structure of a method. Most of it needs no hardware.

Research note. The shared web-search allowance ran out after six searches, so most of this report
rests on pages opened directly: arXiv and IACR ePrint listing and abstract pages, Wikipedia, RFCs
and project pages. Anything recalled from memory and not opened is marked "(unverified)". A few
combinatorial claims that are my own derivations were checked with a short brute-force script and
are marked "(checked by script)". Prices are as of late 2026.

## 1. Summary

- **Magic uses about 1950s coding theory; the literature has moved a long way.** Cheney's trick,
  binary de Bruijn stacks and Gilbreath are in the magic canon. Codes for a channel whose state
  only the sender knows, error-correcting permutation codes, group testing, position-coding
  surfaces, liar-game codes and non-committing commitments are not, and each one maps onto a
  method primitive.
- **The Cheney family has three fresh results (2024 to November 2026)** that change how it can be
  staged: the volunteer may choose the hidden card (deck limit (K-1)!+K-1, which one extra bit
  lifts to a full deck), the cards may be face down or sideways (3-card and 4-card versions for a
  full deck), and the display can be made immune to a heckler swapping two cards (29-card and
  14-card limits).
- **The "impossible chessboard" generalises into something stronger than the puzzle.** With
  2^k - 1 coins the audience can forbid the assistant from touching almost half of them (any
  2^(k-1) - 1), and the assistant still sends k bits by turning at most two of the rest (checked
  by script). This is the "wet paper code" idea from steganography and I found no magic use of it.
- **Liar-tolerant identification is cheap and mechanical.** One of 52 cards with one permitted lie
  takes 10 yes/no answers (optimal), two lies 13 to 15, and one of 4,096 items with three lies
  takes 23 (Golay code). A stack of tinted transparencies decodes any of these with no
  electronics, and also shows which answers were the lies.
- **Group testing gives a two-thinker (or three-thinker) version of the 21-card trick.** Two
  people think of cards and answer jointly, never saying whose card is in which pile. Three deals
  into seven piles identify both cards; four deals identify three thinkers' cards (checked by
  script).
- **Commitments can be made equivocal without breaking any cryptography.** A genuine SHA-256
  Bitcoin timestamp can cover hundreds of millions of predictions through one Merkle root. A
  ciphertext can open to different plaintexts under different keys. Given one visual-cryptography
  share, the other can be made afterwards to reveal any image. The MD5 "Nostradamus" demonstration
  (12 PDFs with one hash, 2007) is the canonical precedent.
- **A zero-knowledge simulator is a magician.** The proof that a protocol leaks nothing is a
  recipe for faking the proof when you control the "random" choices. Card-based secure-computation
  protocols (den Boer's five-card trick and the large literature since) rest on three physical
  assumptions (identical backs, a truly random cut, no peeking), and each is something a card
  worker can secretly break. One identifiable card is enough to break the five-card trick.
- **Covert channels through honest-looking actions are high-capacity and, when keyed, provably
  undetectable.** A deck's order holds 225.6 bits. A world-class bridge pair ran a one-bit
  card-orientation channel under expert scrutiny for years, and it was caught only by statistics
  over recorded hands. A shared rolling key (the minute on two watches) makes the visible action
  statistically independent of the secret, which removes even that attack.
- **Position-coding patterns (Anoto) and universal cycles for objects other than binary strings**
  let any small fragment of a printed surface, or any few consecutive items of a sequence, identify
  where it came from, including which way round it is being read. An MIT-licensed encoder/decoder
  exists. Order-pattern cycles allow a reveal channel that carries no card names: five people
  stand in order of their cards.
- **What computation adds:** every scheme here was once limited by what a person could compute on
  stage. With a hidden computer and a cue, or a printed overlay, decoding cost is zero, so
  two-lie and three-lie games, large-n Cheney, adaptive group tests, slip-proof Kruskal texts
  found by search, and keyed spoken codes all become practical.

## 2. Catalog

### 2.1 Channels whose state only the sender knows: Cheney, the chessboard, wet paper

**Fitch Cheney's five-card trick and its limits.** The volunteer picks 5 cards, the assistant
hides one and shows four in a row, and the medium names the hidden card. Kleber's bound: with K
chosen cards the largest deck is K! + K - 1, so 124 for K = 5. Chen, Khovanova et al. (2024)
extend this:
- If the **volunteer** chooses which card to hide, the limit is N = R^(K-1) (K-1)! + K - 1, where
  R is the number of orientations each shown card may take. For K = 5 and R = 1 that is 28 cards.
  For K = 4 and R = 2 (each card upright or sideways) it is 51.
- If the assistant chooses, N = R^(K-1) K! + K - 1.
- Mulcahy's 4-card version (some cards face down) works for 52 cards. The authors' new 3-card
  version (two shown cards, each face up or down and upright or sideways) works for 54.
- Bounds are also given for hiding two or more cards and for decks with duplicates.

Levy and Malinovsky (November 2026) add an origin-free method (no fixed lowest rank or first
suit, so the spectator can choose where the "clock" starts), an eight-card pocket version, and
versions that survive tampering: if a heckler may swap two neighbouring cards of the display,
29 cards is the largest correctable deck, and if any two cards may be swapped the limit is 14.
They take the error-correcting orders from rank-modulation codes for flash memory.
- References: https://arxiv.org/abs/2405.21007 ; https://arxiv.org/abs/2611.02424 ;
  https://blog.tanyakhovanova.com/2024/08/the-5-card-trick-the-4-card-trick-and-the-3-card-trick/
- Accessibility: a deck of cards. The 124-card arithmetic method and the heckler-proof versions
  are mentally heavy, and a phone lookup removes that.
- Magic relevance: thought transmission. The textbook weakness is that the assistant picks the
  hidden card, and the volunteer-chooses variants remove it. My observation: with five cards and
  the volunteer hiding one, four cards give 24 orders, and 48 unseen cards remain, so exactly one
  extra bit (row laid left-to-right or right-to-left, one card sideways, which hand) covers a full
  deck.
- Prior use: the classic is widely performed. I did not find the 2024 to 2026 variants in magic
  sources (magic-side checking was limited by the search cap).

**One flip sends many bits (the "impossible chessboard").** 64 coins lie heads or tails at
random, the sender turns exactly one, and the receiver learns one of 64 squares. Number the
squares in binary and XOR the numbers of all heads-up squares; one flip can move that XOR to any
target. This is Hamming-code syndrome coding, and it works exactly when the number of squares is a
power of two.
- References: https://rjlipton.com/2016/03/14/one-flip-sends-many-bits/ (Lipton and Regan, 2016).
- Magic relevance: thought transmission in which the audience sets almost the whole display. The
  receiver's mental load on 64 squares is high; 16 cards face up or down in a 4x4 grid (4 bits) is
  comfortable.

**Wet paper codes and "memory with defects".** In steganography, the sender may change only some
positions, the receiver does not know which, and about one bit per changeable position still gets
through (Fridrich, Goljan, Lisonek and Soukal, 2005, unverified; it descends from
Kuznetsov-Tsybakov coding for defective memory, unverified). Applied to the coin board, my
derivation: label 2^k - 1 coins with the non-zero k-bit numbers. The audience freezes any
2^(k-1) - 1 coins. More than half the non-zero vectors remain free, so they span the space, and a
pairing argument shows any target XOR is reached by turning **at most two** free coins. For 15
coins: freeze any 7, turn at most 2, send 4 bits (checked by script over all 6,435 choices). For
63 coins: freeze any 31, send 6 bits. The receiver decodes exactly as in the chessboard puzzle and
never needs to know which coins were frozen.
- Accessibility: coins or cards. Mental for 15; a computer helps the sender at 63.
- Magic relevance: a new condition the audience can state precisely ("we chose which coins he was
  not allowed to touch") that still does not stop the channel.
- Related: write-once-memory codes (Rivest and Shamir, 1982, unverified) let a medium that can
  only change one way (cards only turned face up, corners only torn off) be reused: 3 such cells
  carry 2 bits twice.

**Error-correcting permutation codes (rank modulation).** Codes in the symmetric group under the
Kendall tau metric (number of adjacent swaps) were developed for flash memory. Buzaglo and Etzion
(2014) show no perfect single-error-correcting code exists in S_n for 4 <= n <= 10 and give
larger codes than before for S_5 and S_7; later work tightens bounds.
- References: https://arxiv.org/abs/1408.4963 ; https://arxiv.org/abs/2406.06029
- Magic relevance: a packet's order can be a message that survives a spectator's small mix-up. The
  sphere-packing bound for 7 cards and one adjacent swap is 5040/7 = 720 messages (about 9.5 bits,
  against 12.3 bits unprotected), still more than one card.

### 2.2 Covert channels through honest-looking actions

**Raw capacities (arithmetic).** Order of a full deck: log2(52!) = 225.6 bits. Order of a
5-card packet: 6.9 bits; 8 cards: 15.3 bits. Orientation of a card with a one-way back or a
face-up/face-down state: 1 bit per card. Naming one card: 5.7 bits. So five indifferent cards
dealt in a row, using order and one-way orientation, carry 11.9 bits, enough for two thought-of
cards. Each choice between two equivalent honest actions is one bit.

**Evidence that one-bit object channels are invisible live.** In the Fantoni-Nunes bridge case
(2015), a played card laid vertically meant a high honour held in the suit, and horizontally meant
none. It ran at world-championship level, and it was found by a physicist correlating orientation
with holdings over many recorded deals.
- Reference: https://en.wikipedia.org/wiki/Fantoni_and_Nunes_cheating_scandal
- Lesson for method design: such a channel is detected by statistics against ground truth, not by
  watching. A magic act rarely provides that corpus, and keying removes the correlation entirely.

**Keyed channels: rolling shared secrets and shared time.** TOTP (RFC 6238, 2011) derives a code
from a shared secret and the current 30-second time step, with a tolerance of about one step for
drift. For a two-person code the same idea is: XOR (or shift) the cue with a pad both parties can
derive at that moment, such as the minute shown on both watches, the last card shown, or a
memorised list. The cue then looks uniformly random to anyone without the pad, including a
spectator who has read the code book. This is a one-time pad on the covert channel, so the
security is information-theoretic, not a matter of acting.
- Reference: https://datatracker.ietf.org/doc/html/rfc6238
- Accessibility: two watches. Hardware TOTP tokens that can be seeded with a chosen secret exist
  for about $20 (unverified).
- Magic relevance: *tell*. Removes the classic weakness of verbal codes (repetition lets a
  listener learn the mapping). Two sealed, unconnected devices showing the same changing number is
  the level-1 use and is weak; the keyed code is the real use.

**The classical acts as channel coding.** The Zancigs' verbal code needed "years of study" and
hours of daily practice (Harry Price, quoted on Wikipedia), and Julius Zancig published it in
1924. The Piddingtons never revealed their methods; commentators have suggested that much was
pre-arranged, so no communication was needed in the famous broadcasts. In coding terms the
classical codes are fixed, unkeyed, low-redundancy block codes with no error correction, and
their capacity is bounded by how many phrasings sound natural.
- References: https://en.wikipedia.org/wiki/The_Zancigs ; https://en.wikipedia.org/wiki/The_Piddingtons

**Linguistic steganography with language models.** Ziegler, Deng and Rush (EMNLP 2019) run an
arithmetic decoder against a neural language model, so secret bits select fluent text. Shen, Ji
and Han (2020) improved bits per word by 15.3% and report that 51% of their cover texts fooled
human judges. Meteor (Kaptchuk et al., CCS 2021) is provably indistinguishable from honest model
output. De Witt et al. (ICLR 2023) show perfect security is equivalent to using a coupling. Zamir
(2024) hides an arbitrary payload in LLM output undetectably with a key. For a spoken channel the
relevant numbers are the robust ones: Qu et al. (USENIX Security 2025) embed 20 bits in 200
tokens with a 97.6% match rate and provable survival of edits at an edit distance of 17.
- References: https://arxiv.org/abs/1909.01496 ; https://arxiv.org/abs/2010.00677 ;
  https://eprint.iacr.org/2021/686 ; https://arxiv.org/abs/2210.14889 ;
  https://arxiv.org/abs/2401.10360 ; https://arxiv.org/abs/2401.16820 ;
  https://arxiv.org/abs/2410.04328
- Accessibility: hobbyist. GPT-2-class models run on a laptop or phone.
- Magic relevance: a spoken or written cue that is a different natural sentence every time.
  Arithmetic-coded text breaks on a single mis-heard token, so live speech needs the robust,
  low-rate schemes (about 0.1 bit per token) or a small hand-built phrase grammar. A playing card
  is only 5.7 bits, so a low rate is enough.

**The Russian cards problem: a code that survives exposure.** Seven cards are dealt 3, 3 and 1.
The two three-card holders make public announcements, after which each knows the whole deal and
the one-card holder cannot tell who holds any card they do not hold, even knowing the protocol.
Solutions use block designs. Swanson and Stinson give a perfectly 2-secure strategy for hands of
8, 13 and 3, and Cordon-Franco et al. give geometric protocols for larger deals.
- References: https://arxiv.org/abs/1207.1336 ; https://arxiv.org/abs/1401.1526 ;
  https://arxiv.org/abs/1301.4289 ; https://arxiv.org/abs/2009.13644 ;
  https://arxiv.org/abs/cs/0702097
- Magic relevance: thought transmission where the method is explained first and still cannot be
  beaten by the listening spectator. Mentally feasible at 7 cards.

### 2.3 Identification when answers are unreliable, pooled or minimal

**Ulam's liar game and Hamming-code question cards.** Ehrenborg (Math Horizons, 2006): seven
question cards and a base card find a number from 0 to 15 when the friend may lie once. Each
card is laid one way for "yes" and flipped for "no", teeth on its edge cover the excluded numbers,
and the number covered by at most one card is the answer. The card covering it is the lie. For
one of a million with one lie, 25 questions suffice (Pelc, as cited in the search result for
Krieger's notes). Sphere bounds for 52 items: 10 questions for one lie, 13 for two, 15 for three
(computed). A shortened Hamming code achieves 10; the BCH (15,7) code handles two lies in 15
questions for up to 128 items; the Golay (23,12) code handles three lies among 4,096 items.
- References: https://www.ms.uky.edu/~jrge/Papers/Hamming.pdf ; https://arxiv.org/abs/0705.1220 ;
  https://arxiv.org/abs/math/0407504 ; https://arxiv.org/abs/2104.01664 (queries of limited size)
- Accessibility: printed cards. My extension is in concept 3.
- Magic relevance: identification framed as lie detection. The audience is told lying is allowed.

**Group testing.** Find d marked items among N using pooled tests that say only whether a pool
contains at least one. Aldridge, Johnson and Scarlett's monograph (second edition May 2026)
covers optimal rates, noisy tests and few-round adaptive schemes. The classical "age cards" are
the d = 1 case. For d = 2 the pools must form a 2-disjunct design, and then the decoder is
trivial: cross out everything in any negative pool, and what remains is the answer.
- Reference: https://arxiv.org/abs/1902.06002
- Magic relevance: several thinkers answer jointly, or a yes/no physical test is applied to a
  pile (does this stack contain the marked envelope). See concept 11.

**Set sketches.** A PinSketch (minisketch) of capacity c identifies up to c missing or extra
elements from c*b bits regardless of set size, for example 48 bits for 4 differences among 12-bit
elements. "Clocking the deck" for one missing card is the c = 1 case. Two or more missing cards
by running power sums is a syndrome decode that a hidden computer does instantly.
- Reference: https://github.com/sipa/minisketch

**Covering codes and covering designs: fewest outs for a near-hit.** A covering code of radius 1
guarantees one prediction with at most one miss. Nine forecasts cover all 81 outcomes of four
three-way matches, and 3^10 = 59,049 cover thirteen matches with at most one miss. Covering
designs (lottery "wheels") do the same for "at least t of my k numbers match". The La Jolla
Covering Repository holds tables (unverified; its host was blocked in this session).
- Reference: https://en.wikipedia.org/wiki/Covering_code
- Magic relevance: sizes an index of outs when "all but one right" is acceptable, or when the
  performer can secretly correct one item.

**Hat games and the 100 prisoners.** Ebert's game: 7 players win with probability 7/8 with a
Hamming-code strategy. 100 prisoners: following the permutation cycle from your own number
succeeds for everyone with probability 0.3118, and if one helper may first swap the contents of
two boxes, success is certain.
- References: https://en.wikipedia.org/wiki/Hat_puzzle ;
  https://en.wikipedia.org/wiki/100_prisoners_problem ; https://arxiv.org/abs/1810.08263
- Magic relevance: hat strategies need every participant to compute, so they suit confederates
  only. The box problem needs only a rule spectators can follow, plus one secret swap.

### 2.4 Windows that locate themselves: universal cycles, orientable sequences, position codes

**Beyond the 32-card binary de Bruijn stack.**
- *Any length.* Cut-down de Bruijn sequences give a cycle of any length L with window
  ceil(log L), built in O(n) time per symbol (Cameron, Gundogan and Sawada, 2022). A full 52-card
  deck then works with a six-colour window, or with three suits read as a 4-ary window.
- *Order patterns.* Universal cycles for permutations: every window of k has a distinct relative
  order (Johnson: n+1 symbols suffice; Kirsch et al. 2022 on shortened cycles). With 52 distinct
  cards a cyclic arrangement in which all 52 windows of five have different order patterns is
  found by local search in under a second (checked by script).
- *Subsets and multisets.* Efficient universal cycles for k-subsets, with ranking and unranking,
  appeared in March 2026.
- *Both directions.* Orientable sequences: each window occurs at most once in either reading
  direction, so a window gives position and direction. Asymptotically optimal constructions in
  O(1) amortised time per bit (Gabric and Sawada, 2024), and exact maxima for windows up to 16
  (Mitchell, October 2026).
- *Two dimensions.* De Bruijn tori and universal tori for permutations (September 2026).
- References: https://arxiv.org/abs/2205.02815 ; https://arxiv.org/abs/0710.5611 ;
  https://arxiv.org/abs/2204.02910 ; https://arxiv.org/abs/2603.11954 ;
  https://arxiv.org/abs/2603.11934 ; https://arxiv.org/abs/2401.14341 ;
  https://arxiv.org/abs/2407.07029 ; https://arxiv.org/abs/2610.33601 ;
  https://arxiv.org/abs/2609.27583 ; https://arxiv.org/abs/2306.01498 ;
  https://mathweb.ucsd.edu/~ronspubs/08_05_products.pdf (Diaconis and Graham on products of
  universal cycles, motivated by a card trick)
- Accessibility: software only.
- Magic relevance: *know*. The reveal channel can be made to look information-free (people line up
  by rank). Orientable sequences suit anything that can be turned end for end: a ribbon, a bead
  string, dominoes, a strip of tickets, a deck dealt from either end.
- Prior use: binary and some suit-based de Bruijn stacks are established (Diaconis and Graham,
  "Magical Mathematics"). I did not find order-pattern or orientable versions in magic.

**Position-coding surfaces (Anoto and successors).** Dots are displaced in one of four
directions from an unprinted grid; the displacements follow de Bruijn-type sequences along rows
and columns, so any 6x6 window of dots gives an absolute position. At a 0.3 mm grid the code is
unique over an area the size of Europe and Asia combined. The py-microdots library (MIT licence)
encodes and decodes the Anoto code, recovers rotation from an 8x8 window, and supports smaller
variants such as 4x4. It does not do image processing. Wikipedia notes the related PuzzleBoard
calibration pattern.
- References: https://en.wikipedia.org/wiki/Anoto ; https://github.com/cheind/py-microdots ;
  https://en.wikipedia.org/wiki/De_Bruijn_torus
- Accessibility: hobbyist for coarse pitches on a 1200 dpi laser printer. Original-scale dots are
  beyond typical 300 dpi custom-card printing. Camera decoding is the real work (agent 10).
- Magic relevance: *know* and *prove ordinariness*. Any scrap of a printed page, any exposed
  sliver of a card back, any jigsaw piece or any spot on a mat identifies itself and its rotation.
- Prior use: commercial smart pens are this technology. I did not confirm marketed magic props
  built on a position-coded surface.

### 2.5 Card-based cryptography and physical zero-knowledge

**What exists.** Den Boer's five-card trick (1989): two players each lay two face-down cards
encoding a bit around a centre heart, the row is cut randomly and turned up, and three adjacent
hearts mean both said yes. Nothing else is revealed. Since then:
- Minimal-card and committed-format protocols (Koch, Walzer and Hartel, 2015; Kastner et al.,
  2017; Koch's survey "The Landscape of Optimal Card-based Protocols").
- Active security: Koch and Walzer show uniform closed shuffles can be enforced with a linear
  number of helper cards; earlier fixes used envelopes or sliding cover boxes.
- One shuffle is enough for any circuit (Shinagawa and Nuida, 2019), and every function has a
  single-shuffle, full-open protocol (Eriguchi and Shinagawa, 2025): lay cards, shuffle once,
  turn everything over.
- New single-cut full-open protocols for three- and four-variable functions (2025), and an
  optimisation proof that no others of a certain form exist.
- Oblivious transfer from one shuffle of four distinct cards (Beaver, 2026).
- A complexity hierarchy of shuffles by implementation difficulty (Ono and Ruangwises, 2026).
- Card-game computations with a simulated extra player (Ruangwises, September 2026).
- Other objects: PEZ dispensers (Abe, Iwamoto and Ohta), a balance scale and coins (Ruangwises,
  2025), and polarising plates, balls and bags, envelopes and scratch-off cards (unverified
  individually; the Sudoku paper cites several).
- References: https://eprint.iacr.org/2017/423 (opened) ; https://arxiv.org/abs/2010.08445 ;
  https://arxiv.org/abs/2510.17308 ; https://arxiv.org/abs/2507.03323 ;
  https://arxiv.org/abs/2509.17595 ; https://eprint.iacr.org/2026/1061 (opened) ;
  https://arxiv.org/abs/2603.18608 ; https://arxiv.org/abs/2609.02716 ;
  https://arxiv.org/abs/2501.12080 ; https://arxiv.org/abs/1911.05994 ;
  https://arxiv.org/abs/2402.16290 . ePrint numbers taken from search listings only, not opened
  (two listings disagreed, so check before citing): 2015/865, 2017/863, 2018/951, 2019/380,
  2019/200.

**Physical zero-knowledge proofs.** Gradwohl, Naor, Pinkas and Rothblum (2007) prove knowledge of
a Sudoku solution with playing cards or scratch-off cards, where a face-down card is a
tamper-evident envelope. Follow-ups: two standard decks suffice for Sudoku (Ruangwises, 2021);
protocols for Nonogram, Makaro, Shikaku, Nurikabe, Hitori, Moon-or-Sun, Tatami puzzles, Zeiger,
Hotaru Beam (2026) and the interactive Ball Sort puzzle. Naor, Naor and Reingold's "Where's
Waldo" proof and Fisch, Freund and Naor's physical proofs of physical properties are the classic
non-card examples (unverified; the Weizmann host returned an error).
- References: https://www.microsoft.com/en-us/research/wp-content/uploads/2009/01/GradwohlNPR09.pdf ;
  https://arxiv.org/abs/2106.13646 ; https://arxiv.org/abs/2106.14020 ;
  https://arxiv.org/abs/2112.12042 ; https://arxiv.org/abs/2202.09788 ;
  https://arxiv.org/abs/2302.07251 ; https://arxiv.org/abs/2302.01235 ;
  https://arxiv.org/abs/2304.12388 ; https://arxiv.org/abs/2408.13507 ;
  https://arxiv.org/abs/2409.14308 ; https://arxiv.org/abs/2603.01393

**Which make good magic as they stand.** Only the short, single-shuffle, full-open ones: the
five-card trick (under a minute, one cut, one turn-over) and its three-input relatives. They suit
a "nobody, including me, can know who said no" plot. Sudoku-scale proofs take many minutes and
dozens of cards and read as a lecture.

**How a performer subverts them (my analysis).**
- *Track the cut.* When the five-card result is "not both yes", the three possible inputs give
  the same cyclic pattern at different rotations. Anyone who knows the rotation knows who said
  no. One identifiable card (a crimp, a nick, a back mark on the performer's own centre card)
  gives the rotation. The spectators' cards can be clean.
- *Rely on bias.* Kim and Cetinkaya (2025) quantify the leak when human cuts are not uniform and
  bound how many repeated cuts are needed, so even an unmarked performance leaks to a good
  estimator.
- *Read the commitment.* With marked backs the performer reads a spectator's input as it is laid
  down, and an entirely honest protocol then "certifies" a match he arranged (concept 4).
- *Be the simulator.* A zero-knowledge proof is one where a party who controls the verifier's
  random choices can produce a convincing transcript without the secret. A force or a false
  shuffle gives that control, so the performer can "prove" knowledge he lacks. Dually, a proof of
  knowledge has an extractor: run it twice on the same randomness and the secret falls out. A
  spectator led through a "fair check" twice under a false shuffle reveals their card.
- *Private operations.* Many protocols include a step done behind the back. Hummer's
  "mathematical three-card monte" is the magic ancestor of that model.
- References: https://arxiv.org/abs/2511.05111

**A curiosity in the other direction.** Scott and Spector's "Carnac protocol" is a cryptographic
scheme modelled on billet reading (listed as ePrint 2015/576 in a search result; not opened).

### 2.6 Commitments, and how to make them equivocal

**Multi-collisions (the Nostradamus attack).** Stevens, Lenstra and de Weger published an MD5
hash in 2007 as a "prediction" of the 2008 US presidential election, holding twelve PDFs with
that hash. Each chosen-prefix collision took about two days on one PlayStation 3. A SHA-1
chosen-prefix collision cost about $75,000 of rented GPUs in 2019, estimated at $45,000 in 2020,
with the authors projecting under $10,000 by 2025.
- References: https://marc-stevens.nl/research/hashclash/Nostradamus/ ; https://sha-mbles.github.io/
- Assessment: MD5 is free and fools lay audiences; anyone technical will object to MD5 on sight.

**Merkle-root timestamps.** OpenTimestamps commits one Merkle root to Bitcoin for any number of
documents; calendar servers are free. Todd's announcement states the limit plainly: "A timestamp
only proves a message existed, not the message." The proof for one leaf contains only the hashes
on its path. So a root over every outcome yields, for whichever outcome occurs, a genuine
SHA-256 and Bitcoin proof that the matching document existed beforehand. The six-of-49 lottery
has about 14 million outcomes (about 450 MB of leaves).
- References: https://opentimestamps.org/ ; https://petertodd.org/2016/opentimestamps-announcement

**Non-committing encryption.** AES-GCM, XSalsa20/Poly1305 and ChaCha20/Poly1305 are not
key-committing: one ciphertext can be built to decrypt validly under two or more keys to
different plaintexts ("invisible salamanders", Dodis et al., CRYPTO 2018; Len, Grubbs and
Ristenpart, USENIX Security 2021). The one-time pad is the extreme case: any ciphertext opens to
any message of that length under a suitable key.
- References: https://eprint.iacr.org/2019/016 ; https://eprint.iacr.org/2020/1491

**Trapdoor commitments.** Chameleon hashes (Krawczyk and Rabin, 1998) are collision-resistant
for everyone except the holder of a trapdoor. This is the academically clean equivocal
commitment, and theatrically useless because no audience can verify one.
- Reference: https://eprint.iacr.org/1998/010

**Files with a free variable.** A committed file can be a polyglot that shows different content
in different viewers (unverified; standard in the file-format security literature), or the
commitment can be to a statement that points elsewhere.

**Visual cryptography.** Naor and Shamir (1994): two random-looking transparencies reveal an
image when stacked, with every pixel expanded to subpixels and white areas at 50% contrast. Two
properties matter here. Given one share, a second can be built that reveals any image at all
(noted on Wikipedia and exploited in Horng et al.'s 2006 cheating attack). And extended schemes
make each share a meaningful picture (Ateniese et al., 2001; Wang et al., 2006), with colour and
multi-secret variants (Reif and Zumbragel, 2025; Klein and Wessler, 2003). Random-grid schemes
avoid pixel expansion (Kafri and Keren, 1987). Schemes where one pair of sheets shows different
images at different rotations or offsets exist (unverified).
- References: https://en.wikipedia.org/wiki/Visual_cryptography ;
  https://arxiv.org/abs/math/0302043 ; https://arxiv.org/abs/cs/0610172 ;
  https://arxiv.org/abs/2510.00763 ; https://arxiv.org/abs/2508.05394 ;
  https://arxiv.org/abs/1210.6123
- Accessibility: laser transparencies. Hand alignment wants subpixels of 0.3 to 0.5 mm.
- Magic relevance: prediction and identification with a share the spectator has held for days.
  Random dots cannot be remembered, so swapping or changing a share in view is undetectable.
- Prior use in magic: none found in this pass.

**Unclonable objects.** Toreini, Shahandashti and Hao fingerprint a sheet of paper from its
see-through texture with an ordinary camera: a 2048-bit code with 807 degrees of freedom and no
false accepts or rejects on their data.
- Reference: https://arxiv.org/abs/1705.02510
- Magic relevance: unmarked billets or blank cards individually recognisable over a light source.
  It does not transfer to opaque playing-card stock (agent 10).

**Mental poker, oblivious transfer, time-lock puzzles.** They exist and work
(https://en.wikipedia.org/wiki/Mental_poker). As plots they are weak because the audience cannot
perceive the guarantee. See section 5.

### 2.7 Combinatorics with a magical reading

- **Dobble / Spot It.** 55 of the 57 lines of the projective plane of order 7: any two cards
  share exactly one symbol. Dually, two symbols lie on exactly one card, so a hidden card is
  fixed by the symbol it shares with each of two visible cards. An unaltered children's game is a
  marked deck. https://en.wikipedia.org/wiki/Dobble
- **SET.** Any two cards determine the third card of their set; the maximum number of sets among
  16 cards is 26 (November 2026). https://arxiv.org/abs/2611.18722
- **Kruskal count.** Chains from different starts couple: over 90% for a 52-card deck in the
  source Wikipedia cites, about 97.4% in Dynkin's 100-digit version, and it works on ordinary
  text. A 2026 paper bounds iterations of a Kruskal-type elimination process.
  https://en.wikipedia.org/wiki/Kruskal_count ; https://arxiv.org/abs/math/0110143 ;
  https://arxiv.org/abs/2610.29015
- **Penney's game and the Humble-Nishiyama card version.** The second player wins at odds of 2:1
  to 7.5:1. Newer variants bet on order patterns of consecutive cards (Elizalde and Lin, 2024) or
  on pattern classes (Khovanova and Li, 2020). https://en.wikipedia.org/wiki/Penney%27s_game ;
  https://arxiv.org/abs/2404.06585 ; https://arxiv.org/abs/2009.06080 ;
  https://arxiv.org/abs/2006.13002
- **Intransitive dice.** Random dice are intransitive far more often than intuition suggests;
  for four random dice the chance of a transitive tournament is strictly above 3/8. Even Snakes
  and Ladders squares are intransitive. https://arxiv.org/abs/2011.10067 ;
  https://arxiv.org/abs/2310.17083 ; https://arxiv.org/abs/2201.07004 ;
  https://arxiv.org/abs/2311.12811 . Agent 16 owns this.
- **Dealing and shuffling invariants.** Under-down deal formulas (2025), unshuffles and a
  generalised Elmsley problem for 2^k cards (2023), Hummer's principle for odd packets (2023),
  the 21-card trick for any size (2018). https://arxiv.org/abs/2509.11395 ;
  https://arxiv.org/abs/2302.03579 ; https://arxiv.org/abs/2308.02684 ;
  https://arxiv.org/abs/1809.04072
- **Sure things from extremal theorems.** Any 10 distinct cards in a row contain 4 that rise or 4
  that fall (Erdos-Szekeres). Any deal of 52 cards into 13 piles of 4 lets you take one card per
  pile to make ace to king (Hall's theorem; finding it is a matching problem a computer solves
  instantly). (Standard results, unverified.)

### 2.8 Recent papers and the trick each implies (2018 to November 2026)

1. Levy and Malinovsky, 2026, arXiv 2611.02424: heckler-proof and origin-free Cheney.
2. Chen, Khovanova et al., 2024, arXiv 2405.21007: Cheney with the volunteer choosing; 3-card
   face-down version.
3. Huang, Khovanova et al., 2025, arXiv 2509.11395: design any down-under deal to end on a
   chosen card.
4. Van Cott and Wang, 2023, arXiv 2302.03579: unshuffle sequences that bring a card to a chosen
   position.
5. Fernandez de Soto Guerrero, 2023, arXiv 2308.02684: cut-and-turn-two routines with an odd
   packet.
6. Byrapuram, Khovanova et al., 2024, arXiv 2409.01296: lightning addition for other recurrences.
7. Agrawal, Khovanova et al., 2025, arXiv 2508.18277: at most three mutually nesting "Gozinta"
   boxes in 3D, four in 2D.
8. Appenzeller and Quintanilha, 2026, arXiv 2604.13799: a string move that appears to tie any
   knot from a plain loop.
9. Zhu, 2024, arXiv 2402.13802: model-checking a self-working procedure before printing it. The
   case study is "shousuigongcishi", which I believe is the follow-along trick from the 2024
   Spring Festival Gala (unverified).
10. Icard and Fervari, 2024, arXiv 2401.14516: a formal logic of verbal and visual misdirection.
11. Kim and Cetinkaya, 2025, arXiv 2511.05111: reading private inputs from biased cuts.
12. Corregidor, 2026, arXiv 2610.29015: guaranteed length of a Kruskal-type elimination.
13. Elizalde and Lin, 2024, arXiv 2404.06585: a non-transitive bet on the order of three cards.
14. Khovanova and Li, 2020, arXiv 2009.06080: Penney bets on pattern classes.
15. Sorkin, 2022, arXiv 2201.07004: a minimal intransitive dice set.
16. Pratt, Wagon, Wiener and Zielinski, 2018, arXiv 1810.08263: hat strategies with spare hats.
17. Ruangwises, 2021, arXiv 2106.13646: a Sudoku proof with two ordinary decks.
18. Ruangwises, 2023, arXiv 2302.07251: proving you can solve a move puzzle without showing moves.
19. Ruangwises, 2025, arXiv 2501.12080: secure computation with a balance scale and coins.
20. Eriguchi and Shinagawa, 2025, arXiv 2510.17308: any function with one shuffle and a full
    turn-over.
21. Shinagawa and Nuida, 2025, arXiv 2507.03323: new one-cut, turn-everything-over protocols.
22. Beaver, 2026, ePrint 2026/1061: "you learn one of my two secrets and I cannot know which"
    from four cards.
23. Cameron, Gundogan and Sawada, 2022, arXiv 2205.02815: de Bruijn stacks of exactly 52.
24. Gabric and Sawada, 2024, arXiv 2401.14341: sequences readable from either end.
25. Gerlach et al., 2026, arXiv 2609.27583: two-row permutation tori (a two-row layout where each
    small window is unique).
26. Campbell, Janik-Jones and Sawada, 2026, arXiv 2603.11954: cycles where each window is a
    distinct subset.
27. Qu et al., 2024, arXiv 2401.16820: 20 bits hidden in a paragraph, surviving edits.
28. Zamir, 2024, arXiv 2401.10360: keyed, undetectable payloads in generated text.
29. Rajsbaum, 2020, arXiv 2009.13644: minimal announcements in Russian-cards deals.
30. Ono and Ruangwises, 2026, arXiv 2603.18608: which shuffles are hard to perform honestly.

## 3. Capability primitives

1. *Now possible:* a performer can **transmit** one of 52 cards when the volunteer, not the
   assistant, chooses the hidden card. *Because:* (K-1)!+K-1 bound plus one extra bit. *Before:*
   the assistant had to choose. *Primitives:* tell.
2. *Now possible:* **transmit** a hidden card with three cards, two shown, face up or down and
   upright or sideways, 54-card deck. *Because:* Chen et al. 2024. *Before:* five cards.
   *Primitives:* tell.
3. *Now possible:* **transmit** through a display a heckler may alter by one neighbouring swap
   (29 cards) or any swap (14). *Because:* rank-modulation codes. *Before:* any tampering broke
   it. *Primitives:* tell, prove ordinariness.
4. *Now possible:* **transmit** k bits on 2^k - 1 coins when the audience freezes any 2^(k-1) - 1
   of them, turning at most two. *Because:* wet-paper / Hamming syndrome coding. *Before:* the
   sender needed free access to every coin. *Primitives:* tell.
5. *Now possible:* **transmit** with cues statistically independent of the secret. *Because:*
   one-time pad from shared time (TOTP idea). *Before:* fixed code books, learnable by
   repetition. *Primitives:* tell, erase the evidence.
6. *Now possible:* **transmit** 20 bits in a 200-token natural paragraph that survives about 17
   edits. *Because:* robust multi-bit LLM watermarking. *Before:* fixed phrases. *Primitives:*
   tell.
7. *Now possible:* **transmit** 225 bits (a whole deck order) or 12 bits (five cards by order and
   orientation). *Because:* permutation ranking by computer. *Before:* mental ranking limited to
   3 or 4 cards. *Primitives:* tell.
8. *Now possible:* **converse in public** so that a listener who knows the system learns nothing.
   *Because:* Russian-cards protocols. *Before:* codes relied on secrecy of the system.
   *Primitives:* tell.
9. *Now possible:* **identify** one of 52 with one permitted lie in 10 answers, two lies in about
   14, or one of 4,096 with three lies in 23, naming the lies. *Because:* Hamming, BCH, Golay
   codes. *Before:* one lie among 16 (Ehrenborg). *Primitives:* know.
10. *Now possible:* **decode** any such code with a stack of tinted transparencies. *Because:*
    darkness equals Hamming distance. *Before:* mental syndrome arithmetic. *Primitives:* know.
11. *Now possible:* **identify** two thinkers' cards from joint answers in three deals, three
    thinkers in four. *Because:* 2- and 3-disjunct designs from Reed-Solomon codes. *Before:*
    one thinker per round. *Primitives:* know.
12. *Now possible:* **identify** up to c removed cards from a c-number running sketch.
    *Because:* PinSketch. *Before:* one card by clocking. *Primitives:* know.
13. *Now possible:* **identify** five consecutive cards from how five people rank themselves.
    *Because:* order-pattern universal cycles found by search. *Before:* colours or suits had to
    be stated. *Primitives:* know.
14. *Now possible:* **identify** position and reading direction from a short window of a strip.
    *Because:* orientable sequences. *Before:* de Bruijn stacks assumed a direction.
    *Primitives:* know.
15. *Now possible:* **identify** where any 2 mm patch of a printed surface came from, with
    rotation. *Because:* Anoto-type codes and py-microdots. *Before:* one mark at one place.
    *Primitives:* know, prove ordinariness.
16. *Now possible:* **identify** a hidden Dobble card from two matches with visible cards.
    *Because:* projective-plane duality. *Before:* a marked deck. *Primitives:* know, prove
    ordinariness.
17. *Now possible:* **commit** to hundreds of millions of outcomes under one genuine SHA-256
    Bitcoin timestamp and open only one. *Because:* Merkle aggregation. *Before:* an index of
    envelopes. *Primitives:* control chance, delay.
18. *Now possible:* **commit** to a ciphertext that opens to different messages under different
    short keys. *Because:* non-committing AEAD; the one-time pad. *Before:* a physical switch.
    *Primitives:* swap, delay.
19. *Now possible:* **commit** by giving away half of an image days early, then make the other
    half reveal anything. *Because:* visual cryptography. *Before:* the prediction had to be
    switched. *Primitives:* delay, swap, prove ordinariness.
20. *Now possible:* **prove** a match between two hidden choices with an honest, explainable
    protocol while secretly knowing one of them. *Because:* card-based equality protocols plus
    marked backs. *Before:* the proof step did not exist. *Primitives:* prove ordinariness.
21. *Now possible:* **prove** knowledge you lack, or **extract** a spectator's secret, by
    controlling the randomness of a zero-knowledge procedure. *Because:* simulators and
    extractors. *Before:* not framed this way. *Primitives:* control chance, know.
22. *Now possible:* **learn** who said no in the five-card trick with one identifiable card.
    *Because:* rotation tracking. *Before:* not applicable. *Primitives:* know.
23. *Now possible:* **guarantee** a 31% group success with one secret swap. *Because:* cycle
    structure of permutations. *Before:* luck. *Primitives:* control chance.
24. *Now possible:* **guarantee** a Kruskal convergence from every start, including after a
    one-step miscount. *Because:* computer search over arrangements or texts. *Before:* about
    90% for a deck. *Primitives:* control chance.
25. *Now possible:* **verify** a self-working procedure for every input before printing it.
    *Because:* model checking. *Before:* testing by hand. *Primitives:* control chance.
26. *Now possible:* **size** an index of outs for "all but one right" exactly. *Because:*
    covering codes. *Before:* one out per outcome. *Primitives:* control chance.

## 4. Effect concepts

Levels follow the brief: 1 the phenomenon is the effect, 2 a hidden input to a classical method,
3 a new method architecture. Ten of the twelve are level 2 or 3.

### 1. Her choice (level 2)
- **Effect:** a spectator takes any five cards and decides herself which one to pocket. The
  assistant lays the other four in a row. The medium, who was out of the room, names the pocketed
  card. Afterwards a second spectator may swap two neighbouring cards in a reduced-deck version
  and it still works.
- **Method:** the order of four cards gives 24 messages and 48 cards are unseen, so one extra
  bit completes it: the row runs towards or away from the medium's chair. The medium ranks the 48
  unseen cards and counts. The heckler-proof encore uses the 29-card scheme of Levy and
  Malinovsky.
- **Materials and cost:** one deck. $0.
- **Difficulty:** low to build, moderate to perform (counting to 48 quickly; a lookup helps).
- **Risks:** the extra bit must be motivated. Mathematically literate spectators know the classic
  solution, and this version is designed to break it.
- **Novelty:** the bound was published in 2024; I did not find this staging.

### 2. The frozen board (level 3)
- **Effect:** 15 coins lie in a row, set heads or tails by the audience. A spectator names any of
  16 picture cards. Other spectators put a finger on any seven coins, which the assistant may not
  touch. He turns one or two of the others. The medium returns and names the picture.
- **Method:** section 2.1. Coins carry the labels 1 to 15 by position. The medium XORs the
  labels of the heads. The assistant needs one or two free coins whose labels XOR to the required
  change; one always exists (checked by script).
- **Materials and cost:** coins. $0. A 63-coin stage version sends 6 bits with 31 frozen and
  needs a computed cue for the assistant.
- **Difficulty:** low to build, moderate to perform.
- **Risks:** an XOR slip by either party. People who know the chessboard puzzle will find that
  its solution seems not to allow frozen coins, which helps.
- **Novelty:** high as far as I can tell; the freezing condition comes from steganography.

### 3. Two lies allowed (level 2 to 3)
- **Effect:** a spectator thinks of a card. The performer flashes fifteen fans and asks "do you
  see it?" each time. The spectator is told to lie once or twice whenever they like. The
  performer names the card and then says which answers were lies.
- **Method:** the 52 cards are assigned codewords of the BCH (15,7) code, chosen as
  complementary pairs. Each question has a transparent sheet with grey patches over the cards
  that the answer rules out, flipped for the opposite answer. Stacked on a card chart, the true
  card lies under at most two patches and every other card under at least three. The sheets with
  a patch over it are the lies. A one-lie version needs 10 sheets and the contrast is stark.
- **Materials and cost:** 15 laser-printed transparencies and a chart, about $10. Or a phone.
- **Difficulty:** moderate (layout design is a small program).
- **Risks:** reading two layers against three needs a backlight and practice. Fifteen questions
  is long, so the lie-detector framing must carry it.
- **Novelty:** Ehrenborg's one-lie cards are from 2006. The multi-lie optical decoder is, I
  believe, new.

### 4. Certified match (level 2, subverting a secure protocol)
- **Effect:** two spectators each secretly answer a question by laying two cards face down. The
  performer explains, truthfully, the cryptographers' protocol that reveals only whether both
  said yes. The cards are cut by a spectator and turned over. Later the performer privately tells
  each person what they answered.
- **Method:** den Boer's five-card trick performed honestly, except that the performer's centre
  card can be recognised from the back. Its position after the cut gives the rotation, which
  identifies the inputs. A stronger version uses marked backs and an equality protocol to
  "certify" that a prediction matches a card before it is named.
- **Materials and cost:** five cards, one of them marked. $0 to $15.
- **Difficulty:** low.
- **Risks:** it reveals a private answer, so the question must be harmless. Explaining the
  protocol takes about a minute.
- **Novelty:** the protocol is from 1989. Using its security proof as misdirection is, as far as
  I found, unexplored in magic.

### 5. The timestamped prophecy (level 3)
- **Effect:** a month before an event the performer publishes a proof file. After the event he
  releases a document naming the exact outcome, and anyone can verify with standard open-source
  tools that it existed before the event.
- **Method:** one document per possible outcome, a Merkle tree over all of them, and the root
  timestamped through OpenTimestamps. Afterwards the matching document and its path are released.
  Every hash is genuine. A proof is a chain of hash operations, so the added depth is not
  obviously separable from the calendar's own aggregation (my reading of the format, unverified).
- **Variants:** a ciphertext that opens to different texts under different passwords; a file
  that shows different content in different viewers (unverified).
- **Materials and cost:** a laptop and free software. Fees are zero through public calendars.
- **Difficulty:** moderate (scripting).
- **Risks:** a technical audience will say "he timestamped them all", so pair it with a physical
  prediction that cannot be explained that way. **Ethics flag:** the same construction is the
  basis of real prediction fraud. It should be presented as theatre and never applied to
  lotteries, markets or sport for gain.
- **Novelty:** the principle is the 2007 Nostradamus demonstration. Moving it to an unbroken
  hash through Merkle aggregation is the update.

### 6. Your half was always the answer (level 2 to 3)
- **Effect:** a week before the show a spectator is posted a signed, sealed transparency of
  random dots. At the show they freely name a word or make a drawing. Their transparency is laid
  on a framed sheet of dots that has hung on the wall all evening, and the word or drawing
  appears.
- **Method:** given one visual-cryptography share, the second can be computed for any image in
  milliseconds. The framed sheet is one of an index of prints, or an e-paper panel, or a slip
  from a hidden thermal printer. Nobody can remember a field of random dots, so changing it is
  undetectable. A no-electronics variant uses one printed sheet that reveals two to four
  different images at sub-millimetre offsets.
- **Materials and cost:** laser transparencies ($1 each); optionally an e-paper panel or a
  receipt printer ($20 to $60, unverified).
- **Difficulty:** moderate. Alignment is the craft; use subpixels of 0.4 mm or more and a
  registration frame.
- **Risks:** low contrast in dim rooms. If the second share is on a visible screen, the "it's a
  screen" theory returns, so prefer paper.
- **Novelty:** I found no magic use.

### 7. Every scrap knows where it came from (level 3)
- **Effect:** a spectator tears a printed sheet into pieces, mixes them, keeps one and destroys
  the rest. The performer describes the words on both sides of the kept scrap.
- **Method:** the sheet's background texture is a position code. A brief camera glimpse of any
  small patch gives its coordinates and rotation; a lookup returns the text there.
- **Materials and cost:** py-microdots (free), a 1200 dpi laser printer, a small camera (agent
  10), about $30.
- **Difficulty:** high. Reading dots from a hand-held scrap is the hard part; start with a
  coarse 1 mm pitch.
- **Risks:** dot texture visible on close inspection (disguise it as paper grain or a halftone
  tint); focus and motion blur.
- **Novelty:** the code is 25 years old. As a marking system with no fixed mark location it is,
  I think, unused in magic.

### 8. Just stand in order (level 2)
- **Effect:** a deck is cut several times. Five spectators take five consecutive cards and,
  without showing or saying anything, line up from lowest card to highest. The performer names
  all five cards.
- **Method:** a stack in which every cyclic run of five has a different order pattern (120
  patterns, 52 needed; one was found by search in under a second). A four-person version adds
  "red cards raise a hand".
- **Materials and cost:** a deck and a crib or cue. $0.
- **Difficulty:** low to build; the lookup needs memory work or a hidden prompt.
- **Risks:** a real shuffle destroys the stack, so false shuffles are needed. Spectators must
  agree a suit order for ties, or the stack order must be designed around values only.
- **Novelty:** universal cycles for permutations are in the mathematics literature and discussed
  by Diaconis and Graham. I did not find a full-deck performance version.

### 9. A letter that always ends on the same word (level 3)
- **Effect:** each guest receives a personal note. Each silently picks any word in the first
  line and hops forward by word lengths. Everyone ends on the same word, which is the word
  sealed in an envelope on the table, and it is different for each table.
- **Method:** a language model drafts the note and a search edits it until every start in the
  first two lines, and every chain after a one-step miscount, reaches the same final word.
- **Materials and cost:** printing only.
- **Difficulty:** moderate (a constrained-generation loop).
- **Risks:** a stilted text gives it away, so the edits must stay natural. Agent 12 owns the
  pipeline.
- **Novelty:** Kruskal texts are known. Guaranteed, slip-tolerant and personalised overnight is
  the new part.

### 10. The greeting that means something different every minute (level 2 to 3)
- **Effect:** a spectator's card is chosen. The performer phones a friend and says one ordinary
  sentence. The friend names the card. A spectator who thinks they have spotted the code finds
  that the same sentence produces a different card the next time.
- **Method:** a small grammar of interchangeable phrases carries 8 bits per sentence. The card
  number is shifted by the current minute before encoding, and the friend subtracts it. A version
  with a language model and an earpiece gives unrestricted wording, and robust low-rate embedding
  tolerates slips.
- **Materials and cost:** two watches; optionally an earpiece and a phone.
- **Difficulty:** low for the human version.
- **Risks:** a call that crosses a minute boundary (send the minute's parity as a check).
- **Novelty:** the keyed version of the old "Wizard" plot.

### 11. Either of you (level 2)
- **Effect:** two spectators each think of a card from 49 laid out. The cards are dealt into
  seven piles three times. Each time the pair points to the pile or piles containing "one of
  ours", without saying whose. The performer names both cards. With four deals it works for three
  people.
- **Method:** index the cards (a, b) with a and b from 0 to 6. The three deals group by a, by b
  and by a+b mod 7. No third card is consistent with any two (checked by script for all pairs;
  the four-deal version with a+2b checked for all triples). An 8x8 version uses XOR.
- **Materials and cost:** a deck, or three printed sheets. $0.
- **Difficulty:** low. The pick-up sequences for real dealing need working out.
- **Risks:** three deals take time. A fishing question is needed to assign the cards to people.
- **Novelty:** it is a group-testing design; I did not find it as a card trick.

### 12. Ten boxes, one swap (level 2)
- **Effect:** ten spectators' names are sealed in ten numbered boxes mixed by the audience. Each
  may open at most five boxes, starting with the box bearing their own number and following the
  number they find. All ten find their own name.
- **Method:** the cycle strategy alone succeeds 35% of the time for ten boxes. The performer
  learns the arrangement (marked slips, or a glimpse while "checking the lids") and secretly
  swaps the contents of two boxes to split the one long cycle.
- **Materials and cost:** ten boxes. $10.
- **Difficulty:** low; the swap is the sleight.
- **Risks:** it is procedural and reads as a puzzle unless staged as a bet against the house.
- **Novelty:** the puzzle and the helper variant are known; staging it is the contribution.

## 5. Dead ends and overhyped items

- **Full physical zero-knowledge proofs as entertainment.** Sudoku-scale proofs need dozens to
  hundreds of cards and many minutes. Only the five-card family is short enough.
- **Hat-guessing strategies with real spectators.** Every participant must compute a
  Hamming-code rule.
- **Chameleon hashes and trapdoor commitments.** No audience can verify the commitment, so the
  equivocation buys nothing.
- **MD5 collisions for a technical crowd.** They work and are free, and the first programmer in
  the room will say "MD5".
- **"It's on the blockchain" as a convincer.** It carries little weight with lay audiences and
  invites the multiple-commitments theory from informed ones.
- **Exact arithmetic-coded steganography over live speech.** One mis-heard token desynchronises
  the decoder.
- **Oblivious transfer, private information retrieval, mental poker, time-lock puzzles as
  plots.** The audience cannot see the privacy guarantee, so nothing appears to happen.
- **Quantum pseudo-telepathy games.** They need shared entanglement; lab only.
- **The 64-coin chessboard decoded mentally.** Too slow and error-prone live; use 15 or 16.
- **Anoto-scale dots on commercially printed playing cards.** 0.3 mm grids with sub-0.1 mm
  offsets exceed 300 dpi card printing.
- **Paper-fibre fingerprints for playing cards.** The method needs light through the sheet.
- **Non-transitive dice as a sure-thing bet.** Widely exposed; fine as a gift, weak as a mystery.

## 6. Open leads

- Explicit code tables for single-swap-correcting codes in S_5 and S_7 (Buzaglo and Etzion), and
  Levy and Malinovsky's announced paper on symmetry in optimal card-trick strategies.
- Which functions the 2025 single-cut full-open protocols compute, and whether a three-person
  one-cut protocol makes a better plot than the two-person AND.
- Ueda et al. on physical implementations of the random bisection cut, which I recall includes
  human experiments on whether observers can track a cut (unverified; Springer redirected to a
  login). That is direct empirical data on false-shuffle detectability.
- Multi-secret visual cryptography by rotation or offset: find the original constructions and
  measure contrast for two, three and four images on laser film.
- Polyglot file tooling and key multi-collision code for the non-committing-encryption variant.
- Covering-design tables (La Jolla Covering Repository; host blocked here) for sizing indexes.
- Optimal adaptive strategies for two thinkers among 52 (the lower bound is 11 joint answers).
- Wet-paper constructions for q-state objects (cards in four orientations).
- Magic-side prior art I could not check: Leo Boudreau's binary-code mentalism, Mulcahy's "Card
  Colm" columns, the Gathering 4 Gardner exchange books, College Mathematics Journal and Math
  Horizons back issues, the MOVES conference volumes.
- dblp was blocked by a bot wall, so the full card-based cryptography bibliography was not
  enumerated; the lists here come from arXiv and ePrint search pages.

## 7. Sources

Opened unless marked "(seen in search results)" or "(listing only)".

1. https://arxiv.org/abs/2611.02424 - Levy and Malinovsky, new twists on Cheney's trick (2026).
2. https://arxiv.org/abs/2405.21007 - Chen, Khovanova et al., Card Tricks and Information (2024).
3. https://blog.tanyakhovanova.com/2024/08/the-5-card-trick-the-4-card-trick-and-the-3-card-trick/ - summary of the three tricks.
4. https://web.northeastern.edu/seigen/11Magic/FitchCheneyFiveCardCount/n-card%20tricks%20-%20Chen%20and%20Cooper.pdf - n-card tricks (seen in search results).
5. https://rjlipton.com/2016/03/14/one-flip-sends-many-bits/ - the chessboard coin puzzle and its Hamming solution.
6. https://arxiv.org/abs/1408.4963 - Buzaglo and Etzion, permutation codes under Kendall tau (listing only).
7. https://arxiv.org/abs/2406.06029 - improved bounds on permutation codes (listing only).
8. https://en.wikipedia.org/wiki/Fantoni_and_Nunes_cheating_scandal - card-orientation signalling in bridge.
9. https://datatracker.ietf.org/doc/html/rfc6238 - TOTP specification.
10. https://en.wikipedia.org/wiki/The_Zancigs - the Zancig code and its exposure.
11. https://en.wikipedia.org/wiki/The_Piddingtons - the BBC broadcasts and proposed methods.
12. https://arxiv.org/abs/1909.01496 - Ziegler, Deng and Rush, Neural Linguistic Steganography.
13. https://arxiv.org/abs/2010.00677 - Shen, Ji and Han, self-adjusting arithmetic coding (listing only).
14. https://eprint.iacr.org/2021/686 - Meteor, provably secure steganography.
15. https://arxiv.org/abs/2210.14889 - de Witt et al., minimum entropy coupling (seen in search results).
16. https://arxiv.org/abs/2401.10360 - Zamir, undetectable payloads in LLM output.
17. https://arxiv.org/abs/2401.16820 - Qu et al., provably robust multi-bit watermarking.
18. https://arxiv.org/abs/2410.04328 - OD-Stega (listing only).
19. https://arxiv.org/html/2501.00786v1 - Shifting-Merging steganography (seen in search results).
20. https://arxiv.org/abs/1207.1336 - Swanson and Stinson, Russian cards via designs (listing only).
21. https://arxiv.org/abs/1401.1526 - Swanson and Stinson, further constructions (listing only).
22. https://arxiv.org/abs/1301.4289 - Cordon-Franco et al., geometric protocol (listing only).
23. https://arxiv.org/abs/2009.13644 - Rajsbaum, distributed-computing view (listing only).
24. https://arxiv.org/abs/cs/0702097 - Atkinson, van Ditmarsch and Roehling, bias in cards cryptography (listing only).
25. https://www.ms.uky.edu/~jrge/Papers/Hamming.pdf - Ehrenborg, Decoding the Hamming code (Math Horizons 2006).
26. https://arxiv.org/abs/0705.1220 - simple solution to Ulam's game with one lie (seen in search results).
27. https://arxiv.org/abs/math/0407504 - pathological liar game with fixed lies (listing only).
28. https://arxiv.org/abs/2104.01664 - Renyi-Ulam game with restricted query size (listing only).
29. https://arxiv.org/abs/1902.06002 - Aldridge, Johnson and Scarlett, Group Testing monograph.
30. https://github.com/sipa/minisketch - PinSketch set reconciliation.
31. https://en.wikipedia.org/wiki/Covering_code - football pools problem values.
32. https://en.wikipedia.org/wiki/Hat_puzzle - Ebert's game and line variants.
33. https://en.wikipedia.org/wiki/100_prisoners_problem - cycle strategy and the swap variant.
34. https://arxiv.org/abs/1810.08263 - Too Many Hats (listing only).
35. https://arxiv.org/abs/2205.02815 - cut-down de Bruijn sequences (listing only).
36. https://arxiv.org/abs/0710.5611 - Johnson, universal cycles for permutations (seen in search results).
37. https://arxiv.org/abs/2204.02910 - shortened universal cycles for permutations (listing only).
38. https://arxiv.org/abs/2603.11954 - universal cycles for k-subsets and multisets (listing only).
39. https://arxiv.org/abs/2603.11934 - decoding universal cycles for subsets (listing only).
40. https://arxiv.org/abs/2401.14341 - orientable sequences in O(1) amortised time (listing only).
41. https://arxiv.org/abs/2407.07029 - k-ary orientable sequences (listing only).
42. https://arxiv.org/abs/2610.33601 - Mitchell, searching for binary orientable sequences (listing only).
43. https://arxiv.org/abs/2609.27583 - shorthand universal tori for permutations (listing only).
44. https://arxiv.org/abs/2306.01498 - de Bruijn tori from alternating sequences (listing only).
45. https://mathweb.ucsd.edu/~ronspubs/08_05_products.pdf - Diaconis and Graham, products of universal cycles (seen in search results).
46. https://en.wikipedia.org/wiki/Anoto - dot pattern and products.
47. https://github.com/cheind/py-microdots - open Anoto codec.
48. https://en.wikipedia.org/wiki/De_Bruijn_torus - definition, examples, applications.
49. https://eprint.iacr.org/2017/423 - Koch and Walzer, actively secure card-based cryptography.
50. https://arxiv.org/abs/2010.08445 - Dvorak and Koucky, Barrington Plays Cards (listing only).
51. https://arxiv.org/abs/2510.17308 - single-shuffle full-open protocols for any function (listing only).
52. https://arxiv.org/abs/2507.03323 - single-cut full-open protocols (listing only).
53. https://arxiv.org/abs/2509.17595 - impossibility results by optimisation (listing only).
54. https://eprint.iacr.org/2026/1061 - Beaver, S4 Is All You Need.
55. https://arxiv.org/abs/2603.18608 - complexity hierarchy of shuffles (listing only).
56. https://arxiv.org/abs/2609.02716 - virtual player simulation (listing only).
57. https://arxiv.org/abs/2501.12080 - balance-based cryptography.
58. https://arxiv.org/abs/1911.05994 - n-variable equality with 2n cards (listing only).
59. https://arxiv.org/abs/2402.16290 - card-based overwriting protocol (listing only).
60. https://arxiv.org/abs/2511.05111 - five-card trick under biased shuffles.
61. https://www.microsoft.com/en-us/research/wp-content/uploads/2009/01/GradwohlNPR09.pdf - Sudoku zero-knowledge, cryptographic and physical.
62. https://arxiv.org/abs/2106.13646 - two standard decks for Sudoku (listing only).
63. https://arxiv.org/abs/2106.14020 - Nonogram (listing only).
64. https://arxiv.org/abs/2112.12042 - Makaro with a standard deck (listing only).
65. https://arxiv.org/abs/2202.09788 - Shikaku (listing only).
66. https://arxiv.org/abs/2302.07251 - Ball Sort puzzle (listing only).
67. https://arxiv.org/abs/2302.01235 - printing protocol (listing only).
68. https://arxiv.org/abs/2304.12388 - first non-zero term protocols (listing only).
69. https://arxiv.org/abs/2408.13507 - Tatami puzzles (listing only).
70. https://arxiv.org/abs/2409.14308 - Zeiger (listing only).
71. https://arxiv.org/abs/2603.01393 - Hotaru Beam (listing only).
72. https://marc-stevens.nl/research/hashclash/Nostradamus/ - the MD5 election "prediction".
73. https://sha-mbles.github.io/ - SHA-1 chosen-prefix collision and costs.
74. https://opentimestamps.org/ - timestamping service.
75. https://petertodd.org/2016/opentimestamps-announcement - aggregation and what a timestamp proves.
76. https://eprint.iacr.org/2019/016 - Dodis et al., message franking and non-committing AES-GCM.
77. https://eprint.iacr.org/2020/1491 - Len, Grubbs and Ristenpart, partitioning oracle attacks.
78. https://eprint.iacr.org/1998/010 - Krawczyk and Rabin, chameleon hashing.
79. https://en.wikipedia.org/wiki/Visual_cryptography - schemes and cheating.
80. https://arxiv.org/abs/math/0302043 - extended visual cryptography systems (listing only).
81. https://arxiv.org/abs/cs/0610172 - extended and colour schemes (listing only).
82. https://arxiv.org/abs/2510.00763 - colour visual cryptography (listing only).
83. https://arxiv.org/abs/2508.05394 - random-grid threshold schemes (listing only).
84. https://arxiv.org/abs/1210.6123 - greyscale schemes with reversing (listing only).
85. https://arxiv.org/abs/1705.02510 - paper fingerprinting from texture.
86. https://en.wikipedia.org/wiki/Mental_poker - protocols and limits.
87. https://en.wikipedia.org/wiki/Dobble - projective-plane structure.
88. https://arxiv.org/abs/2611.18722 - maximum sets among 16 SET cards (listing only).
89. https://en.wikipedia.org/wiki/Kruskal_count - history and probabilities.
90. https://arxiv.org/abs/math/0110143 - Lagarias, Rains and Vanderbei, The Kruskal Count (listing only).
91. https://arxiv.org/abs/2610.29015 - Kruskal-type process (listing only).
92. https://en.wikipedia.org/wiki/Penney%27s_game - odds tables and the card variant.
93. https://arxiv.org/abs/2404.06585 - Penney's game for permutations (listing only).
94. https://arxiv.org/abs/2009.06080 - Penney's game with group action (listing only).
95. https://arxiv.org/abs/2006.13002 - variants of Penney's game (listing only).
96. https://arxiv.org/abs/2011.10067 - intransitive dice tournament (listing only).
97. https://arxiv.org/abs/2310.17083 - central limit theorem for intransitive dice (listing only).
98. https://arxiv.org/abs/2201.07004 - Snakes and Ladders intransitivity (listing only).
99. https://arxiv.org/abs/2311.12811 - self-similar non-transitive dice (listing only).
100. https://arxiv.org/abs/2509.11395 - Card Dealing Math (listing only).
101. https://arxiv.org/abs/2302.03579 - Unshuffling a deck of cards (listing only).
102. https://arxiv.org/abs/2308.02684 - the odd Hummer principle (listing only).
103. https://arxiv.org/abs/1809.04072 - the 21-card trick generalised (listing only).
104. https://arxiv.org/abs/2409.01296 - Fibonacci partial sums tricks (listing only).
105. https://arxiv.org/abs/2508.18277 - Gozinta boxes (listing only).
106. https://arxiv.org/abs/2604.13799 - knots by sleight of hand (listing only).
107. https://arxiv.org/abs/2402.13802 - model checking a card trick.
108. https://arxiv.org/abs/2401.14516 - dynamic logic of misdirection (listing only).
