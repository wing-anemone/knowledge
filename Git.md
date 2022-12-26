[toc]

# 流程图



![git](/Users/wing/knowledge/source/git.jpg)

# 常用命令

最左边是本地的工作区，右边的版本库分为 index（暂存区） 和 master（版本库、repo、远程、remote）

```bash
git branch # 查看本地分支
git branch xxxx # 创建本地分支xxxx
git branch -d xxxx # 删除本地分支xxxx，如果有提交未合并会失败
git branch -d xxxx # 强制删除本地分支xxxx

git reset --soft commit_of_Branch_xxxx # 修改HEAD指针位置

git status # 查看git状态

git submodule # 查看submodule状态
git submodule update --init --recursive # 递归拉取submodule代码

git checkout file # 放弃file文件的修改 (从暂存区恢复)
git checkout HEAD fileName # 放弃单个文件的修改 (从 HEAD 恢复)
git checkout --ours fileName # merge出现冲突时使用本地ver

git log 

git diff # 比较的是工作区和暂存区的差别
git diff --cached # 比较的是暂存区和版本库的差别
git diff HEAD # 可以查看工作区和版本库的差别
```



# Example

## 典型开发流程

```bash
git clone git@github.com:wing-anemone/project
git checkout -b new_branch_for_develop #-b 选项新建 branch

# coding . . .
git add . #添加修改
git commit -m “add xxx function” #提交commit
git push --set-upstream new_branch_for_develop #关联远端&上传
```

## 清除 commit 记录

branch: fixbug，commit: aabbccdd -> abcdef -> bcdefg -> cdefgh

```bash	
git reset --soft aabbccdd
git push --force
# branch: fixbug, commit: aabbccdd
git commit -m "fix bug"
git push
# branch: fixbug, commit: aabbccdd -> ssbbpp
```

# 教程

[1. 廖雪峰的详细Git教程](https://www.liaoxuefeng.com/wiki/896043488029600)
