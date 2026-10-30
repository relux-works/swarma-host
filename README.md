# swarma-host

The structure host of the swarma product. It holds the product card and the public key registry:

- the product card: the projects of swarma, where each one lives (remote, or local relative to this host), and who
  works on them;
- the public key registry: each member's public key, checked against identities; each member card names its key path
  and whether that key is local or remote.

The keeper starts from this repository. Members do not read the card directly: they get their own projection of it
(peers, subordinates, superiors) through swarma-pulse.

Status: empty. The card format comes from swarma-pulse. The card and the key registry are added here once that format
is accepted.

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
