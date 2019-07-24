### git 入门（git和svn互相融通可以下载https://tortoisegit.org/download/）

```
#### 安装网址
    https://git-scm.com/downloads
    安装完之后默认位置是在c盘
```
#### 1.1本地创建.git文件
```
####第一种方式  再打开git Gui 再creat 再把路径复制上去 就会有一个.git的文件夹出来
```

```
####第二种方式  再打开git Bash再$git init
```


```
.git就是本地版本库；repo1就是指本地工作目录
```


```
向本地仓库添加文件 可以用TortoiseGit去add再ok
```
#### 2.1本地.git文件传送文件给远程(有ssh方式和http方式)

##### SSH方式

###### 在github上创建仓库(在命令行上创建一个新的存储库)

```
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:ldluodan/repo1.git
git push -u origin master
```

###### 创建ssh秘钥及在github上配置公钥 

```
1.  ssh-keygen -t rsa；生成了一个缪顿
2.  id_rsa是私钥 一定要保存好；id_rsa.pub是公钥
3.  id_rsa.pub打开并把此内容复制到github设置里面；   再点击Add SSH Key
4.  git remote add origin git@github.com:ldluodan/repo1.git
5.  git push -u origin master /然后再yes;这样就和远程仓库建立了一个连接
6.  再刷新github官网；远程仓库也有本地所建立的hellow.txt
```

##### Http方式


```
直接使用图形处理器就可以
```
