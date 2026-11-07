# Host input interface qualification

Status: source-grounded documentation candidate for independent review. The exact accepted Candidate02, whole design
verdict, acceptance receipt and host readiness reconciliation have been inspected. Their prior payload-availability gaps
are closed. Executable successor-interface qualification remains **blocked on exact F3 fixture inputs and an admitted
implementation**. No canonical-card migration, public-key enrollment or new runtime qualification is recorded here.

## Fixed source basis

This document compares the published host at
[`43c082ce387d143d4a6814971cec4cf7f2ddd804`](https://github.com/relux-works/swarma-host/tree/43c082ce387d143d4a6814971cec4cf7f2ddd804)
with Pulse at
[`e86b048cc5135e14897181f1921c7e0fd11212d8`](https://github.com/relux-works/swarma-pulse/tree/e86b048cc5135e14897181f1921c7e0fd11212d8).
These are source observations, not new deployment pins. The host contains a README and desired v3 product card;
it does not contain a host reader or key registry implementation. Its query example pins Pulse
`228b96971aa547ea44daca7a8c844d156d25eced` or a compatible successor. Compatibility and actual adoption of the newer
source are separate checks; this document does not update that selection.

The supplied frozen design verdict accepts Candidate02 for **design readiness only**, with R1–R5 closed and the
nonblocking P3-D1 exact-byte clarification retained. The following lengths and SHA-256 values were recomputed from
the supplied bytes. Availability and integrity do not renew the historical review or confer live admission.

| Artifact | Verified byte length | Verified SHA-256 | Inspection status |
| --- | --- | --- | --- |
| `successor-input-contract-candidate-02.md` | 92,120 | `fca863098a55ae76097f6a1b2866152ad7127d2e4dc57182fa576cacd984c657` | Complete accepted design inspected, including examples and requirement mapping |
| `independent-verdict-02.md` | 25,369 | `ae231d575f5d2bdbe1264db05f9dc4758b8f3fa0a4913ad2b055eac90629f3af` | Whole ACCEPT inspected; design scope and P3-D1 retained |
| `design-accept-receipt-02.md` | 1,307 | `ae71d54d7a5c0add35fd438f5ed90039601dc9273a4427fbf952b17a59a11f3b` | Binds acceptance to the exact candidate and verdict; does not start implementation |
| `accepted-pulse-design-review.md` | 25,369 | `ae231d575f5d2bdbe1264db05f9dc4758b8f3fa0a4913ad2b055eac90629f3af` | Byte-identical to the whole independent verdict; one review, not a second independent acceptance |
| `preconditions/host-interface-readiness-reconciliation-r3.md` | 3,849 | `7e98e9d36ebba1863883a4570dcb38c59a1aefcafe0a38ac78c1d74e9af28313` | Original direct-v3 local-unsigned readiness and its limits inspected |

Preserve that historical acceptance and its original bytes. The published
[host/key proposal](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/specs/product-host-key-registry-v1.md)
is useful evidence of the version boundary; it is not a replacement for Candidate02. Candidate02 was designed against
Pulse `b226d861a91de7cd767d64ba8f7b23e4fa9bd464`; the shipped-source comparison above uses the later fixed source.
Neither source pin is a new host deployment selection. The mapping below now uses the actual design text.

## Supported contract table

“Shipped” below means code is present at the fixed Pulse source. It does not mean this host has installed or exercised it.
All referenced tables are bound to that immutable revision.

| Boundary | Exact supported contract | Design or qualification limit |
| --- | --- | --- |
| Input versions | Static validator accepts `product-card/v3` and `product-card/v4`. The local unsigned query's baseline accepts v3; environment/discovery support `product-card/v3` and `company-card/v1` as documented. | A v4 validator is not a v4 personal-query reader. Neither provides a Candidate02 successor reader. [Validator](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/validator.md), [query](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md) |
| Package and consumer seam | `internal/cardv4` provides static validation, conversion/preservation and desired-change operations inside the Pulse module. `internal/pulse` implements the local query. | These are Go internal packages. An outside consumer requires a separately reviewed public-package split. There is no host SDK or new registration API supplied here. [Open inputs](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/UNRESOLVED_QUESTIONS.md) |
| v4 root | Required keys are exactly `schema`, `product`, `external_members`, `connections`, `bindings`, `profiles_root`, `profiles`, `projects`, `members`; no optional root keys. `schema` is `product-card/v4`. Product requires exactly `id`, `description`, `privacy`, `keeper`, `default_binding`, `host_project`, `topology`. | Every v4 nested object is closed; null, unknown or duplicate fields refuse. This closure must not be imposed retroactively on supported v3 legacy extensions. [Complete v4 tables](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/format-v4.md#closed-object-field-tables) |
| v4 root/path meaning | `product.host_project` resolves to a local project with `location: {kind: local, path: .}`. Project local paths, member `clone`/`git_dir` and `profiles_root` use the card directory; a local task-system path uses its project directory. A profile path uses `profiles_root`. | Supplied admitted roots bound filesystem checks; lexical traversal and symlink escape refuse. Remote locators are declarations, never local reads or fetches. Do not reinterpret the existing v3 nested card layout as a completed v4 relocation. [v4 relations](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/format-v4.md#relations-paths-and-class-constraints) |
| v4 member core | Common required keys: `id`, `role`, `project`, `parent`, `scope`, `binding`, `identity`, `lifecycle`, `desired_state`, `context_mode`, `runtime`. Common optional keys: `desired_state_ref`, `capabilities`, `clone`, `git_dir`, `station`, `logical_source_ref`. | The exact conversational/service branch tables also apply. Optional `station` is preserved verbatim. Logical identity, desired placement, executor observations and authority remain separate. [v4 tables](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/format-v4.md#closed-object-field-tables) |
| Member branches | Conversational members require `profile`; their branch optionally allows `staffing`, `independent_of_producer`, `result_route`, `chat_admission`, `a2a`. Service members require `service_contract_ref` and `result_route`; their branch optionally allows `a2a`, `native_result_ref`, `selector_policy_ref`. | Scope/role/result-route constraints further restrict presence. Service runtime is exactly `{kind: none}`, context mode `none`, without profile/model/effort/staffing. Reviewer context is fresh and independent. Static acceptance does not qualify a service launcher. [v4 constraints](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/format-v4.md#relations-paths-and-class-constraints) |
| Operator and identity | A v4 binding has exactly `operator`, `host`, `connection`, `identity_domain`; domain equals the selected connection's `server_name`. Legacy identity has exactly `scheme: legacy-exact`, `mxid`, `source_ref`. New identity has exactly `scheme: domain-star-v1`, `star`. | Legacy source bytes/revision/digest, unchanged key and independently derived connection/MXID must agree. New tuple/reservation validation grants no account or launch. Existing logical keys retain their explicitly attested compatibility branch. [v4 identity](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/format-v4.md#legacy-sources-new-tuples-and-deterministic-conversion) |
| Validator source supply | `--source-manifest` supplies a JSON mapping with `source_pins: [{file, revision, sha256}]`; each file resolves relative to that manifest under a rooted read. Library source bytes carry explicit kind/revision/digest. | This validator input is distinct from the query discovery manifest and the accepted but unimplemented Candidate02 source/package contract. A precomputed identity map or fetch instruction cannot replace source bytes. [Validator](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/validator.md) |
| Query source set | Discovery uses closed UTF-8 JSON `pulse-sources/v1` with exactly `schema`, `cards`; each additional entry has exactly `id`, `schema`, `path`, `revision`. Entry schema is v3 product or v1 company; revision is `sha256:` plus 64 lowercase hex. The primary is selected separately. | Manifest bytes require their own pin. Paths use the primary card's parent, regardless of manifest directory; primary, manifest and supplied cards must be strictly within explicit absolute clean `--root`. Duplicate or mismatched sources refuse; with a company, unreferenced supplied products also refuse. No workspace scan, Git lookup or remote fetch. [Discovery](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md#company-inventory-and-caller-discovery) |
| Shipped environment/discovery output | Both unsigned views emit `pulse-view/v2` with exactly 17 root fields: `schema`, `mode`, `query`, `caller`, `known_limit`, `sources`, `self`, `peers`, `direct_reports`, `descendants`, `superiors`, `projects`, `products`, `boundaries`, `hierarchy_status`, `observations`, `query_observed_at`. `observations` is an object with `runtime`, `registration`, `installed_profile` and `assignment` records, each with `state: unknown`. | Environment uses `query: {view: environment}`; discovery uses the same closed root with its discovery query/source receipt. This shipped shape is incompatible with Candidate02's same-labeled proposed shape below; the schema string alone cannot discriminate them. [Environment contract](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md#declared-environment-view), [discovery contract](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md#company-inventory-and-caller-discovery), [query source](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/internal/pulse/query.go#L111-L134) |
| Public binding | v4 has no member `identity_key` or product `identity_key_registry`. The host README says its public key registry is pending. | The published proposal describes future index/operator/public-key references, not a shipped binding reader. Public material, operator endorsement, private-key possession, registry authority and runtime permission are separate. A proposed v5 or registry document cannot be supplied to v4 as an extension. [Key proposal §§3–5](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/specs/product-host-key-registry-v1.md#4-proposed-version-boundary) |
| Current caller | The shipped query requires explicit `--local-unsigned` and existing `A2A_AGENT`, matched exactly against one declared/default v3 identity prefix plus member id. UID/eUID must agree. | Caller is explicitly unverified, using single-user local trust. Signed-caller, signature, host-config, trust, policy and clock selectors are unsupported. No identity, token or config lookup is inferred. [Query](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md#local-trust-and-file-boundary) |
| Signed caller design | Closed JSON `pulse-caller/v1` has exactly `schema`, `subject`, `execution_binding`, `card_sources`, `visibility_sha256`, `issued_at`, `expires_at`. Card-source entries carry product/revision/SHA-256. Detached SSHSIG signs exact bytes in namespace `pulse-caller-v1` under host-selected trusted signers. | This is the accepted specification's design boundary, not shipped CLI support. Subject, execution binding, selected card binding, every source pin, validity interval and authorized signer must agree. Candidate02 retains that exact envelope and pins transitive documents through the complete roots under a future admitted v5-aware consumer; it adds no envelope fields. Never reinterpret this as P-256 member signing. [Specification §6](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/specs/product-card-identity-pulse-v1.md#6-pulse-query) |
| Visibility | Signed design: `visibility_sha256` is digest or null. A non-null digest pins exact closed `pulse-visibility/v1` bytes with `schema`, `subject`, `visible_members`; self is always visible. Null means self-only, and unpinned policy refuses. | This policy is not implemented by the unsigned CLI. Baseline/environment are self-only. Explicit unsigned discovery returns related summaries in the supplied universe, with other members' environments/private routes withheld; it proves no visibility entitlement. Restricted and unavailable boundaries in the signed design must remain distinct. [Specification §6](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/specs/product-card-identity-pulse-v1.md#6-pulse-query), [discovery output](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md#company-inventory-and-caller-discovery) |
| Facts and freshness | Query receipts identify exact supplied bytes and their actual card parent. Runtime, registration, installed-profile and assignment observations remain unknown; query UTC time is separate from source freshness. | Desired bindings/profile pins are not actual placement or installation evidence. An unsigned discovery hierarchy may be complete only relative to supplied declarations. No actual local/private/native facts are inferred. [Returned facts](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md#returned-facts) |

## Accepted successor design mapped to the current boundary

References `C:line` below identify Candidate02 at the verified digest above. These are accepted design allocations,
not added fields in the current readers. The complete candidate and whole verdict remain the field-level authority.

| Surface | Exact accepted design | Current qualification and remaining boundary |
| --- | --- | --- |
| Root and members, C:62–72 | Closed `product-card/v5` root has `schema`, `product`, `external_members`, `connections`, `bindings`, `profiles_root`, `profiles`, `projects`, `member_sources`. Product adds `identity_key_registry`, `name_registry`, optional descriptive `display_name`; `member_sources` replaces root `members`. Selection has `id`, `operator`, `operator_ref`, `revision`, `document`; member document has `schema`, `product`, `operator`, `sequence`, `state`, `members`. | v4 still requires `members` and rejects these successor additions. One canonical root and disjoint admitted member union are design requirements; no host composer is supplied. All applicable v4 member branches survive, with the added v5 `identity_key`. |
| Blobs and revisions, C:74–102 | JSON Blob branches are exactly `embedded-json {kind,text,sha256}`, `host-file {kind,path,sha256}`, or `supplied-file {kind,package,revision,path,sha256}`. Public Blob allows only the two file branches and raw DER. Only selection revision, supplied-file revision and index-operator revision get the new `git:`/40-hex or `sha256:`/64-hex grammar. | Selected bytes, roots and package snapshots need independent admission; no fetching, discovery or extraction service. Package revision is separate from per-file digest. Legacy source, caller-v1 and root-provenance revision contracts retain their exact old grammar and bytes. |
| Publisher and source union, C:104–149 | Receiver admits one-to-one safe publisher namespace ↔ exact preserved `operator_ref`, exact member/relationship/placement scope, current pins, sequence floors and known withdrawals. Duplicate logical members refuse even when equal; source order has no precedence. | Hashes and author names grant no authority. Missing/withdrawn selected member sources refuse complete current structure. Historical explanation needs intact previously admitted bytes and historical pins; it cannot revive current authority or update a ledger. |
| Structure and paths, C:151–172 | Stable product/member keys, bindings, graph, desired/parked state, profile locks and source/task/station/result references survive. Project paths remain card-relative, tasks project-relative; host `.` and admitted siblings retain their own roots. | Existing converter still needs the chosen host in the valid source. Adding a missing host is an admitted structural delta, not lossless conversion or fabricated history. Display wording cannot migrate product identity. |
| Public keys, C:176–274 | Registry is unavailable or a selected JSON index; member key is unavailable or exact operator/generation/key-id selection. Closed `pulse-key-index/v2` → `pulse-operator-keys/v2` → public-file chain binds product/member/publisher, custody and record-local generation. Concrete profile is `mac-keyvault-p256-spki/v1`, descriptive `member-public-binding`, `ec-p256`, canonical 91-byte P-256 SPKI DER; hex digest and base64url key id hash the same exact bytes. | v4 has no registry/key fields. All-unavailable keys allow structural description without key qualification. Real key/custody/module/purpose/refresh admission remains absent. No possession, grant, vault use, private-key export or Ed25519/SLH substitution follows. |
| Naming, C:276–313 | `pulse-name-registry/v1` has `schema`, `projects`, `stars`, `accounts`; `project-star-v1` needs exact admitted reservations, including retained retired entries. Legacy-exact/domain-star-v1 remain unchanged and independent of the new registry. | Snapshot is a read-only allocation witness, not an allocator, account or live cutover. Current compact qualification needs separately admitted refresh and finite positive horizon. No naming migration is performed. |
| Caller and audience, C:315–400 | Exact `pulse-caller/v1`, SSHSIG namespace and self-only/pinned visibility remain unchanged. Caller pins complete roots; transitive hashes pin subordinate documents but never replace publisher admission. Candidate02 proposes the same label `pulse-view/v2` for a distinct closed 12-field shape: `schema`, `subject`, `sources`, `self`, `peers`, `direct_reports`, `descendants`, `superiors`, `projects`, `observations`, `scope`, `snapshot`. Its `observations` is an empty array; no observation producer is allocated. | This proposed shape is incompatible with shipped environment/discovery v2. Neither caller-v1 verifier nor v5 query is shipped. Product-qualified project/source associations retain each admitted root; visible-edge traversal cannot skip hidden seats. No hidden markers/counts/paths; same-principal raw access remains outside projection isolation. |
| Snapshot and optional qualification, C:329–418 | Explicit last-received/historical interpretation, received-state-only knowledge, evaluation and admitted/unavailable refresh separate structure from optional qualified-at-evaluation/historical-reference key/name results. Corrupt/forbidden/unauthorized supplied inputs refuse the whole view; missing optional key/name files may omit only their qualification. | No implicit time, current-state guarantee or production freshness default. Known later revocation/withdrawal overrides older current-use pins. Missing selected member sources cannot yield a smaller complete view. These design obligations supply no current CLI exit-code implementation. |
| Bounds and rollout, C:29–60,410–478 | Root and each subordinate JSON ≤1 MiB, public file ≤4096 bytes, total selected bytes ≤16 MiB; ≤256 sources/operators, 1000 projects, 10000 members, 20000 key entries, 10000 entries per naming table, 32 container levels and 1000000 parsed nodes. Identical referenced blobs count once; derived structure keeps v4 limits. | In-memory v4 adaptation is only necessary structural evidence. No in-place downgrade, second canonical publication or fake compact identity. Independently reviewed implementation and version-aware readers precede separately admitted writers, migration and live operations. |

The shared `pulse-view/v2` label does not identify a compatible wire shape or establish a capability. Candidate02
requires `subject`, `scope` and `snapshot`, which the shipped root lacks, and omits the shipped root's `mode`, `query`,
`caller`, `known_limit`, `products`, `boundaries`, `hierarchy_status` and `query_observed_at`. Its array-valued
`observations` also conflicts with the shipped object. Applying either closed shape to the other rejects supported
fields or misses required fields; a consumer must not infer support for the proposal from the schema string alone.
The frozen Candidate02 bytes and historical design acceptance remain unchanged, including their original label;
this comparison neither renames nor reinterprets that design or adopts it. Explicit source-owner version/capability
agreement and an independently reviewed implementation are required before future consumer adoption.

Candidate02 section 9a and the whole verdict close R1 product/root association, R2 non-slug operator preservation,
R3 revision scope, R4 historical/current labels and R5 expiry-versus-freshness controls at the **design** level.
All 34 paired descriptions remain hypothetical contract controls. Their inspection is not 34 executed v5 passes.

## Original readiness and separate admission limits

The exact readiness-r3 resource records the accepted original direct-v3 `pulse me --local-unsigned` operation,
its self-only unverified caller and adjacent digest/unknown-context refusals. That existing path needs no canonical
host migration, issuer, signature, relocated snapshot or new configuration. This reconciliation does not rerun it.
The underlying original execution/check receipts are referenced by the resource, not newly supplied execution evidence.

The same record leaves installed profiles, runtime, registration and assignment unknown; its undeclared keeper project
stays undeclared and hidden hierarchy stays hidden. Byte identity proves no freshness. It still requires a concrete
admitted executable counterpart and paired conformance evidence for the future canonical interface. Source agreement,
historical local readiness and permission for a new shared-host/live caller path are separate qualifications.

## Compatibility, bounds and refusal obligations

The v4 grammar remains unchanged: one UTF-8 mapping, at most 1 MiB, 32 container levels, 1,000 projects, 10,000 members
and 64 traversed reporting edges. Duplicate/non-string keys, explicit tags, aliases, merges, extra documents, nulls,
unknown fields and wrong types refuse. Existing v3 bounded aliases and permitted extensions retain their own reader
semantics. Do not turn the design's stricter v4 rules into a compatibility regression for v3.

Unsigned discovery additionally bounds the input universe to 32 additional cards, 16 MiB total card bytes, 10,000
materialized members and 64 reporting hops; each card/manifest remains at most 1 MiB. Missing supplied paths fail the
query; deliberately unsupplied references return explicit boundaries. Symlinks and unsafe file ancestry refuse even
when lexically inside the read root. The source-digest check hashes exact selected bytes, not reserialized objects.

| Case | Required disposition at the existing boundary |
| --- | --- |
| Supported existing v4 and legacy source pins | Retain static validity and preservation semantics; do not add successor fields or reinterpret identities. |
| Extra v4 key, `product-card/v5`, registry/member-key fields | Refuse under the current closed v4/schema boundary. No implicit future acceptance. |
| Extra or duplicate signed caller-v1 key | Design requires whole-query refusal; no new field admission and no claim of executable evidence. |
| Untrusted/expired signed caller, execution-binding/subject mismatch, bad source pin or unpinned visibility policy | Design requires refusal without a partial projection. Exact host-admitted signer/configuration and execution evidence remain absent. |
| Current CLI missing/duplicate/unknown flags or signed selectors | Usage refusal, exit 2, empty stdout and safe stderr diagnostic. No unsigned fallback. |
| Current query content/context/path/graph failure | Query refusal, exit 1, empty stdout and safe stderr diagnostic. Success is exit 0 with one buffered complete JSON document; output transport failure can interrupt delivery. |
| Current discovery relation conflict versus reporting-hop excess | A relation conflict found within a walk's 64-hop budget takes precedence over another walk's hop excess; otherwise exceeded budget refuses `input_limit`. Earlier source/identity/input-budget checks retain their order. |
| Proposed public binding with matching digest but absent operator admission | Matching hashes supply no authority. Qualification remains blocked; do not enroll, trust, fetch or launch. |

The linked validator documents its own rule/location/exit contract and first-failure ordering; query exit codes above
must not be transplanted onto that separate tool. No new Candidate02 refusal identifier is invented here.

## P3/F3 exact-byte prerequisite

Historical acceptance retains the nonblocking P3-D1 condition before executable F3 use. This document carries it
forward without selecting a serializer, generating a root fixture or turning illustrative literal pins into accepted input:

| Future fixture case | Required evidence/disposition |
| --- | --- |
| Selected valid root serialization with its own admitted pin | Exact selected bytes, applicable pin computation, semantic validity and explicit admission of that pair. |
| Changed selected bytes with the old pin | Refuse; semantic similarity does not repair the stale pin. |
| Alternate valid serialization with its own independent admitted pin | Separate byte/pin and semantic-validity evidence for that alternate; no general production canonical JSON rule follows. |
| Illustrative/recomputed literal pin without exact-artifact admission | Ineligible as an admitted execution input. |

Candidate02 C:946–998 supplies `F3_colliding_project_roots_expected_projection` and
`F3_second_root_from_F0_patch`, using F0 from C:506 onward. These identify logical data and literal expected source
hashes, not separately supplied complete root byte files. P3-D1 in the whole verdict identifies C:951–952 and C:963–964,
compared with C:36–40 and C:798. It reports compact-JSON witnesses of 4,338 and 4,344 bytes and different valid
indented-plus-LF witnesses; its chosen compact encoding is explicitly not a candidate rule or fixture admission.
The acceptance receipt retains that clarification and freezes Candidate02. The supplied set contains no exact F3
root-file locator or accepted fixture pin. Do not treat those illustrative hashes as newly admitted pins, reconstruct
canonical bytes from the objects, or fabricate a fixture filename. No F3 executable case was run here.

## Input resolution and next decisions

| Prior input gap | Resolution from the exact supplied resources | Remaining qualification |
| --- | --- | --- |
| Candidate02 frozen payload | Closed: complete bytes verified and inspected; the source, package, root, member, key and audience mapping above is now grounded in its text. | Accepted design stays unimplemented; current v3/v4 support is unchanged. |
| Whole independent verdict and original acceptance binding | Closed for supplied design evidence: exact whole ACCEPT and acceptance receipt inspected, including all five closure assessments and P3-D1. | Historical review is preserved, not reauthenticated or renewed as a runtime or implementation review. |
| Host accepted design-review resource | Closed: exact supplied resource is byte-identical to that same verdict. | No second review, bilateral adoption or independent host implementation acceptance inferred. |
| Host readiness-r3 resource | Closed: exact reconciliation inspected; original local unsigned route needs no new canonical migration/signing prerequisite. | Underlying original runtime/check receipts and the future admitted executable counterpart are separate evidence. |
| P3-D1/F3 pin/validity excerpts and exact admitted fixtures | Partially resolved: exact candidate/verdict excerpts now available. Exact selected/alternate root bytes, their independently admitted pins and causal stale-pin refusal evidence remain missing. | Existing Pulse fixture custodian supplies the fixture-only bytes/serialization disposition and admission; illustrative witnesses cannot satisfy executable F3 qualification. |
| Actual source/canonical-writer, operator namespace, caller trust/visibility and public-binding dispositions | Design requirements are now inspectable; actual versioned receiving-context dispositions are not supplied by these design/readiness documents. | Existing source/operator custodians own actual admission. No shared-host/public-key/signed-caller adoption, new implementation assignment or grant follows. |

Original source agreement and live admission remain distinct. The separately supplied common-configuration original
specification and proposed revisions concern another contract: source-owner wire/schema agreement and actual usable
Host AND proxy prerequisites remain required for that layer. Their availability does not approve a platform wire
format, launch, configuration write or implementation here. No shared-configuration source is changed.

Next, the existing custodians resolve the named fixture and executable/admission dependencies and obtain the requested
single integrated independent interface review against the exact candidate source and evidence. This documentation
update itself needs fresh exact-head review and its source marker; an earlier documentation verdict cannot approve the
changed head. The dependent usage/extension skill and original source/native/implementation holds remain. Original
acceptance clocks stay fixed. Atomic-operation and shared-configuration contracts remain separate. No runtime, card,
identity, key, installed package or default branch is changed by this document.
