# Get Out experiment: saadsatter

Principle: entry

## Prediction (student writes before building)

TODO: Describe one design change, the player behavior you predict, and what
observation would make you question that prediction.

## Implementation

Changed `app.js`, `index.html`, and `style.css` to preview a slide's destination
on direction-button hover/focus. Optional preview mode lets touch players select
a direction, inspect its destination, then press Slide selected direction.
A dashed ring and text identify the destination; blocked directions are explained.
Preview calls the existing pure `step` function without assigning its result,
so inventory/state, move count, trace, and game rules are unchanged. Actual moves,
undo, reset, completion and editing clear stale previews.

Class `main` was fetched and verified during draft preparation; the branch
had no unrelated commits or tracked differences from that base. Human playtest and learning-transfer evidence
remain TODO. Student prediction and AI disclosure remain for the student to write.

## Playtest observations

Student reported: “I did try it and play tested it, and it works.”
No board, control method, completion, or learning details were supplied.

TODO: Record anonymous player labels, board, version and order played, hints
requested, restarts, completion, and one revealing action or remark. Separate
observations from interpretations. No names, emails, or other personal data.

## Interpretation and revision (student writes)

TODO: Compare the evidence with the prediction. Mention prior familiarity,
practice effects, sample size, or other limits. Describe the revision made or
one next test. A single player's response supports a question, not a general claim.

## AI assistance and human decisions (student writes)

TODO: State what Codex generated, what you checked, and one design decision you
retained or changed. Include any remaining known issues.

## Independent review

A separate Codex reviewer inspected the variation against the reference.
Engine, levels, and engine tests are unchanged. Preview uses the pure `step`
function without assigning state. Review found that the commit button became
enabled outside preview mode, but lost its selection on direction-button blur.
Resolved by enabling commit only in explicit preview mode. The checkbox label
and README now clarify that keyboard arrows and swipes still move immediately.

## Checks recorded during draft preparation (2026-10-12)

- `python3 scripts/minigames.py check --owner saadsatter`: passed (1 submission).
- `python3 scripts/minigames.py test --owner saadsatter`: all 7 tests passed;
  movement, immutability, blocked actions, exit crossing, terminal states,
  shortest paths, unreachable/invalid boards, observations, and solvable levels.
- Course unittest discovery: 34 tests passed; one module failed to import
  because `anthropic` is not installed. This is not a full-suite pass.
- Offline/headless setup diagnostic: incomplete; reported GitHub authentication,
  Pyxel, and deterministic-test failures. Scripted fixture passed; no live model
  call was made. Separate authenticated GitHub identity lookup succeeded.
- Browser UI check was attempted but blocked by the browser file-URL policy.
  No browser interaction or narrow-screen pass is claimed.

TODO: Verify hover/focus preview, preview-mode commit, blocked directions,
reset, undo, hints, completion, editor, and narrow-screen/touch controls in a
browser, including the review fix. Human learning/experience observations
remain unfinished. Student and instructor retain approval decisions.
