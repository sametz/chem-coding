# Creating a Python Environment

This is a guide on how to set up your computer for Python programming. 
The goal is to enable you to create a python "environment" 
for each of your projects, 
tailored to its requirements.

This guide will be opinionated. 
If you want to use another method than one described here, 
my advice would be to use that one method consistently. 
If you start using multiple methods, 
you run the risk of becoming XKCD \#1987:

![XKCD #1987](https://imgs.xkcd.com/comics/python_environment.png)

## Contents

## Why Python Environments?

You may think, 
"my computer already has Python on it. Why can't I just use that?"
The problem is that this "system Python" is used by your operating system,
and if you try to customize it something might break.
It's the ability to customize Python 
that makes it so powerful and so widely useful, 
so it is highly likely that you will want 
to start installing additional libraries at some point.
For example, if you want to do data analysis and visualization, 
you are very early on going to be installing libraries 
such as `pandas` and `matplotlib`.

If you are following a tutorial, 
and at some point it the instructions say something like:

```bash
pip install pandas
```

or

```bash
conda install pandas
```

you will want to make sure you are installing these 
into a Python environment of your own, separate from system Python.

So, at this point you may start Googling how to go about downloading Python 
and creating environments. 
If you do, you'll probably find that there's a lot of ways to do this. 
I will recommend two ways to go about this:

1. Installing Anaconda (or miniconda), 
   and managing virtual environments with `conda`.
   This is probably the best solution for people, 
   particularly those with scientific interests, to get started. 
   If you're interested in programming for data analysis and visualization, 
   you can also obtain R this way.
   An Anaconda installation also makes it easy to start using Jupyter Notebooks,
   which are a great way to start learning Python interactively. 
2. Installing Python directly from python.org,
   and creating virtual environments with `venv`.
   This is a minimalist approach.

## Installing Anaconda or Miniconda

   A full Anaconda installs a lot of stuff on your computer 
   that you may not need. 
   However, if you're just starting out in programming,
   this is the easiest option.
   If hard drive space is a concern, you can install miniconda instead. 
   [This guide](https://docs.anaconda.com/free/anaconda/getting-started/distro-or-miniconda/) 
   on the Anaconda web site summarizes how to choose between the two.

   [Caltech's Be/Bi103 course](https://bebi103a.github.io/lessons/00/index.html) 
   (Introduction to Data Analysis in the Biological Sciences) 
   has great guides for setting up a python environment via Anaconda. 
   The key steps are summarized below.

   1. Download the 
      [Anaconda](https://www.anaconda.com/download/) 
      or [miniconda](https://docs.conda.io/en/latest/miniconda.html) 
      installer and run it.

      - choose "Install for Me Only" if you are given that option
      - you may be prompted to install a (free) JetBrains IDE 
        such as PyCharm or DataSpell. 
        Unless you know you want to use it, skip this—
        you can always install it later if you want.
   2. Open a command-line interface (CLI). 
      {TODO: check on windows if you need to use the anaconda cli}
      If you are not familiar with the CLI,
      note that a command prompt ending in "`$`" 
      precedes the cursor where you start typing.
      Its exact text will be specific to your computer 
      and where you opened the CLI from.
      However, your prompt should include "`(base)`", which indicates which conda environment you're currently using (here, the default "base" environment). 
      For the terminal commands below, 
      "`(environmentname)$`" represents the command prompt 
      (and is not part of the commands you are entering in the CLI).
   3. Update your base conda installation and environment. 
      It is a good idea to run the following commands 
      not only after the initial installation, 
      but every few weeks-to-months. 
      {TODO: footnote warning on what can happen if this is postponed too long}
      ```bash
      (base)$ conda update conda
      ```
      Follow the prompts to update conda itself, and then:
      ```bash
      (base)$ conda update --all
      ```
      and follow the prompts to update all the installed libraries.

### Creating and Using a `conda` Environment

Although you can work from the base conda environment, 
for your own projects you will want to create an isolated environment.
You'll be able to install only what you need for that project,
and you can specify the versions of all the libraries to avoid conflicts.
It is very easy to create environments with conda, and switch between environments as needed

A detailed guide can be found on the [Anaconda website](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html). To get started, here are the most useful commands:

- `conda create` is used to create a new environment.
  For example, if you were taking the Be/Bi 103 course and wanted to create an environment for it, you could do the following:
  ```bash
  (base)$ conda create --name bebi103
  ```
  However, that course requires that Python 3.9 is used, to make sure that all their code runs as originally written. Most likely, when you downloaded conda, you chose the most recent python for the base conda environment.
  If you know you need a specific python version, include it when you create the environment:
  ```bash
  (base)$ conda create --name bebi103 python=3.9
  ```
  You can also add specific packages that you want via this command, but it's not necessary. Installing packages is covered in the next section.
- `conda env list` will list all your environments, e.g.:
  ```bash
  (base)$ conda env list
   # conda environments:
   #
   base                  *  /Users/myname/opt/anaconda3
   bebi103                  /Users/myname/opt/anaconda3/envs/bebi103
  ```
  The asterisk indicates the current active environment, which is still `base`.
  Note the location of your new environment inside the `/envs` folder.
  Every conda environment you create will be in a subfolder of `/envs`.
- `conda activate` is used to switch to another environment, e.g.:
  ```bash
  (base)$ conda activate bebi103
  (bebi103)$
  ```
- `conda list` will list all the packages installed in the active environment.

### Installing Packages Into Your Environment

## Installing Python from python.org

### Creating and Using a `venv` Virtual Environment

### Installing Packages Into Your Environment
## Other Options

- On macOS, homebrew can be used to install Python. 
  However, the author thinks that combining homebrew python installation 
  with other methods such as (Ana)conda can lead to XKCD #1987.
- Power users, especially those writing python packages, 
  can look at pyenv or asdf. 
  The author strongly recommends 
  [*Publishing Python Packages*](https://www.manning.com/books/publishing-python-packages)
  by Dane Hillard to see an example 
  of a publishing toolset that includes asdf.
