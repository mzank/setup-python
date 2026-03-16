# Python 3 Schummelzettel

![Python](https://img.shields.io/badge/python-3-blue)
![License](https://img.shields.io/badge/license-Apache%202.0-green)


Dies ist mein persönlicher Schummelzettel für Python 3 unter Linux. Andere Plattformen wurden nicht getestet.

---

## Inhaltsverzeichnis

- [Python-Skript ausführen](#python-skript-ausführen)
- [Paketverwaltung mit pip](#paketverwaltung-mit-pip)
- [Virtuelle Umgebung](#virtuelle-umgebung)
- [Jupyter](#jupyter)
- [PyTorch](#pytorch)
- [Lizenz](#lizenz)

---

## Python-Skript ausführen

```bash
# Python-Skript ausführen
python3 <PYTHON.PY-DATEI>

# Einzeiler ausführen, zum Beispiel NumPy
python3 -c "import numpy as np; print(np.__version__)"

# Modul-Aufruf (zum Beispiel pip)
python3 -m pip list
```

---

## Paketverwaltung mit pip

```bash
# pip installieren
sudo apt install python3-pip

# pip selbst aktualisieren
python3 -m pip install --upgrade pip
# oder einfacher:
pip install --upgrade pip

# Paket installieren
pip install <PAKET>

# Alle Pakete aus requirements.txt installieren
pip install -r requirements.txt

# Installierte Pakete anzeigen
pip list

# Paket aktualisieren (zum Beispiel NumPy)
pip install --upgrade numpy

# Paket deinstallieren
pip uninstall <PAKET>

# Unbenötigte Abhängigkeiten entfernen:
# Mittels
# pip uninstall <PAKET>
# werden Pakete, welche nur wegen Abhängigkeit installiert wurden,
# NICHT mitentfernt.
# Verwende daher pip-autoremove:
pip install pip-autoremove
pip-autoremove <PAKET>

# pip Cache leeren
pip cache purge

# Installation eines Pakets in einen Ordner, 
# wobei Abhängigkeiten aufgelöst werden.
# Die installierten Pakete landen nicht im Standard-Python-Pfad site-packages
# und stören daher die Standard-Python-Umgebung nicht. 
pip install -t <ORDNER> <PAKETE>

# Das Python‑Projekt im aktuellen Verzeichnis (der Punkt .) 
# im Entwickler‑Modus installieren.
# Voraussetzung: setup.py oder pyproject.toml
pip install -e .

# Umgebungsvariable setzen, damit meinOrdner für Python verfügbar ist:
export PYTHONPATH="$HOME/meinOrdner:$PYTHONPATH"

# Sauberer mit Bash-Parameterexpansion 
# (Hänge :$PYTHONPATH nur an, wenn PYTHONPATH bereits existiert.):
export PYTHONPATH="$HOME/meinOrdner${PYTHONPATH:+:$PYTHONPATH}"
```

---

## Virtuelle Umgebung

```bash
# Virtuelle Umgebung erzeugen
python3 -m venv /path/to/directory

# Aktivieren
source /path/to/directory/bin/activate

# Pakete installieren in virtueller Umgebung mittels:
pip install <PAKETE>

# Deaktivieren
deactivate
```

---


## Jupyter

Website: [Jupyter](https://jupyter.org/)

```bash
# Jupyter Notebook installieren/aktualisieren
pip install --upgrade notebook

# Notebook starten
jupyter notebook

# JupyterLab installieren/aktualisieren
pip install --upgrade jupyterlab

# JupyterLab starten
jupyter lab
```

### Zugriff von Rechner A auf Rechner B über SSH

Um von einem Rechner A per SSH auf JupyterLab auf einem Rechner B
zuzugreifen, verwendet man SSH-Port-Forwarding (Tunneling):

```bash
# Auf Rechner B
jupyter lab --no-browser --port=8888
```
Ausgabe enthält Zeile mit Token:
http://localhost:8888/lab?token=abc123...

```bash
# Auf Rechner A (SSH-Port-Forwarding)
ssh -N -L 8888:localhost:8888 benutzername@IP_VON_RECHNER_B
```

Auf Rechner A im Browser öffnen:
http://localhost:8888
Token von oben eingeben oder man kopiert gleich obigen Link inkl. Token.

---


## PyTorch

Website: [PyTorch](https://pytorch.org/)

```bash
# Installation inklusive CUDA
pip install torch torchvision torchaudio

# Installation für der CPU-Version, siehe
# https://pytorch.org/get-started/locally/ :
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu

```

---

## Lizenz

Dieses Projekt ist unter der Apache License 2.0 lizenziert. Siehe [LICENSE](LICENSE) für Details.

Weitere Informationen zur Lizenz finden Sie hier: https://www.apache.org/licenses/LICENSE-2.0

---
