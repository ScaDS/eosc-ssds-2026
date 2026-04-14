# Prepare Your Laptop

The practical work will be done locally on your laptop. In this section, you will find information on how to prepare your laptop for the training. **Please read everything carefully first and then follow the individual steps.**

## What you need

* Your laptop with internet access
* Administrator rights to install software
* The terminal:
  * **Windows**: CommandPrompt or PowerShell
  * **macOS**/**Linux**: Terminal

## 1. Install uv

* [`uv`](https://docs.astral.sh/uv/) is a fast and convenient tool for Python project and package management
* Install `uv` like described in the [docs](https://docs.astral.sh/uv/getting-started/installation/)
* After installation, close and reopen your terminal
* Then verify in your terminal via

```bash
uv --version
```

## 2. Create a Python virtual environment (venv)

> **NOTE:** If Python is already installed on your system, `uv` will detect and use it without further configuration. However, `uv` can also [install and manage Python versions](https://docs.astral.sh/uv/guides/install-python/), and [automatically installs missing Python](https://docs.astral.sh/uv/guides/install-python/#automatic-python-downloads) versions as needed.

* Create a folder `eosc-ssds-2026`, e.g. on your desktop
* Download the file [`pyproject.toml`](../pyproject.toml), save it in this folder
* Open the terminal and navigate to this folder, e.g.

```bash
cd /path/to/eosc-ssds-2026
```

* In this folder, create a venv using `uv` via

```bash
uv sync
```

* This creates a local virtual environment in `eosc-ssds-2026/.venv` (hidden folder), installs the Python packages defined in `pyproject.toml`, and finally creates a file `uv.lock`.

## 3. Start JupyterLab from the venv

* As a test, start [JupyterLab](https://jupyterlab.readthedocs.io/en/latest/), a web-based interactive environment for computational notebooks
* JupyterLab was already installed via `uv sync` in the venv
* While still in the terminal and in the folder `eosc-ssds-2026`, do

```bash
uv run jupyter lab
```

* Your browser should now open JupyterLab
* If it doesn't, copy the URL displayed in the terminal into your browser  
  (should start with `http://localhost:8888/lab?token=...`)
* To stop JupyterLab, in the terminal press

```text
Ctrl + C
```

> **If everything worked: Congratulations!**  
> You are done and prepared for the training sessions.  
> **If you encounter any problems, please reach out via [email](mailto:matthias.taeschner@uni-leipzig.de?subject=EOSC%20Summer%20School%202026%20Preparation)**
