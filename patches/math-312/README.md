# Math-#312 CI fix (apply-ready)

Target: https://github.com/d6g8k5htny-coder/Math-/pull/312  
Branch: `chatgpt/formal-admission-hardening-20261005`  
Verified locally: `python3 -B -S -m unittest formal.tests.test_gate formal.tests.test_gate_compatibility formal.tests.test_inventory_gate` → **144 OK**.

## Root cause
Compatibility `gate.py` did not bind `gate_helper.ROOT` to `gate.ROOT`, so fixture mutations were ignored. Synthetic execute also returned empty INV transcripts after the inventory gate landed.

## Apply
```bash
cd Math-
git fetch origin pull/312/head:pr-312 && git checkout pr-312
git apply /path/to/math-312-root-sync.patch
# or copy the five files under formal/ from this directory
```

This environment cannot push to `Math-` (`cursor[bot]` 403). Needs a write-capable agent/env to land on the PR.
