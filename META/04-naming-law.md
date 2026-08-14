# META 04 — Naming law

## Rule

Names answer **intention**, not mechanism fashion.  
One concept, one name.  
Code, docs, and design speech use the same words.  
**Concepts** live in the framework; **encodings** (tokens, field paths, ids) do not become concept names.

## Why

Naming failures observed while deriving CEK:

| Failure | Example | Harm |
|---------|---------|------|
| Unclear metaphor | Fiber, Floor | Developers cannot infer the job |
| Execute collision | run | Collides with apply |
| Product collision | flow | Engine/UX meanings |
| OS collision | thread | Wrong mental model |
| Too generic | history, record, group | Dilute accountability |
| Wire promoted to concept | meta.trace_id as “the concept” | Confuses framework with encoding |
| Synonym drift | permission vs Cap vs token | Two official languages |

## Method to choose a name

1. Write the job in one plain sentence.  
2. List candidate words.  
3. Score: intention clarity, developer familiarity, collision risk, decades stability.  
4. Prefer a slightly formal precise word over a popular vague one when the job is accountability (e.g. lineage over history).  
5. Prefer renaming when the word fails the “obvious job” test (Fiber → Activity, Floor → Baseline).  
6. Freeze primary names; allow tutorial gloss once, not a second official term.

## Concept vs identifier

| Level | Example |
|-------|---------|
| Concept | **trace**, **Cap**, **Activity** |
| Runtime/wire identifier | an id string that refers to a trace, Cap token bytes, activity id |

Framework documents discuss **concepts**.  
Schemas may define identifiers later without elevating them into the intention table.

## Official CEK vocabulary

See `CORE/04-vocabulary.md`.  
Primary names are frozen under the charter.

## Rejected names (kernel)

Fiber, Floor, run (as execute or as correlation concept), flow, thread, group/related *as the correlation concept name*, history/record *as the cause-trail concept*, plugin *as ambient load*, command *as substitute for Intent*, token *as substitute for Cap*.

Casual English (“related Intents share a trace”) remains allowed; it does not mint a kernel noun **related**.
