# Titanic Survival Prediction Simulator

An interactive, game-style walkthrough of the *method* behind a first machine-learning project. Board the ship, walk the deck, and try the same decisions a careful analyst makes: how to treat missing values, why leakage inflates a score, how to test fairly, and where a model struggles.

🌐 **Play it:** https://mrigeshlakhanpal.github.io/Titanic-Survival-Prediction-Simulator/
💻 **The real project (code, tests, reports):** [`Titanic-Survival-Prediction`](https://github.com/MrigeshLakhanpal/Titanic-Survival-Prediction)

## Who this is for

Beginners who want the *intuition* behind the project before reading the code. The simulator explains why each step exists; the main repository shows how it is implemented and tested. Together they take you from "what is a pipeline?" to a first complete, honest machine-learning project.

## Suggested path

1. **Play the simulator** (about 20 minutes). Every chapter has two or three experiments. Change a value and read the message that appears: it tells you whether the change makes the result better or worse, and why.
2. **Open the main repository** and read its README.
3. **Read the code that matches each chapter** (table below), then run its tests.
4. **Re-run the leakage ablation yourself** and compare it with what you saw in chapter 5.

## The ten chapters

| # | Chapter | Question it answers | Look it up in the main repository |
|---|---------|--------------------|-----------------------------------|
| 1 | Data intake | What do we know before the ship leaves port? | README |
| 2 | Baselines | Does a model learn anything beyond a simple rule? | README (results) |
| 3 | Feature engineering | How does a raw row become something a model can use? | `src/feature.py` |
| 4 | Missing ages | Who is allowed to teach the imputer? | `src/pipeline.py`, `src/train.py` |
| 5 | Leakage | Can a validation score be quietly inflated? | `reports/leakage_ablation.md` |
| 6 | Cross-validation | How do we test fairly, again and again? | `src/train.py` |
| 7 | Model comparison | What does "best" mean when metrics disagree? | README (model table) |
| 8 | Subgroup audit | Where does the model struggle? | `reports/subgroup_analysis.md` |
| 9 | Software tests | Can the code defend its own assumptions? | `tests/test_pipeline.py` |
| 10 | Voyage's end | What happens when 500 new passengers board? | the whole project |

If a link to a file does not open, the file has moved in the main repository; please open an issue here.

## How evidence is labelled

Every panel carries a tag:

- **REPOSITORY FACT**: a number reported by the main project (for example the 5-fold results and the leakage ablation).
- **TOY MODEL**: a simplified simulation built for intuition. It uses synthetic passengers that mimic only the published group sizes. It is not an experimental result.
- **CHECK AGAINST REPO**: something the simulator demonstrates as a mechanism; confirm what your own code does.

The "Lifeboat number" clue in chapter 5 and the per-feature accuracy splits in chapter 3 are illustrations, not results from the project.

## Limitations

- This is a teaching tool. It does not train the project's models and does not replace reading the code.
- The final-voyage simulation draws survival from typical group rates and makes the model right with each group's reported out-of-fold accuracy; it is a toy.
- No Kaggle data or model files are included. All passengers on screen are fictional.

## Run locally

The game is one self-contained HTML file with no dependencies:

```
python -m http.server 8000 --directory docs
```

then open http://localhost:8000, or simply open `docs/index.html` in a browser.

## Repository layout

| Path | Contents |
|------|----------|
| `docs/index.html` | The simulator (served by GitHub Pages) |
| `LICENSE` | Licence |

## Use of AI assistance

This simulator was designed and built with Claude (Anthropic) as an AI design and coding assistant, under my direction. Numbers taken from the main project were checked against its reports.

