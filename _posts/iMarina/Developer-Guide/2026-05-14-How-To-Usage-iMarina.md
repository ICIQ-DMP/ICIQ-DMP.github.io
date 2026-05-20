---
layout: default
title: Guía de como usar iMarina
permalink: /iMarina/Developer-Guide/How-To-Usage-iMarina
parent: Developer Guide
---

# Guia de uso de iMarina para el Desarrollador

El objetivo de esta guía es mostrar como se usa correctamente iMarina.

## Obtención traducción de los Excels

Por defecto se leen estos Excels  desde la carpeta `input/ folder` pero puedes cambiar la ubicación de estos archivos utilizando los siguientes argumentos.

```shell
 --imarina-input /path/to/iMarina.xlsx      
 --a3-input /path/to/A3.xlsx  
 --countries-dict /path/to/countries.xlsx    
 --jobs-dict /app/input/Job_Descriptions.xlsx
```

Puedes descargar manualmente los Excels necesarios desde el [Sharepoint(carpeta input)](https://iciq.sharepoint.com/sites/digitalitzacio-InstitutionalStrengthening).

También puedes utilizar el `OneDrive` en el contenedor de  **Docker** para sincronizar los archivos del SharePoint en tu máquina de forma automática en segundo plano.

## Ejecutar main

Para iniciar el programa **main** debes ejecutar el siguiente comando con el argumento `--imarina-input`

```shell
   ./venv/bin/python -m imarina --step build --imarina-input ./input/iMarina.xlsx
```
