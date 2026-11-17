# discovery-prompt

**A skill for Claude Code that writes prompts which get a model past the average answer.**

Ask a model a question and you get what most informed people already think. That is useful, but it is not new.
This skill writes the prompt that makes the model look elsewhere, and then makes it prove what it found.

## How it works

Every prompt the skill writes makes three moves:

1. **Name the usual answer and set it aside.** A model cannot move away from an average it has not stated.
2. **Build ideas from the gaps.** The best gap is a missing link: one source shows that A leads to B, another
   shows that B leads to C, and nobody has said that A leads to C.
3. **Let a test decide.** The test is fixed before anyone looks at a result. Most new ideas are wrong, so
   "nothing held up" is an accepted answer.

```text
state the usual answer → find the gaps → build ideas → check they are new → try to kill them → test the few that survive
```

> **Where the idea comes from.** In 1986 Don Swanson read two sets of medical papers that never cited each
> other. One described what fish oil does to the blood. The other described what is wrong with the blood of
> people with Raynaud's syndrome. He joined them, and a trial in 1989 supported the link that neither set had
> drawn.

## How to use it

Open a new session in your project's folder and ask in plain words. The skill picks the size from what you ask.
You can also type `/discovery-prompt` followed by your request.

| You want | Ask for | You get |
| --- | --- | --- |
| A less average answer to one question | "Give me a paragraph to add to my question so I don't get the usual answer." | One paragraph to paste after any question |
| New ideas about your project | "Write me a prompt that finds something we have not thought of about X." | One prompt, fitted to the project's rules and its record of what was tried |
| The ideas themselves | "Don't write a prompt. Tell me what we haven't thought of about X." | At most three ideas, each with a check that could kill it |
| A long run that works alone | "Set up an overnight `/goal` run that finds X." | A brief saved in your project, and one line to paste to start the run |

In a project, the skill reads your rules first and your record of past tries second. That is how it avoids
sending the model back to ideas you already tested.

### The long run breeds ideas

The long run works like a genetic algorithm:

- Several agents invent ideas separately. Half of them never see what you tried, so they are not pulled toward it.
- The best ideas of each kind are kept, plus one unlikely idea drawn by lot.
- The survivors are changed and crossed to make new ideas, for as many rounds as the time allows.

One thing differs from a textbook genetic algorithm: ideas are never chosen by their test result. They are
chosen by their sources, by whether a test could settle them at all, and by a critic that wrote none of them.
The real test comes last, on a few ideas. An idea picked because it scored well on past data tends to do worse
on new data.

## Install

```bash
git clone https://github.com/chrisduvillard/discovery-prompt ~/.claude/skills/discovery-prompt
```

Then start a new Claude Code session.

## What it cannot do

A prompt changes how a model searches, not what it knows. The biggest step away from the usual answer comes
from what the average document does not contain: your own data, your own observations, and a way to run the
test.

## How it was tested

Five kinds of request were run with the skill and, for four of them, without it. Each reply was checked against
a list of what the method requires.

| | Checks passed |
| --- | --- |
| With the skill | 72 of 72 |
| Without it | 37 of 58 |

In a separate trial, one question was asked with and without the skill's paragraph. The plain answer was the
standard list. The other gave five views, each with what would prove it wrong, and three of them were absent
from the plain answer.

These tests show that the method is followed. They do not show that the ideas are true, or better on a real
project. Only your own test can show that.

## What is in this repository

| File | What it holds |
| --- | --- |
| `SKILL.md` | The method and the steps the skill follows |
| `references/blocks.md` | The paragraph, the five-step prompt, and the prompts for breeding ideas |
| `references/long-run.md` | How to write the brief and the starting line for a long run |
| `evals/` | The test cases |
