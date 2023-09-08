---
alias:
tags:
- published
- index/27.16
---

## Subtree vs Submodule

- Use **subtree** when you just want to copy code from an external repo once, or maybe with occasional pulls.
- Use **submodule** when you want to make your relationship to the external repo really explicit, or if you intend to make changes to the submodule code from within the context of your repo and push to the external repo.


## Subtree basics

https://gist.github.com/SKempin/b7857a6ff6bddb05717cc17a44091202

For example, I want to use the graphAPI-Template repo for another project/repo called graph-reports:

![](https://i.imgur.com/BXDuukv.png)

```git
git subtree add --prefix Helpers https://github.com/janeilagan/graphAPI-Template.git main --squash  
```

![](https://i.imgur.com/07FmKJE.png)

Notes: 
- the folder you will specify should not exist yet, the command will create it for you
- ensure you are calling the right branch name (main vs master vs etc)

### Pulling from the original repo

Say there are changes on original repo:

![](https://i.imgur.com/NhdYVFP.png)


And you want to make sure your subtree is updated:

```git
git subtree pull --prefix Helpers https://github.com/janeilagan/graphAPI-Template.git main --squash
```


However, sometimes this will think you have modifications even if your main repo is already clean:

![](https://i.imgur.com/GPmoFjy.png)

you may need to checkout main (still don't know why)

```git$APN
git checkout main
```

then run the subtree pull

![](https://i.imgur.com/Q5Yrk5T.png)


And you should have your subtree updated

![](https://i.imgur.com/wevaBTK.png)

![](https://i.imgur.com/3j6OM3b.png)


## Push changes to the remote repo

```git
git subtree push --prefix Helpers https://github.com/janeilagan/graphAPI-Template.git main
```

![](https://i.imgur.com/tVgdO8S.png)

Notes:
- Commits are stored on host repository so you need to push then pull again.
- Read through [subtree issues](https://gist.github.com/SKempin/b7857a6ff6bddb05717cc17a44091202#subtree-issues) as well.