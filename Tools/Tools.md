# 工具使用说明

## Markdown

下面是一些Markdown的使用参考链接：
* [Markdown Tutorial](http://markdowntutorial.com/)：一个交互式的Markdown教程
* [Markdown Basics - GitHub](https://help.github.com/articles/markdown-basics/)：GitHub上的一个简单的Markdown语法列表
* [GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/)：GitHub上特有的Markdown语法列表，提供了更加丰富的功能，比如不同语言代码的彩色高亮显示

## GitHub for Windows

[GitHub for Windows](https://windows.github.com)是[GitHub](https://github.com)提供的在Windows上管理GitHub上文件的工具。使用浏览器登录GitHub只能编辑和创建文本文件。而使用GitHub for Windows则可以移动文件，创建二进制文件（比如图片等）。

在安装GitHub for Windows时，会弹出窗口要求安装*.NET framwork*，请务必安装，否则无法正常使用。

安装完成之后，需要将GitHub上的文件clone到自己的电脑上，之后才能在自己电
脑上对文件和目录进行修改。如下图所示，点击左边的加号，然后点击Clone，并
选择需要clone的repository。

![Clone GitHub repos to Windows](figures/github-windows-clone.png?raw=true)


## Sublime Text

[Sublime Text](http://www.sublimetext.com/)是一个文本编辑器（Editor），
可以用来集成开发多种语言。Sublime Text 3是其未来主要开发的版本，不过目
前最新的稳定版本是Sublime Text 2，可以在
[Sublime Text 2下载页面](http://www.sublimetext.com/2)获取并免费使用。
注意根据自己电脑的版本来下载相应地安装文件，比如如果是Windows的64位系统，
那么就点击Windows 64bit那个链接。

![Sublime Text Download](figures/sublime-download.png?raw=true)

### 配置

#### 安装Package Control

Sublime Text是一个文本编辑器，它可以通过各种Package扩展来完成更多丰富的功能。[Package Control](https://packagecontrol.io)是Sublime Text的一个Package控制管理器，用它可以方便地安装和管理Sublime Text的Packages。

打开[Package Control的安装网页](https://packagecontrol.io/installation)，然后按照左栏"Simple"中的说明，复制跟你下载的Sublime Text版本一致的安装代码，比如如果是Sublime Text 2，那么就是类似下面的代码（其实这就是一段Python代码）：

```python
import urllib2,os,hashlib; 
h = 'eb2297e1a458f27d836c04bb0cbaf282' + 'd0e7a3098092775ccb37ca9d6b2e4b7d'; 
pf = 'Package Control.sublime-package'; 
ipp = sublime.installed_packages_path(); 
os.makedirs( ipp ) if not os.path.exists(ipp) else None; 
urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); 
by = urllib2.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); 
dh = hashlib.sha256(by).hexdigest(); 
open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; 
print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation') 
```

然后打开Sublime Text，打开Sublime Text的console（打开后是位于窗口下方的一个白色的输入框），将安装代码粘贴，最后回车即可。之后会提示说重启Sublime Text（注意：这个过程中还会多次提示重启Sublime Text）。最后，在Sublime Text的菜单Preferences下就会有Package Control这个选项，表示安装成功。

##Sublime text2 C/C++ 编译环境设置(原文地址http://blog.sina.com.cn/s/blog_6e7384df0101qzya.html)

###下载安装Sublime text2 for windows
下载地址：http://www.sublimetext.com/

###下载安装 MinGW 与系统变量设置

#####2.1本文使用的C/C++编译器是gcc/g++，所以需要下载安装MinGW（下载地址：http://sourceforge.net/projects/mingw/）

安装完成后会让用户选择需要下载的Package
选择要下载的Package：

选择 MinGW Compiler Suite之后，添加 The GNU C++ Compiler 的相关项即可。

####2.2 设置环境变量
右击我的电脑，点属性->高级->环境变量。
在环境变量PATH 添加系统 MinGW 的实际安装位置,如: D:\Program Files\MinGW 或者比如本文中演示的C:\MinGW\bin。在PATH里加入C:\MinGW\bin（具体路径请根据你的MinGW选择）。如果PATH里面还有其他的变量，记得要加个英文半角分号。一般 PATH 中的变量会非常的多,不同变量之间使用;分隔。
新建LIBRARY_PATH变量，如果有的话，在值中加入C:\MinGW\lib，这是标准库的位置。
新建C_INCLUDEDE_PATH变量，值设为C:\MinGW\include。
检查变量设置：Win+R输入: cmd ,在命令行中输入: g++ -v ,有内容输入证明环境变量配置正确.如果出现 'g++' 不是内部或外部命令，也不是可运行的程序或批处理文件。检查上一步配置. 

###三、Sublime Building System 设置
Windows下，要在Sublime Text 2中实现编译、运行C/C++代码，需要修改或新建一个C++编译配置。
具体是：Sublime Text 2中Tools -> Build System -> New Build System
输入如下内容，并将文件保存为C++Bulider.sublime-bulid。

{
     "cmd": ["g++", "${file}", "-o", "${file_path}/${file_base_name}"],
     "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
     "working_dir": "${file_path}",
     "selector": "source.c, source.c++",
     "encoding": "cp936",
     "shell": true,


     "variants":
     [
          {
               "name": "Run",
               //"cmd": ["CMD", "/U", "/C", "g++ ${file} -o ${file_base_name} && ${file_base_name}"] 
               "cmd": [ "start", "${file_path}/${file_base_name}.exe"]
          }
     ]
}

###编译测试


经过以上步骤搭建好C/C++编译环境后，就可以在Sublime Text 2中编译运行C/C++代码了。
如图所示：
ctrl+B：生成
ctrl+shift+B：运行


生成的可执行文件在cpp同目录下：
