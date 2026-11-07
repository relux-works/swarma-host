# Shared platform configuration: contract consolidation delta

Status: proposed reconciliation for counterpart review. The original composable
specification, interaction proposal revision 1, consolidated proposed contract
revision 2 and Router's policy-refusal precision response have now been read
together. This updates the existing consolidation candidate; it defines no
competing format, released loader or permission to implement or roll out.

## Requirement, proposal and source evidence

The owner requirement is one logical configuration with subsystem-owned typed
projections and operator-selected one-file or split-file storage. Equivalent
logical inputs must preserve relevant typed values, precedence, refusals and
section digests. Genuine optional absence preserves independently supported
standalone behavior; broken or unreadable required content refuses. The first
integrated slice remains Curator extensions plus Router.

The original specification is a source-contract agreement input, not evidence
of implemented catalog ingestion, local capacity or execution. Interaction
revision 1 adds the layout requirement. Consolidated revision 2 incorporates
Curator's reader facts and Router's consultation: Curator supplied facts without
accepting the interaction proposal; Router reported no structural disagreement
subject to compatibility conditions. The later Router response corrects refusal
precision without a new mapping decision. These responses do not establish
joint acceptance of the common wire format or the whole contract.

Revision 2 already proposes strict JSON, an explicitly selected envelope OR an
explicit manifest assigning one source per selected section, no implicit scan,
include, environment expansion or last-wins merge, and atomic typed results.
Those choices are recovered proposal content, not missing inputs to reinvent.
Concrete fields, versions, canonicalization and source-reader mapping remain
unagreed. Original documents stay unchanged; this delta records reconciliation.

Implementation of the additional platform layer retains the original usable
Host AND proxy integration MVP prerequisites. Source landing, static checks or
this document do not establish those outcomes. Existing standalone product
work, ready delivery and usable notification paths continue under their own
contracts. No automatic migration, daemon, installed configuration, profile
change or local-model experiment is part of this slice.

## Current source boundaries

The linked revisions are inspected source snapshots, not installed-state claims.
Historical reader facts in the proposals must be interpreted against these
current boundaries.

| Source | Observed current behavior | Consequence |
| --- | --- | --- |
| [Curator Core configuration](https://github.com/relux-works/curator/blob/470331906654c65169b88bb9579c0c929ed272df/internal/config/config.go) and [launcher projection](https://github.com/relux-works/curator/blob/470331906654c65169b88bb9579c0c929ed272df/internal/config/launcher_extensions.go) | Core owns selected machine configuration and system locks/defaults. Schema 7's closed `extensions` contains optional `proxy` and `claude_auth` metadata. `curator.launcher-config/1` includes the actual `config_path`. System configuration cannot supply these extensions or make them lockable. | A real narrow metadata seam now exists. Reuse its authority boundary; do not insert a common envelope, Host or model-catalog fields into the closed object. Shared-source placement still requires the owning mapping. |
| [Launcher selected-config consumer](https://github.com/relux-works/curator-agent-launcher/blob/2045339f703ee8190705c116a05197b12b684b71/internal/launcherconfig/selected.go) and [selection contract](https://github.com/relux-works/curator-agent-launcher/blob/2045339f703ee8190705c116a05197b12b684b71/docs/selected-launcher-config.md) | One Core query obtains effective metadata; command failure, invalid output or unsupported schema refuses without fallback. Explicit network selection precedes selected proxy profile, then the existing operator default. Config inspection opens no secret store. | The old proposal's machine-authority question has a concrete current answer for proxy/OAuth: Core-selected metadata. No second Launcher-side discovery route is needed. Shared-source-to-Core integration and both-layout provenance are still undecided. |
| [Launcher host policy](https://github.com/relux-works/curator-agent-launcher/blob/2045339f703ee8190705c116a05197b12b684b71/internal/launcherconfig/config.go) and [file resolver](https://github.com/relux-works/curator-agent-launcher/blob/2045339f703ee8190705c116a05197b12b684b71/internal/configfile/locations.go) | Closed `curator-run-launcher-v1` host policy remains separate; proxy/OAuth members explicitly refuse there. Both layers are validated. Existing per-file, per-layer legacy fallback happens only after genuine absence. | Neither current legacy fallback nor the proposed manifest is an overlay merge. Preserve host-policy authority and reject attempts to route new extension fields through the old reader. |
| [Curator manager policy](https://github.com/relux-works/curator-spec/blob/35c705be3f60ef2fc33acafa85cfb0df0d4c8041/profiles/manager.md#1-machine-state-and-configuration) | Locked system values override user values; unlocked system values are defaults, with enumerated lock/merge exceptions. | Storage layout adds no override tier and cannot weaken existing locks or enforced-config refusal. Map each existing selection surface explicitly rather than treating every source as one precedence chain. |
| [Router proposed own-domain contract](https://github.com/relux-works/swarma-router/blob/48e537029b325b2480bd8918aa255cd6266be313/agents/skills/swarma-router/references/interface-contract.md) | Full `swarma-router/0.1.0`, draft revision 4, remains proposed. Its config names project, selected interface/adapter/version/configuration references and a policy pin. `policy.read_projection` acquires typed policy; `policy.evaluate` separately evaluates effect admission. | This is the existing design boundary for a Router-owned provider, not an implemented common-envelope loader or authority obtained from a config digest. Exact first-projection wire/version remains for Router agreement. |
| [Router current component inventory](https://github.com/relux-works/swarma-router/blob/48e537029b325b2480bd8918aa255cd6266be313/README.md), [selection](https://github.com/relux-works/swarma-router/blob/48e537029b325b2480bd8918aa255cd6266be313/selection/selection.go), [launch](https://github.com/relux-works/swarma-router/blob/48e537029b325b2480bd8918aa255cd6266be313/launch/router.go) and [workbench policy access](https://github.com/relux-works/swarma-router/blob/48e537029b325b2480bd8918aa255cd6266be313/workbench/policy_access.go) | Separate Go components provide deterministic selection from admitted inputs, explicit launch through a plugin, workbench operation/source-planning and policy seams. Actual owner acquisition, complete runtime wiring and a workbench CLI remain unavailable according to the source inventory. | The original handoff-only baseline is historical. These components must not be called absent, but they also do not prove a shared model-catalog consumer, automatic full routing, integrated Curator readiness or a qualified live tuple. |

The Launcher dependency on agents-management does not settle the shared catalog
reference contract. The typed network-profile catalog is not the model catalog.
No copied model list, favorable observation or configured reference supplies
allocation or launch authority.

## Reconciled clauses and remaining agreement

The following keeps the existing proposal's direction while separating resolved
questions from decisions that still block implementation.

| Topic | Reconciled requirement/proposed direction | Precise remaining decision |
| --- | --- | --- |
| One file versus split files | Revision 2 proposes alternative strict-JSON envelope/manifest layouts of one logical authority. One selected source per section; no implicit includes, scanning, expansion or order-dependent winner. Equivalent inputs preserve relevant typed values, verdicts and digests. | Agree concrete envelope/manifest and section schemas, versions, explicit source-selection surface, resolution base, custody and bounded input/path rules. There is no need to solicit a new include grammar or choose first/last-wins. |
| Precedence and authority | Preserve admitted locks, overrides, defaults and literal origins. Current Core-selected proxy/OAuth metadata and separate Launcher host policy are concrete facts; a caller's launcher-config origin cannot impersonate CLI or inherited runtime authority. | Curator owners map shared-source materialization into Core selection, host policy and each actual runtime/default surface, including fresh run and normal resume. File order cannot create another authority. |
| Relevant semantic digest | Equivalent layouts and unrelated optional-section edits preserve the required projection digest. Global revision and paths are provenance; alone they neither revoke nor qualify an unchanged projection. | Agree digest algorithm, canonical bytes, defaults/dependency coverage, version binding, duplicate/case rejection, number/Unicode treatment and schema-significant array order, with vectors. Existing subsystem encodings are not a substitute common hash contract. |
| Transport and snapshot identity | Core exports truthful actual `config_path`. Router full Snapshot/SelectionInput/Decision identities include source revisions and evidence. Equal relevant semantic digests do not require identical transport bytes or complete Router digests. | Agree relevant section-to-`RevisionRef` binding and comparison boundary without deleting source evidence, falsifying paths or changing existing receipt identity. |
| Optional absence | Omitted optional common input/section preserves the supported standalone path; an omitted optional Router interface is unconfigured. Explicitly selected unreadable, malformed, unsafe, unsupported required or incomplete input refuses before the affected action. A failed query/declared source is not absence. | Agree who declares optional/required sections and stable absence/refusal types. Bind missing declared targets and combined-invalid cases to exact diagnostics. Do not reopen whether a configured read failure may silently fall back: the proposal already excludes it. |
| Validation and refusal | Relevant unknown keys/versions, ambiguous/duplicate authority and inconsistent bindings refuse atomically. No partially usable relevant projection, rewrite or provider effect results. | Specify common-envelope validation versus ignored unrelated optional sections and deterministic precedence when several errors coexist. Preserve native reader refusals instead of translating them into successful empty results. |
| Projection membership | First Curator-plus-Router slice remains fixed. Proxy/OAuth have a current Core seam; Host and model-catalog membership is not admitted by adding fields to schema 7. Each consumer owns only its types. | Owners confirm the first exact section membership and which existing Host/catalog interfaces are available or need separately accepted work. A narrow OAuth/proxy delivery does not wait for a generalized manager API. |
| Secrets and catalogs | Only supported opaque secret references cross configuration boundaries, without resolution, value logging or secret-derived commitments. One catalog lineage is shared, with capability, availability and allocation kept separate. | Bind supported reference shapes and the actual model-catalog owner/entry/revision interface. Keep execution-time custody and existing file/Keychain refusal boundaries. |

## Router policy-refusal precision

Revision 2 excludes current `queued-task-handoff/0.1.0` authorization from the
first common section. Preserve the whole immutable typed per-task Policy,
request and journal. Do not inject a platform revision into its digest, rebuild
an old snapshot from new configuration, rewrite a journal or migrate receipts.

The Router response qualifies the earlier shorthand that every changed Policy
conflicts. Current [CLI intake](https://github.com/relux-works/swarma-router/blob/48e537029b325b2480bd8918aa255cd6266be313/cmd/queued-task-handoff/main.go),
[validation](https://github.com/relux-works/swarma-router/blob/48e537029b325b2480bd8918aa255cd6266be313/handoff/types.go)
and [engine](https://github.com/relux-works/swarma-router/blob/48e537029b325b2480bd8918aa255cd6266be313/handoff/engine.go)
preserve this order:

1. Invalid policy file/JSON refuses as `invalid_policy_file`; typed invalid
   policy or an unauthorized request tuple refuses during validation before
   opening the journal. An unavailable adapter also refuses before journal use.
2. A valid `plan` validates its sources and remains a plan. It never reads an
   existing receipt and cannot become an intent conflict through journal replay.
3. Dispatch journal acquisition, custody/durability and record validation may
   refuse before digest comparison. Only otherwise valid/admitted dispatch,
   the same correlation and a healthy valid existing record reach changed-intent
   `conflict` / `correlation_intent_changed`.
4. Restoring the original policy preserves the applicable verified, unknown,
   reconciliation or durability result. It does not guarantee success. Matching
   historical replay is not fresh authorization or membership evidence.

Paired source controls distinguish an unrelated valid allowlist addition that
keeps the selected tuple (conflict, no additional Post), a malformed server
(`invalid_policy` before journal), and removal of the selected task while
another valid binding remains (`task_not_authorized` before journal). Existing
[immutable-policy recovery tests](https://github.com/relux-works/swarma-router/blob/48e537029b325b2480bd8918aa255cd6266be313/handoff/hardening_test.go)
and [intent-validation tests](https://github.com/relux-works/swarma-router/blob/48e537029b325b2480bd8918aa255cd6266be313/handoff/engine_test.go)
provide source controls; they were inspected, not rerun for this documentation
change. These recovery and compatibility controls retain no additional post,
automatic snapshot regeneration or receipt migration. This precision is resolved by the supplied response and
current code; it is not another unanswered consultation question.

## Implementation-readiness matrix

| Boundary | Evidence now available | Readiness and next accountable decision |
| --- | --- | --- |
| Original specification and proposal lineage | Original copies match; interaction r1, consolidated proposed r2 and Router precision are present and reconciled. | Input-recovery hold resolved. Proposal custodian retains exact bytes privately and records which final clauses counterparts accept; no global acceptance inferred. |
| Common envelope and loader | Existing strict-JSON envelope/manifest proposal and layout/absence/refusal invariants recovered. | Design input ready; implementation blocked on exact shared schema, source selection, error scope/precedence and semantic digest agreement by Curator, Router and the proposal custodian. No loader implemented here. |
| Curator Core / Launcher mapping | Closed schema 7 metadata projection and one-query consumer exist; standalone host-policy reader remains separate. | Existing seam identified. Curator owners settle shared-source placement, layout-specific provenance, origin mapping, native run/resume and first membership before new adapter work. Source inspection is not adoption. |
| Router config projection | Consultation has no structural objection; policy-refusal response verified against current handoff code; full config design and separate Go components identified. | Router confirms exact first provider/section version and section-revision mapping. Keep handoff Policy/journals outside. Full routing/live integration readiness is unproved. |
| Shared model catalog and remaining extension sections | Catalog lineage requirement and current proxy/OAuth shapes are known; no agreed common model entry/reference or Host member in Core's closed extension projection. | Relevant owners supply exact existing interfaces and availability. Do not create a second catalog or define a Host interface here. |
| Usable Host AND proxy prerequisites | Both original and successor proposals retain this delivery order. | Runtime acceptance evidence is not established by these config inputs. Source owners retain the prerequisites; this reconciliation does not waive them or repeat their implementations. |
| Integrated docking and independent review | Paired contract obligations below are defined, with separate current source evidence. | Build only after the exact agreements and prerequisites; parts dock both layouts and cross-review at readiness, then one independent whole-solution review binds the integrated candidate. This amended document itself still needs fresh independent review. |
| Delivery and staged use | Existing signed-delivery and one-project-at-a-time liveness rules retained. | This candidate remains local and unpushed for source-owner selection after review. Later PR/check/landing and supported adoption/rollback require their own evidence. No config/profile/credential/live-provider change occurs here. |

## Later paired verification

These are future contract controls, not executed implementation results.

| Case | Required positive and forbidden-neighbor evidence |
| --- | --- |
| Layout equivalence | Equivalent one-file/split inputs have equal agreed relevant typed values, precedence verdicts and digests; layout-specific provenance remains truthful. Duplicate authority refuses without an order-dependent winner. |
| Projection isolation | Unrelated section/layout/global-revision edits preserve required semantic identity; full-source and Router snapshot changes remain visible separately. Relevant unknown key/version or inconsistent binding refuses atomically. |
| Existing precedence | Mapped accepted origins yield the same effective result in both layouts. Ambient files/env cannot override selected authority or impersonate another origin. |
| Absence versus failure | Genuine optional omission preserves standalone behavior. A selected required target absent, unreadable, malformed, unsafe or unsupported refuses with no partial projection or fallback. |
| Native lifecycle | Selected metadata applies through fresh run and normal native resume. Invalid/unsupported selection refuses before effects; later credential/launch failure preserves required lease cleanup. Help and unrelated runtimes acquire no lease. |
| Handoff compatibility | Original Policy retains its applicable recovery outcome; otherwise admitted changed intent conflicts against a healthy record without posting. Invalid/unauthorized input and unsafe/unavailable/corrupt journals retain their earlier refusals; valid plan stays plan. |
| Catalog and secret references | Both projections bind the same actual catalog entry/revision and admitted opaque references. Replaced artifacts, copied lists, invalid reference shapes or capability-only rows cannot qualify launch or expose secrets. |
| Checker sensitivity | A bounded deliberate required-source read failure reaches the intended real loader refusal. An unexecuted plant, setup failure or reject-everything implementation cannot pass. |

Later consumers such as Pulse, Keyvault, messaging and signing retain their own
section ownership and staged migration. Their runtime integration is outside
the first Curator-plus-Router slice. This reconciliation closes supplied-input
questions only; it neither closes the parent implementation nor asserts a
jointly accepted platform contract.
