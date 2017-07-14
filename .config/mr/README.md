# vcsh and myrepos

Install [myrepos](https://myrepos.branchable.com/), and [vcsh](https://github.com/RichiH/vcsh).

## Requirements

Arch:

*   myrepos
*   vcsh

NixOS:

### myrepos

Initial setup.

```
vcsh clone git://github.com/RichiH/vcsh_mr_template.git mr
cd ~/.config/mr/available.d
```

Then, for each repo.

```
nano mr.vcsh
```

```
[$HOME/.config/vcsh/repo.d/mr.git]
checkout = vcsh clone git://github.com/git@github.com:johnramsden/myrepos.git mr

```

## Activate a repo

make a symlink to tell mr to sync the omzsh repo

```
cd ~/.config/mr/config.d
ln -s ../available.d/oh-my-zsh.vcsh oh-my-zsh.vcsh
```

Setup mr to sync to remote:

```
cd ~/.config
vcsh enter mr
```

Now add mr directory:

```
git add mr
git commit -m 'Initial Commit, add oh-my-zsh and mr configs'
```

Add remote:

```
git remote rm origin
git remote add origin git@github.com:johnramsden/mr.git
exit
```

## oh-my-zsh

vcsh enter oh-my-zsh


## gitignore

```
vcsh write-gitignore oh-my-zsh
vcsh oh-my-zsh add -f ~/.gitignore.d/oh-my-zsh
vcsh write-gitignore oh-my-zsh
vcsh oh-my-zsh add ~/.gitignore.d/oh-my-zsh
vcsh oh-my-zsh commit -m "Add gitignore"
```
