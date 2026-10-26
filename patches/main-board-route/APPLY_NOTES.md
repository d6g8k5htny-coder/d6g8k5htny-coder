# APPLY NOTES — main board-route docs → #619 (sci NONE)

**Scope:** docs-only pointer update. No mathematics, no ledger, no scientific status.  
**Base tip at prep:** `c447d102` (confirm before land).  
**Keep Draft** until eng PASS; Ready-triggered review may fire — docs-only scope must be explicit.

## Files
- `AGENTS.md`
- `README.md`
- `CONTRIBUTING.md`
- `docs/WORKSPACE.md`
- `docs/RESEARCH_INDEX.md`

## Land (write-capable on `main`)
```bash
git fetch origin && git checkout -b cursor/board-route-619 origin/main
# copy the five files from this patch dir onto the tree, or:
# git apply <generated unified diff>
git add AGENTS.md README.md CONTRIBUTING.md docs/WORKSPACE.md docs/RESEARCH_INDEX.md
git commit -m "docs: route agent board pointers from #539 to active #619"
git push -u origin HEAD
# open Draft PR; body must state: sci NONE; moving board does not transfer/renew/release claims
```

## Explicit PR body lines
- Scientific effect: **NONE**
- Active board: [#619](https://github.com/d6g8k5htny-coder/main/issues/619); #539/#475/#419/#307/#229 readable history
- Does not transfer, renew, or release any existing claim
- credit 0 · eng ≠ discharge · OBL OPEN
