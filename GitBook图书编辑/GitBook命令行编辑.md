# GitBook命令行编辑

在前面已经介绍过了GitBook几个重要的文件,下面介绍GitBook命令行搭配MarkDown编辑书籍。

## GitBook书籍配置

```bash
# 创建目录
[root@iz2zecelicizfq27tt3w5xz ~]# mkdir my_book
# 在该目录下创建一下几个文件
[root@iz2zecelicizfq27tt3w5xz my_book]# ls
book.json  README.md  SUMMARY.md
# README.md中编辑该书的介绍
# SUMMARY.md中编辑该书的目录
[root@iz2zecelicizfq27tt3w5xz my_book]# cat SUMMARY.md
# Summary

## [GitBook介绍]  ------ 表示的是第一部分 
* [GitBook简介](./README.md) ------ 一级标题
  * [GitBook功能](./GitBook介绍/GitBook功能.md) ------ 二级标题

## GitBook安装    ------ 表示的是第二部分 
* [GitBook安装流程](./GitBook安装/GitBook安装手册.md)

## GitBook使用    ------ 表示的是第三部分 
* [基础](./GitBook使用/基础/README.md)
    * [目录结构](./GitBook使用/基础/目录结构.md#静态文件)
    * [菜单与页面](./GitBook使用/基础/菜单与页面.md)
    * [配置](./GitBook使用/基础/配置.md)
    * [词汇表](./GitBook使用/基础/词汇表.md)
    * [多语言](./GitBook使用/基础/多语言.md)
    * [Markdown语法](./GitBook使用/基础/Markdown语法.md)
    * [AscillDoc语法](./GitBook使用/基础/AsciiDoc语法.md)

# 在book.json中配置书籍的相关信息
[root@test1 test]# cat book.json
{
    "title": "GitBook使用手册",
    "author": "Meiyifei",
    "language": "zh-hans",
    "gitbook": "3.2.3",
    "styles": {
        "website": "./styles/website.css"
    },
    "structure": {
        "readme": "README.md"
    },
    "plugins": [
        "-sharing",
        "splitter",
        "expandable-chapters-small",
        "anchors",

        "github",
        "github-buttons",
        "-donate",
        "sharing-plus",
        "anchor-navigation-ex",
        "favicon",
	"fontsettings"
    ],
    "pluginsConfig": {
        "github": {
            "url": "https://github.com/meiyifei"
        },
        "github-buttons": {
            "buttons": [{
                "user": "meiyifei",
                "repo": "glory",
                "type": "star",
                "size": "small",
                "count": true
                }
            ]
        },
        "sharing": {
            "douban": false,
            "facebook": false,
            "google": false,
            "hatenaBookmark": false,
            "instapaper": false,
            "line": false,
            "linkedin": false,
            "messenger": false,
            "pocket": false,
            "qq": false,
            "qzone": false,
            "stumbleupon": false,
            "twitter": false,
            "viber": false,
            "vk": false,
            "weibo": false,
            "whatsapp": false,
            "all": [
                "google", "facebook", "weibo", "twitter",
                "qq", "qzone", "linkedin", "pocket"
            ]
        },
        "anchor-navigation-ex": {
            "showLevel": false
        },
        "favicon":{
            "shortcut": "./source/images/favicon.jpg",
            "bookmark": "./source/images/favicon.jpg",
            "appleTouch": "./source/images/apple-touch-icon.jpg",
            "appleTouchMore": {
                "120x120": "./source/images/apple-touch-icon.jpg",
                "180x180": "./source/images/apple-touch-icon.jpg"
            }
        },
	"fontsettings":{
	    "theme": "night",
            "family": "sans" ,
            "size":2        
	}
    }
}
```

## GitBook初始化

GitBook书籍的信息配置好了之后，可以进行初始化了，自动创建有关的目录文件。

```bash
[root@test1 GitBook]# gitbook init
info: create GitBook安装/GitBook安装手册.md 
info: create GitBook使用/GitBook命令行介绍.md 
info: create GitBook使用/GitBook目录结构.md 
info: create GitBook图书编辑/GitBook命令行编辑.md 
info: create GitBook图书编辑/GitBook editor编辑.md 
info: create SUMMARY.md 
info: initialization is finished
```

## GitBook书籍输出

GitBook书籍可以使用静态网站或者pdf、ebook等格式输出。

### 静态网站

```bash
[root@test1 GitBook]# gitbook serve
Live reload server started on port: 35729
Press CTRL+C to quit ...

info: 15 plugins are installed 
info: loading plugin "splitter"... OK 
info: loading plugin "expandable-chapters-small"... OK 
info: loading plugin "anchors"... OK 
info: loading plugin "github"... OK 
info: loading plugin "github-buttons"... OK 
info: loading plugin "sharing-plus"... OK 
info: loading plugin "anchor-navigation-ex"... OK 
info: loading plugin "favicon"... OK 
info: loading plugin "fontsettings"... OK 
info: loading plugin "livereload"... OK 
info: loading plugin "highlight"... OK 
info: loading plugin "search"... OK 
info: loading plugin "lunr"... OK 
info: loading plugin "theme-default"... OK 
info: found 5 pages 
info: found 0 asset files 
info: >> generation finished with success in 1.6s ! 

Starting server ...
Serving book on http://localhost:4000
```

### 其他格式输出

[需要安装calibre-ebook环境](https://www.jianshu.com/p/244c2b4632d9)

```bash
＃生成PDF文件
$ gitbook pdf ./ ./mybook.pdf

＃生成ePub文件
$ gitbook epub ./ ./mybook.epub

＃生成Mobi文件
$ gitbook mobi ./ ./mybook.mobi
```



