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