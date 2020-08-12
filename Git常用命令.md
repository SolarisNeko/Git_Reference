# 常用命令

## 命令总结

```sh
# 设置用户信息
git config --global user.name "SolarisNeko"
git config --global user.email "xxx@qq.com"

# 查看配置信息
git config --list
git config user.name
git config user.email

# 查看本地repo的文件状态
git status

# 将 untracked file 加入"暂存区(.git/index)"
git add hello.txt

# 取消暂存
git reset hello.txt

# 将"暂存区"的文件提交到”本地仓库“
git commit -m "init hello.txt" hello.txt

# 删除本地仓库文件
git rm hello.txt

# 查看日志记录
git log

# 回退版本(修改hello.txt后, 并且add + commit)
git log		# 先查看日志
git log --pretty=oneline	# 简约版日志
1094adb7b9b3807259d8cb349e7df1d4d6477073 (HEAD -> master) append GPL
e475afc93c209a690c39c13a46716e8fa000c366 add distributed
eaadf4e385e865d25c48e7ca9c8395c3f7dfaef0 wrote a readme file
	# 一大串数字是commit id(Version ID, SHA1计算出来)
# 回退到上一个版本
git reset --hard HEAD^
	# 退回去,如果关掉了bash,则无法穿越到未来
# 穿梭到回退前
git reset -hard <Commit ID>

# 查看每一次操作命令
git reflog

#------------------------------

### 远程repo操作
	
# 查看远程仓库
git remote		# 查看已有的远程仓库名
git remote -v	# 查看远程仓库详细url
git remote show origin 
	# 如果已经克隆了远程仓库，那么至少应该能看到 origin ，这是 Git 克隆的仓库服务器的默认名字

# 添加远程repo
git remote add <ID_name> <url>
	# 添加一个新的远程 Git 仓库，同时指定一个可以引用的简写
git remote -v	

# 移除无效的远程repo
git remote 
git remote rm origin
git remote

# 从远程repo中 fetch(抓取) & pull(拉取)

# git fetch : 从远程仓库获取最新版本到本地仓库，不会自动merge
git init
git remote add origin https://gitee.com/SolarisNeko/spring01
git fetch origin master		# 拉取远程repo内容到本地
git merge origin/master

# git pull : 从远程仓库获取最新版本并merge到本地仓库
git init
git remote add origin https://gitee.com/SolarisNeko/spring01
git pull origin master


# 本地repo推送到远程repo
git push https://gitee.com/SolarisNeko/spring01

#----------------------------------

## Git分支

# 查看分支
git branch
# 列出所有远程分支
git branch -r
# 列出所有local branch和remote branch
git branch -a

# 创建分支
git branch branch_name

# 切换分支
git switch branch_name
# Or
git checkout branch_name

# 推送local repo到remote repo Branch
git push origin b1	# 推送到remote branch b1

# 合并分支
git switch master
git merge b1	# master吞下b1,有冲突需要手动调节
	# 解决冲突: 修改 + 重新add + 重新merge

# 删除分支
git branch -d b1

# 强制删除分支(因开发动作,不允许删除)
git branch -D b1

# 删除本地上的远程仓库中的分支(并非实际remote)
git push origin -d branch_name



```



## Git版本控制HEAD指针

```ascii
┌────┐
│HEAD│
└────┘
   │
   └──> ○ append GPL
        │
        ○ add distributed
        │
        ○ wrote a readme file
```



### 建立"忽略管理的file规则"

在本地repo下，建立file -> .gitignore

```sh
# no .a files
*.a

# but do track lib.a, even though you're ignoring .a files above
!lib.a

# only ignore the TODO file in the current directory, not subdir/TODO
/TODO

# ignore all files in the build/ directory
build/

# ignore doc/notes.txt, but no doc/server/arch.txt
doc/*.txt

# ignore all .pdf files in the doc/ directory doc/**/*.pdf
```



## 在IDEA中使用Git ( VCS )

### 本地未初始化的project上传到Gitee

1. 在 File -> Settings -> Version Control -> Git 中设置好Git的安装路径的git.exe，并且Test一下是否有Git version is : ...

2. 然后在 VCS -> Import into Version Control -> Create Git Repository 

3. VCS -> Git -> Add ...
4. VCS -> Git -> Commit
5. VCS -> Git -> Repository -> Push