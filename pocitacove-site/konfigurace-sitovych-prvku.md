Jistě, zde je přehledně zformátovaný tahák na základní konfiguraci Cisco zařízení.

### Základní nastavení Routeru

*   **Přepnutí do privilegovaného režimu:** `enable`
*   **Vstup do globální konfigurace:** `config terminal`
*   **Pojmenování zařízení:** `hostname <jmeno_routeru>`
*   **Vypnutí DNS překladu neznámých příkazů:** `no ip domain-lookup`
*   **Zašifrování hesel v konfiguraci:** `service password-encryption`
*   **Nastavení hesla pro `enable` režim:** `enable password <heslo>`

***

### Základní nastavení SSH

*   **Vytvoření lokálního uživatele:** `username <jmeno> password <heslo>`
*   **Nastavení domény (nutné pro klíč):** `ip domain-name <mojedomena.local>`
*   **Vygenerování šifrovacího klíče:** `crypto key generate rsa`
    *   Poté zadejte délku klíče, pro SSH v2 to je `1024`.
*   **Vynucení moderní verze SSH:** `ip ssh version 2`

***

### Aktivace SSH pro vzdálený přístup

*   **Výběr linek pro vzdálený přístup:** `line vty 0 15`
*   **Povolení přihlášení pouze přes SSH:** `transport input ssh`
*   **Nastavení ověření přes lokální uživatele:** `login local`
*   **Automatické odhlášení při nečinnosti:** `exec-timeout <minuty> <sekundy>`
    *   Např. `exec-timeout 15 0` pro odhlášení po 15 minutách.
*   **Návrat do globální konfigurace:** `exit`

***

### Nastavení IP na Routeru

*   **Zobrazení souhrnu rozhraní:** `show ip interface brief`
*   **Výběr konkrétního rozhraní:** `interface <typ/číslo>` (např. `interface GigabitEthernet0/1`)
*   **Nastavení IP adresy a masky:** `ip address <ip_adresa> <maska_podsítě>`
*   **Aktivace (zapnutí) rozhraní:** `no shutdown`

**Statická cesta (routing):**
*   **Nastavení cesty do jiné sítě:** `ip route <cílová_síť> <maska_sítě> <ip_dalšího_routeru>`

***

### Nastavení IP na Switchi (pro správu)

*   **Výběr virtuálního rozhraní pro správu:** `interface Vlan1`
*   **Nastavení IP adresy a masky:** `ip address <ip_adresa> <maska_podsítě>`
*   **Aktivace rozhraní:** `no shutdown`
*   **Nastavení výchozí brány (důležité!):** `ip default-gateway <ip_adresa_routeru>`
    *   Tento příkaz se zadává v globálním konfiguračním režimu, ne v rozhraní
