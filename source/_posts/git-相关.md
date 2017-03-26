---
title: git 相关
date: 2017-03-25 15:51:50
tags:
---

## 配置
git \-\-version 查看当前git版本
git config \-\-list 查看当前git配置信息
git config \-\-list \-\-global git通用配置信息
git config user.name 获取单独的配置信息(name)
git config user.email 获取单独的配置信息(email)
git config \-\-global user.name cxl 配置name
git config \-\-global user.eamil xxx@xx.com 配置email
git config \-\-global add user.name cxl user.email xx@xx.com 同时配置多个参数
git config \-\-global unset user.name cxl 删除配置

## 配置别名
git config \-\-global alias.st status

## 操作
git init 将一个文件夹设置为git代码仓库
git status 查看仓库状态
git add <file> 提交文件到暂存区
git add . 提交所有改动到暂存区
git commit -m "提交说明" 提交到仓库
git commit \-\-amend -m "提交说明" 追加修改
git log 查看提交记录
git reflog 查看提交记录，即使版本已回退
git shortlog 根据提交者名字进行分组，显示每个开发者的所有commit记录
git diff <file> 查看文件变化
git diff 查看所有文件变化
git diff HEAD 与上一commit节点的差异
git diff HEAD^ 与上上commit节点的差异
git blame <file> 追溯一个指定文件的历史修改记录
gitk 查看图形化的Log记录
git checkout <file> 修改文件之后，git add指令之前，抛弃当前本地所有修改，恢复到上次最后提交版本；执行add指令将代码提交到暂存区后，再修改该文件，然后执行checkout指令，则会将该文件恢复到执行add操作后的初始状态，即恢复add后的所有修改。
git reset HEAD <file> 将文件移出暂存区
git reset \-\-hard HEAD^ 回退到上一个版本（HEAD^^：上上个版本， HEAD~100：上100个版本）
git reset \-\-hard commit id 回退到指定版本版本
git rm <file> 删除文件，不需要再执行git add,可直接执行git commit

## 文件暂存
git stash 将当前修改暂存起来
git stash list 查看当前暂存的内容
git stash apply 内容恢复，不会删除stash记录,git stash list还可以看到记录
git stash pop 内容回复，删除stash记录,git stash list看不到记录
git stash drop 删除stash记录

## 创建SSH Key
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

## 远程仓库
git remote add origin git@github.com:xx/gittest.git 关联远程仓库，其中origin就是远程仓库的名字
git push -u origin master 推送本地master分支到远程仓库，-u表示将本地master分支与远程master分支关联起来
git push 推送到远程仓库
git push origin master 推送到远程仓库
git pull 拉取最新的代码更新
git pull \-\-rebase 拉取最新修改，并且将本地未提交代码作用到最新版本，不会产生多余的Merge Histoey
git clone <git地址> 克隆远程仓库到本地

# 分支
git checkout -b dev 创建并切换到dev分支
git branch dev 创建dev分支
git checkout dev 切换到dev分支
git branch 列出所有本地分支
git branch -r 列出所有远程分支
git branch -a 列出所有本地分支和远程分支
git merge dev 合并dev分支到master分支
git rebase dev 合并dev分支到master分支,git到时间线会被合并
git branch -d dev 删除dev分支
git branch -D dev 强行删除dev分支
git remote 查看远程分支
git remote -v 查看远程分支详细信息
git push origin dev 将本地dev分支推送到远程origin仓库

## Tag
git tag v1 创建tag，默认记录在最后到提交上
git tag v1 <commit id> 创建tag，指定在commit id上创建
git tag -a v1 -m "version1" 创建带有注释说明到tag，-a指定tag名，-m指定注释说明
git tag -a v1 -m "version1" <commit id> 创建带有注释说明到tag，-a指定tag名，-m指定注释说明，指定在commit id上创建
git tag 查看本地tag
git show <tag name> 查看指定tag的详细信息
git tag -d <tag name> 删除tag
git push origin <tag name> 推送本地Tag到远程
git oush origin \-\-tags 推送所有本地Tag到远程

### 删除远程Tag
- 先删除本地tag
  git tag -d v2
- 再重新push到远程
  git push oigin :refs/tags/v2


