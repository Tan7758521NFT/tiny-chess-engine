# tiny-chess-01 entry

A compact chess engine in one packed file (`main.py`, built from
`engine.py` with the kit's `makefun compress`).

0x88 board, negamax alpha-beta with iterative deepening under a fixed
node budget, quiescence over captures, promotions and check evasions,
transposition table, MVV-LVA + killer move ordering, null-move pruning
and late-move reductions. Evaluation is material plus piece-square
tables with a middlegame/endgame king interpolation and a bishop-pair
bonus. No clock, no randomness: every move is a pure function of the
position, the game history and the trial seed, so replays match.

It plays the house gauntlet through the env at `MAKEFUN_ENV_URL`
(`POST /game`, `/move`, `/resign`), exits when every game is over, and
makes no model call.
