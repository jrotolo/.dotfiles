# Dotfiles
My dotfiles for bootstrapping new environments

## To Setup a New Machine

Running the following will clone the dotfiles repo to a temporary directory in order to sync with any default dotfiles
that already exist on the current system.

```
git clone --separate-git-dir=$HOME/.dotfiles https://github.com/jrotolo/.dotfiles.git tmpdotfiles
rsync --recursive --verbose --exclude '.git' tmpdotfiles/ $HOME/
rm -r tmpdotfiles
```

## Managing Dotfiles

The following alias located in our .zshrc allows us to manage our dotfiles with git from anywhere
```
alias dotfiles="$(which git) --git-dir=$HOME/.dotfiles/ --work-tree=$HOME"
```

### Adding a New Dotfile

```
dotfiles add .zshrc
dotfiles commit -m "Add .zshrc"
dotfiles push
```
