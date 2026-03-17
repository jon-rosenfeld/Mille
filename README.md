# Mille Bornes

A browser-based implementation of the classic French card game Mille Bornes, playable solo against an AI opponent.

**[Play now](https://jon-rosenfeld.github.io/mille)** — no installation required.

---

## About

Mille Bornes is a racing card game where you drive 700 km before your opponent by playing distance cards, managing hazards, and using safety cards to protect yourself. This version is a faithful single-player implementation with a custom AI opponent.

## How to Play

Draw a card each turn, then play or discard one card from your hand.

**Distance cards** (25, 50, 75, 100, 200 km) advance your trip — but you need a Roll! card on your drive pile first.

**Hazard cards** (Stop, Accident, Out of Gas, Flat Tire, Speed Limit) can be played on your opponent to slow them down.

**Remedy cards** fix hazards — but most require a Roll! card afterward to get moving again.

**Safety cards** (Driving Ace, Extra Tank, Puncture-Proof, Right of Way) permanently protect you from a hazard type. Play one immediately after that hazard is played on you for a **Coup-Fourré** — you counter the attack and steal the turn.

First to reach the km target wins the round. First to 5000 points wins the game.

## Features

- Single-player vs AI
- Remaining Cards tracker showing live hazard/remedy counts with danger indicators
- Card tracker expands on hover with full per-card breakdown including distance and safeties
- Profile system with win/loss tracking and high score records (up to 5 profiles, saved locally)
- Full scoring: Trip Complete, Safe Trip, Delayed Action, Shutout, Extension bonus, Coup-Fourré
- Debug mode (Shift+D) with full game log

## Running Locally

No build step needed. Just open the HTML file in any modern browser


## Card Art

The game ships with SVG placeholder art for cards. To replace with custom PNG art:

1. Convert your PNG to base64 (any online converter, or `base64 -i card.png | pbcopy` on Mac)
2. Find the `ART` object near the top of the HTML file
3. Replace the relevant SVG entry with:
   ```javascript
   card_id: `<img src="data:image/png;base64,YOUR_BASE64_HERE" style="width:100%;height:100%;object-fit:contain">`
   ```

Card art area is **90×86px** displayed. Recommended asset size: **180×172px** @2x.

Card IDs: `accident`, `out_of_gas`, `flat_tire`, `stop`, `speed_limit`, `repairs`, `gasoline`, `spare_tire`, `end_limit`, `roll`, `driving_ace`, `fuel_tank`, `puncture_proof`, `right_of_way`, `d25`, `d50`, `d75`, `d100`, `d200`

## Version

v2.0.3
