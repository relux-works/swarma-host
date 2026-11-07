# Current source facts

This snapshot binds the desired product structure to published source as observed
at 2026-11-07 04:29:09 UTC. It supports factual intake and identifies the inputs
still needed from their custodians. A source declaration does not establish a
running member, account registration, installed profile, key binding or launch
permission.

## Source acceptance matrix

| Surface | Exact basis | Accepted meaning and remaining boundary |
| --- | --- | --- |
| Canonical desired card | Host commit `43c082ce387d143d4a6814971cec4cf7f2ddd804`, tree `e9ce742c17acb9caf264b9a77b7fa21098552ae5`; [product-card/product-card.yaml](../product-card/product-card.yaml) | `product-card/v3`; exact card SHA-256 `bdf61e4e581f3b04617bb8130a12383885220e5d8218df91686f88b3a9c7b2a4`. Desired assignments and immutable selections, with runtime freshness unknown. |
| Published unsigned reader | Pulse commit `e86b048cc5135e14897181f1921c7e0fd11212d8`, tree `44ba514241067dabe66f985aa9eb6ec55fb94baa`; [query contract](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md) | Self query returns `pulse-view/v1`; environment and explicit-source discovery return `pulse-view/v2`. The canonical v3 card is supported. Claims that the query is absent describe an earlier state. |
| Existing v4 tools | [v4 format at the same Pulse revision](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/format-v4.md) | Converter, validator and change-check contracts remain separate from the current card and unsigned query. Their presence does not migrate this card. |
| Candidate02 successor design | Retained design: 92,120 bytes, SHA-256 `fca863098a55ae76097f6a1b2866152ad7127d2e4dc57182fa576cacd984c657`; independent acceptance: 25,369 bytes, SHA-256 `ae231d575f5d2bdbe1264db05f9dc4758b8f3fa0a4913ad2b055eac90629f3af` | Prior design acceptance remains distinct from a canonical card, executable future-schema support and signed-caller implementation. Full design/review bodies remain custodian inputs for detailed qualification. The exact-byte F3 fixture prerequisite remains with Pulse. |
| Public key registry | Current Host tracked source and [README](../README.md) | The README records the registry as pending; this source tree contains no registry. Public chat-name declarations do not establish registration or a cryptographically verified key binding. |

The query checks the selected file's exact byte pin and complete graph. Unsigned
caller context is an unverified claim. Source freshness and runtime, registration,
installed-profile and assignment observations remain unknown. A query timestamp
records the query, not the age of the source's operational facts.

## Desired structure and observations

The card declares eleven projects: eight active and three parked. The parked
projects are `gha-runner-m1max`, `remote-workplace` and `remote-worker-harness`.
Router and Keyvault are already admitted in the current card; their absence from
an older intake list is stale. Project admission follows this card and custodian
records, never sibling-directory discovery.

The thirteen declared members comprise nine desired active and four parked
members. A project can be desired active while its separate orchestrator remains
parked. Existing member identifiers, identity bindings, parentage and parked
states remain as declared in the linked card.

Two members have complete environment declarations; eleven are incomplete because
explicit config-profile and network selectors are absent. This is a static source
assessment using the published environment contract, not an observation or a
query made as another member. No missing selector receives an implicit direct
network or config-profile fallback. Even a complete declaration requires separate
consumer admission before launch.

No fresh per-member observation receipt accompanies this snapshot. Actual process
state, registration, installed profile, assignments, local path existence and
Mac-native qualification remain unknown. Each existing member/project custodian
owns its bounded public observation receipt; the Mac custodian owns native
receipts. This snapshot does not request process arguments, environment values,
private-home access or remote inspection.

## Profile source projections

Every selection below is declared by the canonical card. Source revision and lock
hash are selection pins; installed configuration requires separate readback.

| Profile | Selected version | Selected source revision | Declared lock SHA-256 | Source evidence |
| --- | --- | --- | --- | --- |
| `swarm-keeper` | `0.1.8` | `38b10a696edc4f0e86b6ec35344e7468ea8b05b6` | `439a215f303c8da49bb88ef644d77c6949cf4e550c2f07560154ca2e3045db19` | Relative source only; admitted source and lock packet needed. |
| `swarm-orch` | `0.1.17` | `f263014590e60492cb794ac4d922c2c6e3a4efd2` | `18270c3f137943e24969bac5e06cf62514495d53477fb2d412dc2814c175bc8a` | Relative source only; admitted source and lock packet needed. |
| `swarm-child` | `0.1.0` | `862babc` | `855c0d128fa113d9f0b5f471fbd20712c80f83525c1f920131580907729f8a90` | Relative source and abbreviated revision; full source and lock packet needed. |
| `development-member` | `0.1.0` | `1e45625449c3816da2095690a76e2c772986cb9a` | `355670628666c213e8514fa1894cf184d693e53ad629e793ccca72244aac0336` | Exact registry descriptor name/version matched. |
| `development_product_solution-architect` | `0.1.2` | `44a6c4b727a50f0a9fd69591c57af5889ca61d89` | `698fa1d48501b25acf5ae9d8bdf6f3116442ee131dd9d2ea4afc2ca4316fe7d8` | Exact registry descriptor name/version matched. |
| `development_go_developer` | `0.1.2` | `d2561e1c14b0ca994b613ce62bf4fdb7ae878494` | `903aa6c67ab554638c6a4b2aaeffa9d081b39f754f906bafc193dd1d92541471` | Exact registry descriptor name/version matched. |
| `development_product_tester-automator` | `0.1.0` | `cfb133c8ff07aa6e11e68c8ef29c7b6a28c59863` | `444baed2db8badee149e0977ca6a3ee2acb98f60976c2e4bc796f0df6ec8e561` | Exact registry descriptor name/version matched. |

The four registry descriptors were read at their declared commits in
[the profile registry](https://github.com/relux-works/alexis-curator-profile-registry).
Their transitive closures and resolved lock bytes were not materialized. The
Curator/profile source custodian owns the admitted source/lock packets and
installation readbacks for all seven selections. Relative locators are interpreted
from the card's declared profile root; their contents are not inferred from the
working machine. No pin upgrade or profile adoption follows from this intake.

## Remaining custodian inputs

| Input | Accountable custodian | Next evidence |
| --- | --- | --- |
| Full retained intake resources and original acceptance clock | Host keeper and intake-record custodian | Immutable resource bodies and the existing acceptance ledger; a takeover does not restart its clock. |
| Successor design and F3 fixture bodies | Pulse source and Host interface custodians | Exact retained design/review bytes and separately admitted fixture bytes before executable qualification. |
| Current member and native observations | Existing member/project and Mac-native custodians | Public observation receipts with source binding, timestamp and bounded scope. |
| Profile source, resolved locks and installed state | Curator/profile source custodian | Immutable source/lock packets and separate installation readbacks. |
| Public key registry and identity/key bindings | Host keeper, Keyvault custodian and authorizing owners | Separately admitted public registry/binding bytes and their verification evidence. |

Interface qualification and consolidated configuration remain separate work. This
factual snapshot changes no card, identity, key, account, profile or runtime. Its
source publication still requires an independent exact-head review and the source
custodian's normal acceptance and landing checks.
