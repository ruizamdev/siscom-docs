---
sidebar_position: 2
---

# FreeRDP Cheatsheet

## 🍖 Chuleta de FreeRDP (Ubuntu/Linux)

**Comando base:**

```bash
xfreerdp /v:SERVIDOR /u:USUARIO /p:CONTRASEÑA
```

---

### 🎛️ Parámetros útiles

**Resolución y pantallas**

- `/size:1920x1080` → fuerza resolución.
- `/f` → pantalla completa (full screen).
- `/multimon` → usa varios monitores.
- `/dynamic-resolution` → ajusta resolución al redimensionar ventana.

**Audio y video**

- `/sound:sys:pulse` → redirige audio (con PulseAudio).
- `/microphone:sys:pulse` → redirige micrófono.
- `/video` → habilita redirección de video.

**Archivos y periféricos**

- `/drive:home,/home/tu_usuario` → comparte tu carpeta local como disco en Windows.
- `/printer` → redirige impresoras locales.
- `/usb:id,dev:XXXX:YYYY` → redirige un USB específico (requiere permisos extras).

**Clipboard (copiar/pegar)**

- `/clipboard` → habilita copiar/pegar entre Windows y Linux.

**Certificados y seguridad**

- `/cert-ignore` → ignora certificados no válidos (práctico en LAN).
- `/sec:nla` → fuerza autenticación con NLA.
- `/sec:rdp` → si hay problemas de compatibilidad, fuerza modo RDP simple.

**Performance**

- `/compression` → habilita compresión (reduce consumo de red).
- `/gfx` → usa aceleración gráfica (si el servidor lo soporta).
- `/network:lan` → ajusta el perfil de red (valores: `modem`, `broadband`, `lan`).

**Sesiones y administración**

- `/admin` → conecta a la sesión de administrador (ideal para servidores Windows).
- `/log-level:DEBUG` → muestra detalles de debug (útil en pruebas).

---

### 🥩 Ejemplo completo

```bash
xfreerdp /v:192.168.1.50 /u:Administrator /p:SuperPass123 \
/f /multimon /sound:sys:pulse /clipboard \
/drive:home,/home/armando /dynamic-resolution /admin /cert-ignore
```

Eso te mete a un servidor Windows, en pantalla completa, con monitores múltiples, audio redirigido, copiar/pegar, tu home como disco, y acceso de admin.
