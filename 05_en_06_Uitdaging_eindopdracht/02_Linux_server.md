# 02 Linux server

## Doel
Configureer de Raspberry Pi 5 als Linux-server en automatiseert gebruikersbeheer met Ansible, Git en Docker.

# 1. Raspberry Pi 5 installeren

## Uitvoeren

- Raspberry Pi OS Lite installeren
- SSH activeren
- Hostname instellen
- Vast IP-adres configureren
- Systeem updaten

---

## Configuratie

| Instelling | Waarde |
|---|---|
| Hostname | pi-01 |
| IP-adres | 10.10.30.10 |
| VLAN | 30 |
| OS | Raspberry Pi OS Lite 64-bit |

---

## Bewijs

Voer onderstaande commando’s uit en maak screenshots van de uitvoer:

```bash
hostnamectl
ip a
ssh pi@10.10.30.10
```

---

# 2. Basis Linux hardening

## Uitvoeren

- Nieuwe beheeruser aanmaken
- SSH-keys configureren
- PasswordAuthentication uitschakelen
- Firewall (UFW) configureren
- Automatische updates activeren

---

## Bewijs

```bash
sudo systemctl status ssh
sudo ufw status
cat /etc/ssh/sshd_config
```

Maak screenshots van:

- Werkende SSH login met sleutel
- Firewall status
- SSH-configuratie

---

# Reflectie

Beantwoord de volgende vragen:

1. Wat ging goed tijdens de configuratie?
2. Welke problemen ben je tegengekomen?
3. Hoe heb je deze problemen opgelost?
4. Wat zou je de volgende keer anders doen?
5. Wat heb je geleerd over Linux, Docker en automatisering?
