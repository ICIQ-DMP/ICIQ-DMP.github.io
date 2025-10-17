---
layout: default
title: Developer Guide
permalink: /iMarina/Developer-Guide/
parent: iMarina
has_children: true
---

## 💻 iMarina-load (Developer guide)

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

## 💻🧑‍💻 IDE Setup — PyCharm

### 🧩 1. Download and Install PyCharm
You can install **PyCharm Community Edition** (free) or **Professional Edition** (paid).

For manual installation on Linux using the `.tar.gz` package:

```shell
# Download the latest version from JetBrains community
wget https://download.jetbrains.com/python/pycharm-community-2024.2.tar.gz
```

## Extract the file
```shell
 tar -xzf pycharm-community-2024.2.tar.gz
```

# Move to /opt (recommended for global access)

```shell
sudo mv pycharm-community-2024.2 /opt/pycharm
```
### 2. Create a Shortcut (Alias)

To launch PyCharm quickly from any terminal, create an alias:
```shell
 echo "alias pycharm='/opt/pycharm/bin/pycharm.sh &'" >> ~/.bashrc
 source ~/.bashrc
```
Now you can open it by simply typing:
```shell
 pycharm
```
The alias will remain available even after restarting your terminal.

## 🌿 3. Clone the Project Repository (iMarina-load)

```shell
 cd /home/username/Desktop

 git clone https://github.com/ICIQ-DMP/iMarina-load.git

 cd iMarina-load
```
Then open the project directly in PyCharm:
```shell
 pycharm .
 pycharm
# all forms is correct
```

## 💡 iMarina-load Usage

### Obtaining translations excels
By default, they are read from the `input/ folder` 
but you can change the location of these expected files with the following arguments:

```shell
--imarina-input /path/to/iMarina.xlsx      
--a3-input /path/to/A3.xlsx  
--countries-dict /path/to/countries.xlsx    
--jobs-dict /app/input/Job_Descriptions.xlsx
```

To start the program execute this command with argument --imarina-input:
```shell
./venv/bin/python src/main.py --step build --imarina-input ./input/iMarina.xlsx
```

You can either Download them manually from [Sharepoint](https://iciq.sharepoint.com/sites/digitalitzacio), or you can use the Dockerized `OneDrive` service to sync files from Sharepoint
to your host computer automatically in the background.

### 💻 OneDrive service 
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

### 🐳 Docker basic info
Access the container shell:
```shell
 docker-compose run --rm app sh
```

### 🧪 Testing section

All tests are managed using **pytest** and are located in the `tests/` directory.  
The testing process ensures that all core functionalities work as expected before deployment.  
For detailed testing setup, configuration, and automation through **Docker** or **GitHub Actions**, refer to the [Programming standard](https://iciq-dmp.github.io/iMarina/Developer-Guide/Programming-standard/) document.

More info in [Programming standard](https://iciq-dmp.github.io/iMarina/Developer-Guide/Programming-standard/)




<!-- TODO git branching model -->











