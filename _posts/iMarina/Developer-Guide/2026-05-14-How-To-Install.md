---
layout: default
title: Guía de instalación para desarrolladores
permalink: /iMarina/Developer-Guide/How-To-Install
parent: Developer Guide
---

# Guia de instalación para desarrolladores

El objetivo de esta guía es mostrarte cómo instalar iMarina como desarrollador.

## Prerrequisitos

Para instalar el proyecto de iMarina, necesita tener lo siguente:

  - Python `3.12.3` (o superior)
  - Git

Para instalar ambas tecnologías puedes hacerlo ejecutando el siguiente comando en tu terminal de Linux:

```shell
  sudo apt install python3.12-venv gcc build-essential git -y
```

## Instalación 

```shell
  # Clona el repositorio de iMarina
  git clone https://github.com/ICIQ-DMP/imarina.git 
  
  # Entra en la carpeta del repositorio
  cd imarina
  
  # Crea un entorno virtual de python
  python3 -m venv venv
  
  # Activa el entorno virtual
  source venv/bin/activate
  
  # Actualiza pip
  pip install --upgrade pip
  
  # Instala las dependencias
  pip install -r requirements.txt
```
