# makefun-tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Panmeii/makefun-tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Panmeii/makefun-tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An original chess engine in 4,043 bytes of Python (standard library only). `main.py` is the whole entry: it unpacks and execs an lzma-compressed payload, then plays the gauntlet through the env at `MAKEFUN_ENV_URL` (POST /game, POST /move) until the env says done. How it plays: a 120-char string board, flipped and case-swapped after every move so all code works from the mover's point of view; material folded into six piece-square tables, scored incrementally; iterative-deepening negamax with alpha-beta (PVS), a transposition table, quiescence over captures and promotions, MVV-LVA ordering, killer moves, null-move pruning, check extensions and futility pruning; repetition and fifty-move draws. The per-move node budget is a fixed function of the position (30k opening / 45k middlegame / 35k endgame nodes) — no clock, no randomness, so replays match move for move. License: MIT (see LICENSE).

## Run it

```sh
MAKEFUN_ENV_URL=http://localhost:8080 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=8nt1dqan&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
