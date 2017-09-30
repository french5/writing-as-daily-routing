# 初步了解github和git

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
* Initialize this repository with a README.这是github让你养成一个习惯，把自己的文档以最简洁的方式让阅读者很快了解大概内容的习惯。
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

# 建议使用的编译工具

visual studio code官网下载。这个编译工具非常好用，
* 可以编辑md，json，js，html，等等扩展格式的文件。
* 而且界面中view-intergreted terminal可以进行终端操作。
* 可以直接把你的工作文件拉进来，增减文件，非常方便。
* 使用方法，先保存是什么格式，然后输入内容。有了格式它才配给你需要的功能。

# 编程的基本功之一就是阅读技术文档的只字不差的能力很多文献你边读边练，就可以做出来个东西，比如我按照MDN从最开始的入门一步步又在github上建立了一个属于自己的网页https://french5.github.io/my-website/
