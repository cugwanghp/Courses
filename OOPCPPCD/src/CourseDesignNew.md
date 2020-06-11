# 计算机高级语言课程设计-2

## 目录
- [课设要求](#课设要求)
- [课设时间安排](#课设时间安排)
- [课设内容](#课设内容)
- [附录](#附录)

## 课设要求
### 内容提要
本次课设的内容，即在[上学期课设](./CourseDesign.md)的基础上，开发一个带界面的图像处理小程序。上学期的代码，可以复用。

本次课设的重点，是进一步巩固面向对象的程序设计思想、编码水平以及GUI程序的设计。
	1. 图像的显示，用视图显示；
	2. 增加菜单，映射对应功能
	3. 增加界面输入参数，得到处理结果
    有关图像处理的功能，可以扩展。。

### 课设报告要求
- [课设模板](https://github.com/cugwhp/OOPCPP/tree/master/docs/Projects/RSImage/%E8%AF%BE%E7%A8%8B%E8%AE%BE%E8%AE%A1%E6%8A%A5%E5%91%8A%E6%A8%A1%E6%9D%BF.doc)


## [课设时间安排](./CourseDesignScheduleNew.md)
课程设计1.5周。其机房和时间安排如下：

|  次数  |  日期   |  星期  |  午别  |  机房  |  备注  |
| :--: | :---: | :--: | :--: | :--: | :--: |
|  1   | 6.4  |  一   |  晚   | 101  |      |
|  2   | 6.5  |  二   |  晚   | 101  |      |
|  3   | 6.6  |  三   |  晚   | 101  |      |
|      | 6.7  |  四   |  休息 | N/A  |  |
|  4   | 6.8  |  五   |  晚   | 101  |  **中期检查** |
|  5   | 6.9  |  六   |  下   | **102** |      |
|  6   | 6.10 |  日   |  晚   | 101  |      |
|  7   | 6.11 |  一   |  晚   | 101  |  |
|      | 6.12 |  二   |  休息 | N/A |  |
|  8   | 6.13 |  三   |  晚   | 101  | **终期检查** |
- **上课时间  |下午：<u>14:30--17:30PM</u>  | 晚上：<u>19:00-22:00PM</u>**

## 课设内容
### [Day 0：准备工作](./D0_Preparation.md)
Qt的下载、安装、配置和帮助等

### [Day 1：构建框架](./D1_Frame.md)
搭建Qt程序框架，具备菜单、视图等基本要素。

### [Day 2：图像显示](./D2_FileIO.md)
在CRSImage读取文件的基础上，扩展图像显示的功能。

### [Day 3：图像信息输出](./D3_Information.md)
将图像的基本信息显示在对话框中，基本信息包括：图像行列值、投影参数及元数据信息等。

### [Day 4：图像统计量计算](./D4_Statistics.md)
将每个波段的最大值、最小值、均值、方差、直方图以图形化界面展示出来。

### [Day 5: 功能移植 ](./D5_ImageProcess.md)
将已有的图像滤波、图像缩放等功能移植到GUI下。

## 附录
### [Qt配置](./QtSetup.md)
### [The Basic of Remote Sensing Image](https://github.com/cugwhp/OOPCPP/tree/master/docs/Projects/RSImage/Basic_RS_Image.pdf)
### [Top 4 Open Source Image Lib](./Top4ImageLib.md)