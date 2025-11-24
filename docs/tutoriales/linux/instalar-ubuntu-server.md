---
sidebar_position: 4
---

# Install && Configure Ubuntu Server 24.04 LTS

## Instalar Ubuntu Server 24.04 LTS

## Configurar Ubuntu Server 24.04 LTS

A continuación se desglosan las instalaciones y configuraciones post-instalación

1. Actualizar repositorios y actualizar programas

```bash
sudo apt update && sudo apt upgrade -y
```

1. Reiniciar sistema si el kernel o librerias criticas se actualizaron

```bash
[ -f /var/run/reboot-required ] && sudo reboot
```

1. Agregar puertos al firewall

```bash
sudo ufw allow OpenSSH
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw enable
```

1. Configurar zona horaria

```bash
sudo timedatectl list-timezones | grep Mexico
sudo timedatectl set-timezone America/Mexico_City
sudo timedatectl set-ntp true
```

1. Instalar herramientas esenciales

```bash
sudo apt install htop curl wget unzip git net-tools software-properties-common -y
```

1. Habilitar actualizaciones automaticas de seguridad

```bash
sudo apt install unattended-upgrades
sudo dpkg-reconfigure --priority=low unattended-upgrades
```

1. Instalar entorno gráfico

```bash
sudo apt install xfce4 xfce4-goodies xfce4-session -y
sudo apt install lightdm lightdm-gtk-greeter lightdm-gtk-greeter-settings -y
sudo dpkg-reconfigure lightdm
sudo systemctl set-default graphical.target
```

1. Configurar acceso remoto

```bash
sudo apt install xrdp -y
sudo systemctl enable --now xrdp
```

Hasta este punto necesitamos un reinicio si queremos ingresar desde interfaz gráfica

```bash
sudo reboot now
```

1. Cambiar de DHCP ip a Static ip

```bash
ls /etc/netplan
# Dependiendo del nombre del fichero de configuración lo abrimos con vim o nano,
# Pero antes hacemos un backup del fichero
sudo cp /etc/netplan/50-cloud-init.yaml /etc/netplan/50-cloud-init.yaml.backup
sudo vim /etc/netplan/50-cloud-init.yaml
```

Aquí modificamos y agregamos lo necesario

Configuración actual con ip dinámica:

```
network:
	version: 2
	ethernets:
		eth0:
			dhcp4: true
```

Configuración modificada con ip estática:

```
network:
	version: 2
	ethernets:
		eth0:
			dhcp4: false
			addresses:
				- 192.168.1.120/24
			routes:
				- to: default
					via: 192.168.1.1
			nameservers:
				addresses: [1.1.1.1, 1.0.0.1]
```

Al guardar aplicamos los cambios con:

```bash
sudo netplan apply
```
