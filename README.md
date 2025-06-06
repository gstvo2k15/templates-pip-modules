# Offline Installation of Python 3.9 Packages
Basic repo for pip modules downloaded locally.

## Folders

- `orphan_requirements_39/`  
  Contains:
  - httpx
  - authlib
  - tenacity
  - all required dependencies (`anyio`, `httpcore`, `idna`, `cryptography`, `cffi`, `h11`, etc.)

## Steps

1. Transfer the `orphan_requirements_39/` folder to the target machine (Python 3.9).

2. On the target machine, create and activate a Python 3.9 virtual environment:
   ```bash
   python3.9 -m venv venv39
   source venv39/bin/activate

3. Check Python version:

   ```bash
   python --version
   ```
    Expected:
    ```
    Python 3.9.x
    ```

4. Install packages using only local .whl files:

    - If inside the folder:
   ```bash
   cd orphan_requirements_39
   pip install --no-index --find-links=. httpx authlib tenacity
   ```

   - If outside the folder:
    ```bash
   pip install --no-index --find-links=/full/path/to/orphan_requirements_39 httpx authlib tenacity
    ```

**Notes**
```
--no-index disables online sources.

--find-links points pip to the local folder.
```

All .whl files must match Python 3.9 (cp39) and system architecture.

To deactivate the virtual environment:

    deactivate


## Wintel steps with VSCode

  ```powershell
  python.exe -m venv wintel

  Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process

  .\wintel\Scripts\Activate.ps1

  (wintel) PS C:\Users\Trending Pc\Documents\PC-4060Ti\Documentos\Repos\GITHUB\templates-pip-modules> 

  mkdir .\wintel\ansible_packages

  cd wintel

  pip download -d ansible_packages ansible-core ansible-lint checkov pylint shellcheck-py
  ```
