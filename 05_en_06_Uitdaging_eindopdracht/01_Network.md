# 01 Netwerk

> Zorg voor een uplink

> Maak je documentatie in github
> TIP: maak een fork van deze github omgeving

---

# 1. Basisconfiguratie MikroTik

## Uitvoeren

- Router resetten:

```bash
/system reset-configuration no-defaults=yes
```

- Hostname instellen
- Tijdzone configureren
- NTP instellen
- Sterk admin-wachtwoord instellen
- Nieuwe beheeruser aanmaken

---

## Bewijs
Maak screenshots van:

```bash
/system identity print
/system clock print
/user print
```

---

# 2. VLAN-configuratie

## VLAN’s aanmaken

| VLAN | Functie | Subnet |
|---|---|---|
| 10 | Management | 10.10.10.0/24 |
| 20 | Servers | 10.10.20.0/24 |
| 30 | Raspberry Pi | 10.10.30.0/24 |
| 40 | Clients | 10.10.40.0/24 |
| 99 | Transit | 10.10.99.0/24 |

---

## Uitvoeren

- Bridge aanmaken
- VLAN filtering activeren
- Tagged/untagged poorten configureren
- VLAN interfaces maken
- IP-adressen toewijzen

---

## Bewijs
Voer onderstaande commando’s uit en maak screenshots van de uitvoer:

```bash
/interface vlan print
/ip address print
/interface bridge vlan print
```

---

# 3. DHCP & Routing

## Uitvoeren

- DHCP pools aanmaken
- DHCP servers configureren
- Default routes instellen
- DNS configureren

---

## Bewijs

```bash
/ip dhcp-server print
/ip route print
/ip dns print
```

---

# 4. Firewall & NAT

## Uitvoeren

- Basis firewall rules configureren
- WinBox beperken tot management VLAN
- SSH-toegang beperken
- NAT configureren

---

## Voorbeelden

```bash
/ip firewall filter
/ip firewall nat
```

---

## Bewijs

- Screenshots van firewallregels
- Screenshot/test van werkende internetverbinding

---

# 5. Loopback interfaces voor klanten

## Klanten

- Stichting BCA
- Regenboog BV
- Vereniging Golf

---

## Uitvoeren

Maak loopback interfaces aan met onderstaande beschrijvingen:

| Klant | Beschrijving |
|---|---|
| Stichting BCA | customer stichting_bca |
| Regenboog BV | customer regenboog_bv |
| Vereniging Golf | customer vereniging_golf |

---

## IP-adressen

| Klant | IP-adres |
|---|---|
| Stichting BCA | 10.100.201.11 |
| Regenboog BV | 10.100.201.12 |
| Vereniging Golf | 10.100.201.13 |

---

## Bewijs

Maak screenshots van:

```bash
/interface print
/ip address print
```

---

# 6. Configuratiebeheer

## Uitvoeren

- MikroTik exports maken
- Configuratie uploaden naar GitLab

---

## Bewijs

Voer onderstaande export-opdracht uit:

```bash
/export file=backup
```

Maak een screenshot van:

- de aangemaakte backupbestanden
- de GitLab repository met de geüploade configuraties

---

# Eindcontrole

Controleer of onderstaande onderdelen correct werken:

| Onderdeel | Controle |
|---|---|
| VLAN’s | Correcte communicatie tussen netwerken |
| DHCP | Clients ontvangen juiste IP-configuratie |
| Routing | Internet en VLAN-routing werken |
| Firewall | Ongewenste toegang geblokkeerd |
| NAT | Internettoegang actief |
| Loopbacks | Correct aangemaakt |
| GitLab | Configuraties succesvol opgeslagen |

---

# Reflectie

Beantwoord de volgende vragen:

1. Wat ging goed tijdens de configuratie?
2. Welke problemen ben je tegengekomen?
3. Hoe heb je deze problemen opgelost?
4. Wat zou je de volgende keer anders doen?
5. Wat heb je geleerd over netwerkbeheer en MikroTik?
