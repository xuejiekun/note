# Git Note
***
## 1.基本
### 创建仓库
* git init

### 添加
* git add `file`
### 删除
* git rm `file`

### 提交
* git commit -m `'comment'`

### 获取状态
* git status
### 查看提交历史
* git log
### 查看命令历史
* git reflog

### 版本切换
* git reset --hard `commit_id`
### 查看修改内容
* git diff
***


## 2.更改提交状态
### 丢弃工作区修改
* git checkout -- `file`

### 撤销暂存区
* git reset HEAD `file`
***


## 3.分支
### 查看分支
* git branch
### 新建分支
* git branch `branch_name`
### 选择分支
* git checkout `branch_name`