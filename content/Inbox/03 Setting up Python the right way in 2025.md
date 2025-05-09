---
title: Setting up Python the right way in 2025
author: Amandeep Singh Khanna
tags:
  - python
  - python-setup
  - pyenv
  - data-science
  - machine-learning
  - development-environment
  - programming-tools
---
If you’ve been frustrated by Anaconda’s recent licensing changes — making Python usage for commercial and academic purposes a paid affair — you’re not alone. I went on a deep dive to find an alternative Python package and environment management setup that feels just as seamless, but is fully open-source and free from corporate control.

After trying many tools, I found a clean, minimal, and highly customizable workflow using **Pyenv** and **venv**. Here's a complete guide to setting up Python the right way in 2025.

---

# Step 1: Installing Pyenv on Windows

**Pyenv** is a lightweight Python version management tool. Here’s how to install it on a Windows system:

```powershell
Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"
```

### Troubleshooting: PowerShell Script Permissions

If you get a script execution error, update your policy with:

```powershell
Set-ExecutionPolicy RemoteSigned
```

Then re-run the install script. Once installed, restart PowerShell to make the changes take effect.

---

# Step 2: Managing Python Versions with Pyenv

With Pyenv, you can install and switch between multiple Python versions — just like you would with Anaconda.

### 2.1 View Available Python Versions

```powershell
pyenv install --list
```

### 2.2 Install a Specific Python Version

```powershell
pyenv install <version>
```

Replace `<version>` with the version string you found in the list.

### 2.3 List Installed Python Versions

```powershell
pyenv versions
```

### 2.4 Set a Global Default Python Version

```powershell
pyenv global <version>
```

This sets the selected version as your system-wide default.

### 2.5 Verify the Default Python Version

```powershell
python --version
```

This should return the version you set using `pyenv global`.

---

# Step 3: Creating Python Virtual Environments with venv

While Pyenv handles Python versions, it doesn’t manage isolated environments like Conda does. That’s where **`venv`** — Python’s built-in virtual environment tool — comes in.

### Why I Prefer venv

Keeping things simple and vanilla helps avoid toolchain bloat. `venv` is lightweight, built-in, and works across platforms.

### Create a Virtual Environment

```bash
python -m venv myenv
```

Activate it using:

- **Windows (CMD):**
  ```cmd
  myenv\Scripts\activate
  ```
- **PowerShell:**
  ```powershell
  .\myenv\Scripts\Activate.ps1
  ```
- **macOS/Linux:**
  ```bash
  source myenv/bin/activate
  ```

### Deactivate the Virtual Environment

```bash
deactivate
```

---

# Final Thoughts

If you're looking for a professional-grade Python setup in 2025 without corporate entanglements, Pyenv and venv provide a clean, modular alternative to Anaconda.

This stack keeps your development workflow:
- Free and open-source
- Easy to maintain
- Compatible across platforms
- Ideal for data science, machine learning, or software development