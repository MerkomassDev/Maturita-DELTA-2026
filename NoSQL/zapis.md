
# Random uryvky

*   **UNF**: Nenormalizovaná databáze.
*   **0NF**: Alespoň jeden atribut obsahuje více než jednu hodnotu.
*   **1NF**: Každý atribut obsahuje pouze atomické hodnoty.
*   **2NF**: Každý neklíčový atribut je plně závislý na každém kandidátním klíči.
*   **3NF**: Všechny neklíčové atributy musí být vzájemně nezávislé.
*   **BCNF**: Atributy, které jsou součásti primárního klíče, musí být vzájemně nezávislé.
*   **4NF**: Relace popisuje pouze příčinnou souvislost mezi klíčem a atributy.
*   **5NF**: Relace již není možno bezeztrátově rozložit.

---

## NoSQL

*   flexibilní schéma
*   nerelační
*   nepoužívá pouze SQL
*   horizontální škálování
*   vysoká dostupnost
*   rychlejší
*   nemusí být NULL
*   nemusí být konzistentní
*   menší - lépe komprimovatelné
*   lepší pro velká data (Big Data)
*   lepší pro nestrukturovaná data
*   pracuje s různými datovými typy

---

## SQL

*   struktura pevná
*   relační
*   používá pouze SQL
*   vertikální škálování
*   pomalejší
*   musí být NULL
*   musí být konzistentní
*   větší - hůře komprimovatelné
*   Pracuje pouze se strukturovanými daty

---

## CAP theorem

*   **Consistency (konzistence)**: Všechny uzly vidí stejná data ve stejný čas.
*   **Availability (dostupnost)**: Každý požadavek obdrží odpověď (úspěšnou nebo neúspěšnou).
*   **Partition tolerance (odolnost vůči dělení)**: Systém pracuje i při ztrátě komunikace mezi uzly.
*   Systém může garantovat pouze dvě ze tří vlastností současně.

**Možné kombinace garancí:**

*   **CA (Konzistence a dostupnost)**: SQL databáze; striktní synchronizace, vyžaduje nepřerušenou komunikaci mezi uzly, obětuje P.
*   **CP (Konzistence a odolnost k přerušení)**: Např. BigTable, HBase, MongoDB, Redis; striktní konzistence, obětuje A v případě dělení sítě.
*   **AP (Dostupnost a odolnost k přerušení)**: Např. Cassandra, Dynamo, CouchDB; vysoká dostupnost i při dělení sítě, obětuje C (může vracet starší data).
