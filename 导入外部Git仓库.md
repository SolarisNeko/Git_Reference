# 导入外部Git仓库



如何导入外部代码仓库（Github、bitbucket、Google Code等等）到Git[@OSC](http://my.oschina.net/u/1164642) ，给出如下解决方案：

```sh
#	从原始地址clone一份bare仓库
git clone --bare  https://github.com/bartaz/impress.js.git 
```

此命令执行完成后即完成导入，删除 impress.js.git 文件夹即可。

-----------



## 方案2

 此方案，手头已经有了项目的完成仓库，则无需再从第三方代码托管平台上clone下来。 

-  到Git@OSC上创建项目，同样不要选择以上所说的三项。 
-  命令行进入项目目录，git status 确保项目状态为： 

```sh
nothing to commit, working directory clean
```

如果状态不是这样，则需要通过提交、暂存等操作，使项目当前状态为clean。



* 添加Git@OSC的remote

```sh
git remote add git-osc git@git.oschina.net:username/transalte4j.git
```

* 推送所有分支&tags

```sh
git push git-osc --all
git push git-osc --tags
```

以上两条命令执行完毕，即完成导入。



-------

## 方案3

 此方案针对导入已有的SVN仓库 

-  同上，先【新建项目】，不要选择以上所说的三项 
-  使用【git-svn工具】clone 【svn仓库】，【git-svn 】已经是【Git的默认组件】，如果你安装的是【较新版本的Git客户端】的话，则不需要再单独下载这个组件 

```sh
git svn clone http://translate4j.googlecode.com/svn/trunk/ translate4j
```

* 同样，进入项目目录，添加remote

```sh
git remote add git-soc git@git.oschina.net:username/impress.js.git
```

* 同样，推送所有分支&标签

```sh
git push git-osc --all
git push git-osc --tags
```

* 以上两条命令执行完毕，即推送完成

