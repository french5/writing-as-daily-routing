# 初步了解github和git
Git is a distributed version control system.Git is free software.
github是一个网络社群，里面有开源的很多代码、项目供使用者使用。
注册号github账号以后，在自己的git终端里可以写代码运行github页面的内容。
而git的作用就是摆脱了必须在窗口界面用鼠标操作的麻烦，直接可以运行命令达到高效工作的作用。
你可以把github当成你的远程硬盘，但是绝对比百度云盘什么的好用，因为它是可以通过git终端指令操作的。

# github的界面简介
注册号github账号以后，打开profile，就是网页内容第一行最右边一个“+”号旁的头像，点开下来菜单中有profile，这个就是你的介绍。
## 第一行的每个单词和用处
* 在小猫右边可以搜索其他人的账号，并加上关注。
* pull requests又称pr，是指多人协作完成任务时，通过一个主服务器（就好比项目负责人）那里fork（叉子叉过来）来同样的项目到自己的远程仓库，然后再下载到自己的电脑上来完成任务。这时候当你修改了复制过来的主项目的一些任务后，需要先提交给自己的远程仓库，然后再提交给主项目核对，项目负责人来决定是否接受你的pr请求。
* issues就是一个问题留言板，所有项目的合作者都可以通过阅读问题来获得答案，高效交流学习。
* Marketplace是一些增值服务，可以省略。
Explore是探索更多github用法。
* 第二行overview是总体概述，repositories叫做项目仓库，相当于你建立的一个文件库，stars表示多少人给你星。
后面的followers和following分别是随从和跟随者的账号。

* 下一行：左侧是头像区域，你的用户名和账户名还有是否follow，显示unfollow就表示你已经跟随对方了，然后是你的位置和邮箱。右侧Pinned repositories是已经建立好的项目。

# 建立一个项目仓库

如果你已经有了github账户可以建立一个项目仓库了。
* 点击New repository 然后出现要填写的Repository name，输入一个你要的英文仓库名
* Description是可选的，来描述你要建立的原因和目的。下面的Public公开选上，因为private是要付费的。
* Initialize this repository with a README.这是github让你养成一个习惯，把自己的文档以最简洁的方式让阅读者很快了解大概内容的习惯，就是建立这个README.md文件。
* 下面的选项Add.gitignore意识是忽略一些文件，建立忽略的规则。细节可以google一下。Add a license是法律声明可以省略。
* 最后点击create repository就可以了。
* 创建后，你的文库里只有一个README.md文件，要实现与git交互，只要copy这个空文库的url后，
* 再git终端中建立一个根目录：（以下指令注意有空格）
mkdir xxxx
* 然后进入：cd xxxx
* 然后git clone（url）
这样就完成了自己本地的创建了，当你要上传什么内容的话，直接放进来
* 然后：git add -xxxx
* git commit -m"提交信息"
* git push
* 第一次提交要输入username和邮箱密码，注意密码不会显示。成功后，你的远程仓库就和有你推送的文件了。
今天你可以试试，然后截图发我微信。

# fork一个项目
我想翻译psychology-of-the-stock-market，今天我翻译了3段，分别是41，43，45三处。你可以fork我的项目writing-as-daily-routine。这里会用到pull request，简称pr。
需要说明的是，fork别人的项目后，在你的远程仓库就会多了一个与别人一样名字的项目，并且会有分叉的一个标志。
然后你在用*建立一个项目仓库*的知识去git clone url到你的本地电脑中，完成你的翻译以后，git commit -m"提交信息"和git push到你的远程仓库，最后只要create pull request就可以了。
##fork的具体步骤
* 进入到要fork的主项目中比如要翻译股票心理学那个项目，进入到我那个项目的主页点击fork。![](https://ws3.sinaimg.cn/large/006tKfTcly1fkzep93wcjj30vn01e3yt.jpg)
* 第二步点击clone复制地址![](https://ws3.sinaimg.cn/large/006tKfTcly1fkzequedcbj30e806wwfc.jpg)
* 第三步进入你选择的文件根目录，git clone [这里是你复制的那个地址]。这样就算是把对方的项目完整fork下来了。
## 如果这个项目需要协同完成，比如说我翻译前半章，你翻译后半章，那怎么办呢？
我翻译的时候我的项目会更新，所以你要先同步更新我的项目。
更新主页方法：
* （第一次使用要，添加主项目仓库，并命名为 upstream，方便以后再次调用，以后就不用这一步了直接后面三步。
> git remote add upstream 
https://github.com/french5/psychology-of-the-market-translation.git）以后就直接下面步骤
* git fetch upstream master
* git merge upstream/master
* git push
## 如果你也翻译完部分需要提交给我（主项目仓库）怎么做呢？
cd进入到根目录：
* git add -A(文件)
* git status
* git commit -m"写提交信息"
* git push 
向主项目发起pull request![](https://ws3.sinaimg.cn/large/006tKfTcly1fkzfd3zzrhj30bj01s74c.jpg)点击以后按照提示继续creat pull request。我这边会收到你的pr（pull request）在确认没有修改我的内容的前提下，我会merge合并。
* 需要注意的是，一般要先更新主页再修改，这样不会产生冲突。![](https://ws3.sinaimg.cn/large/006tKfTcly1fkzfi56w6lj30kf0anwhi.jpg)这个图示意了整个流程。
左边是你自己的项目去clone和push，右边是你fork别人的项目需要先fork然后clone，然后push到自己fork来的项目，然后pull request给主项目。
# 建议使用的编译工具

visual studio code官网下载。这个编译工具非常好用，
* 可以编辑md，json，js，html，等等扩展格式的文件。
* 而且界面中view-intergreted terminal可以进行终端操作。
* 可以直接把你的工作文件拉进来，增减文件，非常方便。
* 使用方法，先保存是什么格式，然后输入内容。有了格式它才配给你需要的功能。cmd+delete删除快捷键
# 回顾如何使用git和常用的git指令
* install git and vsc //安装git和visual studio code
* cd xxx //进入一级文件夹cd ~回到默认位置，pwd查看自己的位置，cd ..回到上一级文件夹，cd ..进入下一级文件夹，cd ../..表示下一级文件夹的某个文件。
* mkdir myproject//创建一个文件夹myproject
* cd myproject//进入这个myproject文件夹
* git init//初始化一般适用于windows操作系统，mac不需要
* git clone https://github.com/peterwufan/compositions.git//把自己的远程仓库下载到本地
* git status//查看状态
* git add file1 file2//添加很多文件
* git commit -m"content whatever"//提交到缓存，说明提交缘由
* git push//推送到自己的远程仓库
* input :user.name "peterwufan"//第一次需要输入用户名
* input :code//和密码，密码不显示。

时光机穿梭
# 编程的基本功之一就是阅读技术文档的只字不差的能力很多文献你边读边练，就可以做出来个东西，比如我按照MDN从最开始的入门一步步又在github上建立了一个属于自己的网页https://french5.github.io/my-website/
举几个例子来说明阅读提示的重要性：
现在，运行git status命令看看结果：

$ git status
* On branch master//在主分支上
* Changes not staged for commit://改变的部分还处在缓存区准备提交
* (use "git add <file>..." to update what will be committed)//更新所提交的信息，使用git add 文件1 文件2（中间有空格，一般你打出第一个字母，按tab键回补全后面，如果没出现说明有两个同样字母的文件，所以接着打到不一样的字母就可以实现tab补全）
*   (use "git checkout -- <file>..." to discard changes in working directory)//在工作区放弃修改的内容，和远程保持一致。工作区-缓存区-远程，这样一个过程，操作的两步，-git add和-git commit
*    modified:   readme.txt//告诉你已经发生的改变。

如上的操作git status以后出现的说明，要仔细认真看懂，这样就知道努力的方向了。
//后面是注释

认真阅读 git --help也可以帮助我们了解那些常用的git命令。

$ git diff readme.txt 
* diff --git a/readme.txt b/readme.txt
* index 46d49bf..9247db6 100644
* --- a/readme.md
* +++ b/readme.md
git diff顾名思义就是查看difference，知道了对readme.txt作了什么修改后，再把它提交到仓库就放心多了，提交修改和提交新文件是一样的两步，第一步是git add：
$ git add readme.md
同样没有任何输出。在执行第二步git commit之前，我们再运行git status看看当前仓库的状态：

$ git status
* On branch master
* Changes to be committed:
*  (use "git reset HEAD <file>..." to unstage)

*      modified:   readme.md

git status告诉我们，将要被提交的修改包括readme.md，下一步，就可以放心地提交了：

$ git commit -m "add distributed"
* [master ea34578] add distributed
* 1 file changed, 1 insertion(+), 1 deletion(-)
提交后，我们再用git status命令看看仓库的当前状态：

$ git status
* On branch master
* nothing to commit (working directory clean)
Git告诉我们当前没有需要提交的修改，而且，工作目录是干净（working directory clean）的。