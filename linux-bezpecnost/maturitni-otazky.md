Jasně, tady je zjednodušená verze, zaměřená na klíčové body pro studium.

### Rozdíl mezi BIOS a UEFI

*   **BIOS (starý způsob)**
    *   Po spuštění hledá zavaděč operačního systému **vždy na začátku disku** v tzv. MBR (Master Boot Record).
    *   Je pomalejší, má textové rozhraní a nepodporuje disky větší než ~2 TB.

*   **UEFI (moderní způsob)**
    *   Je to v podstatě malý operační systém. Zavaděč hledá jako **soubor ve speciálním adresáři** na disku (tzv. EFI oddíl).
    *   Je mnohem rychlejší, má grafické rozhraní ovladatelné myší, podporuje obrovské disky a bezpečnostní funkci Secure Boot.

| Vlastnost | BIOS | UEFI |
| :--- |:---|:---|
| **Jak najde zavaděč?** | V prvním sektoru disku (MBR) | V souboru na speciálním oddílu |
| **Výhody** | Jednoduchost | Rychlost, bezpečnost, podpora velkých disků |
| **Rozhraní** | Textové | Grafické |

***

### Verzování jader (kernelu) Linuxu

Linuxové jádro **nepoužívá** standardní sémantické verzování (Semver). Jeho schéma `MAJOR.MINOR.PATCH` znamená:

*   `MAJOR` (např. **6**.5.3): Mění se jen zřídka, nemá hlubší technický význam.
*   `MINOR` (např. 6.**5**.3): **Nejdůležitější číslo.** Nová verze přináší **nové funkce**, podporu hardwaru a vylepšení.
*   `PATCH` (např. 6.5.**3**): Označuje vydání s **opravami chyb** a bezpečnostními záplatami. Nepřidává žádné nové funkce.

***

### Co je vanilla verze OS?

Je to **čistá, základní verze** operačního systému tak, jak ji vydal její hlavní vývojář, bez jakýchkoliv úprav od třetích stran (výrobců, distributorů).

*   **Příklad:** Čistý Android přímo od Googlu je "vanilla". Android s úpravami a aplikacemi od Samsungu už není vanilla.

***

### Co jsou LTS verze Linux distribucí?

**LTS** je zkratka pro **Long Term Support** (Dlouhodobá podpora).

*   Jsou to verze distribucí (např. Ubuntu LTS), které dostávají **bezpečnostní aktualizace a opravy po velmi dlouhou dobu** (typicky 5 a více let).
*   Během této doby se nepřidávají nové funkce, což zaručuje maximální **stabilitu**.
*   Používají se hlavně na **serverech** a ve firmách, kde je stabilita klíčová.

***

### Jak vzniká PATH u Linuxu?

`PATH` je proměnná prostředí, která říká systému, **kde má hledat spustitelné programy**. Obsahuje seznam adresářů oddělených dvojtečkou (např. `/bin:/usr/bin`).

*   **Funkce:** Když do terminálu napíšete příkaz `ls`, systém se podívá do adresářů v `PATH`, aby našel a spustil soubor `ls`. Bez `PATH` byste museli psát celou cestu, např. `/bin/ls`.
*   **Vznik:** Cesty se do `PATH` načítají postupně z několika systémových a uživatelských konfiguračních souborů (např. `/etc/profile`, `~/.bashrc`).

***

### Význam runlevelu

Je to **starší koncept**, který definuje **režim běhu systému** – tedy které služby jsou spuštěny.

*   **Příklady:**
    *   **Runlevel 1:** Záchranný režim pro jednoho uživatele.
    *   **Runlevel 3:** Plný režim v textovém rozhraní.
    *   **Runlevel 5:** Plný režim s grafickým rozhraním.
    *   **Runlevel 6:** Restart.

**Dnes:** Moderní systémy používají `systemd` a jeho koncept **cílů (targets)**. Runlevely jsou zachovány jen pro zpětnou kompatibilitu.

***

### Jaký proces vzniká na konci inicializace Linuxového jádra?

Po svém startu spustí jádro úplně první uživatelský proces, kterým je **`init`**.

*   Má vždy **PID (identifikační číslo procesu) 1**.
*   Je "rodičem" všech ostatních procesů v systému.
*   Na moderních distribucích je to proces **`systemd`**, který se stará o spuštění všech dalších služeb.

***

### Co jsou systémová volání a jak jsou využívána v Linuxu?

Je to **způsob, jakým aplikace žádá jádro operačního systému o provedení operace**, ke které sama nemá oprávnění.

*   **Proč?** Programy z bezpečnostních důvodů nemohou přímo pracovat s hardwarem (disk, síťová karta). Systémové volání funguje jako **bezpečná brána**, kdy program "poprosí" jádro, aby danou akci (např. čtení souboru) provedlo za něj.
*   **Příklady použití:** Jakákoliv práce se soubory (`open`, `read`), spouštění procesů (`fork`), síťová komunikace (`socket`). Děje se to neustále na pozadí při běžném používání počítače.
