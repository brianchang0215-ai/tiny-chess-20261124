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

## License

MIT. See LICENSE.
