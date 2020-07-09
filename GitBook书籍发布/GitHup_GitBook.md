# 关联GitHup与GitBook

新版 gitbook.com 不支持本地版本管理了，但是可以通过配置GitHup与GitBook关联，先提交到GitHup然后再同步到GitBook上。下面给出关联的步骤:

## 在GitBook上创建space

![img](http://chuantu.xyz/t6/739/1594287225x2073446515.png) 

## 编辑Title

![img](http://chuantu.xyz/t6/739/1594287273x2073446523.png) 

## 关联GitHup

在左侧点击Intergration,然后打开GitHup按钮，根据提示选择同步的仓库和方向。

![img](http://chuantu.xyz/t6/739/1594287332x2073447963.png) 

## 关联完成

提示GitHup上的内容以及导入，并且之后GitHup上的更改会同步到GitBook上。

![img](http://chuantu.xyz/t6/739/1594287509x2073446523.png) 

## GitHup导入成功

![img](http://chuantu.xyz/t6/739/1594287629x2073446515.png) 

## GitBook同步成功

```bash
# GitBook为已经编辑好书籍
[root@test1 GitBook]# ls
book.json  GitBook安装  GitBook使用  GitBook书籍发布  GitBook图书编辑  GLOSSARY.md  node_modules  README.md  SUMMARY.md
#提交更改到GitHup
[root@test1 GitBook]# git add .
[root@test1 GitBook]# git commit -m 'version1.0'
[master d67af7e] version1.0
 14 files changed, 667 insertions(+), 6 deletions(-)
 create mode 100644 "GitBook\344\271\246\347\261\215\345\217\221\345\270\203/GitBook.com.md"
 create mode 100644 "GitBook\344\271\246\347\261\215\345\217\221\345\270\203/GitHup&GitBook.md"
 create mode 100644 "GitBook\344\271\246\347\261\215\345\217\221\345\270\203/GitHup.md"
 create mode 100644 "GitBook\344\271\246\347\261\215\345\217\221\345\270\203/GitHup_GitBook.md"
 create mode 100644 "GitBook\344\275\277\347\224\250/GitBook\345\221\275\344\273\244\350\241\214\344\273\213\347\273\215.md"
 create mode 100644 "GitBook\344\275\277\347\224\250/GitBook\347\233\270\345\205\263\351\205\215\347\275\256.md"
 create mode 100644 "GitBook\345\233\276\344\271\246\347\274\226\350\276\221/GitBook editor\347\274\226\350\276\221.md"
 create mode 100644 "GitBook\345\233\276\344\271\246\347\274\226\350\276\221/GitBook\345\221\275\344\273\244\350\241\214\347\274\226\350\276\221.md"
 create mode 100644 "GitBook\345\233\276\344\271\246\347\274\226\350\276\221/GitBook\345\234\250\347\272\277\347\274\226\350\276\221.md"
 rewrite README.md (100%)
[root@test1 GitBook]# git push -u origin master --force
Username for 'https://github.com': meiyifei
Password for 'https://meiyifei@github.com': 
Counting objects: 838, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (782/782), done.
Writing objects: 100% (838/838), 1.70 MiB | 359.00 KiB/s, done.
Total 838 (delta 95), reused 0 (delta 0)
remote: Resolving deltas: 100% (95/95), done.
To https://github.com/meiyifei/sync_githup_to_gitbook.git
 + 4a3972b...d67af7e master -> master (forced update)
分支 master 设置为跟踪来自 origin 的远程分支 master。![img](http://chuantu.xyz/t6/739/1594289050x2073446515.png) 
```

可以看到GitBook上已经同步了书籍内容的更改。

![img](http://chuantu.xyz/t6/739/1594289127x2073447963.png)

同步成功后可以通过下面的链接访问已经编辑好的书籍:
https://app.gitbook.com/@meiyifei1/s/gitbook/ 
