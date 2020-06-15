# [@hoshino](https://github.com/hoshino)'s Dotfiles

From [this tutorial](https://www.atlassian.com/git/tutorials/dotfiles).

## Installing Dotfiles on a New System

Prior to the installation make sure you have committed the alias to your `.bashrc` or `.zsh`:
```bash
alias dots='/usr/bin/git --git-dir=$HOME/.dots/ --work-tree=$HOME'
```

and make sure your source repository ignores the folder where you'll clone it, so that
you don't create weird recursion problems:
```bash
echo ".dots" >> .gitignore
```

Now, clone your dotfiles into a bare repository in a "dot" folder of your `$HOME`:
```bash
git clone --bare git@github.com:hoshino/dots.git $HOME/.dots
```

Define the alias in the current shell scope:
```bash
alias dots='/usr/bin/git --git-dir=$HOME/.dots/ --work-tree=$HOME'
```

Checkout the actual content from the bare repository to your `$HOME`:
```bash
dots checkout
```

Set the flag `showUntrackedFiles` to `no` on this specific (local) repository:
```bash
dots config --local status.showUntrackedFiles no
```
