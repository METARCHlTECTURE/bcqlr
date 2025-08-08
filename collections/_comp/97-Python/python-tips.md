---
title: Python Tips
categories: Python
---


## Error Installing by pip: externally-managed-environment

When you use pip to install Python packages, you may encounter an ‘`externally-managed-environment`’ error. This error occurs because your Python environment is “externally managed” by a package manager, which prevents direct use of pip for system-wide installations to avoid conflicts or issues.

```shell
× This environment is externally managed
╰─> To install Python packages system-wide, try 'pacman -S
    python-xyz', where xyz is the package you are trying to
    install.

    If you wish to install a non-Arch-packaged Python package,
    create a virtual environment using 'python -m venv path/to/venv'.
    Then use path/to/venv/bin/python and path/to/venv/bin/pip.

    If you wish to install a non-Arch packaged Python application,
    it may be easiest to use 'pipx install xyz', which will manage a
    virtual environment for you. Make sure you have python-pipx
    installed via pacman.
```

Error: externally-managed-environment occurs when a package manager is managing a Python environment, which prevents direct use of pip. 

**Solution 1: Using a virtual environment**

```shell
python3 -m venv ~/py_envs
source ~/py_envs/bin/activate
python3 -m pip install xyz
```

**Solution 2: Force Install**

pip install xyz --break-system-packages.

## Bad Network Connection with pip

Change mirror:
```shell
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```