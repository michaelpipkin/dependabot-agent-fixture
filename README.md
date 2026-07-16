# dependabot-agent-fixture

**Test fixture. Not for use. Deliberately vulnerable.**

This repository exists to exercise [dependabot-agent](https://github.com/michaelpipkin/dependabot-agent)'s handling of **multi-line advisories** — a single advisory that carries one vulnerable range per release line.

It pins two copies of `js-yaml` on different majors, each vulnerable to a different line of [`GHSA-mh29-5h37-fv8m`](https://github.com/advisories/GHSA-mh29-5h37-fv8m):

| package | js-yaml | vulnerable range | patched at |
| --- | --- | --- | --- |
| `packages/consumer-old` | `3.14.1` | `< 3.14.2` | `3.14.2` |
| `packages/consumer-new` | `4.1.0` | `>= 4.0.0, < 4.1.1` | `4.1.1` |

`3.14.2` clears the 3.x line and `4.1.1` the 4.x line, so no single version is the answer — the point of the fixture. See [issue #2](https://github.com/michaelpipkin/dependabot-agent/issues/2).

The vulnerable versions are pinned on purpose. Do not "fix" them.
