# APPLY NOTES — main#342 (write-capable; do not claim GREEN from eng alone)

Source: Cursor recipe agent (2026-10-26). Target: https://github.com/d6g8k5htny-coder/main/pull/342  
Branch: `codex/routing-broker-tests-20261009`  
Tip: `c447d102` (#636)

**Verdict:** infra/harness red (Hub `toomanyrequests` → cascade), not product-broker red. Tip-sync onto `c447d102` is a **prerequisite** (head behind ~1095); tip already has `mirror.gcr.io` for research-architecture. Tip-sync alone does **not** clear navigation — gate required.

## Failure map

| Check | Workflow | Root |
|---|---|---|
| `architecture-routing-tests` | `architecture-routing-tests.yml` | unauth Hub pull `python:3.11.14-slim-bookworm@sha256:83f339c1…` → `RUNTIME_SETUP_BLOCKED` |
| `architecture / research-architecture` | via `workspace-landing.yml` | same bare `docker pull` on PR head |
| `verify` | `workspace-landing.yml` | `REQUIRED_FORMAL_CHECK_FAILED` (checks) |
| `navigation` | `navigation.yml` | bare `unittest` loads broker tests → 42× `FIXTURE_MOUNT` |

## Steps

### 0) Tip-sync FIRST
```bash
git fetch origin
git checkout codex/routing-broker-tests-20261009
git merge --no-ff origin/main   # expect tip c447d102; resolve only workflow/path collisions
```
Keep PR’s product files + `architecture-routing-tests.yml`; adopt tip RA/ARA/nav/landing.

### 1) Patch A — Hub rate limit
In `.github/workflows/architecture-routing-tests.yml`, before `docker pull … "$IMAGE"`: use tip pattern (`architecture-runtime-acquisition.yml`) — set daemon `registry-mirrors: https://mirror.gcr.io`, pull same pinned IMAGE digest, restore daemon.  
Alt: Hub login with **existing** secret only. Keep pin  
`python:3.11.14-slim-bookworm@sha256:83f339c1be6340ae1096010fdccf6552ac932d8f410d45d206014916bdf37e48`.  
Do not reintroduce bare docker pull in tip RA after sync.

### 2) Patch B — skip/gate bare unittest
In `tests/test_architecture_routing_broker.py`, when mount missing:
```python
if not FIXTURE_MOUNT.is_dir():
    self.skipTest("hosted /routing-fixtures mount required")
```
Keep hard asserts when mount IS present (dedicated workflow still mounts fixtures). Do not narrow tip navigation discover unless skipTest refused.

### 3) Local verify
```bash
python3 -B -S -m unittest discover -s tests -p 'test_architecture_routing_broker.py' -v
# expect 42 skipped, 0 fail (no /routing-fixtures)
```

### 4) Push / CI
Expect: routing-tests image-pull OK → RA mirror prep → landing-checks → verify; nav skips routing module. `image-pull.log` must not contain `toomanyrequests`.

## Out of scope
No product GREEN claims; no SHA-pin rewrite without re-measure; no comments from read-only `cursor[bot]`.
