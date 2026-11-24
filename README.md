# tiny-chess-engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/ltaobo75-sketch/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/ltaobo75-sketch/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine: 0x88 board, alpha-beta with a transposition table, killer moves, history heuristic, null-move pruning and quiescence search, iterative deepening to a fixed 40,000-node budget per move (never a clock), material plus piece-square evaluation. The readable source (`engine.py`, kept beside the repository) is packed into `main.py` (3,313 bytes) with the kit's `makefun compress`, as the rules allow.

## Local grading

Practice trials against the kit's house gauntlet (6 games each, local env server + scorer):

- trial-0 (before null-move pruning): 1 win, 1 draw, 4 losses — Elo 997
- trial-1 (with null-move pruning + history): 2 wins, 1 draw, 3 losses — Elo 1191

Best move times stay well under the 10 s per-move limit (max ~3.8 s, mean ~1 s).

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=75k23xv8&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
