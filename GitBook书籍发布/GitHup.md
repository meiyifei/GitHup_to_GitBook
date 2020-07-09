# 在GitHup上发布

## 创建仓库

```bash
# 首先在GitHup上创建一个仓库，然后创建本地仓库目录。
[root@test1 ~]# mkdir GitBook
```

## 复制代码到仓库对应的目录

```bash
# 将静态网站代码复制到仓库对应的目录
[root@test1 GitBook]# cd /root/gitbook/
[root@test1 gitbook]# ls
book.json  GitBook安装  GitBook介绍.md  GitBook使用  GLOSSARY.md  node_modules  README.md  SUMMARY.md
[root@test1 gitbook]# gitbook build ./ ../GitBook/
info: 16 plugins are installed 
info: 13 explicitly listed 
info: loading plugin "splitter"... OK 
info: loading plugin "expandable-chapters-small"... OK 
info: loading plugin "anchors"... OK 
info: loading plugin "github"... OK 
info: loading plugin "github-buttons"... OK 
info: loading plugin "sharing-plus"... OK 
info: loading plugin "anchor-navigation-ex"... OK 
info: loading plugin "favicon"... OK 
info: loading plugin "highlight"... OK 
info: loading plugin "search"... OK 
info: loading plugin "lunr"... OK 
info: loading plugin "fontsettings"... OK 
info: loading plugin "theme-default"... OK 
info: found 27 pages 
info: found 2 asset files 
info: >> generation finished with success in 3.1s !

[root@test1 GitBook]# ls
gitbook  GitBook安装  GitBook使用  GitBook书籍发布  GitBook图书编辑  GLOSSARY.html  index.html  search_index.json
```

## 同步本地仓库到远程仓库

```bash
# 同步本地仓库到远程仓库
[root@test1 GitBook]# git init
初始化空的 Git 版本库于 /root/GitBook/.git/
[root@test1 book]# git add .
[root@test1 book]# git commit -m 'first commit'
[master（根提交） 41ce30e] first commit
 64 files changed, 22242 insertions(+)
 create mode 100644 ".GitBook\344\273\213\347\273\215.md"
 create mode 100644 GLOSSARY.html
 create mode 100644 "GitBook\344\273\213\347\273\215.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\237\272\347\241\200/AsciiDoc\350\257\255\346\263\225.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\237\272\347\241\200/Markdown\350\257\255\346\263\225.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\237\272\347\241\200/index.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\237\272\347\241\200/\345\244\232\350\257\255\350\250\200.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\237\272\347\241\200/\347\224\237\346\210\220\347\224\265\345\255\220\344\271\246\345\222\214pdf.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\237\272\347\241\200/\347\233\256\345\275\225\347\273\223\346\236\204.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\237\272\347\241\200/\350\217\234\345\215\225\344\270\216\351\241\265\351\235\242.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\237\272\347\241\200/\350\257\215\346\261\207\350\241\250.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\237\272\347\241\200/\351\205\215\347\275\256.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/index.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\344\270\273\351\242\230/index.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\217\222\344\273\266/api.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\217\222\344\273\266/index.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\217\222\344\273\266/\345\210\233\345\273\272\346\217\222\344\273\266.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\217\222\344\273\266/\345\233\236\350\260\203\345\207\275\346\225\260.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\217\222\344\273\266/\345\235\227.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\217\222\344\273\266/\346\265\213\350\257\225\346\217\222\344\273\266.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\217\222\344\273\266/\350\277\207\346\273\244\345\231\250.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\250\241\346\235\277/index.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\250\241\346\235\277/\345\206\205\345\256\271\345\274\225\347\224\250.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\250\241\346\235\277/\345\217\230\351\207\217.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\345\256\232\345\210\266/\346\250\241\346\235\277/\346\250\241\346\235\277\345\212\251\346\211\213.html"
 create mode 100644 "GitBook\344\275\277\347\224\250/\346\217\222\344\273\266\345\274\200\345\217\221/index.html"
 create mode 100644 "GitBook\345\256\211\350\243\205/GitBook\345\256\211\350\243\205\346\211\213\345\206\214.html"
 create mode 100644 "GitBook\345\256\211\350\243\205/README.md"
 create mode 100644 gitbook/fonts/fontawesome/FontAwesome.otf
 create mode 100644 gitbook/fonts/fontawesome/fontawesome-webfont.eot
 create mode 100644 gitbook/fonts/fontawesome/fontawesome-webfont.svg
 create mode 100644 gitbook/fonts/fontawesome/fontawesome-webfont.ttf
 create mode 100644 gitbook/fonts/fontawesome/fontawesome-webfont.woff
 create mode 100644 gitbook/fonts/fontawesome/fontawesome-webfont.woff2
 create mode 100644 gitbook/gitbook-plugin-anchor-navigation-ex/lib/config.js
 create mode 100644 gitbook/gitbook-plugin-anchor-navigation-ex/lib/log.js
 create mode 100644 gitbook/gitbook-plugin-anchor-navigation-ex/lib/plugin.js
 create mode 100644 gitbook/gitbook-plugin-anchor-navigation-ex/style/plugin.css
 create mode 100644 gitbook/gitbook-plugin-anchors/plugin.css
 create mode 100644 gitbook/gitbook-plugin-expandable-chapters-small/expandable-chapters-small.css
 create mode 100644 gitbook/gitbook-plugin-expandable-chapters-small/expandable-chapters-small.js
 create mode 100644 gitbook/gitbook-plugin-fontsettings/fontsettings.js
 create mode 100644 gitbook/gitbook-plugin-fontsettings/website.css
 create mode 100644 gitbook/gitbook-plugin-github-buttons/plugin.js
 create mode 100644 gitbook/gitbook-plugin-github-buttons/plugin.js.map
 create mode 100644 gitbook/gitbook-plugin-github/plugin.js
 create mode 100644 gitbook/gitbook-plugin-highlight/ebook.css
 create mode 100644 gitbook/gitbook-plugin-highlight/website.css
 create mode 100644 gitbook/gitbook-plugin-lunr/lunr.min.js
 create mode 100644 gitbook/gitbook-plugin-lunr/search-lunr.js
 create mode 100644 gitbook/gitbook-plugin-search/lunr.min.js
 create mode 100644 gitbook/gitbook-plugin-search/search-engine.js
 create mode 100644 gitbook/gitbook-plugin-search/search.css
 create mode 100644 gitbook/gitbook-plugin-search/search.js
 create mode 100644 gitbook/gitbook-plugin-sharing-plus/buttons.js
 create mode 100644 gitbook/gitbook-plugin-splitter/splitter.css
 create mode 100644 gitbook/gitbook-plugin-splitter/splitter.js
 create mode 100644 gitbook/gitbook.js
 create mode 100644 gitbook/images/apple-touch-icon-precomposed-152.png
 create mode 100644 gitbook/images/favicon.ico
 create mode 100644 gitbook/style.css
 create mode 100644 gitbook/theme.js
 create mode 100644 index.html
 create mode 100644 search_index.json
 
[root@test1 GitBook]# git remote add origin https://github.com/meiyifei/GitBook.git
[root@test1 GitBook]# git push -u origin master
```

## 添加Githup Pages

```bash
# 给仓库添加GitHup Pages
# 创建gh-pages分支
[root@test1 GitBook]# git checkout -b gh-pages
切换到一个新分支 'gh-pages'
[root@test1 GitBook]# git branch 
* gh-pages
  master
[root@test1 GitBook]# git push -u origin gh-pages
Username for 'https://github.com': meiyifei
Password for 'https://meiyifei@github.com': 
Total 0 (delta 0), reused 0 (delta 0)
remote: 
remote: Create a pull request for 'gh-pages' on GitHub by visiting:
remote:      https://github.com/meiyifei/GitBook/pull/new/gh-pages
remote: 
To https://github.com/meiyifei/GitBook.git
 * [new branch]      gh-pages -> gh-pages
分支 gh-pages 设置为跟踪来自 origin 的远程分支 gh-pages。
[root@test1 GitBook]# git branch -a
* gh-pages
  master
  remotes/origin/gh-pages
  remotes/origin/master
# 在对应仓库的Settings里面的GitHup Pages已经出现(https://meiyifei.github.io/GitBook/)
# 使用该网址即可访问该书籍

# 注意此时默认的master分支可以根据需要删除
# 如果要删除需要在Settings修改默认的分支(master之外的)
[root@test1 book]# git branch -d master
已删除分支 master（曾为 41ce30e
[root@test1 book]# git push origin --delete master
Username for 'https://github.com': meiyifei
Password for 'https://meiyifei@github.com': 
To https://github.com/meiyifei/GitBook.git
 - [deleted]         master
[root@test1 book]# git branch -a
* gh-pages
  remotes/origin/gh-pages
# 此时master分支已经删除
```

完成后即可通过下面链接访问以编辑好的书籍:
https://meiyifei.github.io/GitBook/

