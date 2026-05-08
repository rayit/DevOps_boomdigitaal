
# 4. osTicket container uitrollen

## Doel
Een ticketsysteem (osTicket) uitrollen met Docker.

## Uitvoeren

- Docker Compose installeren
- osTicket container starten
- MariaDB container configureren
- Poort 8080 publiceren

---

## Voorbeeld toegang

```text
http://10.10.30.10:8080
```

---

## Bewijs

```bash
docker compose ps
```

### 1. Vereisten

Zorg dat de volgende software al is geïnstalleerd:

- Docker
- Docker Compose
- Linux server of Raspberry Pi
- Werkende internetverbinding
- Poort 8080 vrij

Controleer installatie:

```bash
docker --version
docker compose version
```

---

### 2. Projectmap aanmaken

Maak een map voor osTicket:

```bash
mkdir osticket-docker
cd osticket-docker
```

---

### 3. Docker Compose bestand maken

Maak het bestand aan:

```bash
nano docker-compose.yml
```

Plak de volgende configuratie:

```yaml
version: '3.8'

services:
  db:
    image: mariadb:10.6
    container_name: osticket-db
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: rootpassword
      MYSQL_DATABASE: osticket
      MYSQL_USER: osticket
      MYSQL_PASSWORD: osticketpass
    volumes:
      - db_data:/var/lib/mysql

  osticket:
    image: tiredofit/osticket
    container_name: osticket-app
    restart: always
    ports:
      - "8080:80"
    environment:
      DB_HOST: db
      DB_NAME: osticket
      DB_USER: osticket
      DB_PASS: osticketpass
    depends_on:
      - db

volumes:
  db_data:
```

---

### 4. Containers starten

Start de omgeving:

```bash
docker compose up -d
```

---

### 5. Controleren of alles draait

```bash
docker ps
```

Je moet zien:
- osticket-app
- osticket-db

---

### 6. Webinterface openen

Open in browser:

```
http://<IP-ADRES>:8080
```

Voorbeeld:

```
http://10.10.30.10:8080
```

---

### 7. Installatie via webinterface

Vul de database gegevens in:

- Database: osticket
- Username: osticket
- Password: osticketpass
- Host: db

---

### 8. Admin account aanmaken

Maak een admin account:

- Naam: admin
- Email: admin@local
- Wachtwoord: kies sterk wachtwoord

---

### 9. Testen

Maak een test ticket aan:

- Titel: Test ticket
- Bericht: Eerste test van osTicket

Controleer:
- Ticket wordt aangemaakt
- Dashboard werkt
- Database verbinding werkt

---

Maak screenshots van:

- Werkende osTicket webinterface
- Draaiende containers

---

---

# Reflectie

Beantwoord de volgende vragen:

1. Wat ging goed tijdens de configuratie?
2. Welke problemen ben je tegengekomen?
3. Hoe heb je deze problemen opgelost?
4. Wat zou je de volgende keer anders doen?
5. Wat heb je geleerd over Linux, Docker en automatisering?
