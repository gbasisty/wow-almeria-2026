---
name: upload-site
description: Sube el sitio WOW Almería al servidor FTP de producción
disable-model-invocation: true
allowed-tools: Bash(curl *)
---

# Upload Site — WOW Almería 2026

Sube todos los archivos del directorio `html/` al servidor de producción por FTP.

## Conexión FTP
- **Host:** 185.18.197.22
- **Usuario:** wow26
- **Contraseña:** CornerstoneWow26!
- **Directorio remoto:** /wow/

## Proceso

1. Buscar todos los archivos dentro de `html/` en el proyecto
2. Subir cada archivo en paralelo manteniendo la estructura de directorios
3. Verificar el contenido remoto tras la subida

## Subida de archivos

Para cada archivo encontrado en `html/`, subirlo con curl preservando la ruta relativa:

```bash
curl -s --ftp-pasv --ftp-create-dirs -T "<archivo_local>" "ftp://185.18.197.22/wow/<ruta_relativa>/" --user "wow26:CornerstoneWow26!"
```

Ejecutar las subidas en paralelo cuando sea posible para optimizar el tiempo.

## Verificación

Listar el directorio remoto para confirmar:

```bash
curl -s --list-only --ftp-pasv "ftp://185.18.197.22/wow/" --user "wow26:CornerstoneWow26!"
```
