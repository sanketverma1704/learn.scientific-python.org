---
title: Install
---

Before installing Scientific Python libraries, you need to have Python
itself installed. There are two, largely equivalent, ways of doing
that, and we describe both below.

If you have a working version of Python on your system already (check
by running `python` at the terminal), you can skip to "Segment 1: Set up a virtual environment".

## Segment 1: Python.org

This is the official Python distribution, which uses the `pip` package manager. `pip` installs packages from Python Package Index, or [PyPI](https://pypi.org/) for short.

Download the installer from https://www.python.org/downloads/.

### Set up a virtual environment

A virtual environment is a workspace into which you can install Python
libraries, separate from what is being used by your operating system.

Here, we create a new virtual environment in a directory `science` (you can use whichever name you prefer!):

```
python -m venv science
```

Start using it by activating it as follows:

```
source science/bin/activate
```

You are now ready to install Scientific Python packages using `pip`! For example:

```
pip install ipython numpy scipy
```

You should now be able to run IPython (the interactive Python shell) to try out NumPy:

```
$ ipython

In [1]: import numpy as np

In [2]: np.linspace(0, 10, 5)
Out[2]: array([ 0. ,  2.5,  5. ,  7.5, 10. ])
```

Remember to re-activate your environment every time you open a new terminal, using:

```
source science/bin/activate
```

## Segment 2: Miniforge

Miniforge is a small Python distribution based around the conda
package manager, and installs packages from the community repository
conda-forge.

Conda is a bit different from Python's `pip` package manager in that
it can, in addition to Python libraries, also install compilers,
libraries, and so forth.

Download the latest version [from
GitHub](https://github.com/conda-forge/miniforge#miniforge3).

Back up your shell init (`~/.zshrc`, `~/.bashrc`, etc.), since the installer will modify these.
Run the installer (typically, `sh Miniforge3-Linux-x86_64.sh` at the terminal), and when it asks you "Do you wish the installer to
initialize Miniforge3 by running conda init?" enter "yes".

If you don't like the changes made to your shell init, restore it from backup,
and enable `miniforge` with `source ~/miniforge3/bin/activate`.

### Set up a virtual environment

A virtual environment is a workspace into which you can install Python
libraries, separate from what is being used by your operating system.

Create a new virtual environment called `science` (or name it whatever
you like!):

```
conda create -n science
```

Switch to the new environment (you need to do this every time you want
to use it):

```
conda activate science
```

You are now ready to install Scientific Python packages using `conda`!
For example:

```
conda install ipython numpy scipy
```

You should now be able to run IPython (the interactive Python shell) to try out NumPy:

```
$ ipython

In [1]: import numpy as np

In [2]: np.linspace(0, 10, 5)
Out[2]: array([ 0. ,  2.5,  5. ,  7.5, 10. ])
```

Remember to re-activate your environment every time you open a new terminal:

```
conda activate science
```
