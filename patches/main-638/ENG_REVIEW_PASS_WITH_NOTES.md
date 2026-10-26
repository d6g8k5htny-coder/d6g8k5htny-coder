# NONAUTHOR ENG REVIEW — main#638 RETRO_SOURCE_CELL_RECHECK (Cursor/Composer)

Parallel different-family engineering check only. **Does not claim or close the CoS-seated a1 review seat** ([619/6405627090](https://github.com/d6g8k5htny-coder/main/issues/619#issuecomment-6405627090), ACK [619/6405634304](https://github.com/d6g8k5htny-coder/main/issues/619#issuecomment-6405634304)).

Source: Cursor agent bc-df811228-fe3a-5e03-be5e-f6b1a4645174

---

## NONAUTHOR ENG REVIEW — #638 RETRO_SOURCE_CELL_RECHECK (Cursor/Composer)

**Verdict: PASS_WITH_NOTES** (engineering / source-accounting only). **NOT A RESULT.** Scientific effect **NONE**. COMMENT-only; no Ready, no merge, no MAIN-LOCK. Does not adopt ledger cells.

**Exact pins**
- Head: `18ad71abd4ac0ba26bf310ee3cb8d69b7ba81be9` (Draft `claude/retro-source-cell-recheck-20261026`)
- Recorded base: `9271adf5bece327639ba9e6ba636d850c4120806` (matches PR / merge-base)
- Live tip at review: `1354bc8d62ba0418af2725c1350a19e3723704e5` → `mergeStateStatus=BEHIND` (tip ~6 commits ahead of base; PR still MERGEABLE vs its base)
- Author commit: Claude / Anthropic (`noreply@anthropic.com`); pickup [619/6405600087](https://github.com/d6g8k5htny-coder/main/issues/619#issuecomment-6405600087)
- Reviewer family: Cursor/Composer (≠ Anthropic). Org may still be 0 (same GitHub account). Independence note only; not scientific credit.

**File list (additive-only — confirmed)**
1. `docs/retro/RETRO_SOURCE_CELL_RECHECK_20261026.py` (+295)
2. `docs/retro/RETRO_SOURCE_CELL_RECHECK_20261026.reviewed.json` (+1778)
3. `docs/retro/RETRO_SOURCE_CELL_RECHECK_20261026.json` (+4637)
4. `docs/retro/RETRO_SOURCE_CELL_RECHECK_20261026.md` (+200)

No ledger / RETRO-MATH-BIND / GB-8 / graph / v2-register / count edits. `changedFiles=4`, all `ADDED` under `docs/retro/`.

**Builder / `--check`**
- Script exists; docstring and `main()` agree: with `--check`, rebuilds JSON+MD in memory from ledger pin `99adffc8` + cuts Math-`9f3fb691` / main `a487cfd4` + companion `.reviewed.json`, compares to committed files, prints `check: OK` or `DIFFERS` (exit 1).
- Local nonauthor run: `python3 -I …/RETRO_SOURCE_CELL_RECHECK_20261026.py <main> <Math-> --check` → **`check: OK`**.
- Limit (disclosed, accepted): `--check` does **not** re-derive reader classes; it regenerates the merge of pinned tree listings + committed judgments.

**Count verification (no mutation)**
| Claim | Independent check |
|---|---|
| 129 MISSING rows | Ledger blob `03fe9db3…` at `99adffc8`: 344 rows, **129** with proof/lemma cell `MISSING` |
| 83 SOURCE_DOCUMENT_PRESENT | JSON `row_result_counts` + MD present table: **83** |
| 45 NO_MATH_SOURCE_DOCUMENT | JSON + MD absent table: **45** |
| 1 NOT_CHECKED_PINNED_TO_OPEN_PR | Row **330**, lane `PENDING_OPEN_PR #370` |
| 218 statement documents | `reviewed.json` documents length **218**; class counts match MD |

**CI (head `18ad71ab`)** — 8/8 SUCCESS: public-intake, navigation, public-shop, browser-smoke, architecture / research-architecture, formal / formal-evidence, landing-checks, verify.

**Notes (non-blocking)**
1. **Tip lag:** Draft is behind live tip `1354bc8d`. Content PASS does not clear Ready/merge; tip-sync + fresh checks before integration.
2. **PR-body vs artifacts on #509:** Body groups “#500, #508 and #509 re-pin manifests (rows 34, 161, 162)”. Artifacts attach **#500→34**, **#508→161**, **#508→162**. `#509` is in `REPIN_MERGES` but does not appear in OUT carrier tables for MISSING rows (cosmetic body over-map).
3. **Reader classes** are model-assisted judgments with quoted evidence; eng review confirms structure/reproducible merge, **not** mathematical correctness.

**Seat / double-claim**
CoS seated **a1** as nonauthor eng reviewer. This Cursor text is a parallel different-family engineering check; it does **not** close or replace the a1 seat unless CoS says so.

credit 0 · sci NONE · eng ≠ discharge · OBL OPEN
