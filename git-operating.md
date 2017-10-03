# git终端使用
##第一次使用git看[这里](https://github.com/xugy0926/getting-started-with-javascript/blob/master/topics/%E7%AC%AC%E4%B8%80%E6%AC%A1%E4%BD%BF%E7%94%A8Git.md)
## 删除远程仓库的方法
克隆远程仓库到本地库：git clone http文件
对需要删除的文件：git rm test.txt  (删除文件)
文件夹：git rm -r test/    (删除文件夹）
提交修改：git commit -m "提交信息"
将修改提交到远程仓库:git push 
## 退出vim和node以及其他模式
![](http://upload-images.jianshu.io/upload_images/1513738-8ccacfe77506eb53.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
使用:q或者Ctr+C
## fork别人的项目更新主页方法
git fetch upstream master
git merge upstream/master
git push
###出现过的问题
>git fetch upstream master
fatal: 'upstream' does not appear to be a git repository fatal: Could not read from remote repository.
* [configuring a remote for a fork](https://help.github.com/articles/configuring-a-remote-for-a-fork/).
配置远程fork仓库,然后三步走
---
>$ git merge upstream/master
Updating 48477c5..67e6709
error: Your local changes to the following files would be overwritten by merge:
	homework/.DS_Store
Please commit your changes or stash them before you merge.
>Aborting
* rm homework/.DS_Store（deleted:    homework/.DS_Store）
  git merge upstream/master
  git push
---
>$ git merge upstream/master
Updating e842e43..dbf103a
error: Your local changes to the following files would be overwritten by merge:
	webapp/src/public/stylesheets/style.css
	webapp/src/views/_head.ejs
	webapp/src/views/index.ejs
	webapp/src/views/sayToTeacher.ejs
Please commit your changes or stash them before you merge.
Aborting
* $ git reset --hard
HEAD is now at e842e43 lesson6
$ git pull
Already up-to-date.
重新三步
git fetch upstream master
git merge upstream/master
git push
---
>$ git merge upstream/master
error: The following untracked working tree files would be overwritten by merge:
	homework/.DS_Store
Please move or remove them before you merge.
>Aborting
* You can try command to clear the untracked files from the local
git clean  -d  -fx ""
where -d can be replace with following:
-x means ignored files are also removed as well as files unknown to git.
-d means remove untracked directories in addition to untracked files.
-f is required to force it to run.
---
>How to ignore error on git pull about my local changes would be overwritten by merge?>Your local changes to the following files would be overwritten by merge
What if I want to overwrite them?
I've tried things like git pull -f, but nothing works.
To be clear, I only want to overwrite specific changes, not everything.
* If you want remove all local changes from your working copy, simply stash them:
git stash save --keep-index
If you don't need them anymore, you now can drop that stash:
git stash drop
If you want to overwrite only specific parts of your local changes, there are two possibilities:
Commit everything you don't want to overwrite and use the method above for the rest.
Use git checkout path/to/file/to/revert for the changes you wish to overwrite. Make sure that file is not staged via git reset HEAD path/to/file/to/revert.
或者git checkout HEAD^ file/to/overwrite
git pull
---