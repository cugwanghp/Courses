# Day 1 - 搭建课设框架

## 目标
>根据课程课设的要求，搭建简单的遥感图像处理程序的菜单，具体的功能不予实现，只要求程序能响应用户的菜单输入即可。

## 需求分析
> 课设要求在控制台输入例如：“O”、“I”、“H”、“X"等字符，执行相应的功能。
> 此处所用到的关键点有：1）switch---case的判断分支；2）do---while循环，多次输入。

## 实现过程
1. 用户输入字符，直到输入"x"或"X"退出程序。其代码示例如下：
```c++
#include <iostream>
using namespace std;

int main()
{
  char	cCmd;
  
  do
  {
 	cin >> cCmd;
  }while(cCmd!='x' && cCmd!='X');	//cCmd=='x'or'X'，则退出循环，此处判断条件为false，
  // 即!(cCmd=='x' || cCmd=='X') ==> (cCmd!='x' && cCmd!='X')
  
  return 0;
}
```

2. 增加 switch-case判断分支
> 在上一代码片中，增加switch-case
```c++
#include <iostream>
using namespace std;

int main()
{
  char	cCmd;
  
  do
  {
 	cin >> cCmd;
 	//新增switch-case判断分支
 	switch(cCmd)
 	{
 	// 此处重点关注switch-case的语法
      case 'O':
      case 'o':
      	cout << "Menu Open." << endl;
      	break;
      case 'C':
      case 'c':
      	cout << "Menu Close." << endl;
      	break;
      case '?':
      	cout << "Menu Help." << endl;
      	break;
      case 'X':
      case 'x':
      	cout << "Menu Exit." << endl;
      	break;
      default:
      	cout << "Menu None." << endl;
      	break;
 	}
 	// switch - case end
 	
  }while(cCmd!='x' && cCmd!='X');	//cCmd=='x'or'X'，则退出循环，此处判断条件为false，
  // 即!(cCmd=='x' || cCmd=='X') ==> (cCmd!='x' && cCmd!='X')
  
  return 0;
}
```

3. 增加菜单帮助说明
> 为了保证程序的友好，我们增加菜单提示的功能，当用户输入不合法时，程序弹出提示。我们通过定义一个函数来专门负责输出提示信息，代码如下：
>
```c++
//===================================================================
// 菜单提示，命令行
//===================================================================
void Usage()
{
	cout << "############ Remote Sensing Image Process Tools.############\n";
	cout << "# X – Exit Exit\t退出程序" << endl;
	cout << "# O – Open \t打开影像文件" << endl;
	cout << "# I – Information\t输出当前图像的路径 ，行列值 、波段数 、数据类 数据类 型、排列方式等信息" << endl;
	cout << "# C –Closed\t关闭当前图像" << endl;
	cout << "# S – Statistics\t输出图像数据统计量 ，若文件未打开 ，输出提示" << endl;
	cout << "# H – Histogram\t输出图像的直方" << endl;
	cout << "# ? – Help\t输出本信息" << endl;
	cout << "# A – Save as\t输入保存的文件路径 ，输出图像为二进制文件" << endl;
	cout << "# R – Rotate\t图像旋转，输入角度逆时针" << endl;
	cout << "# Z – Zoom\t图像缩放，输入比例尺出" << endl;
	cout << "# F - Filter\t输入滤波核，输出滤波后图像" << endl;
	cout << "#################################################################" << endl;
}
```


[课设内容](./CourseDesignSubject.md)

