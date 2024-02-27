# How to use worktree
## why git worktree
when you want to have multiple branches at the same time.

## how to create worktree

create a worktree for emergency fix

```bash
git worktree add -b emergency-fix ../temp master
pushd ../temp
# ... hack hack hack ...
git commit -a -m "memergency fix for boss"
popd
git worktree remove ../temp
# delete branch by hand
# git branch -D memergency-fix
```

create from a repository

```bash
git clone --bare <upstream>
```

## use worktree
1. clone repository
```bash
git clone --bare "http://changbing.cai@gerrit.ecarxgroup.com/a/spb/parking/sal" .bare

```
1. config
create .git for nomal use
```bash
echo "gitdir: ./.bare" > .git
# add fetch for origin
# fetch = +refs/heads/*:refs/remotes/origin/*
```
1. create worktree
```bash
git worktree add dev
git worktree add -b gtest gtest
```


