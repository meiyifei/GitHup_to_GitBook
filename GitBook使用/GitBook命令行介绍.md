# GitBook命令行介绍

下面介绍GitBook几个重要的命令行的作用：

```bash
[root@test1 ~]# gitbook help
    build [book] [output]       build a book
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
        --format                Format to build to (Default is website; Values are website, json, ebook)
        --[no-]timing           Print timing debug information (Default is false)

    serve [book] [output]       serve the book as a website for testing
        --port                  Port for server to listen on (Default is 4000)
        --lrport                Port for livereload server to listen on (Default is 35729)
        --[no-]watch            Enable file watcher and live reloading (Default is true)
        --[no-]live             Enable live reloading (Default is true)
        --[no-]open             Enable opening book in browser (Default is false)
        --browser               Specify browser for opening book (Default is )
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
        --format                Format to build to (Default is website; Values are website, json, ebook)

    install [book]              install all plugins dependencies
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    parse [book]                parse and print debug information about a book
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    init [book]                 setup and create files for chapters
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    pdf [book] [output]         build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    epub [book] [output]        build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    mobi [book] [output]        build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
```

## gitBook install

该命令安装在book.json中配置的有关的插件,在图书输出之前需要安装相应的插件

```bash
[root@test1 test]# gitbook install
info: installing 9 plugins using npm@3.9.2 
info:  
info: installing plugin "splitter" 
info: install plugin "splitter" (*) from NPM with version 0.0.8 
info: >> plugin "splitter" installed with success 
info:  
info: installing plugin "expandable-chapters-small" 
info: install plugin "expandable-chapters-small" (*) from NPM with version 0.1.7 
info: >> plugin "expandable-chapters-small" installed with success 
info:  
info: installing plugin "anchors" 
info: install plugin "anchors" (*) from NPM with version 0.7.1 
info: >> plugin "anchors" installed with success 
info:  
info: installing plugin "github" 
info: install plugin "github" (*) from NPM with version 2.0.0 
info: >> plugin "github" installed with success 
info:  
info: installing plugin "github-buttons" 
info: install plugin "github-buttons" (*) from NPM with version 3.0.0 
info: >> plugin "github-buttons" installed with success 
info:  
info: installing plugin "sharing-plus" 
info: install plugin "sharing-plus" (*) from NPM with version 0.0.2 
info: >> plugin "sharing-plus" installed with success 
info:  
info: installing plugin "anchor-navigation-ex" 
info: install plugin "anchor-navigation-ex" (*) from NPM with version 1.0.14 
info: >> plugin "anchor-navigation-ex" installed with success 
info:  
info: installing plugin "favicon" 
info: install plugin "favicon" (*) from NPM with version 0.0.2 
info: >> plugin "favicon" installed with success 
info:  
info: installing plugin "fontsettings" 
info: install plugin "fontsettings" (*) from NPM with version 2.0.0 
/root/test
├── gitbook-plugin-anchor-navigation-ex@1.0.14 
├── gitbook-plugin-anchors@0.7.1 
├── gitbook-plugin-expandable-chapters-small@0.1.7 
├── gitbook-plugin-favicon@0.0.2 
├── gitbook-plugin-fontsettings@2.0.0 
├── gitbook-plugin-github@2.0.0 
├── gitbook-plugin-github-buttons@3.0.0 
├── gitbook-plugin-sharing-plus@0.0.2 
└── gitbook-plugin-splitter@0.0.8 

info: >> plugin "fontsettings" installed with success 
```

## gitbook init

该命令根据SUMMARY.md文件中配置的书籍的目录信息，生成相应的文件。

```bash
[root@test1 test]# cat SUMMARY.md
# Summary

## GitBook介绍
* [GitBook介绍](./README.md)

## GitBook安装
* [GitBook安装流程](./GitBook安装/GitBook安装手册.md)

## GitBook使用
* [GitBook命令行介绍](./GitBook使用/GitBook命令行介绍.md)
* [GitBook目录结构](./GitBook使用/GitBook目录结构.md)

## GitBook图书编辑
* [GitBook命令行&MarkDown编辑](./GitBook图书编辑/GitBook命令行编辑.md)
* [GitBook editor编辑](./GitBook图书编辑/GitBook editor编辑.md)

[root@test1 test]# gitbook init
info: create GitBook安装/GitBook安装手册.md 
info: create GitBook使用/GitBook命令行介绍.md 
info: create GitBook使用/GitBook目录结构.md 
info: create GitBook图书编辑/GitBook命令行编辑.md 
info: create GitBook图书编辑/GitBook editor编辑.md 
info: create SUMMARY.md 
info: initialization is finished 

[root@test1 test]# ls
book.json  GitBook安装  GitBook使用  GitBook图书编辑  GLOSSARY.md  node_modules  README.md  SUMMARY.md
```

## gitbook build

该命令会将书籍会输出一个包含静态的HTML文件_book,我们可以对该文件打包然后发布。

```bash
[root@test1 test]# gitbook build
info: 15 plugins are installed 
info: 14 explicitly listed 
info: loading plugin "splitter"... OK 
info: loading plugin "expandable-chapters-small"... OK 
info: loading plugin "anchors"... OK 
info: loading plugin "github"... OK 
info: loading plugin "github-buttons"... OK 
info: loading plugin "sharing-plus"... OK 
info: loading plugin "anchor-navigation-ex"... OK 
info: loading plugin "favicon"... OK 
info: loading plugin "fontsettings"... OK 
info: loading plugin "highlight"... OK 
info: loading plugin "search"... OK 
info: loading plugin "lunr"... OK 
info: loading plugin "theme-default"... OK 
info: found 7 pages 
info: found 0 asset files 
info: >> generation finished with success in 1.1s !
```

## gitbook serve

该命令以静态网站的方式输出该书籍，其实该命令是调用gitbook build，然后启动Web服务器在本地的4000端口监听。

```bash
[root@test1 test]# gitbook serve
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
info: found 7 pages 
info: found 0 asset files 
info: >> generation finished with success in 1.3s ! 

Starting server ...
Serving book on http://localhost:4000
```

