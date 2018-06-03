
目录  
[建立三个oem分支测试同时维护三个版本](#1)  
[Git 使用技巧](#2)


# <a name=1 />通过建立三个不同的分支测试rebase三个不同版本是否可行  
1. 建立三个分支：oem1，oem2，oem3
2. 分别独立进行两次commit
3. 建立一个hotfix分支，独立进行两次commit
4. 分别rebase三个oem分支
5. 测试，是否三个oem分支正确的打上了hotfix补丁

测试失败

如果三个oem分支分别打hotfix补丁，用cherry_pick是可以的，测试通过


# <a name=2 />Git 使用技巧
* clone远程库并设定本地文件夹名称
>git clone git@github.com:tianfengs/oemTest.git oemTestLocal  
* 一次性下载所有远程分支到本地  
>git branch -r | grep -v '\->' | while read remote; do git branch --track "${remote#origin/}" "$remote"; done  

* 用 Atom的 markdown-writer 插件编写md文件

".platform-linux atom-text-editor:not([mini])":
  "shift-ctrl-K": "markdown-writer:insert-link"
  "shift-ctrl-I": "markdown-writer:insert-image"
  "ctrl-i":       "markdown-writer:toggle-italic-text"
  "ctrl-b":       "markdown-writer:toggle-bold-text"
  "ctrl-'":       "markdown-writer:toggle-code-text"
  "ctrl-h":       "markdown-writer:toggle-strikethrough-text"
  "ctrl-1":       "markdown-writer:toggle-h1"
  "ctrl-2":       "markdown-writer:toggle-h2"
  "ctrl-3":       "markdown-writer:toggle-h3"
  "ctrl-4":       "markdown-writer:toggle-h4"
  "ctrl-5":       "markdown-writer:toggle-h5"

* Markdown preview enhanced
在插件页面禁用内置的Markdown Preview插件

使用
该插件的功能很多, 这里只列出一些最常用的功能, 更多功能请参考中文官方文档
1. 预览md的快捷键任然为Ctrl+Shift+M
2. 编辑预览同步滚动
3. 命令Create Toc可以在当前位置生成md文件的toc
4. md文件导出为PDF, PNG, JPEG等文件
5. 命令Insert Table用于插入表格
6. 在预览窗口右键可以选择在浏览器中打开预览
7. 支持GitHub Flavored Markdown样式的TODO List

配置
下面是我的配置

"*":
  "markdown-preview-enhanced":
    breakOnSingleNewline: true
    useGitHubStyle: false
    useGitHubSyntaxTheme: false
有了以上两个插件, Atom已经可以被称作最好的MD编辑器了.
