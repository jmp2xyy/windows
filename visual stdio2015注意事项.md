登录 781720849@qq.com
	tangziliang456



1.不能开腾讯TGP
2.system("pause")头文件：stdlib.h
3.用ctrl+F5来运行程序
4.查看汇编代码步骤：F9设置断点，F5开始调试，调试-窗口-反汇编！
5.改变背景颜色：工具——选项——环境
6.scanf→scanf_s
或者#pragma warning(disable:4996)
7.用release x86 
8.关于Visual Stdio2015 编写汇编程序：
参考网址：（这个是关于Nasm的，研究了下现在可以使用masm了）http://blog.csdn.net/x356982611/article/details/51260841
	1：新建项目后，在右边，右击项目属性，生成依赖项，自定义选择masm，选择了之后，添加新项，这里添加asm文件，将.cpp后缀修改为.asm，然后在右边的.asm源文件中右击——属性——项目类型选择Microsoft Macro Assembler，（只有在生成依赖项中选择了自定义masm才能在这里看见Microsoft Macro Assembler这个项目类型）然后就可以使用书上的源代码了
	具体代码例子：VS projects中p386.测试FindArray性能（但是这个例子中的主函数不是汇编，这个例子是调用的函数是汇编代码，中间代码有所修改，不修改无法通过编译）
	
	2.关于使用Irvine32.inc（参考http://blog.csdn.net/sxhelijian/article/details/74853459）
	在右边*.asm属性——Microsoft——general——include path——添加D:\RadASM\masm32\include（就是Irvine32.inc的文件目录），
项目属性中——链接器——输入——附加依赖项添加Irvine32.lib；常规中——附加库目录添加D:\RadASM\masm32\lib（就是库文件目录）网页中其他项可以不用改
	3.以上两个解决了如何使用Irvine32.inc库和在C代码中调用汇编函数，但是无法解决在汇编代码中调用C函数和C库函数
	https://bbs.pediy.com/thread-20233.htm这个网页说可以将.h的C库函数头文件转换为.inc汇编头文件，来实现汇编调用C库函数，但是需要工具，未安装。
9.VS自带头<stdafx.h>,不需要再在代码中附加
10.闪退解决：项目——属性——配置属性——链接器——系统——子系统（在窗口右边）——下拉框选择控制台（/subsystem:console）
11.关于“Error: "const char *" 类型的实参与 "LPCWSTR"类型的形参不兼容”错误的解决方案：项目——属性——常规——字符集——使用多字节字符集
12.关于DLL的创建：直接选择创建DLL会出现找不到SDK之类的，可以通过创建一个win32控制台应用程序，在应用程序类型中选择DLL——空项目——写完DLL后不能ctrl+F5运行，但在文件目录下已经生成了DLL文件，然后点击生成——生成解决方案（F7）
具体参考“https://msdn.microsoft.com/zh-cn/library/ms235636.aspx”
13.我跟新了VS，安装了DLL模板后，之前所有写过的代码都需要重新编译成release版本才可以运行
14.关于VS中用LoadLibrary，在需要加载的动态库前面加上L 比如LoadLibrary(L"D:\\Netfairy.dll")否则会报错

15.在VS中用socket通信的时候，编译的时候可能会遇到一大堆为定义的错误，这可能是由于头文件Windows.h和Winsock2.h的顺序导致的，目前可以通过编译的头文件为：
#include<WS2tcpip.h>
#include<iostream>
#include<winsock2.h>
#include <stdio.h>
#include <windows.h>
#pragma comment(lib, "wsock32.lib")
#include<ws2tcpip.h>
using namespace std;

16.关于printf输出乱码的问题：网上的方法都不管用，
后来发现是自己cmd属性的问题，直接删除cmd的注册表：运行regedit——HKEY_CURRENT_USER——Console——删除%SystemRoot%_system32_cmd.exe就可以了

	但是后来我的VS2015后可以用中文了：高级保存选项还是unicode（UTF-8带签名），工程属性常规字符集unicode字符集
17.VS如何配置mysql
https://blog.csdn.net/grand910616/article/details/50197859
标识符MYSQL 语法错误时可以试试：
#pragma comment(lib, "ws2_32.lib")  
#pragma comment(lib, "libmysql.lib")，还有一点就是和win socket一样，头文件的顺序也可能有讲究 
		//在连接数据库之前，设置额外的连接选项  
		//可以设置的选项很多，这里设置字符集，否则无法处理中文  
		if (0 == mysql_options(&mysql, MYSQL_SET_CHARSET_NAME, "gbk")) {
			cout << "mysql_options() succeed" << endl;
		}
		else {
			cout << "mysql_options() failed" << endl;
			return -1;
		}
18.解决VS2012/VS2013/VS2015下编译的程序无法在XP下运行的问题:
   * 1. 项目菜单->项目属性->配置属性->常规->平台工具集，选择“VS2013WindowsXP(v120_xp)”; 
　　*2. 项目菜单->项目属性->配置属性->常规->MFC的使用，选择在静态库中使用MFC; 
　　3. 项目菜单->项目属性->链接器->系统->子系统->控制台或窗口windows（根据你的项目类型选择），第二项版本号设成5.01。 
　　4. C/C++->代码生成->运行库，选择“多线程调试(/MTd)”; （如果要在OEP出看到call security cooki的代码，就不能用这个！）（前面那个括号的内容好像有问题，有时候会出错。当程序有问题的时候参考下面第5条）
    5.C++/代码生成/运行库改成多线程MT
    6.或者用VS2017试试


19.2018/8/6日 添加了miracl.h、MIRDEF.H 和miraclms32.lib
在项目中添加
#include<MIRACL.H>
#pragma comment (lib,"ms32.lib")
就可以用了

手册：https://blog.csdn.net/shuilan0066/article/details/8520337
参考资料 《加密与解密第三版》常用加密函数库一章节




20.关于选中部分的背景颜色修改：https://www.cnblogs.com/a14907/p/6218873.html
具体设置方法是：

1. 菜单：工具  -》 选项  -》环境  -》字体和颜色 

2. 在右边的 “显示项：” 列表框内选择 “ 突出显示的引用”、“突出显示的书面引用”

3. 在列表框右边，可以设定 “项前景色”  和 “ 项背景色”



21.VS在写函数的时候，如果在函数的上方有注释，那么在下面用函数的时候就会有提示注释
例如：
//a为1，b为2，c为3
int fun(int a,int b,int c)
{
}

int main ()
{
	fun();//用的时候就会有提示a b c 分别是什么参数
}















