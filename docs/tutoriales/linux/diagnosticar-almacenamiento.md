---
sidebar_position: 3
---

# Diagnosticar Almacenamiento desde terminal Linux

Despues de descartar puertos y equipo.

## 1. Checar con dmesg

```bash
sudo dmesg | grep -i sdX
```

Se sustituye la X por la letra del disco a revisar

Se buscan errores tipo: “I/O error”, “medium error” o cualquier panic message.

## 2. Probar con smartctl (smartmontools)

```bash
sudo smartctl -i /dev/sdX
sudo smartctl -H /dev/sdX # health check
sudo smartctl -a /dev/sdX # todo el diagnóstico
```

## 3. Checar con hdparm

```bash
sudo hdparm -I /dev/sdX
```
