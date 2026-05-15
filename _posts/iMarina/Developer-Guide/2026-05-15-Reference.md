---
layout: default
title: Guía de como usar iMarina
permalink: /iMarina/Developer-Guide/Reference
parent: Developer Guide
---


# Referencia API

El objetivo de esta referencia es documentar tanto argumentos de la **CLI** como definir los **Excels** utilizados y su estructura para el proyecto
con sus respectivas carpetas `INPUT` y `OUTPUT`.
Como deben ser estos `Excels` y porque se guardan en las carpetas del SharePoint.


##  CLI 
La **Command Line Interface** es muy importante en el proyecto de iMarina.
Estos son los comandos a ejecutar:

```shell
# argumentos a ejecutar en la CLI
 venv/bin/python3 -m imarina download
 venv/bin/python3 -m imarina build
 venv/bin/python3 -m imarina upload
```

### Download

El comando `Download` descarga todos los Excels de la carpeta input del SharePoint.

### Build

El comando `Build`  une los Excels de A3 y de iMarina y genera el último Excel de upload (con la fecha en la cuál se ha generado).

### Upload

El comando `Upload` sube a la carpeta Output el Excel generado tras ejecutar el comando Build.


## INPUT
En la carpeta Input del SharePoint se encuentran los Excels de A3 y de iMarina.

### A3 Excel

Es el Excel que nos facilita `RRHH`, contiene la información de los `Researchers` en los siguientes 19 campos:

> A continuación  muestro el orden de los campos que debe seguir el Excel de principio a fin.

* Codigo empleado
* Codigo Centro
* Nombre
* Primer Apellido
* Segundo Apellido
* NIF
* Sexo
* Nacionalidad
* Pais Nacimiento
* Email
* Puesto de trabajo
* Grupo Unidad
* Fecha Antigüedad
* ORCID
* Fecha Inicio Contrato
* Fecha Fin Contrato
* Fecha Inicio Prórroga
* Fecha Fin Prórroga
* Fecha de baja en compañía


Hay `Researchers` que tendrán algunos campos vacíos **sobretodo fechas** pero no afecta en absoluto a gestión de los datos.


### iMarina Excel
Este Excel contiene los datos actualizados de los `Researchers` y muchos más campos que en A3:

> Orden correcto de los campos del iMarina Excel
* Code
* Nombre
* Primer Apellido
* Segundo Apellido
* signature
* signature_custom
* DNI/NIE/NIF
* Fecha de Nacimiento
* Sexo
* Pais de Nacimiento
* Ciudad de Nacimiento
* Región/Comunidad de Nacimiento
* Correo Electrónico
* Web Personal
* Tipo de Contrato
* Tipo de Adscripción 
* Categoria Investigadora / Docente 
* Dedicación
* Fecha de Inicio
* Fecha de Fin
* id_1 
* Tipo de Entidad
* País de la Entidad
* Región de la Entidad
* Provincia de la Entidad
* Ciudad de la Entidad 
* Codigo Postal de la Entidad 
* Dirección de la Entidad
* Web de la Entidad 
* Tipo de Entidad Nivel 2
* Entidad (Nivel 2)
* id_2
* Entidad (Nivel 3)
* id_3
* ORCID
* ResearchID
* AuthorID(Scopus)
* DialnetID
* Google Scholar ID
* Telefono de Contacto


También hay campos completamente vacios ya que no es  obligatorio rellenarlos todos 
(no todos los Researchers tienen todos los datos anotados).



## OUTPUT
Después de la fusión del `Excel` de A3 y el de iMarina, esta unión genera el último Excel de Upload que se guarda en la carpeta Output del SharePoint.

Esto ha unido campos que no estaban A3 junto a los campos de iMarina, pero con los datos totalmente curados y actualizados.

Excel final de Upload (en la carpeta OutPut)

<!-- TODO-->



