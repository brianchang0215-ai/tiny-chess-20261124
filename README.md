# Tiny Chess 4K

A chess engine in at most 4,096 bytes of Python: a 0x88 board, negamax with quiescence search, a transposition table, killer moves and a history heuristic, and an incremental material plus piece-square evaluation. It talks to the make.fun env over `MAKEFUN_ENV_URL` and searches a fixed node budget per move, so play is fully deterministic.

[![make.fun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/brianchang0215-ai/tiny-chess-20261124/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/brianchang0215-ai/tiny-chess-20261124/reward.svg)](https://make.fun/bounty/tiny-chess-01)

## Run

`main.py` is the entrypoint, packed with `makefun compress` from the readable `engine.py` source. Python 3.13, standard library only:

```
MAKEFUN_ENV_URL=http://127.0.0.1:PORT python3 main.py
```

## Search

Iterative deepening from depth 1 to 8 under a fixed budget of 70,000 nodes per move: no clock, no unseeded randomness, so the same position always plays the same move. Quiescence search covers captures and captures that promote, and every legal reply when in check, with a one-ply extension when in check. Repetition and the fifty-move rule score as draws, and the root move is always verified against the env's legal move list before it is played.

## License

MIT. See LICENSE.
