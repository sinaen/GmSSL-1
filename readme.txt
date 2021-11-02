
windows 编译：

https://blog.csdn.net/kuaxianpan2004/article/details/104397521

perl Configure VC-WIN32


32位编译
首先从github上拉取最新的源码。

安装以下工具：
1.VS2017(我是用的这个版本，其他的版本没试过),
2.ActivePerl： ActivePerl-5.28.1.0000-MSWin32-x64-432e1938.exe
3.NASM： nasm-2.14.03rc2-installer-x64.exe

以管理员身份打开Visual Studio Tools下的Developer Command Prompt for vs2017控制台，cd到源码目录下，运行以下命令：

perl Configure VC-WIN32
nmake
nmake install
1
2
3
这时，第一个命令会发生错误：

Can't locate Win32/Console.pm in @INC (you may need to install the Win32::Console module)
1
此时，在控制台运行下面命令：

perl -MCPAN -e shell

install Win32:Console
1
2
3
再下载如下链接的site，替换perl安装目录下的site目录（默认是路径是C:/Perl64/site）
https://download.csdn.net/download/u011234288/10346624

执行perl Configure VC-WIN32便可以配置成功了，之后运行

nmake
nmake install
1
2
便可编译、安装成功，安装的默认路径是C:\Program Files (x86)\GmSSL。运行bin目录下的gmssl.exe，如下图所示，说明安装成功了。


64位编译
工具还是那三个，安装完成之后，以管理员身份打开Visual Studio Tools下的x64 Native Tools Command Prompt for vs2017控制台，cd到源码目录下，运行以下命令：

perl Configure VC-WIN64A
nmake
nmake install
1
2
3
perl Configure VC-WIN64A碰到了问题，可用32位编译里的方法解决。
编译、安装完成之后，安装的默认路径是C:\Program Files\GmSSL。运行bin目录下的gmssl.exe，如下图所示，说明安装成功了。


下一篇将介绍如何在windows下编译GmSSL-GO，以供go语言调用GmSSL提供的接口。
————————————————
版权声明：本文为CSDN博主「luoning12」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/kuaxianpan2004/article/details/104397521

