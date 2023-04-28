I was going to test installing Python straight from python.org, 
as [recommended by Brian Okken](https://pythontest.com/python/installing-python-3-11/)[^1].
However, Linux is trickier (e.g. compiling from python.org download).

Instead, I'm following the setup described in *Publishing Python Packages*
by Dane Hillard. 

[^1]: See also: [PythonBytes clip on his article](https://www.youtube.com/live/9wU19yAB2mM?feature=share&t=1112).

## Install asdf

`asdf` does what `pyenv` does but for more than Python.

1. Check https://github.com/asdf-vm/asdf/tags and note the latest version. 
   At the time of writing, it was v0.11.3.

2. Clone the repo to `~/.asdf`:
   ```bash
   $ git clone https://github.com/asdf-vm/asdf.git \
    $HOME/.asdf --branch v0.11.3 
   ``` 
3. Edit the correct bash configuration file.
   Hillard says to edit `$HOME/.bash_profile`. 
   Mint has `.bashrc` and `.profile`
   (plus `.bash_logout`). 
   Editing .profile according to his directions failed.
   So, I
   [read the ASDF docs](https://asdf-vm.com/guide/getting-started.html#_3-install-asdf), 
   and then added this to `.bashrc`:
   ```bash
   . "$HOME/.asdf/asdf.sh"
   . "$HOME/.asdf/completions/asdf.bash"
   ```
   This worked!

## Use `asdf` to install Python

1. Make sure you have the required dependencies.
   The [asdf documentation](https://asdf-vm.com/guide/getting-started.html) 
   says that `git` and `curl` are required.
   The [asdf-python documentation](https://github.com/asdf-community/asdf-python) directs you to the dependencies for [pyenv](https://github.com/pyenv/pyenv/wiki#suggested-build-environment),
   which says to install the following:
   ```bash
   sudo apt update; sudo apt install build-essential libssl-dev zlib1g-dev \
   libbz2-dev libreadline-dev libsqlite3-dev curl \
   libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
   ```
2. Install the python plugin:
  ```bash
  asdf plugin add python
  ```
3. List the available python versions:
  ```bash
  asdf list all python
  ```
4. Select the versions that you want to install.
   For now, I want 3.8.16, 3.9.16, 3.10.11, and 3.11.3.
   ```
   asdf install python 3.8.16
   ```
   etc.

