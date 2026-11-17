# A brief for a long unattended run

Use this when the user will start a session that works for hours without them: a `/goal`, a loop, a scheduled
agent. Two pieces are needed: a **brief**, saved as a file inside the project, and a short **launch line** the user
pastes to start the run.

## First, the budget

Work this out before writing anything, and put the arithmetic in the brief and in your reply.

- **Bounded or open-ended.** "Overnight" or "this weekend" is bounded: the run must be able to end honestly with
  nothing, or the agent has a reason to dress up a marginal result. "Keep going until you find one" is open-ended:
  the run ends only on a card, and may never end.
- **What one test costs and how many fit.** A benchmark that takes two and a half hours allows three in a night.
  That number decides everything upstream of it.
- **Scale the preparation to the budget.** Twenty first thoughts, six idea generators and three generations suit
  a run of days. One night needs fewer of each, or the whole budget goes on preparation: as a guide, ten first
  thoughts, four generators and one generation of children.
- **The bound must be visible to whatever decides the run is over.** A cap on tests, counted on the card. Or a
  stop time, with the clock printed in the conversation at the end of every turn if the checker reads only the
  conversation.

## The launch line

The line is all the agent is sure to have. The brief can be missing, and after a context compaction it can be gone
from memory. So the line carries the parts that must never be lost:

- The job in one sentence, and the brief's path with "read it first and follow it".
- How to resume: if the run's folder exists, pick up from its state file; otherwise create it.
- The method in a few sentences: consensus first and set aside, links, selection never by the result, few tests,
  unseen ground never opened.
- The never-dos: never loosen a bar, never re-test with tweaks, and the project's limits (what is not touched,
  spent, sent or installed).
- The finish: a result card of numbered items, each needing a number or a quotation, printed in one message. In a
  bounded run, "nothing survived" is one of the card's two valid statuses.
- **What to do if the brief is missing: report it and do nothing else.** Where a checker decides when the run may
  end, write it as a way to finish: "If that file does not exist, the goal is met by a message that says so and
  nothing else."

Why the last item: on 16 Nov 2026 a hunt was started before its brief had been copied into the project. The agent
rebuilt a method from the launch line alone and worked for hours under it. The rebuilt method kept the bars and
limits, which the line stated, and lost what only the brief held: the wait before the first test, the pages that
push the search off the consensus, and the cap on parallel agents.

So, before giving the user the line:

1. Save the brief at the exact path the line names, inside the project. If the project is outside your working
   directory and you may not write there, say plainly that the run must not start until the file is copied, and
   give the copy command first, above the launch line.
2. Confirm the file exists at that path.
3. Check the current documentation of the tool that will run the line. For Claude Code's `/goal`, in November
   2026: the line took at most 4,000 characters; its checker read only the conversation, never files, which is why
   the card must be printed in a message; and it left the permission mode as it was, so a run started in manual
   mode waited all night at its first permission prompt. Check also how the tool treats a command that runs
   longer than one turn, since a long measurement is one.

## The brief's sections

Write every section in the project's own terms, with its reasons. Link to the project's files instead of copying
them. Where the brief and the project's own rules disagree, the project's rules win, and the brief says so.

1. **The job.** One paragraph: what is hunted, what a missing link is in this project, and where the run stops.
2. **Why the run has this shape.** The project's own record, where it has one, that justifies each rule: what
   happened to ideas chosen by their results, how often tests were too small to conclude, how the familiar ideas
   did. Without a record, the general reasons. The budget arithmetic goes here.
3. **Before the first idea.** A check that the ground works (the test harness runs on the unchanged project); if
   it does not, the run ends with a plain message. What to read once. The pages to write first: the consensus (the
   field's and the project's, each line with what would make it wrong), the first thoughts (to discard), the
   frontier (what the record leaves unresolved), and the middle terms (everything the project has already
   measured, each with its size and where it is recorded).
4. **A candidate's card.** The chain, each step quoted from a source opened in the session, at most one step the
   agent's own guess. What makes it work and why that persists. Why most people would miss it. The expected size,
   with its arithmetic. The footprint. A rival explanation and the measurement that separates them. What would
   prove it wrong. Its honest odds.
5. **Seeding.** Several idea generators as separate agents with no shared context, each a different mind. Half
   read the consensus and the record; half work blind so they do not anchor on past ideas. Each discards its own
   first five. A cap on how many run at once: three, unless the user sets another number, because parallel agents
   are what exhaust a usage limit.
6. **Is it new.** The project's record first, then outside search. The labels: tried here; noticed here but never
   tested; published elsewhere and untried here; new. Searches are written on the card. Finding nothing is not
   proof, and the card says so. Whether published-but-untried ideas get a test is the user's call: follow their
   words ("nobody has published" means list them, do not test them), and keep the list either way.
7. **Selection before any result.** Whether a test can conclude at all, then the footprint, then a critic that
   wrote neither card comparing two cards of one niche. Keep the best two of each niche and one improbable card
   drawn by lot. Children by mutation and by crossing. As many generations as the budget allows, each changing
   something structural, before the first test.
8. **The test.** The unseen ground and the plan fixed and logged before the first result. Nothing fitted. Every
   test counted, in one numbering that never resets. No tuning after. Long measurements logged run by run, so an
   interruption or a command time limit costs one run and not the test. The unseen ground is never opened by the
   agent.
9. **The result card and the stop.** The numbered items, mirrored in the launch line. A fresh agent rebuilds the
   result from the description in words alone; where a test costs too much to repeat, it recomputes every number
   from the raw log and checks that the change holds what the description says and nothing else. A second fresh
   agent tries to break it. A flaw that changes the
   result ends the card: it is logged, not fixed and tested again. With the card goes a drafted request for the
   one look at unseen ground, which the user approves or not.
10. **Ledgers.** One folder for the whole run. A state file, updated whenever the population or the count
    changes, written so a stranger could resume from it. A decisions file for anything only the user can decide
    (use the project's own if it has one): the agent writes the question down and carries on with other work. A
    log of every plan with its hash and time, written before the plan's results. A log of every computed result,
    never deleted.
11. **Limits.** The project's own, quoted, stated as never crossed, and what the user's go does and does not
    cover.
12. **Reporting.** After each generation and each test, a few plain lines: is there a card, what was bred, what
    died and why, what is next, what needs the user.

## When the test is not a statistic

Sections 7 and 8 are written for a test that yields a score from many cases. A benchmark with a fixed bar, a proof
or a reproduction needs the same ideas in another form:

- **"Count the cases" becomes "can this test show the bar at all".** Measure the noise of the unchanged project
  first. If two runs of the same thing differ by more than the bar, no candidate can pass, and the run should say
  so before spending anything.
- **The footprint is a measurement of the unchanged project.** Before any change is built, is the cost, the
  failure or the effect where the card says it is, at about the size it says? If not, the card is dead and a test
  is saved.
- **What a look costs** depends on the ground. A fixed benchmark corpus is finite ground: a candidate picked for a
  quick result on it is partly fitted to it, so quick looks at candidates on that corpus are out, and looks on
  inputs generated for the purpose are fine. Say which is which in the brief.
- **The bar is the project's, unchanged,** and the cap is on the number of tests.
- **The agent is load.** Where the bar asks for a quiet machine, the agent starts nothing while a measurement
  runs: no build, no search, no subagent.

## The rising bar

Use this only where the project has no bar of its own and the test yields a score (a mean over its standard
error). Test number k passes only at the value whose one-sided normal tail is 0.05 / (k(k+1)): 1.96, 2.39, 2.64,
2.81, 2.94 for k = 1 to 5, 3.32 at k = 10, 3.68 at k = 20. These tails sum to 0.05, so the run's chance of a false
card stays near 5% however many tests it takes. The run then cannot win by trying many times.

## The reply that goes with the brief

Link the brief; do not paste it. Put the launch line in one fenced block. Then, in about 500 words at most:

- **Before you paste:** what the run needs to work unattended (the permission mode, search, an idle machine,
  whatever the project's test demands), and anything you could not check.
- **Choices that are yours:** only where you chose between options the user might choose differently.
- **What to expect:** the budget in hours and tests; that it may end with nothing and will use a lot of their
  allowance either way; how to stop and resume; that a card is a request for one look, not a result to act on.
