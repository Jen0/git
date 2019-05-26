# git 常用命令


###### 查看文件夹详细

```Shell
ls -a
```

###### 初始化版本库

```Shell
git init
```

###### 显示版本库状态

```Shell
git status
```

###### 查看提交过的详细日志

```Shell
git log
```

###### 只查看提交过的日志描述和版本号

```Shell
git log -oneline
```

###### 配置 `git` 账号

```Shell
git config --global user.name xxx
git config --global user.email xxx@qq.com
```

###### 查看配置列表

```Shell
git list
```

###### 工作区添加到暂存区

```Shell
git add index.html
git add .
git add \*
```

###### 暂存区添加至版本库

```Shell
git commit -m 'description'
```

###### 工作区直接提交至版本库

```Shell
git commit -m 'description'
```

###### 将工作区修改的文件直接提交至版本库

```Shell
git commit -am 'description'
```

###### 撤销上一次提交，并将暂存区的文件重新提交 `--->` 进入 `vim` 编辑器 可以修改文件提交描述和文件内容

```Shell
git commit --amend
```

###### 工作区错误或者放弃，即从暂存区返回到工作区

```Shell
git checkout -- index.html
git checkout -- .
```

###### 撤销暂存区的提交,即从版本库返回到暂存区

```Shell
git reset HEAD index.html
git reset HEAD .
```

###### 将版本库,暂存区和工作区都回退版本

```Shell
git reset --hard HEAD index.html
```

###### 将版本库,暂存区都回退版本，工作区不受影响

```Shell
git reset --mixed HEAD index.html
```

###### 将版本库都回退版本，暂存区和工作区不受影响,其中 `HEAD` 可以替换为 `log` 日志中的版本号 至少为 `8` 位，即返回到指定的版本

```Shell
git reset --soft HEAD index.html
```

###### 删除文件，将工作区和暂存区的文件删除

```Shell
git rm index.html
```

###### 如果文件已被修改，将工作区和暂存区的都删除

```Shell
git rm -f index.html
```

###### 如果文件已被修改，只将暂存区中的删除。

```Shell
git rm --cached index.html
```

###### 重命名文件(前缀没有 `git`，需要手动添加到暂存区)

```Shell
mv index.html index2.html
```

###### 重命名文件(前缀有 `git`，工作区和暂存区都会被改动)

```Shell
git mv index.html index2.html
```

###### 查看分支

```Shell
git branch
```

###### 创建分支

```Shell
git branch dev
```

###### 切换分支

```Shell
git checkout dev
```

###### 删除分支

```Shell
git branch -d dev
```

###### 修改分支名称

```Shell
git branch -m dev dev2
```

###### 创建分支并切换至该分支

```Shell
git branch checkout -b dev
```

###### 分支内容合并,在 `master` 分支下，将 master 分支和 `dev` 分支内容合并

```Shell
git merge dev
```

###### 查看工作区和暂存区的差异

```Shell
git diff
```

###### 查看暂存区和版本库的差异

```Shell
git diff --staged
```

###### 查看两个版本之间的差异，选择 `log` 日志中的版本号进行比较，推荐使用 `8` 位长度以上

```Shell
git diff be70b52 c39e038
```

###### 查看两个分支的差异

```Shell
git diff master dev
```

###### 在分支 `dev` 下，修改文件后还没有提交，不能切换到 `master` 分支上，需要执行 `git stash` 先保存修改记录，再切换 `master` 分支。

```Shell
git stash
```

###### 在 `master` 分支切换回 `dev` 分支后，可以查询之前 `git stash` 保存的记录

```Shell
git stash list
```

###### 将保存记录拉取下来,`(stash@{0}`是记录名称

```Shell
git stash apply stash@{0}
```

###### 或者拉取下来并且删除

```Shell
git stash pop stash@{0}
```
