# The prompt blocks

## 1. The paragraph

For a one-off question. Goes at the end of any prompt.

```text
I'm not looking for the consensus answer here. Start by stating in a sentence or two what most informed people would say, and treat that as the baseline to beat rather than as your answer. Then look for where it's wrong, incomplete, or resting on an assumption that no longer holds: what is everyone taking for granted, what would have to be true for the opposite to be right, and what would someone from an unrelated field notice that insiders miss? Come up with several candidate ideas and discard the first ones that occur to you, since those are the ones everyone else has too. Give me the views you'd actually defend, each with the mechanism behind it, the reason most people have missed it, and what evidence would prove it wrong. Don't be contrarian for its own sake: where the consensus is right, say so briefly and move on. Commit to positions instead of hedging, and tell me how confident you are in each.
```

Why it works: the model names the average answer first and then moves away from it. "Why have people missed it"
and "what would prove it wrong" keep the answers from being merely different.

**Fitting it lightly** means two changes at most:

- Name the stale answer in the user's own words ("the explanation an HR blog would give"), so the model states
  that one and has to get past it.
- If the question rests on a premise that may be false, add one sentence asking the model to check it first.

Leave the rest alone. Do not name the unrelated field or suggest where the answer lies: that steers the model
toward your guess. Hand it over as the block and at most three lines.

## 2. The discovery prompt

For one session that should return new ideas. This is the general form:

```text
I want something that isn't already known. One real new idea is worth more to me than a good summary of existing ones. Work through this in order:

1. Map the frontier. Briefly state what is established on this topic, then list what is unresolved: anomalies the standard explanation handles badly, findings that contradict each other, assumptions nobody has tested, and questions nobody seems to have asked.

2. Generate conjectures from those gaps. Connect findings from fields that rarely cite each other (if A drives B in one literature and B drives C in another, has anyone stated that A drives C?). Take accepted premises and follow their implications several steps further than people usually do. Take a method or result that works in a distant domain and ask what it predicts here. Ask what the anomalies would mean if they were the signal rather than the noise.

3. Check novelty. For each conjecture, say whether you think it already exists and where. Use search if you have it. Drop anything that restates known work.

4. Try to kill each one. Make the strongest case against it and check it against everything you know. Keep only what survives. If nothing survives, say so instead of promoting a weak idea.

5. Make the survivors testable. For each, give the precise claim, the mechanism, a prediction that would be surprising if the claim were false, and the cheapest experiment or dataset that would settle it. If you have tools or data, run the test and report what happened.

Mark clearly what is established, what you derived, and what is conjecture, and cite only sources you are sure exist.
```

Used as it stands, it suits a question with no project behind it. In a project, rewrite it in the project's terms.
Keep the five steps and their order; this is what each one holds once fitted:

**Before the steps.** The question in the user's words, with the answers they are tired of. What to read first,
by path. What the session has to work with (the data, the tools, whether it can search). The project's rules that
shape the work, quoted, each with its reason. What to do if something the prompt relies on is absent.

**Step 1, three things.**
- The two lists, the field's and the project's, each line with what would make it wrong. Point at any belief in
  the record that nothing could contradict as written, and ask what it predicts.
- The first thoughts, written and discarded. Name the entries of the record that already dispose of the usual
  answers, so they cannot come back unless they name something those tests could not have detected.
- The frontier, by path: the unexplained observations, the real results nobody followed up, the data nobody has
  used.

**Step 2.** Say what A, B and C are in this project. List the measured halves the record holds. Ask for candidates
by each of the four ways, and name the kinds of outside field worth transplanting from without naming a result.
Do not state a join yourself.

**Step 3.** The paths to search first, then outside. The four labels: tried here; noticed here but never tested;
published elsewhere and untried here; new. Outside searches use general terms and nothing private from the
project.

**Step 4.** The objection comes from a reader who did not write the idea: a separate agent if the session can
start one, given the candidate without its reasoning; otherwise the session itself, saying so in its report. Ask
for a rival explanation of the same facts and the
observation that would separate the two. Name the traps the project's own record shows, such as a confound that
undid an earlier result.

**Step 5, in this order.**
- For each survivor: the claim, the mechanism, a prediction that would be surprising if the claim were false.
- Rank without looking at the result: what supports each half, whether the test can conclude, how much the idea
  could explain if true, and the footprint. Look for the footprint first: if it is absent the mechanism is wrong
  and a test is saved.
- Test few, with the number and its reason. Each test is written in full before it is run, run once, judged by
  the project's bar as quoted, and recorded whatever the result.
- Stop before the unseen ground. If something passed, write the exact check for its owner to run there, with the
  predicted result.

**After the steps.** The report's shape, plain words first. The source labels. "Nothing held up" as an acceptable
answer.

Three things outside the wording matter as much; mention the one that applies in the handover:

- **A way to test.** Code execution, the user's data, search.
- **Many runs, then a filter.** Good ideas are rare. Several independent sessions with the survivors compared
  beat one session asked to be brilliant. Each further session adds tests to the total, so count them together.
- **A loop.** Feed the test results back and ask the model to revise or drop each idea.

## 3. Breeding over rounds (optional)

Use only when the user wants ideas improved over several rounds. Each call is separate: the gain comes from
independent samples and from a judge that did not write the idea.

Three cautions decide whether it works:

- **The score matters most.** A real test beats a model judge. A model judge prefers what sounds plausible, which
  is what sounds familiar, so it pulls the population back to the consensus.
- **Protect variety.** Keep the best idea of each niche (by field or mechanism), not the best overall, or the
  population collapses onto one idea and its rewordings.
- **A score from past data overfits.** Keep ground the loop never sees, and judge the winner knowing how many
  candidates were tried.

Variation:

```text
Here are two ideas that survived the last round, with the critiques they received:

[IDEA A + critique]
[IDEA B + critique]

Produce four new ideas:
1. A mutation of A: change one core assumption and follow what changes.
2. A mutation of B: move it to a different domain, scale, or time horizon.
3. A cross: the mechanism from A applied to the evidence or setting of B.
4. A wildcard that addresses the same gap as either parent by a different route.

Each must be a distinct claim, not a rewording of a parent. For each, state the claim, the mechanism, a prediction that would be surprising if the claim were false, and the cheapest test.
```

Judge, in a fresh context:

```text
Compare these two ideas. You did not write either.

[IDEA 1]
[IDEA 2]

For each, answer separately:
- Novelty: does this already exist? Name the closest known work.
- Mechanism: is there a causal story that holds together? Give the strongest objection.
- Testability: is there a concrete, affordable test whose outcome could prove it wrong?

Then pick the one more likely to be both new and true. An idea that sounds familiar and safe should lose to one that is riskier but has a sound mechanism and a clear test. If neither clears all three bars, say so.
```
