# Guide to Installing a Python Environment on Mac

This guide will help you correctly set up the Python environment as I used it for the project, both with pyenv and with Anaconda.  
**Assumption:** you have the files `requirements.txt` and `environment.yml`, and they are located in your Mac “home” folder (typically `~/yourname`).

---

## 1. Install Xcode Command Line Tools

Open Terminal and type:

```xcode-select --install
```
Follow the on-screen instructions to complete the installation.

---

## 2. Install Homebrew

Homebrew is the recommended package manager for Mac.
In Terminal, run:

```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

When finished, update Homebrew:

```brew update
```

---

## 3. (Optional but recommended) Install pyenv to manage Python versions

### Install pyenv:

```brew install pyenv
```

### Add pyenv to your shell profile (for example, for zsh):

```echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init --path)"' >> ~/.zshrc
source ~/.zshrc
```

### Install Python 3.11.5 with pyenv:
```pyenv install 3.11.5
```

### Set Python 3.11.5 as the global version:

```pyenv global 3.11.5
```

### Verify the version:

```python --version
```

You should see: `Python 3.11.5`

---

## 4. (Alternative to pyenv) Install the latest version of Python 3

If you do not want to use pyenv, you can install Python directly:
- Go to [https://www.python.org/downloads/](https://www.python.org/downloads/)
- Download and install the latest Python 3 version for macOS.
- Verify the installation with:

  ```python3 --version
  ```

---

## 5. Create and activate a Python virtual environment

In Terminal, inside your project folder:

```python3 -m venv venv
source venv/bin/activate
```

---

## 6. Install dependencies from requirements.txt

With the virtual environment active:

```pip install -r requirements.txt
```

---

## 7. Instructions to install Miniconda 

These command-line instructions will quickly set you up with the latest Miniconda installer. Follow the steps for your system to download and install Miniconda, then follow the steps above to verify the Miniconda installation.

**Instructions for Apple Silicon**

Run the following four commands to download and install the latest macOS Miniconda installer for your chosen chip architecture. Line by line, these commands:
1. Create a new directory called `Miniconda3` in your home directory.
2. Download the macOS Miniconda installation script for your chosen chip architecture and save it as `Miniconda.sh` in the `Miniconda3` directory.
3. Eseguire lo script di installazione di `Miniconda.sh` in modalità silenziosa usando Bash.
4. Remove the `Miniconda.sh` installation script file once the installation is complete.

```mkdir -p ~/miniconda3
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh -o ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh
```

After installing, close and reopen the Terminal application, or refresh it by running:
```source ~/miniconda3/bin/activate
```

Then, initialize Conda for all available shells by running:
```conda init --all
```

Restart your shell or run:

```exec zsh
```

This guide is excerpted from: https://www.anaconda.com/docs/getting-started/miniconda/install#macos-2

## 8. (After installing Miniconda) Create and activate the environment from environment.yml

### Create the environment:
```conda env create -f environment.yml
```

### Activate the environment:
```conda activate condaenv
```
*(replace `condaenv` with a custom name if you specified one in `environment.yml`)*

---

## 9. Ready to work!

Your Python environment is now configured and you can start working on the project.

---

**Notes:**  
- Always keep the virtual environment or Conda environment active when working on the project.
- If you have doubts, ask the project lead or consult the official documentation for Python, pyenv, Homebrew, or Anaconda.

**Vittorio Ing. Stile | PhD Fellow | Professor | Consultant**

- Ingegnere (albo sez. A, settore Industriale, n°23605)
- Manager dell’Innovazione (elenco Unioncamere, n°755)
- M.Sc. in Ingegneria Gestionale
- B.Sc. in Ingegneria Industriale

Contacts:

- Primary email: <vittoriostile@gmail.com>
- Work email: <vittorio.stile@studenti.unimercatorum.it>

Follow me: <https://linktr.ee/vstile> 

---

**Privacy and reuse policy**

* This repository contains code and guide.
* **Reuse is permitted provided that you cite the author and this work.**
* Recommended license: **Creative Commons Attribution 4.0 International (CC BY 4.0)**. You are free to share and adapt the material for any purpose, even commercially, as long as appropriate credit is given, a link to the license is provided, and any changes are indicated.

Short attribution text you can include in derivative works:
```
This material reuses data and methods from:
Stile, V. (2025). “AI-generated Deepfakes: A Study on Attribute-Aware Detection, Bias Analysis, and Generalisation” Ph.D. dissertation, Universitas Mercatorum, Roma.
© 2025 Vittorio Stile - Licensed under CC BY 4.0.
```