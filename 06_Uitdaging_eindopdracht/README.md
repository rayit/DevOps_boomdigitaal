# 06 Uitdaging eindopdracht

## Situatieschets
Je werkt als beginnende DevOps-engineer voor een snelgroeiende start-up. De organisatie levert diverse clouddiensten en verwacht binnen korte tijd op te schalen naar 100 medewerkers. Daarom moet de technische omgeving standaardiseerbaar, schaalbaar en volledig scriptbaar zijn.

## Wat moet er gebeuren?

### 1. Linux-server (Raspberry Pi 5)
Voor elke klant moet automatisch (via Ansible) een gebruiker worden aangemaakt:
- Gebruikersnaam: <klantnaam>
- Groep: cloud_users
- Wachtwoord: klantnaam achterstevoren
- Geen shell-toegang

### 2. MikroTik-router
Voor iedere klant wordt een loopback-interface aangemaakt:
- Omschrijving: customer <naam>
- IP-adres: beginnend bij 10.100.201.11, daarna oplopend

### 3. Fysiek 10-inch rack
De opstelling bestaat uit:
- 1× MikroTik-router
- 2× Raspberry Pi 5
  - Pi #1: Linux-server
  - Pi #2: Ansible-server + Git server

### 4. Klanten
- Stichting BCA
- Regenboog BV
- Vereniging Golf

### 5. Ticketsysteem (Docker)
Installeer osTicket via Docker op een van de Raspberry Pi’s.

## DevOps-Werkwijze
1. YAML-bestanden worden aangepast
2. Commit naar Git
3. Ansible haalt veranderingen binnen
4. Configuraties worden uitgerold

## Voorbereiding – Plan van Aanpak
Maak een schets waarin je je stappen plant voor rackopbouw, Pi-installaties, Ansible, Docker en testen.

## Uitvoering
Voer alles fysiek en technisch uit volgens het plan.

## Terugkijken (Reflectie)
Schrijf over een moment waarop je iets anders of beter had kunnen doen en wat je ervan hebt geleerd.
