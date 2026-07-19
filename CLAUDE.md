# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project state

This repository has no code yet — it currently contains only planning/contract docs (`INTENT.md`, `DESIGN.md`, `MEMORY.md`). There are no build, lint, or test commands to run because no application has been scaffolded.

## Where knowledge lives

Read `MEMORY.md` first — it defines which file owns which kind of decision and how decisions get consolidated (draft → discuss → commit) so this doesn't need re-litigating every session. In short: **what** we're building lives in `INTENT.md`, **how it looks** lives in `DESIGN.md`, and **why a decision was made** lives in commit messages — not in this file.

## Project intent

Before writing any code, read `INTENT.md` in full — it is the single source of truth for what this project is meant to do. Summary:

A web application that turns a white/plain-background product photo into an e-commerce campaign showcase image in one flow:
1. The product is cut out (dekupe) from the uploaded photo — product details (color, texture, logo, shape) must be preserved exactly, unchanged by AI.
2. The cutout product is composited into a scene chosen from a set of ready-made scene templates (no free-text scene prompts or custom background uploads in this version).
3. Campaign text (title, discount/highlight) is AI-suggested from product/campaign info and placed on the image without covering the product; the user can edit the suggested text.
4. The final image can be exported in several fixed output sizes (e.g. Instagram square post, Instagram story, site banner).

Explicitly out of scope for this version (see INTENT.md "Kapsam dışı" for the full list): changing the product itself via AI, free-text/custom scene input, video/animation output, multi-product collages, auto-publishing to e-commerce/social platforms, user accounts, and a scene-template editing/admin panel.

When INTENT.md changes, update this summary to match — it should never drift from the source document.
