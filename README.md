xunlei-lixian-web
=================

迅雷离线下载脚本的WebUI
须与迅雷离线下载脚本配合使用： https://github.com/iambus/xunlei-lixian

### 声明
迅雷离线下载为会员功能。非会员无法使用。

Quick start
-----------

假设已完成后面所说的安装步骤，程序文件存放在：~/python/xunlei-lixian-web，下载的文件存放位置在：~/download，使用方法如下：

    cd ~/download  
    python ~/python/xunlei-lixian-web/src/start.py

用浏览器打开：

    http://localhost:8180/xunlei  --  本机

或

    http://xxx.xxx.xxx.xxx:8180/xunlei  --  IP为xxx.xxx.xxx.xxx的下载主机


网页只提供以下几个基本功能：

* 登录
* 列出所有有效任务（未过期，未删除的）
* 可删除任务（离线任务）
* 可下载到本机（或下载主机），路径为当前目录（如上面的~/download）
* 可取消未开始的下载任务（下载到本机的任务，不是离线任务）

其它功能请使用迅雷离线官方网页版

安装指南
--------

* 安装git（非github用户应该只需要执行第一步Download and Install Git）
<pre>
http://help.github.com/set-up-git-redirect
</pre>
* 下载代码（Windows用户请在git-bash里执行）
<pre>
cd ~/python
git clone git://github.com/raptorz/xunlei-lixian-web.git
cd xunlei-lixian-web/src/
git clone git://github.com/iambus/xunlei-lixian.git lixian
touch lixian/\__init__.py
</pre>
* 安装Python 2.x（请下载最新的2.7版本。3.x版本暂不支持。）
<pre>
http://www.python.org/getit/
</pre>
* 安装bottle，sqlalchemy和bottle-sqlalchemy
<pre>
sudo pip install bottle
sudo pip install sqlalchemy
sudo pip install bottle-sqlalchemy
</pre>

* 在命令行里运行
<pre>
cd ~/download
python ~/python/xunlei-lixian-web/src/model.py
python ~/python/xunlei-lixian-web/src/start.py
</pre>

####注意：上面第二句仅用于在第一次运行时创建数据库，以后重新启动程序不需要第二句。（感谢 turygo, goxofy, zhasm 提醒）

一些提示
--------

1. 你可以创建一个启动脚本让它在开机的时候启动，具体方法视操作系统而定，这里不提供。
1. 你可以使用离线脚本自身的配置功能来指定下载文件的存放路径。详见原项目文档。
1. 我只在FreeBSD/Ubuntu/MacOSX三个系统下试过，基本上没啥问题。Windows用户建议还是去用官方客户端吧。
1. 浏览器只试过FireFox和Chrome。
1. FreeBSD用户要注意，离线脚本默认使用的是wget，需要单独安装（Linux一般默认自带wget，FreeBSD默认的下载工具是fetch），或者参考离线脚本的官方说明使用其它下载工具（比如aria2）。
1. 另外，FreeBSD要修改shell的默认编码方式为UTF-8，否则可能下载出错（如果碰到非英文文件名的话）。


Change log
----------

* 修复在bottle 0.12及以上版本运行出错的bug。（感谢zhasm提醒）

许可协议
--------

xunlei-lixian-web使用MIT许可协议。

此文档未完成。
--------------
