# Shared brief: technology-transfer literature review for magic

Every research agent on this project reads this first. It gives the thesis, the shared
vocabulary, the report format, and the quality bar.

## Thesis being tested

The person commissioning this is a hobbyist who has recently got into magic and can build things
(3D printer, hobby electronics, software). Their intuition:

> Lots of engineering / physics / materials-science results from the last ~10 years can now be
> reproduced for tens to hundreds of dollars, because of cheap on-demand fabrication (3D printing,
> PCB/PCBA houses, CNC/laser services), cheap components, and LLMs that can write CAD, firmware and
> software. Magic has barely absorbed any of this. So there should be many new or much-improved
> magic effects sitting unbuilt.

Two directions of search:

1. **Effect -> technology**: take existing magical effects and methods and ask how newer
   materials, fabrication, electronics or software could improve them (stronger, cleaner, more
   examinable, cheaper, more reliable). Simply 3D-printing an old gimmick better counts.
2. **Technology -> effect** (the more interesting direction): survey engineering, physics,
   materials science, HCI and software, and ask what impossible-looking phenomena each result could
   produce in front of a live audience.

Software effects are in scope, but the person finds phone-screen magic weak ("people only looking
at phones"). Prefer software whose result shows up in the physical world, on ordinary objects.

## Shared vocabulary

**Effect classes** (Fitzkee's list, used as common tags): production, vanish, transposition,
transformation, penetration, restoration, animation, anti-gravity/levitation, attraction,
sympathetic reaction, invulnerability, physical anomaly, spectator failure, control,
identification, thought reading, thought transmission, prediction, extrasensory perception.

**Performance contexts**: close-up (inches away, objects handled by spectators), parlor (5-50
people), stage, walk-around/street, installation or unattended object (no performer), video-only.

**What makes technology useful as a magic method** (judge every item against these):

- Invisible, or disguised as something ordinary, or it has an innocent reason to be there.
- The effect is clear in one sentence from the audience's point of view.
- Examinability: can the object be handed out before or after? What gives it away (seams,
  weight, sound, heat, smell, glow, wires, lag)?
- Angles, lighting, distance and ambient-noise constraints.
- Reliability and failure modes in live performance; reset time; pocket/table space; battery life.
- Too-perfect problem: if the only explanation an audience can think of is "it's electronic" or
  "it's a screen", the effect is weak. Note when a technology has this problem and how it could be
  disguised or cancelled out.
- Buildable by one hobbyist for roughly $10 to $500, with consumer 3D printing, ordered PCBs, and
  off-the-shelf parts. Flag anything that needs a lab.

## How to research

- Use web search and page fetches heavily (WebSearch / WebFetch; if they are not in your tool
  list, load them with ToolSearch `select:WebSearch,WebFetch`). Expect to run 30 to 60+ searches.
  Send several searches per turn.
- Time window: mainly 2015 to 2026. Older work only where it is the foundation.
- Prefer primary sources: papers (arXiv, ACM DL, Nature/Science family, Advanced Materials, APL,
  SIGGRAPH, UIST, CHI, TEI, ICRA), lab project pages, patents (Google Patents), supplier and
  service pages for prices, and for magic: books, journals, product pages, maker write-ups.
- **Never invent a citation.** Give a URL you actually saw in search results or opened. If you
  are recalling something from memory and could not confirm it, write "(unverified)" next to it.
  Give prices with the source and note that they are as of late 2026.
- Go for breadth first (map the whole slice), then depth on the 10 to 20 most promising items.
- Stay in your slice. Other agents cover the neighbouring slices listed in your task; a one-line
  pointer is enough when you touch theirs.
- Flag safety hazards plainly: lasers, high voltage, chemicals, fire, strong magnets, electrical
  muscle stimulation, anything aimed at a spectator's body.

## Report format

Write one Markdown file at the path given in your task. Aim for 3,000 to 6,000 words and 30+
distinct sources. Structure:

1. **Summary** - 10 or so bullet points: the most important things found.
2. **Catalog** - the main body. One entry per technology / principle / product / paper cluster:
   - What it is and how it works (2 to 5 sentences, concrete numbers where they matter).
   - Key references: authors, year, venue, URL.
   - Accessibility: off-the-shelf / hobbyist-buildable / lab-only, with rough cost.
   - Magic relevance: which effect classes it could power, which existing method it could
     upgrade, and its deception properties against the criteria above.
   - Known prior use in magic, if any (products, performers, patents).
3. **Effect concepts** - 6 to 12 concrete ideas from your slice. For each: the effect as the
   audience experiences it, a method sketch, a rough bill of materials and cost, build difficulty,
   main risks, and how novel you believe it is.
4. **Dead ends and overhyped items** - things that sound magical but will not work live, and why.
5. **Open leads** - things worth a deeper look that you ran out of budget for.
6. **Sources** - a flat list of URLs with one-line descriptions.

(Survey agents whose slice is magic itself rather than a technology adapt section 2 to their
subject as described in their task, and keep the rest.)

Do not commit or push anything. Do not write files other than your report.

## What to send back

Your final message is read by the coordinating agent, not the end user. Keep it under 400 words:
the file path, the five most important findings, your three best effect concepts in one line
each, and anything you could not verify or could not access.
