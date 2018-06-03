# 通过建立三个不同的分支测试rebase三个不同版本是否可行

目录

1. 建立三个分支：oem1，oem2，oem3
2. 分别独立进行两次commit
3. 建立一个hotfix分支，独立进行两次commit
4. 分别rebase三个oem分支
5. 测试，是否三个oem分支正确的打上了hotfix补丁

测试失败

如果三个oem分支分别打hotfix补丁，用cherry_pick是可以的，测试通过


# Git 使用技巧
* clone远程库并设定本地文件夹名称 
''' 
git clone git@github.com:tianfengs/oemTest.git oemTestLocal  
'''
* 一次性下载所有远程分支到本地  
'''
git branch -r | grep -v '\->' | while read remote; do git branch --track "${remote#origin/}" "$remote"; done  
'''
