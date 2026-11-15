# blog-topic-and-title

A Claude skill for two decisions most blog posts get wrong before a word is
written: **what to write about**, and **what to call it**.

It deliberately does not cover writing. Pair it with a writing skill for
voice, structure and prose.

## What it contains

- A five-gate funnel for topic selection, with volume and difficulty
  thresholds
- A mapping from reader prompt type to title shape
- A ten-minute method for checking that mapping yourself against live search
  results, instead of trusting anyone's table
- Canonical-first publishing order

## Why the title mapping

Counting ranking titles across real keywords shows the winning shape is a
property of the query, not of house style. Definitional queries reward
question titles. Tool-selection queries reward lists and often contain no
question titles at all. Build queries reward statements.

A blog where every headline is a question reads as filler to a human even
when individual posts perform, which is the failure mode this is written
against.

## Install

```bash
git clone https://github.com/mithileshgau/blog-topic-and-title \
  ~/.claude/skills/blog-topic-and-title
```

MIT licensed.
