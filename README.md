# Best practices (my pov) for setting up Python dev environment using vscode

This is my pov to compile some of the best practices on setting up a new Python environment for local development. This also includes integration with Visual Studio Code, however, it’s not necessary abd it will work with other IDE u like to work with.

I am using MAC and this is what the below is based on.

[![macOS](https://svgshare.com/i/ZjP.svg)](https://svgshare.com/i/ZjP.svg) 

---

general cleanup first

```shell
brew update && brew upgrade
```

## 1. Install `pyenv`


pyenv lets you easily switch between multiple versions of Python. It's simple, unobtrusive, and follows the UNIX tradition of single-purpose tools that do one thing well.


```shell
brew install pyenv && brew pyenv-virtualenv
```
the following needs to be added to the `zshrc`
```bash
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"
eval "$(pyenv virtualenv-init -)"
```

 ![](https://img.shields.io/static/v1?label=&message=NOTE!&color=red) Having `binutils` installed with brew, this will block `pyenv` Python version installation. I had to remove it installed the required Python versions and added it later to keep the set-up brewing clean.

 ```bash
 brew uninstall --ignore-dependencies binutils
 ```