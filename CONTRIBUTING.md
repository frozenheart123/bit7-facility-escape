# Contributing

Thanks for helping make AI concepts easier to learn. The whole game lives in `index.html` so it can be opened anywhere with no build step. Please keep it that way: no frameworks, no bundler, no external scripts.

## Development loop

1. Serve the folder: `python -m http.server 8000`, then open <http://localhost:8000>.
2. Edit `index.html`.
3. Open <http://localhost:8000/#selftest>, or go to **Evals → System check**. **All checks must pass** before you open a pull request.
4. Play the level you changed with **Offline demo**, in both languages (use the 中文 / EN button).

## Ground rules

- **Both languages, always.** Every user-facing string exists in `STR.zh` and `STR.en`, and every level, document, card and question has `zh` and `en` text. The system check fails if the string keys differ.
- **Picture first.** New concepts need a pictogram (`PICTO`), a codex diagram (`DIAG`) and a one-line summary (`CARD_SHORT`). Keep text short; put depth behind “Read more”.
- **Model-facing text stays in English.** Tool descriptions, tool results and prompts are what the model reads; the UI language only changes the narration language.
- **Pixel icons are 12×12** strings using the palette in `PAL`.
- **Honest simplifications.** If something is a teaching simplification (like the 16-dimension embeddings), say so in the codex card or the README.

## Adding a level: checklist

- [ ] `LEVELS`: a 15×9 map, `slots`, `par`, `start` loadout, `cards`, plus `zh` and `en` (`name`, `concept`, `brief`, `mission`, `takeaway`)
- [ ] Any new map characters handled in `buildWorld`, `blockedBy`, `mapAscii`, `objState` and the drawing code
- [ ] New tools added to a server in `SERVERS`, with a clear English `desc` and `schema`
- [ ] Level documents added to `DOCS` with `only: [levelNumber]`
- [ ] An offline script in `DEMOS` that clears the level with 3 stars
- [ ] A `PICTO` row, `DIAG` and `CARD_SHORT` entries, and a `CARDS` entry with a quiz
- [ ] A knowledge-check question in `EXAM` if it's a new concept
- [ ] `SOL` updated and at least one negative test added to `SELFTESTS` (proving the lesson's failure mode actually happens)
- [ ] README tables and `docs/PLAYER_GUIDE*.md` updated

## Pull request checklist

- [ ] System check: all passed (paste the summary line)
- [ ] Tested in English and Chinese
- [ ] Tested at phone width (about 400px)
- [ ] No new external dependencies

## Reporting bugs

Please include your browser, the level, the language, and, if the system check fails, the failing line exactly as shown.
