# Creating a Python Environment

This is a guide on how to set up your computer for Python programming. 
The goal is to enable you to create a python "environment" 
for each of your projects, 
tailored to its requirements.

This guide will be opinionated. If you want to use another method than one described here, my advice would be to use that one method consistently. If you start using multiple methods, you run the risk of becoming XKCD \#1987:

![XKCD #1987](https://imgs.xkcd.com/comics/python_environment.png)

## Contents

## Why Python Environments?

You may think, 
"my computer already has Python on it. Why can't I just use that?"
The problem is that this "system Python" is used by your operating system,
and if you try to customize it something might break.
It's the ability to customize Python that makes it so powerful and so widely useful, so it is highly likely that you will want to start installing additional libraries at some point.
For example, if you want to do data analysis and visualization, you are very early on going to be installing libraries like `pandas` and `matplotlib`.

If you are following a tutorial, 
and at some point it the instructions say something like:

```bash
pip install pandas
```

or

```bash
conda install pandas
```

you will want to make sure you are installing these into a Python environment of your own, separate from system Python.

So, at this point you may start Googling how to go about downloading Python and creating environments. If you do you'll probably find that there's a lot of ways to do this. I will recommend two ways to go about this:

{TODO: or maybe the opposite order?}

1. Installing Anaconda (or miniconda), 
   and managing virtual environments with `conda`.
   {TODO: add what it is and why}
2. Installing Python directly from python.org,
   and creating virtual environments with `venv`.
   {TODO: add what this is and why}

## Installing Anaconda or Miniconda

### Creating and Using a `conda` Environment

## Installing Python from python.org

### Creating and Using a `venv` Virtual Environment
