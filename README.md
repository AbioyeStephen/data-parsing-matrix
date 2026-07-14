# Automated Data Parsing & Semantic Translation Matrix

A client side tool that ingests unstructured operational text onboarding memos, SOP drafts, meeting notes and serializes it into two synchronized outputs in a single pass: human readable Markdown documentation and a machine readable JSON payload.

**[Live demo →](https://abioyestephen.github.io/data-parsing-matrix/)**

## The Problem

Operations teams lose significant time converting messy, unstructured notes into two different formats by hand: a clean document people can actually read, and a structured payload systems can actually use. Usually someone writes both versions separately, and they drift out of sync.

## The Solution

A dual-layer instruction matrix that decouples raw text into two aligned outputs from one source:

- **Layer A — Human-Readable Markdown.** Restructures the input into scannable steps, bolds critical variables (deadlines, quantities, thresholds), and isolates compliance-sensitive language into flagged warning blocks.
- **Layer B — Machine-Readable JSON.** Serializes the same content into a validated schema — step sequence, critical variables, and compliance risk flags ready for direct API or database ingestion.

Both layers are generated from the same parse pass, so they can never drift apart.

## How It Works

1. Paste raw operational text into the input panel (or load the built-in demo).
2. The parser splits the text into discrete steps, using pattern matching to detect:
   - **Critical variables** — numeric values, time windows, and deadlines
   - **Compliance risk language** — terms like *must*, *required*, *mandatory*, *cannot*, *failure*
3. Markdown and JSON views render simultaneously from the same parsed structure.
4. Either output can be copied with one click.

Everything runs client-side no external API calls, no network latency, no server dependency.

## Stack

- Vanilla HTML / CSS / JavaScript — zero dependencies, zero build step
- Regex-based entity extraction and sentence segmentation
- Deployable as a static site (GitHub Pages compatible)

## What I'd Improve Next

- Swap the regex-based extraction for an LLM-backed parser (few-shot prompted) to handle more ambiguous or non-English phrasing
- Add configurable schema templates for different document types (SOPs, incident reports, training transcripts)
- Persist parsed sessions so outputs can be revisited and diffed over time

---
Built by [Stephen](https://github.com/Starking-1) · part of an ongoing series on AI-powered operational tooling.
