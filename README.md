# Stockfish 19 WDL Calculator

Converts the centipawn score printed by Stockfish 19 to win/draw/loss odds
and back. Single static HTML page, no build step.

Live page: https://Ayhyeong.github.io/ST19-cp-WDL-Calculator/

## How it works

Stockfish 19 models the win probability as `1 / (1 + exp((a - v) / b))`,
where `a` and `b` are cubic polynomials of the material count
(pawn 1, minor 3, rook 5, queen 9, both sides added, clamped to 17-78).
The printed cp is `round(100 * v / a)`. Draw is `1000 - W - L`.

## Sources

- Coefficients and formulas: Stockfish 19, tag `sf_19`,
  [`src/uci.cpp`](https://github.com/official-stockfish/Stockfish/blob/sf_19/src/uci.cpp)
- Model fitting: <https://github.com/official-stockfish/WDL_model>

Development builds of Stockfish may use different coefficients.

## Disclaimer

Unofficial. Not affiliated with or endorsed by the Stockfish developers.
Mate and tablebase scores are not converted.

## License

GPL-3.0-or-later. See [LICENSE](LICENSE).
Contains coefficients from Stockfish (© The Stockfish developers, GPL-3.0-or-later).
Fonts (Instrument Sans, JetBrains Mono) are loaded from Google Fonts under the SIL Open Font License.
