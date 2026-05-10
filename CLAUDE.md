# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

A single-file browser-based Tic Tac Toe game (`tictactoe.html`) with no build system, dependencies, or server. Open the file directly in a browser to run it.

## Architecture

Everything lives in one file — HTML structure, CSS, and JavaScript are inline. Key JS components:

- `WINS` — static array of the 8 winning index combinations
- `init()` — resets board state and DOM for a new game
- `checkWinner()` — checks `WINS` after each move; returns `{ winner, line }` on win, `{ winner: null, line: [] }` on draw, or `null` if still in progress
- Score counters (`scoreX`, `scoreO`, `scoreD`) are read directly from the DOM (`textContent`) and updated in place — there is no JS score state variable

State is held in three module-level variables: `board` (9-element array), `current` (active player), `over` (game-over flag).
