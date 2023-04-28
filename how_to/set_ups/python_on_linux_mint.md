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
3. Edit `$HOME/.bash_profile`: 
   Mint has `.bashrc` and `.profile`
   (plus `.bash_logout`). 
   Not clear, but opting to add the edit to `.profile` instead of creating `.bash_profile`.
   ```bash
   if [ -f $HOME/.asdf/asdf.sh ]; then
       source $HOME/.asdf/asdf.sh
   fi
   ```
   After restarting the shell, `asdf --version` failed.
   [Read the ASDF docs](https://asdf-vm.com/guide/getting-started.html#_3-install-asdf), 
   and trying instead adding this to `.bashrc`:
   ```bash
   . "$HOME/.asdf/asdf.sh"
   . "$HOME/.asdf/completions/asdf.bash"
   ```
   This worked!
