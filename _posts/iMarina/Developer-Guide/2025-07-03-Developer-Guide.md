---
layout: default
title: Developer Guide
permalink: /iMarina/Developer-Guide/
parent: iMarina
has_children: true
---

  - [Guía de instalación](/iMarina/Developer-Guide/How-To-Install)
  - [Guía de configuración de PyCharm](/iMarina/Developer-Guide/How-To-Setup-PyCharm)
  - [Guía de uso de iMarina](/iMarina/Developer-Guide/How-To-Usage-iMarina)
  - [Reference](/iMarina/Developer-Guide/Reference)  

   
<!-- TODO -->




### Obtaining translations excels 
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


## 🧭 Git Branching Model

The project uses a **two-branch model** based on Git best practices:

- **master** → stable, production-ready branch  
- **develop** → main branch for integrating and testing new features

### 🌱 Workflow

1. Pull the latest version of `develop`:
```shell
   git checkout develop
   git pull origin develop
```

2. Create a new branch for your feature or fix:
```shell
 git checkout -b feature/my-feature
```
3. After finishing your changes:
```shell
 git add .
 git commit -m "feat: add ......"
```
4. Push your branch to GitHub:
```shell
  git push --set-upstream origin feature/my-feature
```
5. Open a **Pull Request (PR)** (if necessary) on GitHub to merge into `develop`.
6. Once tested and approved, `develop` can be merged into `master` for release.


### 🛠️ Useful Commands

- **List all branches**
```shell
   git branch -a
```
- **Switch between branches**
```shell
   git checkout branch_name   
```

- **Delete a local branch**
```shell
   git branch -d branch_name
#or
   git branch -D branch_name
```
- **Visualize branch history**
```shell
   gitk --all &
```

- **Discard local changes**
```shell
    git reset --hard
```

- **Update your branch with the latest develop**
```shell
   git pull origin develop --no-ff
```


More info in [Programming standard](https://iciq-dmp.github.io/iMarina/Developer-Guide/Programming-standard/)




<!-- TODO  -->

















Additions from the readme of iMarina load
---


#### Initialize `PYTHONPATH`
This initialization adds the project path to Python's module search path, so that it can find our tests.

##### With `pytest.ini`
To use the library correctly and find our tests, we must create the following file and place it in the same root 
directory as `Desktop/iMarina-load`. If it is already present 

Create the `pytest.ini` file with the following content if not present:

``` ini
[pytest]
pythonpath = .
```

Pytest uses the `pytest.ini` file to define global settings.
The option `pythonpath = .`
tells pytest to add the project root folder (.) to `PYTHONPATH`.

The test file must be in the project root (same folder as `src/` and `tests/`).


##### With environment variable
To ensure that Python sees the project root, you can manually add it to `PYTHONPATH` running this command:

```shell
export PYTHONPATH=$PYTHONPATH:/home/your_usersystem/Desktop/iMarina-load
```

---


### Creating tests
Test functions are written that begin with `test_`  in files with the same
name.

#### Test Folder
Folder test for example `test_main.py`.

All the tests that we implement must be stored in this folder called `tests`.

#### Folder Location
And the tests folder must be located in the **root directory** of your project:
`Marina-load/tests.`

In the file called `test_main.py`, you must first import the classes needed for the test
For example:

```python
from src.main import Researcher, is_visitor
```

