# Charades

A party charades game in a single static `index.html`: no build step, no dependencies, works offline once loaded.

One player acts out or describes the word on the card without saying it, the others guess before the timer runs out (1 minute by default; 30 s, 1:30 and 2 min available).

- 1–4 teams with a scoreboard, pause, skip, and correcting results after each round
- Categories: world movie hits, family and animated movies, Czech classics, animals, actions, jobs, food and drink, sports and hobbies, famous people
- Czech and English interface (picked from the browser language), with Czech titles for foreign movies
- Settings and seen cards are kept in the browser's localStorage

## Run locally

```sh
python3 -m http.server 8765
```

Then open <http://localhost:8765>.

## Deploy

Copy `index.html` to the web root of any static host, e.g. `scp index.html <host>:/var/www/game-ehlas/`.
Live at <https://game.ehlas.cz>.

## Adding cards

Word lists are the arrays near the top of the script in `index.html` (`HITS`, `ANIMALS`, `ACTIONS`, ...). Each entry is `["English", "Czech"]`; the Czech part may be omitted when identical.
