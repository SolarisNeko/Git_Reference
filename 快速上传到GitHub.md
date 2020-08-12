# Git快速部署到Remote



Remote：指GitHub/ Gitee等远程服务器

### 0. 添加远程仓库

```sh
git remote add origin https://gitee.com/SolarisNeko/test.git
```

如果已存在，想修改Remote

```sh
git remote rm origin

git remote add origin https://gitee.com/SolarisNeko/test.git
```



### 1.同步Remote中已有，且本地没有的文件

创建一个暂时的新分支，且拉取到Local master分支

```sh
git pull --rebase origin master
	# git pull --rebase: 当有这些冲突存在时，
	# git帮我们自动创建了一个新的分支，并且git告诉你接下来你要在[这个新的分支上]处理这个冲突
```

等同于 git pull --rebase = git fetch + git rebase

fetch是从远程仓库更新到本地仓库，pull是从远程仓库直接更新到工作空间中



### 2. 将 当前文件夹 添加到 git缓存区

```sh
git add .
```



### 3. 提交Local，git记录下此处缓存

```sh
git commit -m "commit this folder"
```



### 4.提交Remote

因为已经提交到Local，所以可以提交Remote

```sh
git push origin master
	# 推送到Remote master分支
```



