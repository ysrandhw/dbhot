### 01 git是什么

svn （集中式）： 单一集中管理服务器       缺点：中央服务器的单点故障

git 版本  控制 （分布式版本控制工具 ） 本地版本管理

### 02 为什么要做版本控制 

​	版本管理  代码回滚

### 03 安装

本地

线上中心（github、gitlab）

mac、linux、win

### 04 管理流程

git  管理文件夹流程

1、进入要管理的文件夹 

2、初始化代码 

3、 管理文件夹

4、生成版本

 git init    

git status （检测文件状态） 红色（新增、修改）  绿色 已经管理起来

git add .

git commit -m "描述"    git log 查看版本信息



用户名 邮箱 配置

### 06 git 三大区域

工作区  

暂存区   git add .

版本库	git commit 

### 07 回滚

mac  iTERM  终端软件

git reset --hard  版本号

git reflog 查看 所有版本 包括回滚后的

### 08 git 操作命令

git checkout -- index.html  工作区修改回到未修改

git reset HEAD index.html  暂存回到工作区

### 09 初试分支

v1---v2--v3 保留修改部分 ，未修改的指针 ，指向到v2

### 10 紧急修复线上bug思路

主分支  dev分支 bug分支 环境隔离，合并到主分支

### 11 基于分支修复线上bug过程

git branch 查看当前分支    默认master

git branch dev  创建分支

git checkout dev 切换到dev 分支

创建 bug 分支 修改代码，切换会 master分支  git merge bug 合并分支（master 合并 bug分支）

合并后  git branch -d bug   删除修改bug的分支

冲突  手动 修复bug

### 12 命令总结 和工作流

工作流  master  主分支  

​			dev 开发分支（稳定后 合并到 maser ）

### 13 github

代码托管仓库   

gitlab（开源工具）  自建仓库 服务器 自己公司管理

1. 注册账号
2. 创建仓库
3. 本地代码推送到远程仓库 

### 14 基于 github 代码管理

1.给远程仓库起别名

git remote add origin 远程仓库地址

2. 向远程推送代码

   git push -u origin 分支

   3。 克隆远程代码仓库

   git clone 远程仓库地址

   4.切换分支

   git checkout 分支  

### 15 家里 公司分支

公司 clone后  git checkout dev       把master合并到 dev     git merge master

公司修改 后 git push -u origin dev

家里  git checkout dev 

​		更新代码 git pull origin dev  =  git fetch origin dev(远程仓库 到版本库) + git merge origin/dev（版本库合并到工作区） 

### 16 忘推送代码

在公司忘推送

家：写其他 后推送

公司 ：拉代码   合并（可能冲突）

### 17 rebase 应用场景

rebase 变基 （使git 提交记录简洁）

```
1. 多个记录 整合为一个记录(不要rebase已经提交到远程仓库)
git log 后
gir rebase -i 版本号  （合并当前版本到 版本号的记录）
git rebase -i HEAD~3   （合并当前开始 最近的3条版本号记录）
```

### 18 rebase 应用场景二

主分支  dev分支  类似合并 rebase后 主分支 一条线 没有其他分支记录

git log --graph   图形化信息

dev上  git rebase master

### 19 rebase 应用场景三

在公司忘推送

家：写其他 后推送

公司 ：拉代码   合并（可能冲突）

之前是 git pull origin dev

现在  先 git fetch origin dev  然后 git rebase origin/dev

```
注意 rebase 冲突
git rebase continue
```



