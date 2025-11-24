# SISCOM Docs

Sitio de documentación para **SISCOM** (Soluciones Integrales en Sistemas Computacionales). Este proyecto contiene documentación técnica, tutoriales y guías de procesos relacionados con administración de sistemas y tecnologías de la información.

## Contenido

El sitio incluye:

- **Tutoriales de Linux**: Guías para instalar Ubuntu Server, configurar Oh My Zsh, usar FreeRDP y diagnosticar almacenamiento
- **Procesos**: Documentación de procedimientos como instalación de Windows
- **Documentación general**: Recursos adicionales sobre sistemas computacionales

## Tecnología

Este sitio está construido con [Docusaurus](https://docusaurus.io/), un generador moderno de sitios web estáticos.

## Installation

```bash
yarn
```

## Local Development

```bash
yarn start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

## Build

```bash
yarn build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

## Deployment

Using SSH:

```bash
USE_SSH=true yarn deploy
```

Not using SSH:

```bash
GIT_USER=<Your GitHub username> yarn deploy
```

If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.

## Sitio en Producción

El sitio está desplegado en GitHub Pages:
- URL: [https://ruizamdev.github.io/siscom-docs/](https://ruizamdev.github.io/siscom-docs/)

## Autor

Desarrollado por Armando Ruiz ([@ruizamdev](https://github.com/ruizamdev))
