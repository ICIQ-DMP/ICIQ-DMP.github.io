---
layout: default
title:  User Guide
permalink: /iMarina/User-Guide/
nav_order: 1
has_children: true
parent: iMarina
---

## iMarina-load (User guide)
# Cómo generar automáticamente el excel UPLOAD

> El objetivo de esta guía es mostrar los pasos para generar automáticamente el excel UPLOAD usando la automatización de iMarina. 

**Prerequisitos:**

  - Excel de A3
  - Excel de iMarina

**Pasos a seguir:**

  1. Subir los excels de A3 e iMarina a la carpeta `input` en el SharePoint: [ruta carpeta input](https://iciq.sharepoint.com/sites/digitalitzacio-InstitutionalStrengthening/Shared%20Documents/Forms/AllItems.aspx?id=%2Fsites%2Fdigitalitzacio%2DInstitutionalStrengthening%2FShared%20Documents%2FInstitutional%20Strengthening%2F%5FProjects%2FiMarina%5Fload%5Fautomation%2Finput&viewid=0ae5c925%2D86eb%2D4f0c%2D8620%2D7baf35c6fe1b&csf=1&siteid=%7BD8419D28%2DB330%2D4B4A%2D82A1%2D8DD1A7303017%7D&webid=%7B3ADA0D28%2DBA74%2D4BED%2DB8B1%2DDD7C3F30C7FD%7D&uniqueid=%7BC3B97637%2D2C3B%2D499C%2DABDB%2D2474D96DD0D2%7D&FolderCTID=0x012000886FD1202D2C7D48825926C584FEE25F) 
  2. Abre el formulario: [link formulario](https://iciq.sharepoint.com/sites/digitalitzacio-InstitutionalStrengthening/_layouts/15/listforms.aspx?cid=ZjU0YTQwMmEtMGYxMi00MTNiLTkyYWYtZmZlYTQ3OGQ2MWM0&nav=MzU3MGYzZjktM2Y4MS00NzliLWE1YWUtMDQ2YjZiNjllMDg4)
  3. Rellena el formulario.
  4. Envía el formulario.
  5. Pasado unos minutos, recibirás un correo en tu cuenta de Outlook con el resultado de la automatización.

**Si la automatización es exitosa:**

  1. Recibirás un email comunicando que se ha completado con éxito.
  2. El fichero `UPLOAD` estará disponible en el SharePoint en esta ruta:
     [ruta carpeta output](https://iciq.sharepoint.com/sites/digitalitzacio-InstitutionalStrengthening/Shared%20Documents/Forms/AllItems.aspx?id=%2Fsites%2Fdigitalitzacio%2DInstitutionalStrengthening%2FShared%20Documents%2FInstitutional%20Strengthening%2F%5FProjects%2FiMarina%5Fload%5Fautomation%2Foutput&viewid=0ae5c925%2D86eb%2D4f0c%2D8620%2D7baf35c6fe1b&csf=1&siteid=%7BD8419D28%2DB330%2D4B4A%2D82A1%2D8DD1A7303017%7D&webid=%7B3ADA0D28%2DBA74%2D4BED%2DB8B1%2DDD7C3F30C7FD%7D&uniqueid=%7BC3B97637%2D2C3B%2D499C%2DABDB%2D2474D96DD0D2%7D&FolderCTID=0x012000886FD1202D2C7D48825926C584FEE25F)

**Si la automatización falla:**

  1. Recibirás un email comunicando que ha ocurrido un error.
  2. Contacta con la unidad de digitalización por correo: digitalitzacio@iciq.es 

**Nota:** El emisor del correo será <imarina@iciq.es> y <digitalitzacio@iciq.es> el correo operativo del departamento para resolver posibles incidencias con el workflow.




# Formulario de generación automática del excel Upload iMarina

> Esta referencia documenta el formulario para hacer la petición con iMarina.

El formulario tiene 4 campos que el usuario debe rellenar: 

  - `TITLE`
  - `A3 Excel Link`
  - `iMarina Excel Link`
  - `Observacions`

## TITLE

El `TITLE` es una descripción breve de la solicitud que identifique quién la ha realizado. Es un campo opcional.

**Ejemplo:** "Solicitud Mario Piqué 2026-05-11"

## A3 Excel Link

El `A3 Excel Link` es la ruta donde está guardado el Excel A3. La ruta de archivo debe ser dentro de la carpeta `input` del SharePoint. Es un campo obligatorio.

**Ejemplo:** `https://iciq.sharepoint.com/:x:/s/digitalitzacio-InstitutionalStrengthening/IQDtCYVY1CALS4BIXy-xVXWuAct7PC88Spq_OJ6urLknMrg?e=AYADWd`

## iMarina Excel Link

El `iMarina Excel Link` es la ruta donde está guadado el excel de iMarina. La ruta de archivo debe ser dentro de la carpeta `input` del SharePoint. Es un campo obligatorio.

**Ejemplo:** `https://iciq.sharepoint.com/:x:/s/digitalitzacio-InstitutionalStrengthening/IQBJq7Md39aySZNG1mbl0CLpASXiB7uNGgxtUhZFt8s4BN4?e=aowmWp`

## Observaciones

El campo de `Observaciones` puede ser rellenado libremente con dudas, comentarios o notas que el usuario quiera dejar registrados para la Unidad de Digitalización del ICIQ. Es un campo opcional.

**Ejemplo:** "El excel de A3 no está actualizado a este mes."




















<!-- TODO -->

