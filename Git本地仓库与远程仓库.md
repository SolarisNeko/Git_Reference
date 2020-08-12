# Git 本地仓库 && 远程仓库



## 命令总结

```sh

```





### 关联一个远程repo

把已有的本地repo与远程repo关联起来

```sh
git remote add origin https://gitee.com/SolarisNeko/spring01.git
```



### 把本地repo全部内容推送到远程repo

```sh
git push -u origin master
# 把本地库的内容推送到远程，用git push命令，实际上是把当前分支(master)推送到远程。

# 加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。
```



### 本地与远程repo关联后の提交

```sh
git push origin master
```



### 第一次连接 --- SSH警告

```sh
The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
RSA key fingerprint is xx.xx.xx.xx.xx.
Are you sure you want to continue connecting (yes/no)?
# 这是因为Git使用SSH连接，而SSH连接在第一次验证GitHub服务器的Key时，需要你确认GitHub的Key的指纹信息是否真的来自GitHub的服务器，输入yes回车即可。
Warning: Permanently added 'github.com' (RSA) to the list of known hosts.
# Git会输出一个警告，告诉你已经把GitHub的Key添加到本机的一个信任列表里了：

# ps: 如果你实在担心有人冒充GitHub服务器，输入yes前可以对照GitHub的RSA Key的指纹信息是否与SSH连接给出的一致。
```













### 强制同步远程repo文件(不覆盖)

git提交代码报错:Push to origin/master was rejected

```sh
git pull <URL:.../x.git> --allow-unrelated-histories
# Or
git pull origin master --allow-unrelated-histories
```



分布式版本系统的最大好处之一是在本地工作完全不需要考虑远程repo的存在，也就是有没有联网都可以正常工作，而SVN在没有联网的时候是拒绝干活的！

当有网络的时候，再把本地提交推送一下就完成了同步，真是太方便了！