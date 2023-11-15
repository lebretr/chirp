# Python 3 Developer Environment Setup

## Windows
### Install Python

    1. Download and install from python.org. At the time of this writing, "Python 3.10.8" is recommended. 
    During install note these options:
        Choose Add python.exe to PATH
        Choose Disable path length limit
    2. In Windows settings, search "Manage app execution aliases" and:
        Disable App Installer: python.exe
        Disable App Installer: python3.exe
        Disable App Installer: python3.7.exe

### Install Git

    1. Download and install from git-scm.org. During installation take the defaults except for:
        Configuring the line ending conversions: choose Checkout as-is, commit Unix-style line endings

### Configure Git

From a command line:

    git config --global user.name "FIRST_NAME LAST_NAME"
    git config --global user.email "MY_NAME@example.com"
    Optional, if you want to set an editor: git config --global core.editor "PATH TO EDITOR"

### Clone the chirp git repository (master branch)

From a command line:

    C:\Users\{user}\Documents> git clone https://github.com/kk7ds/chirp
    C:\Users\{user}\Documents> cd chirp

### Install the python dependencies

    python3 -m pip install -r requirements.txt
    python3 -m pip install tox

### Run chirp

From inside the chirp git repo, type this to run chirp from source:

    chirpwx.py

### Optional, but recommended: Install GitHub CLI

Via winget: winget install --id GitHub.cli or manually from github.com

    Note: {user} as shown in paths above is the logged in Windows user
    Note: The steps above were done on Windows 10 Pro, version 22H2k


## VS Code

launch.json
``` json
{
    // Utilisez IntelliSense pour en savoir plus sur les attributs possibles.
    // Pointez pour afficher la description des attributs existants.
    // Pour plus d'informations, visitez : https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Python : fichier chirpwx.py",
            "type": "python",
            "request": "launch",
            "program": "chirpwx.py",
            "console": "integratedTerminal",
            "justMyCode": true,
            "cwd": "${workspaceFolder}"
        },
        {
            "name": "Python : fichier actif",
            "type": "python",
            "request": "launch",
            "program": "${file}",
            "console": "integratedTerminal",
            "justMyCode": true
        }
    ]
}
```