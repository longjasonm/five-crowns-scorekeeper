# Five Crowns Scorekeeper

A tablet-friendly, installable PWA for playing Five Crowns with a physical deck. Built with React + Vite, with no accounts, backend, or paid services.

## Run locally

```bash
npm install
npm run dev
```

Open the local URL printed by Vite.

## Deploy to Vercel

1. Push this folder to a GitHub repository.
2. In Vercel, choose **Add New Project**, import the repo.
3. Vercel should detect Vite. The build command is `npm run build` and output directory is `dist`.
4. Deploy. On iPad, open the HTTPS link in Safari, then use Share → Add to Home Screen.

The app saves to `localStorage` in the current browser. It works offline **after opening the production site once while online**. Scores do **not** sync between devices or different browsers. Clearing site data removes the game.

## Rules implemented

- 2–7 players, 11 rounds; 3 cards through 13 cards.
- Wilds advance 3 through King. Cards of the round's wild rank count as 20 points; jokers count as 50; all other cards count their face value (J=11, Q=12, K=13).
- Standard scoring: person who goes out scores 0.
- Alternate house rule: person who goes out scores negative the number of cards dealt for that round (−3 to −13). Other players score unmatched cards normally.
- Running totals; lowest score wins; official multiple-winner or optional tiebreak handled manually.
- Previous round scores can be edited. Names can be changed, but player count and scoring mode lock once scoring begins.

Official rules source: https://cdn.accentuate.io/8384995033396/632763187209/GS002_FiveCrowns_Instructions-v1688660376181.pdf

## Scoring workflow

Type total points for each player after selecting who went out. The going-out player receives 0 (standard) or the negative of cards dealt (alternate) automatically. No card-by-card picker is shown.

## Prototype boundaries

This is a scorekeeper, not a digital card game: it does not verify valid books/runs or automatically detect unmatched cards. Players type their leftover point totals directly. The app does not need card suits to record scores.

### Player name entry

Tapping a player-name field selects the existing name, so typing immediately replaces it (both during setup and in settings).
