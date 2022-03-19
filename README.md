# 论语新新新解 -- The Analects of Confucius

**Version:** BUILD_VERSION

**Build At:** BUILD_DATE

## 环境设置

使用 nvm 可以切换 npm 版本。

```bash
$ nvm use v10.24.0
```

本文档开发所用 gitbook 版本：

```bash
$ gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```

## 本地 preview

本地修改文档可以使用如下命令验证：

```bash
$ gitbook serve
```

默认监听 `4000` 端口，你可以在浏览器中访问 `http://localhost:4000/` 查看修改效果。

如果想修改监听端口，可以使用如下方式：

```bash
$ gitbook --port 8080 serve
```

## 如何修改本文档

直接修改 `src/` 下的内容，然后发送 PR 即可。

**不需要**修改 docs 下面的内容，这部分会统一发布。

## 更新在线阅读分支

执行 `make deploy` 即可。

**注意：** 需要确保当前分支（main）不能包含未提交内容。

## 生成 pdf 文件

生成 pdf 文件需要 [calibre](https://calibre-ebook.com) 的支持。

在 macOS 下，如果安装了 calibre ，可能还是会出错，类似这样。

```
InstallRequiredError: "ebook-convert" is not installed.
Install it from Calibre: https://calibre-ebook.com
```

如果确认已经安装了 calibre ，那么很可能是因为 `ebook-convert` 命令没有在 `$PATH` 环境变量中，执行下面的命令即可：


```
$ sudo ln -s /Applications/calibre.app/Contents/MacOS/ebook-convert /usr/local/bin
```

然后通过 `make` 命令即可生成 pdf 文件：

```
$ make pdf
```

成功的话，就会在当前文件夹下生成 `book.pdf`，这也就是电子书的 pdf 格式。
