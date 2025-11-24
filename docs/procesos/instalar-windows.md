---
sidebar_position: 1
---

# Instalación de Windows

## Proceso para su correcta instalación

_**ADVERTENCIA INICIAL: Antes de hacer cualquier procedimiento, consulta con Gerencia, Mesa de Control, Jefe de Taller, o personal responsable de supervisar los servicios, para confirmar si el servicio requiere RESPALDO DE INFORMACIÓN. Confirma a pesar de que el folio lo indique. Verifica si el equipo a formatear cuenta con programas que requieran respaldo de bases de datos o cualquier otro tipo de información a demás de la información de usuario.**_

### 1. Respaldo de Información

Si confirmaste que el equipo requiere respaldo, respalda las siguientes carpetas de la carpeta del usuario:

- **Descargas**
- **Documentos**
- **Escritorio**
- **Imágenes**
- **Música**
- **OneDrive**
- **Vidos**

Utiliza un formato estandarizado para la carpeta de respaldo:

```text
BACKUP_<FOLIO>_<NOMBRE-DEL-CLIENTE>
```

Ejemplo:

```text
BACKUP_10192_Juan_Perez
```

Confirma si existen más de un usuario en el equipo para respaldarlos también.

**DATO EXTRA**: Respalda la carpeta `user data` si el usuario cuenta con el navegador **Google Chrome**, la puedes encontrar en la siguiente ruta:

```text
C:\Users\<Usuario>\appdata\Local\Google\Chrome\
```

Si no encuentras la carpeta `appdata`, debes de activar la opción de _ver archivos ocultos_ del menu _vista_ del explorador de archivos de windows.

Al final del respaldo verifica si se realizó correctamente, lo puedes verificar rápidamente checando el tamaño del mísmo.

**NOTA**: Para respaldos especiales (bases de datos, etc) leer el apartado específico para el tipo de respaldo.

### 2. Preparación del medio de instalación

Para estandarizar los procedimientos utilizaremos [**Rufus**](https://rufus.ie/es/#download) (Da click para descargar)

Antes de crear la USB de instalación, debes de verificar varias cosas:

1. **Esquema de particiones soportado por el equipo**: Debes de verificar que tipo de esquema de particiones soporta el equipo, existen dos, `MBR` y `GPT`, los equipos más antiguos utilizarán `MBR`, los más nuevos utilizan `GPT`, para verificar es necesario ingresar al BIOS del equipo, ir al apartado de `Boot settings` y si muestra opciones para activar/desactivar secure boot o activar modo legacy, el equipo soporta GPT. Estos equipos que soportan GPT utilizan un tipo de BIOS denominado **UEFI**
2. **Secure Boot y Legacy**: En caso de que el equipo tenga UEFI, hay que desactivar la opción Secure Boot y Legacy para garantizar la correcta instalación.
3. **Arquitectura**: Existen dos arquitecturas 32 y 64 bits. Por default, si el equipo tiene UEFI, su arquitectura será de 64 bits. Caso contrario con los que aún cuentan con BIOS Legacy, ya que pueden ser de 32 o 64 bits,
