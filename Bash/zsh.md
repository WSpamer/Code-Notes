# ZSH

## 1) Plugins

### 1.1) Direnv

Install

```bash
    # Run
    brew install direnv
    # Update .zshrc
    # In ~/.zshrc
    eval "$(direnv hook zsh)"
```

Project
Step 1: Create an .envrc file in your project

```bash
    touch .envrc
    direnv allow .
```

```bash
    # In ~/my_project/.envrc
    # Example
    alias build="npm run build"
    alias test="npm test"
```

Step 2: Allow .envrc

```bash
    # In ~/my_project/.envrc
    # Example
    alias build="npm run build"
    alias test="npm test"
```

## 2) Dotfiles Management

### 2.1) Aliases

```bash
    alias dotfiles='/usr/bin/git --git-dir=$HOME/dotfiles_osx/ --work-tree=$HOME'
    alias rzenv='source $HOME/.zshenv'
    alias rzrc='source $XDG_CONFIG_HOME/zsh/.zshrc'
```
