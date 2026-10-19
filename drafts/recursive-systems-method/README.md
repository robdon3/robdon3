# The Recursive Systems Method

A written method for thinking, investigating, building, and orchestrating with AI.

The Recursive Systems Method begins with a desired end state and recursively descends through the systems preventing that state from being true. Each descent produces evidence. Each discovery changes the map. The end state remains visible throughout.

The process continues until the problem becomes sufficiently structured to cross a **Tool Threshold**: the point at which a specialized tool, agent, model, or human capability becomes the appropriate next intelligence to receive it. The work is then handed off without losing state, evidence, constraints, or intent.

There is no application to install. The repository is the method documents below, plus `MANIFESTO.md`.

## Problem

Serious work loses the goal, the evidence, or the reason a tool was chosen when it moves between people and models. The method keeps those explicit.

## The core loop

```text
                      END STATE
                          ▲
                          │
                  continuously retained
                          │
BEGIN → OBSERVE → DESCEND → DISCOVER
  ▲                           │
  │                           ▼
  │                      REINTERPRET
  │                           │
  │                           ▼
  └──── SYNTHESIZE ←── DESCEND AGAIN
                          │
                          ▼
                   TOOL THRESHOLD
                          │
                          ▼
                       HANDOFF
```

This is a spiral, not a closed circle. The same question can return, at higher resolution.

## How the documents fit

| File | What it holds |
| --- | --- |
| This README | Loop, evidence rules, tool threshold, one narrative case |
| [METHOD.md](METHOD.md) | Primitives, roles, and operative disciplines |
| [AGENTS.md](AGENTS.md) | Explorer, Builder, Critic, Validator, and State Keeper: purpose, authority, and limits |
| [MANIFESTO.md](MANIFESTO.md) | The method is updated from use, not finished in isolation |

`METHOD.md` points at `/primitives/`, `/agents/`, `/templates/`, and `/cases/`. Those directories are not in this repository.

No agent owns the end state. Human judgment stays on intent, tradeoffs, and consequential decisions. Tools supply local exploration, implementation, criticism, and state preservation.

## Evidence discipline

Every serious investigation separates:

- **Known** — directly demonstrated
- **Inferred** — strongly supported by evidence
- **Hypothesized** — plausible but untested
- **Unknown** — information still required
- **Disproved** — explanations contradicted by evidence

A hypothesis does not become a fact because it is useful.

## Case study in this repo

The first written case is the reverse engineering of an Anker A8392 USB-C dock, told in this README rather than as a code folder. The starting goal was to make three physical monitors behave as one logical display through one cable. The descent recorded in the original write-up runs from the user requirement through macOS display behavior, MST, USB-C / DisplayPort Alt Mode, the dock controller, firmware, Synaptics VMM, ViewExpand, HID, DisplayPort AUX, GPU-specific Windows APIs, and binary reverse engineering. The point of the case is how the tool changed as the problem changed shape.

## Read

Start with this file, then `METHOD.md` and `AGENTS.md`. Nothing to build or run.

## Tech

Markdown.
