# GitBook相关配置

## 目录结构

```bash
├── book.json
├── README.md
├── SUMMARY.md
├── chapter-1/
|    ├── README.md
|    ├── something.md
├── chapter-2/
|    ├── README.md
```

## 文件功能介绍

| 文件          | 说明                                                         |
| ------------- | ------------------------------------------------------------ |
| `book.json`   | 保存 [配置文件](http://gitbook.hushuang.me/config.html)数据(**可选**) |
| `README.md`   | 简介 - 书籍的简单介绍(**必填**)                              |
| `SUMMARY.md`  | 目录(参见[目录管理](http://gitbook.hushuang.me/pages.html))(**可选**) |
| `GLOSSARY.md` | 字段/注释 - 专业术语列表(参见[词汇表](http://gitbook.hushuang.me/lexicon.html))(**可选**) |

### book.json

该文件为书籍的配置信息，具体的配置信息如下:

| 变量            | 说明                                                         |
| --------------- | ------------------------------------------------------------ |
| `root`          | 包含所有图书文件的根文件夹的路径，除了`book.json`            |
| `structure`     | 指定自述，摘要，词汇表等的路径。请参见[结构段落](http://gitbook.hushuang.me/%EF%BC%83%E7%BB%93%E6%9E%84)。 |
| `title`         | 书的标题，默认值从README中提取。在GitBook.com上，此字段已预填。 |
| `description`   | 您的图书说明，默认值从自述文件中提取。在GitBook.com上，此字段已预填。 |
| `author`        | 作者姓名。在GitBook.com上，此字段已预填。                    |
| `isbn`          | 书的国际码ISBN                                               |
| `language`      | [语言ISO规范](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)的书的语言，默认值是`en` |
| `direction`     | 文本的方向。可以是`rtl`或`ltr`，默认值取决于`language` 的值  |
| `gitbook`       | GitBook的版本。使用[SemVer](http://semver.org/)规范并接受诸如`“> = 3.0.0”`的条件 |
| `plugins`       | 加载需要的插件                                               |
| `pluginsConfig` | 配置插件信息                                                 |

### GLOSSARY.md

该文件主要用来为书籍中出现的专业术语提供定义说明，例如:

```bash
[root@test1 GitBook]# cat GLOSSARY.md
## git
一个分布式版本控制软件
```

### SUMMARY.md

该文件主要用来配置书籍的目录结构，具体用法如下:

[SUMMARY配置](../GitBook图书编辑/GitBook命令行编辑.md)

