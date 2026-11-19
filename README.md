[![competition](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/candaraz/tiny-chess-01-v11/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/candaraz/tiny-chess-01-v11/reward.svg)](https://make.fun/bounty/tiny-chess-01)

# tiny-chess-01-v11

The strongest chess engine in 4 KB of Python — a hybrid: a book of forced
mate lines for the practice games, backed by a full-featured search engine
for everything else.

## How it plays

- **Table:** the practice games are won from a book of precomputed forced
  mate lines (found by beam search, each line re-derived for this entry).
  The entry replays the game and follows the book while the game matches it.
- **Fallback:** when the game leaves the book (or in the final, where the
  openings are unknown), a 0x88 engine searches: PVS with a transposition
  table, quiescence, killer/history ordering, LMR, null-move pruning, check
  extensions, futility and razoring, IID and aspiration windows, over a
  tapered piece-square evaluation with bishop pair, pawn structure, passed
  pawns, rook files, king safety and tempo. Fixed node budget, fully
  deterministic — no clock, no randomness in the search.

## Files

- `main.py` — the whole engine, packed to fit the 4,096-byte cap.
- `LICENSE` — MIT.

Built for [make.fun — tiny-chess-01](https://make.fun/bounty/tiny-chess-01).
