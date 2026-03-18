# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file browser game: `tictactoe.html`. No build step, no dependencies, no package manager. Open the file directly in a browser to run it.

## Architecture

Everything lives in one HTML file with three sections:

- **CSS** (`<style>`) — dark theme (`#1a1a2e` background), grid layout for the 3×3 board, CSS classes `.x`, `.o`, `.taken`, `.win` drive visual state
- **HTML** — static 9-cell board (`data-i` attributes index cells 0–8), score display, two buttons (Restart, vs CPU toggle)
- **JS** (`<script>`) — all game logic in plain vanilla JS:
  - `board[]` — source of truth (9-element array of `''`, `'X'`, or `'O'`)
  - `place(i, player)` — single function that mutates board, updates DOM, checks win/draw, and triggers CPU
  - `minimax(b, isMax)` — unoptimized full-depth minimax; CPU (O) is unbeatable
  - `vsCPU` flag toggled by the mode button; CPU move fires after a 350 ms delay

## Git / GitHub

- Repo: https://github.com/JerryAUG/AI-Project
- Branch: `master`
- After every change: commit with a descriptive message and push to `origin/master`
