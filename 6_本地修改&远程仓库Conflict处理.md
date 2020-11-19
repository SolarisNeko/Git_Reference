# 冲突处理

本地仓库 & 远程仓库 の <b>Conflict 处理</b>



```txt
没有 add 的文bai件，不会被覆盖。add 了文件没有 commit，不能du pull。commit 了之后 pull 有冲突zhi，会自行解决或者提示需要编dao辑。只要 commit 过，都可以用 git reflog 找回。

git库版本与本地库版本冲突：个人定义为就是git库版本与本地库版本不匹配，详细地说就是我们从git库clone克隆下来的版本，经过修改后提交并合并成新版本，但是后来又将git库的该版本撤销了，而本地没有撤销该版本，此时就是本地库拥有此版本而git库中没有此版本。这样在使用git pull或git pull origin master可能会出现：“Your local changes to the following files would be overwritten by merge”或"PULL  不可用，因为您尚有未合并的文件“或"自动合并失败，修正冲突后提交修正后的结果"“Your local changes to the following files would be overwritten by merge”这样的错误，意思就是你的本地修改以下文件将被覆盖合并。
```

