
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

---

## ACID vs BASE
*   **ACID** (Atomicity, Consistency, Isolation, Durability): Vlastnosti tradičních relačních databází zajišťující spolehlivost transakcí.
    *   **Atomicity (Atomovost)**: Transakce je nedělitelná jednotka - buď se provede celá, nebo vůbec.
    *   **Consistency (Konzistence)**: Transakce přenáší databázi z jednoho konzistentního stavu do druhého.
    *   **Isolation (Izolace)**: 
        *   Transakce probíhají izolovaně, bez vzájemného ovlivňování.
        *   Různé úrovně izolace (Read Uncommitted, Read Committed, Repeatable Read, Serializable) určují, jak moc mohou transakce vidět změny jiných transakcí.
    *   **Durability (Trvanlivost)**: Po úspěšném dokončení transakce jsou její změny trvalé, i při selhání systému.

*   **BASE** (Basically Available, Soft state, Eventual consistency): Vlastnosti NoSQL databází zaměřené na vysokou dostupnost a škálovatelnost.
    *   **Basically Available (Základní dostupnost)**: Systém je vždy dostupný, i když nemusí být konzistentní.
    *   **Soft state (Měkký stav)**: Stav systému se může měnit v čase, i bez vstupu uživatele.
    *   **Eventual consistency (Nakonec konzistentní)**: Systém se nakonec stane konzistentním, pokud nejsou prováděny žádné nové operace.

---

## Typy a jejich principy ( REVIEW PENDING, AI GENERATED, nerozumim tomu lol )

* **Škálovatelnost**
    * **Vertikální škálování (scale up)**: Přidání více zdrojů (CPU, RAM) do jednoho serveru.
    * **Horizontální škálování (scale out)**: Přidání více serverů do systému.
* **Replikace**
    * **Master-Slave**: Jeden hlavní server (master) přijímá zápisy, ostatní (slaves) jsou kopie pro čtení.
    * **Master-Master**: Více serverů může přijímat zápisy, synchronizují se mezi sebou.
* **Sharding**
    * Rozdělení dat do menších částí (shardů) na různých serverech pro zlepšení výkonu a škálovatelnosti.
* **Indexování**
    * Vytváření datových struktur pro rychlejší vyhledávání dat.
* **Konzistence**
    * **Silná konzistence**: Po zápisu jsou data okamžitě viditelná pro všechny čtenáře.
    * **Eventuální konzistence**: Data se nakonec stanou konzistentními, ale nemusí být okamžitě viditelná.
* **Transakce**
    * **ACID**: Vlastnosti zajišťující spolehlivost transakcí v relačních databázích.
    * **BASE**: Vlastnosti zaměřené na vysokou dostupnost a škálovatelnost v NoSQL databázích.

---

## Druhy dat 
* **Strukturovaná data**: Data organizovaná do tabulek s pevně definovanými schématy
* **Nestrukturovaná data**: Data bez pevné struktury, jako jsou textové dokumenty, obrázky, zvuk, videa
* **Polostrukturovaná data**: Data s částečnou strukturou, jako jsou JSON/XML soubory, E-maily s kategorizací, Tweety podle příjemce





