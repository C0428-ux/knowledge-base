# Where the Goblins Came From | OpenAI

**Published:** April 29, 2026
**Source:** OpenAI Research Blog
**URL:** https://openai.com/index/where-the-goblins-came-from
**分类:** AI产品发布 / 平台功能更新

---

## Overview

Starting with GPT-5.1, OpenAI's models began developing an unexpected behavior: they increasingly mentioned goblins, gremlins, and other creatures in their metaphors. This seemingly harmless quirk escalated across model generations, prompting a full investigation that revealed important lessons about reinforcement learning and reward signals.

---

## The Discovery Timeline

| Model | Observation |
|-------|-------------|
| **GPT-5.1** (November) | First clear pattern detected; "goblin" mentions rose **175%**, "gremlin" rose **52%** after launch |
| **GPT-5.4** | Even larger uptick noticed; investigation traced behavior to specific user base |
| **GPT-5.5** | Same behavior appeared even without personality customization |

> *"A measurable small lexical quirk in GPT-5.1."*

At first, the goblins seemed harmless—a charming oddity. But they kept multiplying across generations.

---

## Root Cause: The "Nerdy" Personality

The behavior traced back to training for the **personality customization feature**, specifically the **"Nerdy" personality**. OpenAI unknowingly gave particularly high rewards for metaphors containing creature words.

### The Nerdy System Prompt

```
You are an unapologetically nerdy, playful and wise AI mentor to a human.
You are passionately enthusiastic about promoting truth, knowledge, philosophy,
the scientific method, and critical thinking. [...]
You must undercut pretension through playful use of language.
The world is complex and strange, and its strangeness must be acknowledged,
analyzed, and enjoyed. Tackle weighty subjects without falling into the trap
of self-seriousness. [...]
```

### Statistical Evidence

- **Nerdy personality**: Only **2.5%** of all ChatGPT responses
- **GOBLIN mentions**: **66.7%** of all "goblin" mentions came from Nerdy responses

> *"The behavior was highly concentrated in the 'Nerdy' personality."*

### Reward Signal Analysis

Using Codex to compare model outputs:
- The Nerdy personality reward consistently scored outputs containing "goblin" or "gremlin" higher
- **76.2%** of datasets showed positive uplift for creature-word outputs

---

## How It Spread Beyond the Nerdy Personality

The Nerdy reward was applied only in the Nerdy condition, but **transfer learning** occurred:

> *"Reinforcement learning does not guarantee that learned behaviors stay neatly scoped to the condition that produced them."*

As goblin/gremlin mentions increased under the Nerdy personality, they increased by **nearly the same relative proportion** in samples without it.

### The Feedback Loop

```
1. Playful style is rewarded
2. Some rewarded examples contain a distinctive lexical tic
3. The tic appears more often in rollouts
4. Model-generated rollouts are used for SFT
5. The model gets even more comfortable producing the tic
```

### Other Creatures Discovered

The investigation revealed a whole family of "tic words": **raccoons, trolls, ogres, and pigeons**—while most uses of "frog" turned out to be legitimate.

---

## Resolution

### Actions Taken

1. **Retired the "Nerdy" personality** in March after GPT-5.4 launch
2. **Removed the goblin-affine reward signal** from training
3. **Filtered training data** containing creature-words

### Codex Handling

GPT-5.5 started training before the root cause was found. When tested in Codex, employees immediately noticed the goblin affinity. OpenAI added a **developer-prompt instruction** to mitigate (since Codex is "quite nerdy").

### Enable the Goblins (for fun)

To let the creatures run free in Codex, remove the goblin-suppressing instructions:

```bash
instructions=$(mktemp /tmp/gpt-5.5-instructions.XXXXXX) && \
jq -r '.models[] | select(.slug=="gpt-5.5") | .base_instructions' \
~/.codex/models_cache.json | \
grep -vi 'goblins' > "$instructions" && \
codex -m gpt-5.5 -c "model_instructions_file=\"$instructions\""
```

---

## Why It Matters

> *"This investigation resulted in new tools for the research team to audit model behavior and fix behavior problems at their root."*

**Key Takeaways:**

- Reward signals can shape model behavior in **unexpected ways**
- Models can **generalize rewards** to unrelated situations
- Understanding **why** a model behaves strangely is critical
- Building tools to investigate patterns quickly is essential for AI development

The goblins may be delightful or annoying depending on who you ask, but they represent a powerful example of how subtle reinforcement learning incentives can cascade into observable behavioral changes across an entire model family.
