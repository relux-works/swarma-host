# Host input interface qualification

Status: source-grounded documentation candidate for independent review. The current reader boundaries below are
identified; full Candidate02-to-host qualification is **blocked on missing exact artifacts**. No integrated acceptance,
reader implementation, canonical-card migration, public-key enrollment or runtime qualification is recorded here.

## Fixed source basis

This document compares the published host at
[`43c082ce387d143d4a6814971cec4cf7f2ddd804`](https://github.com/relux-works/swarma-host/tree/43c082ce387d143d4a6814971cec4cf7f2ddd804)
with Pulse at
[`e86b048cc5135e14897181f1921c7e0fd11212d8`](https://github.com/relux-works/swarma-pulse/tree/e86b048cc5135e14897181f1921c7e0fd11212d8).
These are source observations, not new deployment pins. The host contains a README and desired v3 product card;
it does not contain a host reader or key registry implementation. Its query example pins Pulse
`228b96971aa547ea44daca7a8c844d156d25eced` or a compatible successor. Compatibility and actual adoption of the newer
source are separate checks; this document does not update that selection.

The supplied historical design record reports Candidate02 as accepted, with a whole independent ACCEPT and closed
R1–R5 findings. The following identifiers locate the **missing bytes**; they are not recomputed digests or a renewed review:

| Artifact | Reported byte length | Reported SHA-256 | Inspection status |
| --- | --- | --- | --- |
| `successor-input-contract-candidate-02.md` | 92,120 | `fca863098a55ae76097f6a1b2866152ad7127d2e4dc57182fa576cacd984c657` | Payload unavailable in this qualification |
| `independent-verdict-02.md` | 25,369 | `ae231d575f5d2bdbe1264db05f9dc4758b8f3fa0a4913ad2b055eac90629f3af` | Whole verdict unavailable in this qualification |

Preserve that historical acceptance and its original bytes. The published
[host/key proposal](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/specs/product-host-key-registry-v1.md)
is useful evidence of the version boundary; it is not a replacement for Candidate02. No exact Candidate02 field table,
source-package format or refusal code is inferred from its title, digest or later metadata.

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
| Validator source supply | `--source-manifest` supplies a JSON mapping with `source_pins: [{file, revision, sha256}]`; each file resolves relative to that manifest under a rooted read. Library source bytes carry explicit kind/revision/digest. | This validator input is distinct from the query discovery manifest and the unavailable Candidate02 source/package contract. A precomputed identity map or fetch instruction cannot replace source bytes. [Validator](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/validator.md) |
| Query source set | Discovery uses closed UTF-8 JSON `pulse-sources/v1` with exactly `schema`, `cards`; each additional entry has exactly `id`, `schema`, `path`, `revision`. Entry schema is v3 product or v1 company; revision is `sha256:` plus 64 lowercase hex. The primary is selected separately. | Manifest bytes require their own pin. Paths use the primary card's parent, regardless of manifest directory; primary, manifest and supplied cards must be strictly within explicit absolute clean `--root`. Duplicate or mismatched sources refuse; with a company, unreferenced supplied products also refuse. No workspace scan, Git lookup or remote fetch. [Discovery](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md#company-inventory-and-caller-discovery) |
| Public binding | v4 has no member `identity_key` or product `identity_key_registry`. The host README says its public key registry is pending. | The published proposal describes future index/operator/public-key references, not a shipped binding reader. Public material, operator endorsement, private-key possession, registry authority and runtime permission are separate. A proposed v5 or registry document cannot be supplied to v4 as an extension. [Key proposal §§3–5](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/specs/product-host-key-registry-v1.md#4-proposed-version-boundary) |
| Current caller | The shipped query requires explicit `--local-unsigned` and existing `A2A_AGENT`, matched exactly against one declared/default v3 identity prefix plus member id. UID/eUID must agree. | Caller is explicitly unverified, using single-user local trust. Signed-caller, signature, host-config, trust, policy and clock selectors are unsupported. No identity, token or config lookup is inferred. [Query](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md#local-trust-and-file-boundary) |
| Signed caller design | Closed JSON `pulse-caller/v1` has exactly `schema`, `subject`, `execution_binding`, `card_sources`, `visibility_sha256`, `issued_at`, `expires_at`. Card-source entries carry product/revision/SHA-256. Detached SSHSIG signs exact bytes in namespace `pulse-caller-v1` under host-selected trusted signers. | This is the accepted specification's design boundary, not shipped CLI support. Subject, execution binding, selected card binding, every source pin, validity interval and authorized signer must agree. New registry/source fields need an explicitly admitted successor envelope. Never reinterpret this as P-256 member signing. [Specification §6](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/specs/product-card-identity-pulse-v1.md#6-pulse-query) |
| Visibility | Signed design: `visibility_sha256` is digest or null. A non-null digest pins exact closed `pulse-visibility/v1` bytes with `schema`, `subject`, `visible_members`; self is always visible. Null means self-only, and unpinned policy refuses. | This policy is not implemented by the unsigned CLI. Baseline/environment are self-only. Explicit unsigned discovery returns related summaries in the supplied universe, with other members' environments/private routes withheld; it proves no visibility entitlement. Restricted and unavailable boundaries in the signed design must remain distinct. [Specification §6](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/specs/product-card-identity-pulse-v1.md#6-pulse-query), [discovery output](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md#company-inventory-and-caller-discovery) |
| Facts and freshness | Query receipts identify exact supplied bytes and their actual card parent. Runtime, registration, installed-profile and assignment observations remain unknown; query UTC time is separate from source freshness. | Desired bindings/profile pins are not actual placement or installation evidence. An unsigned discovery hierarchy may be complete only relative to supplied declarations. No actual local/private/native facts are inferred. [Returned facts](https://github.com/relux-works/swarma-pulse/blob/e86b048cc5135e14897181f1921c7e0fd11212d8/docs/pulse.md#returned-facts) |

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

No F3 executable case was run here. The sealed paper packet provides a prospective matrix and explicitly lacks the
Candidate02 payload, native acceptance and fixture contract. Its existence does not discharge this prerequisite.

## Exact missing inputs and next decisions

| Missing artifact | Needed from its existing custodian | What remains blocked |
| --- | --- | --- |
| `successor-input-contract-candidate-02.md`, exact length/digest above | Pulse design custodian: deliver the frozen bytes through an admitted source or sealed handoff. | Exact Candidate02 source/package/root/member/operator/public-binding/visibility/refusal mapping. |
| `independent-verdict-02.md`, exact length/digest above, and original design acceptance | Pulse design custodian: deliver the whole verdict and acceptance binding to the frozen candidate. | Verification of accepted R1–R5 closure and the full design review basis. No replacement design review is implied. |
| `accepted-pulse-design-review.md` | Host contract custodian: deliver the existing frozen intake/review resource with byte length, digest and custody binding. | Qualification against the host's actual accepted intake. |
| `preconditions/host-interface-readiness-reconciliation-r3.md` | Host contract custodian: deliver the existing exact reconciliation resource with byte length, digest and custody binding. | Verification of remaining readiness inputs and the original no-canonical-migration determination. |
| P3-D1/F3 applicable pin/validity excerpts and exact admitted fixture artifacts | Pulse fixture custodian: deliver accepted root-byte boundary, computation/encoding rules, selected and alternate byte artifacts, their own pins and admissions. | Executable F3 qualification; the metadata-only paper is insufficient. |
| Accepted source/canonical-writer, operator namespace, caller trust/visibility and public-binding input dispositions | Existing source and operator custodians: supply exact versioned artifacts for the receiving context. | Actual shared-host/public-key/signed-caller adoption. No missing operator grant is inferred from a public locator. |

The first two missing design artifacts already have exact identifiers. The two host resources have exact resource names,
but their bytes, lengths and hashes were not supplied; inventing those values would invalidate the qualification.
This document leaves all original acceptance clocks and existing source/native/implementation holds intact.

After exact inputs arrive, compare Candidate02 field-by-field with the frozen current boundaries, resolve any contract
conflict through the existing custodian, and obtain the requested single integrated independent interface review against
the exact candidate source. Until then the dependent usage/extension skill remains held. Atomic-operation and
shared-configuration work have separate contracts and are not authored or qualified here. No runtime, host, card,
identity, key, installed package or default branch is changed by this document.
