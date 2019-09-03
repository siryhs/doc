## git相关
- **git中文乱码**
`命令修改 git config --global core.quotepath false`

```
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   "\345\270\270\347\224\250\344\277\241\346\201\257/maven.md"

no changes added to commit (use "git add" and/or "git commit -a")
```
- **git撤销**

写完代码后，我们一般这样 `git add .`添加所有文件`git commit -m`本功能全部完成执行完commit后，想撤回commit，怎么办？这样：`git reset --soft HEAD^`HEAD^的意思是上一个版本，也可以写成`HEAD~1`如果你进行了2次commit，都想撤回，使用`HEAD~2`
1. `--mixed`意思是：不删除工作空间改动代码，撤销commit，并且撤销`git add .`操作这个为默认参数`git reset --mixed HEAD^`和`git reset HEAD^`效果是一样的
2. `--soft`不删除工作空间改动代码，撤销commit，不撤销`git add . `
3. `--hard`删除工作空间改动代码，撤销commit，撤销`git add . `注意完成这个操作后，就恢复到了上一次的commit状态。如果commit注释写错了，只是想改一下注释，只需要` git commit --amend`
