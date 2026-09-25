<!-- PR TARGET: https://github.com/NaluNinja/allen-mehr | Individual Research Paper -->
# Individual Research Paper — pre-deadline read

**What I read.** `docs/briefs/research-brief.md` · `docs/briefs/originals/research-brief.docx`
(opened with python-docx — 27 paragraphs, one inline chart image, no tables) ·
`capabilities/economic-research/spec.md` · `capabilities/economic-research/source-verification.md` ·
`capabilities/economic-research/README.md` · `drafts/README.md` ·
`analysis/figures/shortage-duration-by-drug-type.svg` · `analysis/required-uplift-u.xlsx` (formulas,
not just values) · `analysis/figure2-breakeven-recompute.csv` · `prompt-log.md` · the READMEs under
`analysis/`, `data/` and `capabilities/` · the file tree and commit history.

**What I did not open this pass.** `capabilities/marginal-analysis/` · `analysis/perfect-competition-analysis.md`
· `docs/decisions/perfect-competition-memo.md` · `docs/briefs/perfect-competition-brief.md` · the three
Stage 3 marginal-cost PNGs · `docs/templates/` · `AGENTS.md`, `BIO.md`, `CLAUDE.md`, `RESUME.md`,
`README.md`. If something in those changes an item below, say so and I will look.

---

`source-verification.md` is real verification, and nobody asked you for it. It does the thing the name
claims: it goes to the source and reports what the source says, against the claim, and it catches your
own brief five times. The GPO reverse auction your third pillar rests on is not in the Brookings piece
at all — that piece covers MAC lists and nothing else, so the claim either finds a source or narrows to
what is sourced. "Intas voluntarily shut the plant down" is a different event from the documented FDA
import alert, and you noticed that the second one makes your argument stronger. The 10–15% price
decline is a 2017–2018 rate that moderated to 5–10% by 2021, not an ongoing one. "Nearly two decades"
undersells tracking that runs back to 2001. And "loses money on roughly half its products" is both
understated and the wrong population — ASPE puts 60–76% of generic *injectable* entries underwater at
36 months, which is your number and your category. You also resolved a primary behind a secondary:
E(CC) is ASPE's own derivation from ERG, not a figure in ERG's Table A-6, whose eighteen product
pathways contain no plain sterile injectable. And you marked three sources you could not reach rather
than letting secondary reporting pass as verified. This is a list you wrote, not one I found.

**The one thing it cannot yet reach is the paper.** §2's verification table has nine rows and all nine
come from one document, the ASPE ROI brief. KFF, Brookings, Hamilton, ASHP and the FDA record carry the
paper's narrative and have no row, so the column that says "anything not yet verified cannot enter the
paper" does not govern the sources most likely to enter it. Give them rows.

**One side of your own test is not sourced, and it decides the paper.** §3 states the condition you
accepted: the recommendation holds if the uplift needed to make a sterile line viable is small next to
the dollar cost of the shortages it prevents — and if it isn't, the Hamilton loans win. You have built
the uplift side and built it well. `required-uplift-u.xlsx` is live formulas, `MAX(0, E(CC)/R − 0.58)`,
and `figure2-breakeven-recompute.csv` reproduces all 75 cells. There is no shortage-cost series
anywhere in §2, in `data/`, or in the history. Until that number exists the comparison cannot be run,
and everything below is contingent on it.

**Figure 2 has no anchor on its x-axis.** The curve runs $1M to $25M in revenue, and §4's claim is that
a flat add-on "that rescues the median product does nothing for the tail." Nothing committed says where
the median injectable product's 36-month revenue sits, so "median" has no value and the tail claim
cannot be checked. Your own spec says ASPE publishes that distribution in $100,000 increments — pull
it, and the figure gets a vertical line and the claim gets a number.

**§6 is three empty checkboxes and one item I could not trace.** Success Criteria is the section that
tells you before you look at the data whether the answer counts, and it is the only section still
unwritten. The failure condition in §3 is already the criterion; it needs a threshold in numbers rather
than "small next to." The one item there — footnote the ASPE appendix ROI discrepancy — names a
discrepancy I could not find in `source-verification.md` or in the prompt log. What is it, and where is
it written down? It belongs in the verification file with the rest of the checking.

**The spec is at 13.8 KB and `drafts/` holds a 272-byte README.** That README says what it is for:
"dated snapshots of the research paper, one per working session, kept as the real chain of drafts,
including the versions that were wrong." §§3 and 5 have gotten sharper on each pass and §5 now reads as
argument rather than plan, so a first snapshot would be mostly transcription — which is an argument for
writing it, not against. The spec is already longer than four double-spaced pages allow, roughly a
thousand words, and the one question a spec cannot answer is whether the argument fits. A draft answers
it.

**The scope amendment is in the spec and not in the brief.** The brief's title names four drugs; §1
narrows to cisplatin and carboplatin and puts amoxicillin and IV saline out of scope. Two honest exits:
amend the brief so it names the two drugs the paper covers, or keep all four. Amending is the sanctioned
move and the commit history records it — that is what history is for. Your spec has already chosen, so
this is a matter of making the brief say so. `capabilities/economic-research/README.md` has not followed
either: it still names "cisplatin, carboplatin, and IV saline," still lists `spec.md` as "Not yet
written," and still says source-verification holds "the four that still need fixing" where the file now
names five.

**Mechanical, and cheap while there is no draft.** Figure 1 is built, labeled and sourced, and it
carries a correction the brief's table does not — that route and essentiality are two cuts of the same
data, not one five-row ranking. It satisfies Graph/Chart/Diagram at 10% on its own; a table would not.
In the references, Wosińska and Frank carries no year. Four pages maximum excluding title page, graphs,
bibliography and appendix; APA, MLA or Chicago with the bibliography on its own page; the title page is
the only page that carries your name, and no repository URL appears anywhere in the paper — peer review
is double-anonymous, and the identifying-information check runs before papers are distributed. Separately,
the first 41 lines of `prompt-log.md` duplicate lines 42–82: the heading, the whole table and three
reflection sections appear twice. Nothing is lost; delete one copy.

**In order — item 1 decides whether 2 and 3 are worth doing:**

1. Find or build the dollar cost of shortages, and put it in §2. Your failure condition needs both sides.
2. Pull ASPE's revenue distribution and anchor Figure 2's median, then export the image.
3. Write §6 as numbers — the threshold that makes the recommendation hold — and record the appendix ROI discrepancy in `source-verification.md`.
4. Commit a first dated draft, and find out whether the argument fits in four pages.
5. Give KFF, Brookings, Hamilton, ASHP and the FDA record rows in §2's verification table, and carry the five corrections into the paper's prose.
6. Amend the brief to the two drugs, and update `capabilities/economic-research/README.md`.
7. Date the Wosińska and Frank reference; de-duplicate `prompt-log.md`.
