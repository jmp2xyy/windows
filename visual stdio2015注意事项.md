��¼ 781720849@qq.com
	tangziliang456



1.���ܿ���ѶTGP
2.system("pause")ͷ�ļ���stdlib.h
3.��ctrl+F5�����г���
4.�鿴�����벽�裺F9���öϵ㣬F5��ʼ���ԣ�����-����-����࣡
5.�ı䱳����ɫ�����ߡ���ѡ�������
6.scanf��scanf_s
����#pragma warning(disable:4996)
7.��release x86 
8.����Visual Stdio2015 ��д������
�ο���ַ��������ǹ���Nasm�ģ��о��������ڿ���ʹ��masm�ˣ�http://blog.csdn.net/x356982611/article/details/51260841
	1���½���Ŀ�����ұߣ��һ���Ŀ���ԣ�����������Զ���ѡ��masm��ѡ����֮���������������asm�ļ�����.cpp��׺�޸�Ϊ.asm��Ȼ�����ұߵ�.asmԴ�ļ����һ��������ԡ�����Ŀ����ѡ��Microsoft Macro Assembler����ֻ����������������ѡ�����Զ���masm���������￴��Microsoft Macro Assembler�����Ŀ���ͣ�Ȼ��Ϳ���ʹ�����ϵ�Դ������
	����������ӣ�VS projects��p386.����FindArray���ܣ�������������е����������ǻ�࣬��������ǵ��õĺ����ǻ����룬�м���������޸ģ����޸��޷�ͨ�����룩
	
	2.����ʹ��Irvine32.inc���ο�http://blog.csdn.net/sxhelijian/article/details/74853459��
	���ұ�*.asm���ԡ���Microsoft����general����include path�������D:\RadASM\masm32\include������Irvine32.inc���ļ�Ŀ¼����
��Ŀ�����С����������������롪���������������Irvine32.lib�������С������ӿ�Ŀ¼���D:\RadASM\masm32\lib�����ǿ��ļ�Ŀ¼����ҳ����������Բ��ø�
	3.����������������ʹ��Irvine32.inc�����C�����е��û�ຯ���������޷�����ڻ������е���C������C�⺯��
	https://bbs.pediy.com/thread-20233.htm�����ҳ˵���Խ�.h��C�⺯��ͷ�ļ�ת��Ϊ.inc���ͷ�ļ�����ʵ�ֻ�����C�⺯����������Ҫ���ߣ�δ��װ��
9.VS�Դ�ͷ<stdafx.h>,����Ҫ���ڴ����и���
10.���˽������Ŀ�������ԡ����������ԡ�������������ϵͳ������ϵͳ���ڴ����ұߣ�����������ѡ�����̨��/subsystem:console��
11.���ڡ�Error: "const char *" ���͵�ʵ���� "LPCWSTR"���͵��ββ����ݡ�����Ľ����������Ŀ�������ԡ������桪���ַ�������ʹ�ö��ֽ��ַ���
12.����DLL�Ĵ�����ֱ��ѡ�񴴽�DLL������Ҳ���SDK֮��ģ�����ͨ������һ��win32����̨Ӧ�ó�����Ӧ�ó���������ѡ��DLL��������Ŀ����д��DLL����ctrl+F5���У������ļ�Ŀ¼���Ѿ�������DLL�ļ���Ȼ�������ɡ������ɽ��������F7��
����ο���https://msdn.microsoft.com/zh-cn/library/ms235636.aspx��
13.�Ҹ�����VS����װ��DLLģ���֮ǰ����д���Ĵ��붼��Ҫ���±����release�汾�ſ�������
14.����VS����LoadLibrary������Ҫ���صĶ�̬��ǰ�����L ����LoadLibrary(L"D:\\Netfairy.dll")����ᱨ��

15.��VS����socketͨ�ŵ�ʱ�򣬱����ʱ����ܻ�����һ���Ϊ����Ĵ��������������ͷ�ļ�Windows.h��Winsock2.h��˳���µģ�Ŀǰ����ͨ�������ͷ�ļ�Ϊ��
#include<WS2tcpip.h>
#include<iostream>
#include<winsock2.h>
#include <stdio.h>
#include <windows.h>
#pragma comment(lib, "wsock32.lib")
#include<ws2tcpip.h>
using namespace std;

16.����printf�����������⣺���ϵķ����������ã�
�����������Լ�cmd���Ե����⣬ֱ��ɾ��cmd��ע�������regedit����HKEY_CURRENT_USER����Console����ɾ��%SystemRoot%_system32_cmd.exe�Ϳ�����

	���Ǻ����ҵ�VS2015������������ˣ��߼�����ѡ���unicode��UTF-8��ǩ�������������Գ����ַ���unicode�ַ���
17.VS�������mysql
https://blog.csdn.net/grand910616/article/details/50197859
��ʶ��MYSQL �﷨����ʱ�������ԣ�
#pragma comment(lib, "ws2_32.lib")  
#pragma comment(lib, "libmysql.lib")������һ����Ǻ�win socketһ����ͷ�ļ���˳��Ҳ�����н��� 
		//���������ݿ�֮ǰ�����ö��������ѡ��  
		//�������õ�ѡ��ܶ࣬���������ַ����������޷���������  
		if (0 == mysql_options(&mysql, MYSQL_SET_CHARSET_NAME, "gbk")) {
			cout << "mysql_options() succeed" << endl;
		}
		else {
			cout << "mysql_options() failed" << endl;
			return -1;
		}
18.���VS2012/VS2013/VS2015�±���ĳ����޷���XP�����е�����:
   * 1. ��Ŀ�˵�->��Ŀ����->��������->����->ƽ̨���߼���ѡ��VS2013WindowsXP(v120_xp)��; 
����*2. ��Ŀ�˵�->��Ŀ����->��������->����->MFC��ʹ�ã�ѡ���ھ�̬����ʹ��MFC; 
����3. ��Ŀ�˵�->��Ŀ����->������->ϵͳ->��ϵͳ->����̨�򴰿�windows�����������Ŀ����ѡ�񣩣��ڶ���汾�����5.01�� 
����4. C/C++->��������->���п⣬ѡ�񡰶��̵߳���(/MTd)��; �����Ҫ��OEP������call security cooki�Ĵ��룬�Ͳ��������������ǰ���Ǹ����ŵ����ݺ��������⣬��ʱ�������������������ʱ��ο������5����
    5.C++/��������/���п�ĳɶ��߳�MT
    6.������VS2017����


19.2018/8/6�� �����miracl.h��MIRDEF.H ��miraclms32.lib
����Ŀ�����
#include<MIRACL.H>
#pragma comment (lib,"ms32.lib")
�Ϳ�������

�ֲ᣺https://blog.csdn.net/shuilan0066/article/details/8520337
�ο����� ����������ܵ����桷���ü��ܺ�����һ�½�




20.����ѡ�в��ֵı�����ɫ�޸ģ�https://www.cnblogs.com/a14907/p/6218873.html
�������÷����ǣ�

1. �˵�������  -�� ѡ��  -������  -���������ɫ 

2. ���ұߵ� ����ʾ��� �б����ѡ�� �� ͻ����ʾ�����á�����ͻ����ʾ���������á�

3. ���б���ұߣ������趨 ����ǰ��ɫ��  �� �� ���ɫ��



21.VS��д������ʱ������ں������Ϸ���ע�ͣ���ô�������ú�����ʱ��ͻ�����ʾע��
���磺
//aΪ1��bΪ2��cΪ3
int fun(int a,int b,int c)
{
}

int main ()
{
	fun();//�õ�ʱ��ͻ�����ʾa b c �ֱ���ʲô����
}















