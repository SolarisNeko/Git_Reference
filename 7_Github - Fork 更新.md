 

# Fork 更新

## 背景

> github上，Fork 别人项目，但别人项目更新了，你需要 合并/重新fork。



## 方法1 - 合并分支

> 以下步骤，在一个 Folder（文件夹）中进行。

1、先 clone 需要更新fork的项目（你自己的github）

```sh
git clone https://xxx.x.xx.xx.git
# ps: 会新建一个【项目文件夹】

```



2、进去 clone 的 文件夹，再打开 git

```sh
# 添加 远程地址（后地址 = 你fork的项目的地址）
git remote add upstream https://github.com/y1ndan/genshin-impact-helper.git
```



3、抓取更新 到 master分支

```sh
git fetch upstream master
```



4、切换 master分支（如果没有额外分支，部分人可省略）

```sh
git checkout master
```



5、合并分支 (upstream 合并到 master，部分人可省略)

```sh
# 如果创建了新分支，拉取的更新，才需要此步骤
git merge upstream/master
```



6、添加-提交-上传

```sh
git add .
git commit -m "new"
git push origin master
```



## 方法2 - 删掉重fork

删掉 github 上 fork的项目，重新 fork