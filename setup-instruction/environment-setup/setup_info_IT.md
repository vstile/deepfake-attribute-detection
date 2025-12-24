# Guida all’installazione dell’ambiente Python su Mac

Questa guida ti aiuterà a configurare correttamente l’ambiente Python così come utilizzato da me per il progetto, sia con pyenv che con Anaconda.  
**Presupposto:** hai i file `requirements.txt` e `environment.yml`e questi sono posizionati nella cartella "home" del tuo Mac (tipicamente `~/tuonome`).

---

## 1. Installa gli strumenti di sviluppo Xcode

Apri il Terminale e digita:

```xcode-select --install
```
Segui le istruzioni a schermo per completare l’installazione.

---

## 2. Installa Homebrew

Homebrew è il gestore di pacchetti consigliato per Mac.  
Nel Terminale, esegui:

```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Al termine, aggiorna Homebrew:

```brew update
```

---

## 3. (Opzionale ma consigliato) Installa pyenv per gestire versioni di Python

### Installa pyenv:

```brew install pyenv
```

### Aggiungi pyenv al tuo profilo della shell (ad esempio, per zsh):

```echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init --path)"' >> ~/.zshrc
source ~/.zshrc
```

### Installa Python 3.11.5 con pyenv:
```pyenv install 3.11.5
```

### Imposta Python 3.11.5 come versione globale:

```pyenv global 3.11.5
```

### Verifica la versione:

```python --version
```

Dovresti vedere: `Python 3.11.5`

---

## 4. (Alternativa a pyenv) Installa l’ultima versione di Python 3

Se non vuoi usare pyenv, puoi installare Python direttamente:
- Vai su [https://www.python.org/downloads/](https://www.python.org/downloads/)
- Scarica e installa l’ultima versione di Python 3 per macOS.
- Verifica l’installazione con:

  ```python3 --version
  ```

---

## 5. Crea e attiva un ambiente virtuale Python

Nel Terminale, nella cartella del progetto:

```python3 -m venv venv
source venv/bin/activate
```

---

## 6. Installa le dipendenze dal file requirements.txt

Con l’ambiente virtuale attivo:

```pip install -r requirements.txt
```

---

## 7. Istruzioni per installare miniconda 

Queste istruzioni per la riga di comando ti faranno impostare rapidamente con l'ultimo programma di installazione di Miniconda. Seguire i passaggi per il tuo sistema per scaricare e installare Miniconda, quindi seguire i passaggi per verificare l'installazione sopra per verificare l'installazione di Miniconda.

Istruzioni per Apple Silicon

Esegui i seguenti quattro comandi per scaricare e installare l'ultimo programma di installazione MacOS per l'architettura Chip prescelta. Riga per riga, questi comandi:
1. Crea una nuova directory denominata "Miniconda3" nella tua home directory.
2. Scarica lo script di installazione Miniconda MacOS per l'architettura Chip prescelta e salva lo script come Miniconda.sh nella directory Miniconda3.
3. Eseguire lo script di installazione di Miniconda.sh in modalità silenziosa usando Bash.
4. Rimuovere il file di script di installazione di Miniconda.sh al termine dell'installazione.

```mkdir -p ~/miniconda3
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh -o ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh
```

Dopo aver installato, chiudere e riaprire l'applicazione del terminale o aggiornarlo eseguendo il seguente comando:
```source ~/miniconda3/bin/activate
```

Quindi, inizializza Conda su tutte le shell disponibili eseguendo il comando seguente:
```conda init --all
```

Riavvia la shell o esegui

```exec zsh
```

Questa guida è un estratto tratto da: https://www.anaconda.com/docs/getting-started/miniconda/install#macos-2

## 8. (Dopo aver installato miniconda) Crea e attiva l’ambiente da environment.yml

### Crea l’ambiente:
```conda env create -f environment.yml
```

### Attiva l’ambiente:
```conda activate condaenv
```
*(Sostituisci `condaenv` eventualmente con un nome personalizzato che puoi specificare in `environment.yml`)*

---

## 9. Pronto per lavorare!

Ora il tuo ambiente Python è configurato e puoi iniziare a lavorare sul progetto.

---

**Nota:**  
- Usa sempre l’ambiente virtuale o conda attivo quando lavori al progetto.
- Se hai dubbi, chiedi al responsabile del progetto o consulta la documentazione ufficiale di Python, pyenv, Homebrew o Anaconda.

**Vittorio Ing. Stile | PhD Fellow | Docente | Consulente**

- Ingegnere (albo sez. A, settore Industriale, n°23605)
- Manager dell’Innovazione (elenco Unioncamere, n°755)
- Dott. Magistrale in Ingegneria Gestionale
- Dott. in Ingegneria Industriale

Contatti:

- Email personale e per pubblicazioni: <vittoriostile@gmail.com>
- Email istituzionale: <vittorio.stile@studenti.unimercatorum.it>

Seguimi: <https://linktr.ee/vstile> 