1 配置
    $ git config --global user.name "runoob"            # 去掉 --global只对当前仓库有效
    $ git config --global user.email test@runoob.com

    $ git config --global core.editor emacs   文本编辑器
    $ git config --global merge.tool vimdiff  差异分析工具

    $ git config --list

    $ git config user.name

2 基本概念
    工作区：就是你在电脑里能看到的目录。
    暂存区：英文叫 stage 或 index。一般存放在 .git 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
    版本库：工作区有一个隐藏目录 .git，这个不算工作区，而是 Git 的版本库。

https://www.runoob.com/git/git-workspace-index-repo.html

3 Git 创建本地仓库
    $ git init
    $ git add *.c
    $ git commit -m '备注'

4 或从远程clone
    $ git clone <repo> <directory>

5 基本操作
    https://www.runoob.com/git/git-basic-operations.html

    . workspace：工作区
    . staging area：暂存区/缓存区
    . local repository：或本地仓库
    . remote repository：远程仓库

    提交与修改:
        $ git add	    添加文件到仓库
        $ git status	查看仓库当前的状态，显示有变更的文件。
        $ git diff	    比较文件的不同，即暂存区和工作区的差异。
        $ git commit	提交暂存区到本地仓库。
        $ git reset	    回退版本。
        $ git reset	    回退版本。
        $ git rm	    删除工作区文件。
        $ git mv	    移动或重命名工作区文件。

    远程操作:
        $ git remote	远程仓库操作  
          
          git remote add origin git@gitee.com:imnoob/runoob-test.git
          git remote -v
          git remote rm origin

          # 使用多个远程库:
          git remote add github git@github.com:tianqixin/runoob-git-test.git
          git remote add gitee git@gitee.com:imnoob/runoob-test.git
          
          # 推送到 GitHub，使用命令：
          git push github master
          git push gitee master

        $ git fetch	    从远程获取代码库
        $ git pull	    下载远程代码并合并
        $ git push	    上传远程代码并合并

6 Git 分支管理
    创建分支命令：
        git init 的时候，默认情况下 Git 就会为你创建 master 分支
        git branch (branchname)   手动创建一个分支
    切换分支命令:
        git checkout (branchname)
        git checkout -b (branchname) 命令来创建新分支并立即切换到该分支下
    合并分支命令:
        git merge 
    合并冲突:
        https://www.runoob.com/git/git-branch.html
    列出分支基本命令：
        git branch
    删除分支命令：
        git branch -d (branchname)

7 Git 查看提交历史
    $ git log - 查看历史提交记录。
    $ git blame <file> - 以列表形式查看指定文件的历史修改记录。

    $ git log --oneline  查看历史记录的简洁的版本

    $ git log --graph 选项，查看历史中什么时候出现了分支、合并

    $ git log --reverse 参数来逆向显示所有日志

    $ git log --author=Linus --oneline -5 查找指定用户的提交日志
    
    $ git log --oneline --before={3.weeks.ago} --after={2010-04-18} --no-merges 指定日期 --no-merges 选项以隐藏合并提交

    查看指定文件的修改记录可以使用 git blame 命令，格式如下：
    git blame <file>









1 git强制覆盖本地代码（与git远程仓库保持一致）：
    git fetch --all                  //只是下载代码到本地，不进行合并操作
    git reset --hard origin/master   //把HEAD指向最新下载的版本
    git pull

2 git强制覆盖本地命令（单条执行）：
    git fetch --all && git reset --hard origin/master && git pull

3 git友好合并远程修改和本地修改
    git rebase origin/master

4 git强制推送本地代码到远程仓库的develop分支
    git push --force origin develop