# Phase 2: invention

Phase 1 produced 27 research reports in /home/user/verified-gifs-only/magic-research/ (files 01 to 27). Phase 2 uses them to invent. You are one of five invention agents, each working through a different lens (yours is named in your prompt and described at the bottom of this file). Web research is not the job now; thinking is. Look something up only to check a number that decides whether an idea works.

## What the person commissioning this wants

They are a hobbyist who has recently got into magic and can build things (3D printer, hobby electronics, software, ordered PCBs). Their words, lightly condensed:

> I want you to be more creative, and anchor less on obviously "illusion-like" science. Instead, ask: what could this enable me to do? It can be a small input to a more traditional illusion, but more excitingly could enable an entirely new mechanism. Think creatively.

So: a published phenomenon shown as a trick is the least interesting output. The most interesting is a mechanism that could not have existed before, built from capabilities that look nothing like magic (an adhesive, a tolerance, a timer, a print service, a sensing chip, a statistics table), where the audience never sees or suspects the technology.

## Read first

1. /home/user/verified-gifs-only/magic-research/00-brief.md (the "Course correction" and "Shared vocabulary" sections).
2. /home/user/verified-gifs-only/magic-research/digest.md in full. It holds every report's summary, its list of capability primitives, and the titles of the effect concepts each report already proposed. It is long (about 45,000 words); read all of it, because the value you add comes from connecting things that sit in different reports.
3. Then open the full reports that matter for your ideas (catalog sections have the numbers, part names and sources). Do not read all 27 in full.

## What makes a good idea here

- It answers "what can I now do?" with a mechanism, and the mechanism is specific enough to start building: named parts or materials, rough dimensions, forces, times, costs.
- It combines capabilities from at least two different reports, or pairs one new capability with a classical principle so that each covers the other's weakness (sleight of hand cancels "it's electronic"; technology cancels "they switched it").
- The audience's experience is stated first, in one or two sentences, and is strong: it happens in their hands, to their own object, under conditions they set, or long after the performer has gone.
- It handles the standard audience theories on purpose. Report 04 found that a false solution the audience has seen disproved keeps blocking the real one, that visible inert technology is readily believed, and that an examinable electronic prop is still shrugged off as "rigged" (report 03). Say which theory the audience will reach for and how the design kills it.
- It is not already in the "Effect concept titles" lists in the digest. Those ideas are taken. You may build on one (say which) if you take it somewhere clearly further, or combine two of them into something neither report saw.
- It is not an existing commercial product (report 02) or documented prior art (report 03, and the prior-art notes in 19, 21, 22, 25).
- Odd, risky, half-formed ideas are wanted, as long as the risk is named. A list of safe obvious ideas is a failure.

Avoid: phone screens as the visible prop; visible science demos (levitators, colour-change beakers, aerial images) as the effect; anything that needs a lab; anything unsafe to a spectator; methods that depend on deceiving third parties, forging signatures on documents, copying currency, or reading people's private data. Respect the dead-ends each report lists.

## Output

Write one Markdown file at the path given in your prompt. Create it early with a skeleton and extend it in place. Do not edit other files and do not commit.

Structure:

1. **How I worked the lens** (short): what you looked for and the three or four patterns you found most fertile.
2. **Concepts**: 14 to 18 of them, best first. For each:
   - **Name** and a one-line pitch.
   - **Effect**: what the audience experiences, in their terms. Performance context (close-up, parlor, stage, installation, at-home-later).
   - **Method**: the mechanism, step by step, concrete. Include the secret operations it relies on (hold/release, move, swap, duplicate, conceal, transform, know, tell, delay, control chance or choice, erase evidence, prove ordinariness).
   - **What makes it newly possible**: the capabilities used, each with the report number it comes from (for example "gadolinium Curie release, report 07") and the key number.
   - **Audience theories and how they die**.
   - **Build**: parts, rough cost, tools, difficulty (weekend / month / hard), and reset or per-show cost.
   - **Riskiest assumption** and the cheapest bench test that would kill or confirm it (ideally under $30 and an afternoon).
   - **Novelty**: what the nearest existing thing is, as far as the reports show, and what is different.
3. **Sparks**: 15 to 25 one- or two-line ideas you did not have room to develop. Quantity matters here; do not polish.
4. **Patterns**: 5 to 8 general design patterns you noticed (reusable recipes of the form "capability X plus classical principle Y gives Z"), since the person will keep inventing after this review.

Your final message goes to the coordinating agent, not the end user. Keep it under 300 words: the file path, your five strongest concepts in one line each, and the patterns in one line each.

## The five lenses

**A. Weakness-first.** Start from the demand side. Report 01 section 3 ranks the classical method weaknesses most worth attacking, and its sections 2.3 and 2.7 state the secret operations as engineering specs ("Wanted / Today"). Report 02 section 3 lists product gaps. For each major weakness, design the best new solution you can from the whole capability pool, then say which classic routines it unlocks or transforms. Aim to cover most of the ranked weaknesses, with more than one solution for the top few.

**B. Architecture-first.** Ignore individual tricks and invent new ways of structuring a method. Candidates to develop and go beyond: methods whose work happens hours or weeks before or after the performer is present; gimmicks that erase themselves so the final object is honest; brute-force outs at a scale no person could carry; every-visible-object-is-passive designs where the room, table or performer holds all the technology; closed loops that sense and act faster or more patiently than a person; methods designed by computer search; methods that use the audience's own checks (examination, sealing, shuffling, signing, weighing, photographing) as the working part; props that behave one way for the performer and another for a spectator; outsourcing the "dirty work" to a neutral third party such as a print service or the post. For each architecture give two or three fully worked instances.

**C. Collisions.** Deliberately combine capabilities from reports that have nothing to do with each other. Work systematically: take a primitive from one report and ask what it becomes next to a primitive from a distant report (dental lab x coding theory; packaging line x chemistry timers; coin acoustics x cryptographic commitments; tape-spring booms x thermochromics; card-based cryptography x instrumented tables; paper fingerprinting x print-on-demand; eddy-current braking x choice statistics; sublimating wax x postal services). Run at least 40 such pairings, keep a visible log of the pairings you tried in section 1 (one line each, including the ones that went nowhere), and develop the best into full concepts. Prefer the strange ones.

**D. Plot-first.** Invent new effects, not only new methods. Classical magic has roughly nineteen effect types because those were what classical methods could deliver. With this capability pool, what impossible experiences become available that are not in the classical list or are only there in name? Think about things that happen across time (days, weeks), across distance, inside sealed or owned or borrowed things, to several people at once in different ways, in the spectator's home after the show, to objects the spectator has lived with, through senses other than sight (weight, temperature, taste, sound for one person only), and effects whose "impossible" quality comes from conditions the audience can state precisely (provable fairness, verified seals, their own measurements). Describe each as an experience first and make it emotionally worth having; then give the method.

**E. Classic routines, upgraded.** The person is learning standard magic. Take about fifteen routines a hobbyist will actually meet (Ambitious Card, card to impossible location, any card at any number, Out of This World, Triumph, coins across, coin in bottle, Chop Cup or cups and balls, linking rings, ring on string or ring flight, torn and restored, bill in lemon, book test, billet or drawing duplication, prediction in a sealed envelope, floating or haunted object, spoon or key bending, which hand, Rubik's cube solves, the "light and heavy" plot, a séance-style piece) and for each design the upgrade that most changes what the audience sees or what conditions the performer can allow, using small hidden inputs from the capability pool. Keep the classical method doing the visible work wherever that helps cancel suspicion. For each, state what the standard version cannot do that yours can.
