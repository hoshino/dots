# [@hoshino](https://github.com/hoshino)'s Dotfiles

From [this tutorial](https://www.atlassian.com/git/tutorials/dotfiles).

Prior to the installation make sure you have committed the alias to your `.bashrc` or `.zsh`:
```alias dots='/usr/bin/git --git-dir=$HOME/.dots/ --work-tree=$HOME'```

and make sure your source repository ignores the folder where you'll clone it, so that
you don't create weird recursion problems:
```echo ".dots" >> .gitignore```

Now, clone your dotfiles into a bare repository in a "dot" folder of your `$HOME`:
```git clone --bare <git-repo-url> $HOME/.dots```

Define the alias in the current shell scope:
```alias config='/usr/bin/git --git-dir=$HOME/.dots/ --work-tree=$HOME'```

Checkout the actual content from the bare repository to your `$HOME`:
```dots checkout```
