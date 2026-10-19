# Multi-Agent LLM Systems Research

A single static page that explains research and art projects on long-running, multi-agent LLM dialogue. It is a reading interface, not an agent runtime. No model is called, and no conversation is generated from this repo.

## What it is

`index.html` is the whole project. A sticky nav walks through six sections: an introduction to continuous AI dialogue, a card grid of named projects, an accordion of context and coherence problems, a bar chart, an AutoGen role diagram, and a short conclusion.

## Problem

Long multi-agent conversations are hard to compare from papers and project sites alone. This page puts a few of those projects, failure modes, and framework ideas on one screen.

## Approach

```text
index.html
  ├─ landscape cards (click to open a modal)
  │    infinitebackrooms.com, Infinite Convo, AutoGen,
  │    Jeda.ai, DreamLLM-3D, MAEBE
  ├─ challenge accordion (context loss, repetitive dialogue,
  │    coordination, emergent harm)
  ├─ Chart.js bar chart labeled "Predictability Score (Illustrative)"
  │    hardcoded values, not a measurement from this repo
  └─ AutoGen diagram: user → manager / coder / critic / human → task
```

Project blurbs and challenge text are embedded in a `reportData` object in the page. The chart axis is explicitly illustrative.

## Run

The page loads Tailwind and Chart.js from public CDNs, so it needs network access.

```bash
python3 -m http.server 8080
# http://localhost:8080
```

Opening `index.html` directly in a browser also works if those CDN scripts are allowed.

## Tech

HTML, CSS, and JavaScript. Tailwind and Chart.js via CDN. No package manager, no build, no tests.
