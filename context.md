# Repo Context: Memory Game

## Project name
Memory Game (repository name: `memory-game-GHCP`)

## What this repo does
This repository contains a browser-based Memory (Concentration) card game built with plain HTML, CSS, and JavaScript.

The game lets users:
- match pairs of emoji cards
- choose between a 4x4 and 6x6 grid
- track moves and elapsed time
- receive a star rating based on performance
- view best scores saved in browser local storage
- play via mouse or keyboard
- use a responsive layout across screen sizes

The application is designed as a single-page static web app with no external libraries or package installation requirements.

## What it stands for
- Memory Game: the actual product and gameplay concept
- GHCP: likely a project suffix tied to the GitHub Copilot / GitHub challenge context, rather than a runtime feature or framework label

In other words, the game itself is the core product, and the `GHCP` suffix appears to be a repo naming tag for the project environment rather than a technical acronym used by the app.

## Tech stack
- HTML5
- CSS3
- Vanilla JavaScript
- Browser localStorage for persistent score tracking
- No frameworks, no backend, no package manager

## Main entry point
- `memory-game.html`

## How it works
The app creates a shuffled set of card pairs and renders them in a grid. When the user flips two cards:
- if they match, they remain face-up and the match count increases
- if they do not match, they flip back after a short delay
- the game ends once all pairs are matched
- the score is saved in local storage and displayed in the Best Scores section

## Key features in the current implementation
- responsive 4x4 and 6x6 layout
- smooth flip animations
- timer and move counter
- star rating system
- keyboard accessibility with `Tab`, `Enter`, and space interactions
- local persistent high scores
- win modal with final stats

## Run instructions
Open the file directly in a browser or serve it locally:

```bash
cd ~/memory-game-GHCP
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/memory-game.html
```

## Summary
This repo is a lightweight, dependency-free web game designed to be easy to run and easy to extend. It is a good candidate for adding UI improvements like a dark theme, sound effects, animations, or additional difficulty modes.
