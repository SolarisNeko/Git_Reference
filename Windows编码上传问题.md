

 git add：添加至暂存区，但并未提交至服务器。git add . 是表示把当前目录下的所有更新添加至暂存区。有时在终端操作这个会提示：

```txt
github报错：
The file will have its original line endings in your working directory
```



这是因为文件中换行符的差别导致的。这个提示的意思是说：会把windows格式（CRLF（也就是回车换行））转换成Unix格式（LF），这些是转换文件格式的警告，不影响使用。

```txt
git默认支持LF。windows commit代码时git会把CRLF转LF，update代码时LF换CRLF。
```

## 解决办法

```sh
git rm -r --cached .
git config core.autocrlf false
git add .
```

