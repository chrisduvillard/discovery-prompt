---
name: discovery-prompt
description: Write a prompt, or a brief for a long unattended run, that makes a model leave the consensus answer and come back with new ideas that have been tested or can be, fitted to the project at hand. Use whenever the user asks for a prompt, brief, goal or agent instructions and wants original, contrarian, creative, outside-the-box or non-obvious thinking, new knowledge, new hypotheses or connections nobody has written down, or complains that a model only gives generic, average or consensus answers. Also use when the user says "discovery prompt", "missing link", "beyond the consensus" or "invent new knowledge", and when they ask to apply this method to a question directly.
---

# Discovery prompt

Write a prompt that gets a model past the consensus answer, fitted to the project you are in.

In a project, read its rules (`CLAUDE.md`, `AGENTS.md`) before any command that lists or searches it. A rule can
forbid even listing a folder, and a recursive listing breaks it before you have read it. Test runs of this skill
made exactly that slip.

## Why a prompt needs this

A model answers with an average of what has been written, so unprompted it returns what most informed people
already think. Three moves get past that, and every prompt this skill writes contains all three:

1. **Name the consensus and set it aside.** A model cannot move away from an average it has not stated. Once the
   usual answer is on the page, it becomes the thing to beat instead of the thing to repeat.
2. **Build candidates from the gaps.** The richest gap is a join nobody has written: one record shows A leads to B,
   another shows B leads to C, and no record says A leads to C. In 1986 Don Swanson joined two bodies of medical
   research that never cited each other (what fish oil does to the blood; what is wrong with the blood of Raynaud's
   patients) and a 1989 trial supported the conclusion neither had drawn. A model has read both sides of many such
   pairs and will not state the join unless asked.
3. **Let a test decide, and fix the test first.** A prompt alone produces conjectures. An idea becomes knowledge
   when it survives a test it could have failed. Most joins are trivial or false, so they are candidates, never
   answers.

Contrary is not the aim. New and true is. Where the consensus is right, the prompt should let the model say so and
move on, or it will produce takes that are different without being right.

## Step 1: Choose the size

| Size | When | What you produce |
| --- | --- | --- |
| Paragraph | A one-off question; the user wants a less average answer | The paragraph in `references/blocks.md`, lightly fitted |
| Discovery prompt | One session that should return new ideas, tested where tools allow | A five-step prompt built from `references/blocks.md` |
| Brief and launch line | A long unattended run in a project with data and tools | A brief saved in the project and a short line that starts the run; read `references/long-run.md` |

Choose from the request. When unsure, write the smaller one and say in a line that the larger exists.

If the user wants the method applied to a question now, not a prompt written ("just do it yourself", "what
haven't we thought of"), go to *Applying the method yourself* below.

## Step 2: Read the project before writing

Skip this for the paragraph. For the other two it is most of the work: a discovery prompt that does not know the
project's record sends the model to rediscover what the project already tried.

Find four things, the rules first:

- **The user's rules.** Project instructions (`CLAUDE.md`, `AGENTS.md`, the README, any method or contributing
  page). Where a rule is the user's own, quote it in the prompt in their words.
- **The record of what has been tried.** Experiment logs, idea lists, issues, changelogs, post-mortems, benchmark
  history, notes. This is the project's own consensus, and half of the novelty check.
- **What a test is here, and what it costs.** A benchmark, a backtest, a measurement, an A/B test, a proof, a
  reproduction, a user interview. How long one takes. What has not been looked at yet: data, cases or users that
  could serve as unseen ground.
- **The limits.** What must never be touched, spent, sent or installed.

If the project keeps no record, say so in the prompt and have the model build the consensus from outside sources
alone. If you cannot tell what would count as a test, ask the user that one question before writing: every other
part hangs on it.

## Step 3: Put the method into the project's terms

The five steps of the prompt carry seven parts:

| Part | What the prompt asks for | Step |
| --- | --- | --- |
| Consensus | Two lists, written first: what the field says, and what this project's record now believes. Beside each line, what would have to be true for it to be wrong | 1 |
| First thoughts | The first ideas that come to mind, written down and discarded: everyone has those. Name the answers the user is tired of, and the entries of the record that already dispose of them | 1 |
| Frontier | What the record leaves unresolved: anomalies, results that contradict each other, real effects nobody uses, things that worked and stopped, beliefs the data contradicted, data nobody has used, rules that changed recently | 1 |
| Links | Candidates built four ways: join two records through a shared middle term; push an accepted premise three steps further; transplant a result from another field; read an anomaly as the signal. Say what A, B and C are here. Things the project has already measured are ready-made halves | 2 |
| Is it new | Check the project's record, then search outside. Label each candidate: tried here; noticed here but never tested; published elsewhere and untried here; new | 3 |
| Kill | The strongest objection, from a critic that did not write the idea. A rival explanation of the same facts, and the observation that would come out differently under each | 4 |
| Choose, test, stop | Rank without the result, test few, each test stated in full before it is run and run once; then stop before the unseen ground and write the exact check for the owner to run | 5 |

Seven judgments go with the table. Write each one's reason into the prompt, because a session that knows the reason
applies the rule to cases the prompt did not foresee.

- **Choose among candidates by evidence that is not the result.** Rank by sources, by whether the test can
  conclude at all (count the cases, or the tests that fit in the time), by how much the idea could explain if
  true, and by a footprint: a trace the mechanism should leave that is not the outcome itself. The winner of many
  tries is partly luck, so an idea chosen for its result keeps less of it on unseen ground.
- **Decide what a look costs here.** Where the test ground is finite (a history, a fixed corpus, a cohort), every
  look at results spends some of it: the more candidates are looked at, the more the best one is fitted to that
  ground. There, results are read late and on few. Where fresh ground is cheap (new random samples, new inputs
  generated at will), a quick look may screen candidates, provided the judging test runs on ground the screen never
  saw and every judging test is counted. Say in the prompt which case this project is.
- **Keep the user's bar.** If the project defines what counts as a finding, quote it unchanged and cap the number
  of tests. Add a bar that rises with each test only where the project has none.
- **Fix the bar before the look, and never tune after it.** An idea that tests badly is not tested again with
  small changes until it passes.
- **Leave your own hypothesis out.** Reading the record, you will see joins yourself. List the halves in the
  prompt and leave the joins unstated: a session handed a hypothesis tends to come back having confirmed it. If
  one seems worth the user's attention, tell them in a line outside the prompt.
- **Test for the generic answer.** Have the prompt reject any idea that would apply unchanged to every other
  project of this kind. That is the average answer again, however it is worded.
- **Material is not prior art.** Something the record noticed and never tested is raw material to build on. A
  candidate is not new for restating it, and not dropped as tried for using it.

## Step 4: Write it

These apply to the discovery prompt and the brief. The paragraph already carries what it needs.

- **Plain words, with the reasons.** A bare list of musts gets followed to the letter and missed in spirit.
- **A finish that can be checked.** For a prompt, a fixed report format. For a long run, a card of numbered items
  that each need a number or a quotation.
- **Stop before what cannot be redone.** Spending unseen data, spending money, sending anything, changing anything
  that is live: the prompt has the model stop there and hand the decision to the user.
- **Honest labels.** The model marks what is in the record, what comes from a source it opened in the session,
  what is its own result and what is conjecture. Its memory of a paper is not a source.
- **"Nothing survived" is a valid result.** Say so in the prompt, or the model will promote a weak idea to have
  something to show.
- **Every sentence changes what the session does.** A fitted prompt runs long, and that is fine. Cut sentences
  that only explain the method to the user: those belong nowhere.

## Step 5: Hand it over, briefly

The user will read the prompt itself. The note around it is for what they must do or decide, and a long note
buries those. Do not describe what the prompt contains.

- **Paragraph:** the block, then at most three lines.
- **Discovery prompt:** the whole prompt in one fenced block, then about 250 words at most: what must be true
  before they paste it; the choices you made that they might make differently; one line on what the prompt cannot
  do.
- **Brief:** the brief saved inside the project and linked, not pasted; the launch line in one fenced block; then
  about 500 words at most: what to do before pasting, the choices that are theirs, what to expect.

What the prompt cannot do, for that one line: it changes how the model searches, not what it knows. The largest
step away from consensus comes from what the average document does not contain: their own data, observations and
constraints, and a way to run the test.

## Applying the method yourself

When the user wants the answer and not a prompt, do the five steps of the discovery prompt yourself; section 2 of
`references/blocks.md` says what each step holds once fitted to a project. Steps 2 and 3 above still apply: read
the project, rules first, and put the method into its terms. The seven judgments bind you as they would bind
the session you would have written for.

Keep the working out of the reply. The two lists, the first thoughts and the candidates you dropped are working
notes: the user asked for what survived.

Where a step needs something this session lacks, say so once and use the fallback:

| Missing | Do this instead |
| --- | --- |
| A way to run the test | End each survivor in a check for the owner: the cheapest measurement on the unchanged project that would confirm or kill it, the result that kills it, and only then the full test, with its expected size and the arithmetic |
| A separate agent to object | Argue against each candidate yourself and say the objections are your own. Keep the objection you could not answer: it tells the reader more than the ones you could |
| Search | Label novelty "not searched", never "new" |

The reply, in this order:

1. **The verdict, in the first lines.** How many candidates are worth the test the user named, which comes first,
   and what the whole reply rests on (for instance, that nothing was run).
2. **At most three candidates in full,** best first. For each: the claim in one sentence; what it joins (the
   recorded facts and the middle term); how new it is (one of the four labels, with the nearest earlier work
   linked); the check to run first and the result that would kill it; the expected size with its arithmetic,
   against the user's bar; the strongest objection.
3. **Everything else in a line each:** candidates checked and dropped, with the reason; the usual answers, with
   the entry of the record that disposes of them; beliefs in the record that nothing has tested.
4. **The stop.** How many full tests you would spend and why so few; the user's bar, quoted once; what to hand
   the owner of the unseen ground if something passes.
5. **Choices you made** where you would have asked, then the sources you opened.

Mark where a statement comes from only where a reader could mistake it, not on every sentence: a figure from the
record gets its path, a claim from outside gets its link, and a guess is called a guess. Something you remember
and did not open is a guess.

Keep it to about 1,200 words before the sources, commands and arithmetic included. A reader given seven candidates at equal length cannot tell
which two you would stake a test on, and that ranking is what they asked for.

## Reference files

- `references/blocks.md`: the paragraph, the five-step discovery prompt and how to fit each, and two optional
  prompts for breeding ideas over rounds. Read it before writing a paragraph or a discovery prompt, and before
  applying the method yourself.
- `references/long-run.md`: the launch line, the sections of a brief, the budget, the ledgers and the rising bar.
  Read it before writing a brief.
