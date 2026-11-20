# Phase 3: critique

Phase 1 produced 27 research reports (files 01 to 27 in /home/user/verified-gifs-only/magic-research/, with a cross-report digest in digest.md). Phase 2 produced five invention files in /home/user/verified-gifs-only/magic-research/ideas/ (A to E), each with 14 to 18 developed concepts for new magic methods and effects. Phase 3 is an adversarial review of those concepts. You are one of two critics; your role is named in your prompt and described below.

The person this is for is a hobbyist who has recently got into magic and can build things (3D printer, hobby electronics, software, ordered PCBs). They want mechanisms that are new, not science demos dressed as tricks, and they will actually try to build the best ones. A concept that fails on the bench or falls flat in front of people costs them weeks, so an honest "this will not work, because..." is worth more than encouragement. The inventors were asked to be bold; many of their numbers are estimates and some will be wrong.

## Read

1. /home/user/verified-gifs-only/magic-research/00-brief.md ("Course correction" and "Shared vocabulary").
2. All five files in /home/user/verified-gifs-only/magic-research/ideas/ in full (developed concepts; skim the "Sparks" lists and flag any spark that deserves promotion).
3. The research reports that bear on what you are checking. digest.md gives you the map; the full reports have the numbers and sources.

## Roles

**Critic X: engineering and physics.** For every developed concept, check whether the mechanism can work as described. Redo the arithmetic that the idea depends on (forces, energies, thermal budgets, thicknesses, masses, timings, link budgets, battery life, tolerances, chemistry timings, probabilities) with a short calculation, and run a script where a simulation or enumeration settles it. Look for the unstated requirement that breaks it (a part that does not exist at that size, a material that does not behave that way, a signal lost in noise, heat that has nowhere to go, a tolerance a hobby tool cannot hold, a consumable that will not survive a pocket). Judge buildability by one person with the stated tools, the real cost, and safety. Where an idea fails as written but a modified version would work, give the modification.

**Critic Y: magic, audience and prior art.** For every developed concept, judge it as a piece of magic: is the effect clear in one sentence and does anyone care; what will a real audience guess, and does the design defeat that guess or just assert that it does (use report 04's findings on false solutions, examination, suspected technology, delay costs, and report 03's finding that an examinable electronic prop was still dismissed as "rigged"); the too-perfect problem; practicality in performance (angles, lighting, noise, pocket and table management, reset, what happens when it fails mid-show, how long the audience is asked to wait); whether the method needs conditions a hobbyist performing for friends will not have. Then check novelty: compare against report 02 (market), report 03 (prior art) and the prior-art notes in reports 19, 21, 22 and 25, and use web search and page fetches on the strongest 15 to 20 concepts to look for existing products, published tricks or patents that already do it (dealer sites, Conjuring Archive / Conjuring Credits, Genii and Magic Cafe threads, Google Patents). Web search may be capped at a small number of calls, so spend them on the concepts that would otherwise rank highest. Flag ethical or legal problems (deceiving third parties, forging identity marks beyond props, currency, privacy, false psychic claims, safety).

## Output

Write one Markdown file at the path given in your prompt. Create it early and extend it in place. Do not edit other files and do not commit.

1. **Verdict table** covering every developed concept in all five files. Columns: ID (file letter plus the concept's number, for example B7), name, score 1 to 5 on your axis (5 = sound and worth building; 1 = does not work), one-line reason, and the single most important fix or test.
   - Critic X scores: feasibility.
   - Critic Y scores two columns: strength as magic, and novelty (5 = nothing like it found; 1 = already sold or published).
2. **The best**: your top 15, each with a paragraph: why it survives, what must be true, and the first bench test or rehearsal test to run.
3. **The broken**: every concept you scored 1 or 2, with the specific failure, and a repair if one exists.
4. **Duplicates and merges**: concepts from different files that are the same idea or that would be stronger combined.
5. **Corrections to the research**: any figure in the phase 1 reports that your checking shows to be wrong or misleading.
6. **Sparks worth promoting**: up to 10 of the undeveloped one-liners that you think beat most of the developed concepts, with a sentence on why.

Your final message goes to the coordinating agent, not the end user. Keep it under 300 words: the file path, your top 10 concept IDs in order with a few words each, the most serious failures, and anything you could not check.
