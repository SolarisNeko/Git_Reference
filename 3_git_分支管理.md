# git 分支管理



## Eclipse

### 1-1. 新建分支

```txt
选中Project 右键 -> Team -> Switch To -> new Branch 
```



### 1-2. 切换分支

```txt
选中Project 右键 -> Team -> Switch To -> 选择要切换的分支
```



### 2-1. 合并分支 - Merge

​	合并分支，必须在 master分支上，才可以 Merge

```txt
选中Project 右键 -> Team ->  Merge -> 选中 被Merge的branch -> Merge
----------
会报 冲突
```

### 2-2. 冲突管理

```txt
用户1  写入 add()
用户2 写入 delete()

用户1  先提交
用户2  后提交  失败

用户2  需要pull（拉取)了 才能 再提交

后提交的人 -- 会发生冲突
```





### 2-2. 删除分支

​	（上班，一般是没有这个权限）

#### 2-2-1. 删除本地分支



#### 2-2-2. 删除Remote分支

