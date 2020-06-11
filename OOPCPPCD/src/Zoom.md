# Day 6. 图像的缩放
在对图像的数据有了基本了解之后，可以单波段的图像视作二维的矩阵。访问二维矩阵a[row][col]的某个像素值，我们采用行、列值而得。如访问第i行第j列的像素值，即a[i][j]。
图像缩放的意思就是分别给予水平(x)和垂直(y)方向一个比例因子，改变图像的大小，之后用原始图像的像素值来填充缩放后的图像（矩阵）内容。
在这个过程中，有一个非常重要的操作，我们称之为[图像重采样](https://blog.csdn.net/LanerGaming/article/details/49207435?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522159188202719725247625540%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=159188202719725247625540&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-4-49207435.ecpm_v1_rank_ctr_v3&utm_term=%E5%9B%BE%E5%83%8F%E9%87%8D%E9%87%87%E6%A0%B7)。因为我们知道缩放比例，可以知道b[i][j]对应于a[i0][j0]的位置，经过坐标转换后，你会发现i0,j0极有可能是非整数。此时，就需要利用i0,j0周围若干个整数位置的像素值加权求得第i0行,j0列的像素值，此过程称之为重采样。

- [图像缩放的参考例子](https://blog.csdn.net/jizhidexiaoming/article/details/80305451)

- 缩放的效果图
![image](https://img-blog.csdn.net/20180514101349889?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ppemhpZGV4aWFvbWluZw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

---
|[Home](Subject.md)|
