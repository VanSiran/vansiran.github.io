# Git全局禁止.DS\_Store
在Mac上使用Git遇到一个烦人的问题：git文件夹内充满了 macOS 的隐藏文件，.DS\_Store、.Trash......
每次删除这些文件再进行 git commit 烦人的很啊。 google了一篇文章：[让 Git 全局性的忽略 .DS\_Store]可以解决这个问题。
## 第一步
> 创建 \~/.gitignore\_global 文件，把需要全局忽略的文件类型塞到这个文件里。
'' .DS_Store .DS_Store? *.swp ._* .Spotlight-V100 .Trashes Icon? ehthumbs.db Thumbs.db
++⬆️⬆️⬆️我把这些东西写进文件就好了。++
## 第二步
然而。发现我的\~/下面并没有.gitconfig配置文件......
我的gitconfig在哪里呢？其实我并没有进行过全局设置，也自然就没有gitconfig文件了。直接在\~/下创建一个.gitconfig文件就好了，在里面写进这个：
'' [core]
'' 	excludesfile = /Users/van/.gitignore_global
其实可以另辟蹊径，通过命令行 `git config --global core.excludesfile /Users/van/.gitignore\_global` 命令来实现。
命令行写入后，ls -al \~发现已经创建了一个.gitconfig。内容和上面自己写进去的一样。
---- 
gitconfig详细参考资料：[https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration]
