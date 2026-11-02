# swarma-host

The structure host of the swarma product. It holds the product card and the public key registry:

- the product card: the projects of swarma, where each one lives (remote, or local relative to this host), and who
  works on them;
- the public key registry: each member's public key, checked against identities; each member card names its key path
  and whether that key is local or remote.

The keeper starts from this repository. Members use swarma-pulse to read a caller-relative projection of the card.
The shipped unsigned query is self-only; broader hierarchy discovery remains separate work.

The desired product card is [product-card/product-card.yaml](product-card/product-card.yaml), using `product-card/v3`.
Relative project, task-system and clone paths start at that card's directory;
profile paths start at its declared `profiles_root`. The layout preserves the existing sibling checkouts.

The card describes desired assignments and launch selections. Its profile pins, runtime and network selection do
not attest a running process or grant access. The keeper declares its current Codex profile and explicit direct
selection for the existing route; this does not qualify a proxy or change the separately controlled rollout.
Other members retain their existing declarations. The public key registry is still pending.

## Tools

Use the reviewed Pulse CLI with the environment view (source revision `335308e7ca87bc042907283acb80fc542f424f4c`
or a compatible successor). It validates the complete v3 card before returning the invoking member's projection.
Keep the caller's existing `A2A_AGENT`; this command creates no identity and starts no runtime.

From this repository root:

```sh
card_path="$PWD/product-card/product-card.yaml"
card_sha256="$(shasum -a 256 "$card_path" | cut -d ' ' -f 1)"
pulse me --local-unsigned --view environment --card "$card_path" \
  --revision "sha256:$card_sha256" --format json
```

`shasum` pins the selected bytes. Pulse writes one JSON document to stdout and no card or persistent state;
redirect output to a chosen local file when needed. `state: complete` means the declared fields are present,
while runtime, registration and installed-profile observations remain unknown. Other members can legitimately
return an incomplete environment until their own declarations are updated. Missing unsigned mode or a wrong
content pin refuses without a partial view. Pulse's [query contract](https://github.com/relux-works/swarma-pulse/blob/335308e7ca87bc042907283acb80fc542f424f4c/docs/pulse.md)
defines the command's trust boundary and intended refusals.

Owner decisions:

- 2026-10-29: «где должна храниться такая карточка продукта - на каждый продукт будем заводить отдельынй проект
  названиеПродукта-хост / типо сварма-хост где и будет лежать эта карта где какие проекты ремоутно , где локально от
  этого хоста релативно и кто на них трудится каике работяшки».
- 2026-10-30: «в киволте нашем заводится пара, публичный реджистри  - должен лежать видимо в хосте проекта гитхабе т.е
  какой-то проект считается хостом  и тогда в нем хостится карта продукта и реджистри ключей и в карточках сотрудников
  путь на ключ локальный или ремоутный (указывается какой он и сам путь), тогда каждому участинку через ту же утилиту
  пульса будет доступна проверка ключей против личностей».
- 2026-10-30: «по структуре как обсудили есть продукт в нем будет либо отдельная репа продукт-хост и в ней энтрипойнт
  для кипера и тогда работнички через пульс от этого продукта понимают всю карту продукта и где они в этой структуре
  через проекцию карты против сотрудника».
