# tiny-chess-engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/ltaobo75-sketch/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/ltaobo75-sketch/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine: 0x88 board, alpha-beta with a transposition table, killer moves, history heuristic, null-move pruning (R=3) and quiescence search with delta pruning, late-move reductions, iterative deepening to a fixed 70,000-node budget per move (never a clock), material plus piece-square evaluation with a bishop-pair bonus and a king endgame table. The readable source (`engine.py`, kept beside the repository) is packed into `main.py` (3,643 bytes) with the kit's `makefun compress`, as the rules allow.

## Local grading

Practice trials against the kit's house gauntlet (6 games each, local env server + scorer, server-faithful: no `NODE_BUDGET` / `MAX_DEPTH` overrides):

- trial-0: 3 wins, 0 draws, 3 losses — **Elo 1279** (beats depth-2/3/4, loses to nodes-100k/250k/500k)
- trial-1: 2 wins, 0 draws, 4 losses — Elo 1099
- trial-2: 1 win, 1 draw, 4 losses — Elo 997

Mean over the three practice trials: Elo 1125. Perft is exact (startpos d1–d3: 20/400/8902; Kiwipete d1–d2: 48/2039), make/unmake and hash are consistent. Move times stay well under the 10 s per-move limit (root search from the start position: ~3.4 s, 64,902 nodes, ~19k nps); whole trials take ~560–790 s of the 1,800 s wall budget.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=75k23xv8&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
