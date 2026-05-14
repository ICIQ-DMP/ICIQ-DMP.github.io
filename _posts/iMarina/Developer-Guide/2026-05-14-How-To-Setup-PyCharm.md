---
layout: default
title: Guía de instalación para desarrolladores
permalink: /iMarina/Developer-Guide/How-To-Setup-PyCharm
parent: Developer Guide
---

# Guía para configurar PyCharm para iMarina

## Paso 1. Descargar PyCharm 

El IDE que te recomiendo descargar es **Pycharm** ya que creo que es la mejor opción para trabajar con Python y tiene muchas herramientas y plugins interesantes (sobretodo de leer Excels). 

Hay dos versiones disponibles: 

  - PyCharm Community Edition (versión gratuita)
  - PyCharm Professional Edition (versión de pago)

En esta guía instalaremos la versión gratuita. Tienes 2 opciones de descargar el IDE, através del sitio web y de la terminal. Elige la opción de descarga que prefieras.

**(Web).** Descargalo aqui desde la propia web de Pycharm: [IDE](https://www.jetbrains.com/pycharm/download/?section=linux)

**(Terminal).** También puedes descargarlo por terminal: 

```shell
  wget https://download.jetbrains.com/python/pycharm-community-2024.2.tar.gz
```

Como vas a descargar la versión para Linux se te descargará un paquete `.tar.gz`  

## Paso 2. Instalar PyCharm

Extrae el archivo .tar:

```shell
 tar -xzf pycharm-community-2024.2.tar.gz
```

Mueve el archivo a la carpeta `/opt` (carpeta recomendada pero puede ser otra):

```shell
  sudo mv pycharm-community-2024.2 /opt/pycharm
```

Crea un alias (_shortcut_).

```shell
  echo "alias pycharm='/opt/pycharm/bin/pycharm.sh &'" >> ~/.bashrc
  source ~/.bashrc
```

Cierra la terminal y abrela de nuevo para que esté disponible el alias.

Usa el alias para ejecutar PyCharm desde la terminal:

```shell
  pycharm
```
