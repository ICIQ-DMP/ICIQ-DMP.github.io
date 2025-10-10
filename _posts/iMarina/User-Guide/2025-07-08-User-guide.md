---
layout: default
title:  User Guide
permalink: /iMarina/User-Guide/
nav_order: 1
has_children: true
parent: iMarina
---

## iMarina-load (User guide)

### Prerequisites

You need Python 3.12.3 (or higher) version and git installed.
To install them on Ubuntu, run this command:

```shell

sudo apt install python3.12-venv gcc build-essential git -y

```

### Installation

1.Clone repository of iMarina:

git clone https://github.com/ICIQ-DMP/iMarina-load.git

### Enter to folder of iMarina

```shell
 cd iMarina-load
```

2.Initialize a virtual environment (venv)

```shell
 python3 -m venv venv

```

3.Upgrade pip and install dependencies and requirements

```shell
 ./venv/bin/pip install --upgrade pip
 ./venv/bin/pip install -r requirements.txt

```


<!-- TODO -->

