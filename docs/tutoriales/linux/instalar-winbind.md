---
sidebar_position: 5
---

# Instalar winbind

```bash
sudo apt update
sudo apt install winbind libnss-winbind
```

Edita el nsswitch:

```bash
sudo nano /etc/nsswitch.conf
```

Busca la línea `hosts:` y modifícala así:

```bash
hosts: files dns wins
Reinicia el servicio:
bashsudo systemctl restart winbind
```
