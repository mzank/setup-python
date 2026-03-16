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

# Einzeiler ausführen, z. B. NumPy
python3 -c "import numpy as np; print(np.__version__)"

# Modul-Aufruf (z. B. pip)
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

# Paket aktualisieren (zB NumPy)
pip install --upgrade numpy

# Paket deinstallieren
pip uninstall <PAKET>

# Unbenötigte Abhängigkeiten entfernen
pip install pip-autoremove
pip-autoremove <PAKET>

# pip Cache leeren
pip cache purge

# Paket in Ordner installieren (unabhängig vom Standard-Python-Pfad)
pip install -t <ORDNER> <PAKETE>

# Python-Projekt im Entwickler-Modus installieren
# Voraussetzung: setup.py oder pyproject.toml
pip install -e .

# PYTHONPATH setzen
export PYTHONPATH="$HOME/meinOrdner:$PYTHONPATH"

# Sauberer mit Bash-Parameterexpansion
export PYTHONPATH="$HOME/meinOrdner${PYTHONPATH:+:$PYTHONPATH}"
```

---

## Virtuelle Umgebung

```bash
# Virtuelle Umgebung erzeugen
python3 -m venv /path/to/directory

# Aktivieren
source /path/to/directory/bin/activate

# Pakete installieren
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

```bash
# Auf Rechner B
jupyter lab --no-browser --port=8888

# Auf Rechner A (SSH-Port-Forwarding)
ssh -N -L 8888:localhost:8888 benutzername@IP_VON_RECHNER_B
```

Auf Rechner A im Browser öffnen:
http://localhost:8888

---


## PyTorch

Website: [PyTorch](https://pytorch.org/)

```bash
# Installation inklusive CUDA
pip install torch torchvision torchaudio

# Installation der CPU-Version
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
```

---

## Lizenz

Dieses Projekt ist unter der Apache License 2.0 lizenziert. Siehe [LICENSE](LICENSE) für Details.

Weitere Informationen zur Lizenz finden Sie hier: https://www.apache.org/licenses/LICENSE-2.0

---