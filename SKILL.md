---
name: blog-topic-and-title
description: Choose what blog post to write and what to title it, using search evidence rather than taste. Use this before drafting any blog post, when retitling an underperforming one, or when someone asks "what should we write about". It covers topic selection and title shape only; use a writing skill for voice and prose.
---

# Choosing a blog topic and title

Most weak blog posts are weak because the topic was never tested and the
title was chosen by taste. This skill covers those two decisions. It does not
cover writing — pair it with a dedicated writing skill for voice, structure
and prose.

---

## Part 1: choose the topic

Five gates, in order. Stop at the first failure.

### Gate 1 — Where did it come from?

Best sources first:

1. A question a real user asked, in support or a community channel
2. Something that just shipped
3. A competitor release or a news event
4. A gap found in keyword research

The first two are the only ones a competitor cannot also mine.

### Gate 2 — Do people type this phrase?

```bash
curl -s -G --data-urlencode "q=<phrase>" \
  "https://suggestqueries.google.com/complete/search?client=firefox" \
  -H 'User-Agent: Mozilla/5.0' |
python3 -c "import sys,json;d=json.load(sys.stdin);print(len(d[1]),d[1][:5])"
```

Zero suggestions means nobody phrases it that way. Rephrase or drop it.

**This tells you which words to use. It does not tell you how many people
search.** Those are different questions and the answers disagree constantly: a
phrase can return ten suggestions and have ten searches a month.

### Gate 3 — Is there real demand, and can you rank?

Pull volume and difficulty from a keyword tool. **This gate, not gate 2,
decides whether to write.**

| Volume | Difficulty | Verdict |
|---|---|---|
| 500+/mo | under 35 | Write it |
| 500+/mo | over 50 | Only with an asset nobody else has: original data, a shipped feature |
| 100–500/mo | under 25 | Write it, cheap to rank |
| Under 100/mo | any | Only for a stated reason: original data, an announcement, a partnership, or a weakness worth owning |

### Gate 4 — Can you say something true and specific?

If the post needs a claim you cannot support, reframe it or drop it. A
high-volume topic you cannot be honest about is a trap, not an opportunity.

### Gate 5 — Could a competitor write this identically?

If yes, it is worth less. Rank by what only you have: your data, your users,
your incidents, your measurements.

---

## Part 2: choose the title

**The title matches the prompt a reader types. Its shape follows that
prompt's shape.** Not every title is a question, and none should begin with
"How Do I".

| Reader's prompt | Title shape |
|---|---|
| "what is X" | What Is X? |
| "best X tools" | N / Top / Best X in YEAR |
| "how to build X" | X: Architecture, Tools and Failure Modes |
| "why does X happen" | Why X Happens / Fixing X |
| "how much does X cost" | What X Actually Costs in YEAR |
| Product news | Statement |

Worked rewrites and the method for checking this yourself:
`references/title-shapes.md`.

### Rules that hold regardless of shape

- **Never open a title with "How Do I."** Use "How to" only when the prompt is
  itself a how-to, and put the topic phrase before it where possible
- Put the searched phrase in the title, word for word, as early as it reads
  naturally
- Keep it under 60 characters
- Add the year only on "best" and "top" posts
- Never ship a title that is only a thesis. A clever line nobody searches for
  is unfindable by the people it was written for
- Across any four posts, vary the shape. A page of identical headlines reads
  as filler even when each one performs

### Declare the shape before writing

```yaml
query_type: definitional | selection | build | troubleshooting | cost | announcement
```

It forces the decision early and lets a reviewer tell a wrong-shaped title
from a deliberate one.

---

## Part 3: publishing

Publish to the canonical home first and confirm it is live. Then syndicate,
with `canonical_url` pointing back at the home URL. Verify the canonical on
the live page, not in the editor.

Never publish a syndicated copy first. Some platforms fix the canonical at
import and it cannot be changed afterwards.
