

### 1.生成 ssh 密钥

```txt
Windows -> Perferences -> General -> Network Connections -> SSH2 -> Key Management -> Generate RSA Key... -> 右下角Save Private Key.. -> 确认C:\Users\...\ .ssh \ id_rsa 和 id_rsa.pub
```



### 2.github中配置 ssh的 公钥 & 密钥

```txt
GitHub 右上角用户 -> Settings -> SSH and GPG keys —> New SSH key -> 把id_rsa.pub (公钥) 配进来
```



### 3.Eclipse + EGIT

```txt
Window -> Perference -> Team -> Git -> Configuration -> Add Entry

Key: user.name
Value: ...

Key: user.email
Value: xxx@xx.com

Key: http.sslVersion
Value: tlsv1.2

配置：
1.帐号 密码
2.邮箱
3.https协议
	http.sslVersion = tlsv1.2 定义ssl协议版本, Github在最近的更新中，关闭了tlsv1.0和tlsv1.1协议的访问，不提供此参数，无法访问Github远程版本仓库。


```



### 4.显示Git

```txt
Window -> show View -> Other -> Git Repository
```

```txt
Add ... -> 

Destination (本地仓库)
```



### 5.修改Encoding

```txt
window -> Perference -> General -> workspace -> 左下角 TextFileencoding : Other = UTF-8
```



### 6.项目关联

```txt
Clone a Repository -> 远程repo的URL

选中Project -> Team -> Share Project... -> 选中要关联的Remote Project
```

### 7. 项目commit & push

```txt
project -> 右键 Team -> 最上面Commit...* -> commit and push
```

### 7. 项目 1. commit  + 2. push  == 2步走

```txt
1. project -> 右键 Team -> 最上面Commit...* -> 输入信息 -> commit

2. project -> 右键 Team -> Remote -> Push -> 最上面选择提交的local .git 然后 Next下一步 -> Add create/update specification 的 Source ref: 选择master -> 点击 右边的Add Spec -> 
```

