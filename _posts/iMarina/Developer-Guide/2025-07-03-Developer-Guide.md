---
layout: default
title: Developer Guide
permalink: /iMarina/Developer-Guide/
parent: iMarina
has_children: true
---

## iMarina-load (Developer guide)

### Prerequisites

You need `Python 3.12.3` (or higher) version and git installed.
To install them on Ubuntu, run this command:

```shell

sudo apt install python3.12-venv gcc build-essential git -y

```

### Installation

1.Clone repository of iMarina:

```shell
 git clone https://github.com/ICIQ-DMP/iMarina-load.git
```

### Enter to folder of iMarina

```shell
 cd iMarina-load
```

2.Initialize a virtual environment `(venv)`

```shell
 python3 -m venv venv

```

3.Upgrade pip and install dependencies and requirements

```shell
 ./venv/bin/pip install --upgrade pip
 ./venv/bin/pip install -r requirements.txt

```


# Usage

### Obtaining translations excels
By default, they are read from the `input/ folder` 
but you can change the location of these expected files with the following arguments:


--imarina-input /path/to/iMarina.xlsx      
--a3-input /path/to/A3.xlsx  
--countries-dict /path/to/countries.xlsx    
--jobs-dict /app/input/Job_Descriptions.xlsx


To start the program execute this command with argument --imarina-input:
```shell

./venv/bin/python src/main.py --step build --imarina-input ./input/iMarina.xlsx

```

You can either Download them manually from [Sharepoint](https://iciq.sharepoint.com/sites/digitalitzacio), or you can use the Dockerized `OneDrive` service to sync files from Sharepoint
to your host computer automatically in the background.

### OneDrive service 
The program will display a link and ask you to authenticate and paste the answered URL into the terminal.

```shell
  cd services/onedrive
  bash run.sh
```


After following the steps, OneDrive will be syncing the folder   
Institutional `Strengthening/_Projects/iMarina_load_automation/input`  
from Sharepoint into `services/onedrive/data`. 

Add or change the necessary arguments to read from this new source, 
instead of **input/**, so that data consumed by the program is always updated.

You can leave OneDrive running so that the files are always in sync.

### Docker basic info
Access the container shell:
```shell

 docker-compose run --rm app sh

```
More technician info of Docker in section [Programming standard](https://iciq-dmp.github.io/iMarina/Developer-Guide/Programming-standard/)










