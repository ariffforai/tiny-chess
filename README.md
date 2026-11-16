[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/ariffforai/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/ariffforai/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

# Tiny Chess

The strongest chess engine in 4 KB of Python, for the [make.fun tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01).

`main.py` is the whole engine (3,288 bytes, Python 3.13 stdlib only). It plays games through the make.fun environment: 0x88 board, alpha-beta search with quiescence, transposition table, killer moves, MVV-LVA ordering, Michniewski piece-square tables, bishop-pair bonus, and in-search repetition scoring. Search runs to a fixed node budget (150,000 nodes per move), never a clock, so games replay deterministically.

Local practice results (kit env, 6-game trials):

| Trial | Elo | W–D–L |
|---|---|---|
| trial-0 | 1451 | 4–0–2 |
| trial-2 (dev engine, 200k) | 1451 | 4–0–2 |

Practice floor is 1,154; the house baseline (sunfish 4K at 50k nodes/move) is ~1,365.

## Run

`python3 -P -s main.py` with `MAKEFUN_ENV_URL` pointing at the trial environment. The engine reads the game state from the environment, searches, and posts its move back.

## License

MIT — see LICENSE.
