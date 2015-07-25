# 工具使用说明

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
