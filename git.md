
### git&github简介
    git是一种分布式版本控制系统：每个用户都在自己的计算机上拥有完整的仓库
    github是git的项目托管服务
[git文档](https://git-scm.com/docs)
### 版本控制系统
    1.帮助保留项目的详细历史记录，并且能够在不同的版本上进行工作。
    2.保留详细的项目历史记录，可以看出一段时间内项目的进度。
    3.如果需要，还可以回到项目的某个阶段，并恢复数据或文件。

### 1.基本术语
    Commit:保存当前文件的状态的命令，类似游戏的存档
    Repository/repo:一个项目的目录，用git进行通信。可以存在本地或作为副本远程存储在其它计算机上
    Working Directory:在本地文件系统中，进行编辑或者其它操作的文件目录，对应有区别的就是commit之后保持                 在仓库中的文件
    Checkout:检出是指将仓库中的内容复制到工作目录下。
    Staging Area / Staging Index / Index:Git 目录下的一个文件，存储的是即将进入下个 commit 内容的信息。
    SHA:SHA 是每个 commit 的 ID 编号，全称是：Secure Hash Algorithm
    Branch:从主开发流程中分出来的新流程。作用是保持不更改主流程的同时，延伸新的流程
    
    

### 2.Windows下安装配置：
    1.转到 https://git-scm.com/downloads
    2.下载 Windows 版软件
    3.安装 Git 并选择所有默认选项
    
#### 设置你的 Git 用户名
git config --global user.name "< Your-Full-Name >"
#### 设置你的 Git 邮箱
git config --global user.email "< your-email-address >"
#### 确保 Git 输出内容带有颜色标记
git config --global color.ui auto
#### 对比显示原始状态
git config --global merge.conflictstyle diff3
git config --list

### 3.Git 与代码编辑器
   最后一个配置步骤是让 Git 能与你的代码编辑器结合使用。以下是三个最热门的代码编辑器。如果你使用的是其他编辑器，则在 Google 中搜索“修改 Git 默认编辑器为 X 编辑器”（将 X 替换为你的代码编辑器的名称）
#### Atom Editor 设置
git config --global core.editor "atom --wait"
#### Sublime Text 设置
git config --global core.editor "C:/Program Files/Sublime Text 2/sublime_text.exe' -n -w"
#### VSCode 设置
git config --global core.editor "code --wait"
#### 快速打开文件夹
    右键 git bash here
    在bash中，某目录中 start . 打开当前目录

### 4.git仓库命令
    git init:create a brand new repo on computer
    git clone:copy a repo from somewhere else to local computer
    git status:check the status for a repo
    git log:display infomation about existing commit
    git show:display infomathion about given commt
#### git init:
    ls:list file in current dir
    mkdir:create a new dir
    cd :change dir
    rm:remove dir and files  (rm -rf is funny)
#### git clone
    pwd
    mv name new name Vs git clone url newname
    git status
        1.已在工作目录中被创建，但尚未开始跟踪的新文件
        2.git正在跟踪的已修改文件
#### git log
    默认情况下，该命令会显示仓库中每个 commit 的：SHA、作者、日期、消息
    git log --oneline : show SHA + Message
    git log --stat :显示文件及代码变化数量
    git log -p :p means patch ，显示具体修改
    git log -p --stat: 统计信息+补丁信息
    git log -p -w :不显示空格修改
    git log -p sha(若干位)
    
    git show:显示最近的commit
    git show sha:同git log -p
   ##### 要向下滚动，按下
    j 或 ↓ 一次向下移动一行
    d 按照一半的屏幕幅面移动
    f 按照整个屏幕幅面移动
   ##### 要 向上滚动，按下
    k 或 ↑ 一次向上移动一行
    u 按照一半的屏幕幅面移动
    b 按照整个屏幕幅面移动
   ##### 按下 q 可以退出日志（返回普通的命令提示符）

    

### 5.向仓库中commit
    git add :add files from working dir to staging inedx
    git commit:take files from the staging index and save them in the respository
    git diff: display diffreences between 2 files
#### git add
    git rm --cached <file>: to unstage
    git add <file1> <file2> … <fileN>
    git add ./git rm --cashed .  新增或者移除当前目录及子目录所有文件
#### git commit 
    git commit -m "blabla"
    git commit + save editing in editor
>[How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)  
>[Commit message 和 Change log 编写指南](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)  
>[前端工程师纳米学位样式指南 - Git.md](https://github.com/udacity/frontend-nanodegree-styleguide-zh/blob/master/%E5%89%8D%E7%AB%AF%E5%B7%A5%E7%A8%8B%E5%B8%88%E7%BA%B3%E7%B1%B3%E5%AD%A6%E4%BD%8D%E6%A0%B7%E5%BC%8F%E6%8C%87%E5%8D%97%20-%20Git.md)
### 6.commit message 基本规范
    1.只解释对哪里做了更改，而不许要解释更改了什么
    2.要对更改位置精确到大标签，而不要只说更改了某文件
    3.可以在message中增加对更改的详细描述，但是需要空一行。此部分不会在git log --oneline出现

#### git diff
    可以对比当前修改和repo中的区别
  [git diff 文档](https://git-scm.com/docs/git-diff)
  
#### gitignore
    mv name .gitignore
    将需要忽略的文件加入当中即可
    文件夹也有效
 

### 7.git branch and .etc
