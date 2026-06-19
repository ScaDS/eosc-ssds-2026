# Practical Exercises

How-To for redoing the exercises on your own laptop after the training.

## Download and unpack the notebooks

- Download [`sessions_download.zip`](https://raw.githubusercontent.com/ScaDS/eosc-ssds-2026/main/preparation/sessions_download.zip) (right-click > "Save Link As") - see explaination for **Pitfall** below!
- Unpack it. You get a folder `sessions_download/` with:
  - `pyproject.toml`
  - `secrets`
  - `session1/`
  - `session2/`

## Create the virtual environment (venv)

- Open the terminal and navigate into the unpacked folder

```bash
cd /path/to/sessions_download
```

- Create the venv and install all packages

```bash
uv sync
```

- This creates a local `.venv` folder and a `uv.lock` file inside `sessions_download/`

## Fill your `secrets` file

- Open the file `secrets` in a text editor and fill in your values:
  - `ENDPOINT_URL` - the LLM API endpoint URL (`https://...`)
  - `OPENAI_API_KEY` - your API key (`sk-...`)
  - `ZENODO_SANDBOX_TOKEN` - Personal access token for Zenodo Sandbox
- Leave `SYSTEM_PROMPT_DATA_STEWARD` as provided

> **NOTE:** Treat the `secrets` file like a password - never commit or share it.

## Start JupyterLab with your secrets

- From the `sessions_download/` folder, start JupyterLab so it loads `secrets` as environment variables

```bash
uv run --env-file secrets jupyter lab
```

- Work through the notebooks under `session1/notebooks/` and `session2/notebooks/`
- To stop JupyterLab, press `Ctrl + C` in the terminal

## Pitfall: cloud-synced and network folders

> **IMPORTANT:** Do **not** place `sessions_download/` inside any synced folder (OneDrive, Dropbox, Google Drive, iCloud), or other remote network drives.

On many managed laptops these locations apply stricter execution restrictions and constant file syncing, which can:

- block running the Python interpreter/scripts installed in `.venv` (so `uv sync`, `uv run`, `uv add` fails or hangs), and
- corrupt the environment as files get locked or re-synced mid-install.

Use a plain **local** folder outside any synced or networked path instead, e.g. `C:\Users\<you>\eosc-ssds-2026` (Windows) or `~/eosc-ssds-2026` (macOS/Linux).
