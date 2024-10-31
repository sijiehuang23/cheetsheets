# Set up Python with Anaconda

## Table of Contents
- [Set up Python with Anaconda](#set-up-python-with-anaconda)
  - [Table of Contents](#table-of-contents)
  - [On Windows](#on-windows)
    - [Install Anaconda](#install-anaconda)
    - [Run Python from Conda](#run-python-from-conda)
    - [Appendix: Add VS Code Tile to Anaconda Navigator](#appendix-add-vs-code-tile-to-anaconda-navigator)
  - [On macOS](#on-macos)
  - [Appendix: What is a Virtual Environment in Python?](#appendix-what-is-a-virtual-environment-in-python)

---

## On Windows

### Install Anaconda

**Anaconda** is a distribution of Python (and R) for _scientific computing_, simplifying package management and deployment via **Conda**. [Learn more here][1].

Anaconda installs the latest Python distribution by default ([details here][2]).

Supported Version Details:
- Windows 10 Home Version 21H1 (OS build: 19043.1645)
- Anaconda 2021.11, Conda 4.12.0, Python 3.9.7

### Run Python from Conda

Conda creates a virtual environment for Python. You can start Python from Conda in two ways:

1. **From Anaconda Terminal** ([see guide][3]):
    1. Open *Anaconda Terminal* via the *Navigator* or the Windows _Start_ menu.
    2. List available environments:
        ```bash
        conda info --envs
        ```
    3. Activate an environment:
        ```bash
        conda activate <env-name>
        ```
        The default environment is `base`.
    4. Type `code` to open VS Code from the command line.

2. **Add Conda to System Path** ([see guide][4]):
    1. Go to `Start > Advanced System Settings > Environment Variables`.
    2. Edit `User variables`, adding the following paths:
        ```plaintext
        <installed path>
        <installed path>\Library\bin
        <installed path>\Scripts
        ```
        Place the `Scripts` path last to ensure correct functionality.
    3. Now, VS Code can use the Conda environment’s Python interpreter. Conda will automatically execute:
        ```bash
        conda environment <env-name>
        ```

**Note**: The first method is generally recommended ([see details][4]).

### Appendix: Add VS Code Tile to Anaconda Navigator

If the VS Code tile isn’t visible in Anaconda Navigator, go to:
```
File > Preferences > VS Code Path
```
([more details here][6]).

---

## On macOS

macOS includes Python by default. The current macOS version `Monterey Version 12.3.1` has `Python 3.8.9`.

If Conda is installed, the terminal will show the default environment (`base`). You can check the Python version in this environment with:
```bash
python3 --version
```

To deactivate the `base` environment, use `conda deactivate` ([see details here][7]).

---

## Appendix: What is a Virtual Environment in Python?

A virtual environment is an isolated, self-contained working copy of Python that maintains its own files, directories, and paths. It allows you to manage specific versions of libraries and Python without affecting other projects, making it easy to separate dependencies and avoid conflicts ([more details here][5]).

---

[1]: https://en.wikipedia.org/wiki/Anaconda_(Python_distribution)
[2]: https://stackoverflow.com/questions/30034840/what-are-the-differences-between-conda-and-anaconda
[3]: https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html
[4]: https://stackoverflow.com/questions/44515769/conda-is-not-recognized-as-internal-or-external-command
[5]: https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/
[6]: https://github.com/ContinuumIO/anaconda-issues/issues/11640
[7]: https://apple.stackexchange.com/questions/371727/how-do-i-remove-the-source-base-from-my-terminal
