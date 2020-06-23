# Day 7. 图像空间域滤波
图像空间域滤波是一种邻域算子，通过对某个像素点一定范围内的邻域点（如：3*3,5*5）作用某种算子，得到一幅新的图像。空域滤波的运算过程并不复杂，比如滤波算子是3*3的矩阵，将3*3的窗口在图像的每个像元中滑动（中心对齐某个像元），卷积求和的方法得到新的像素值即为滤波后的图像。
滤波(Filter)功能的要求是：
1. 写出一个通用的卷积功能，要求卷积核的内容可以是任意方阵（通常方阵的行列数为奇数）
2. 测试以下卷积核滤波后，滤波结果图像有何差别？
  - 3*3均值滤波
$$
\begin{bmatrix}
\frac{1}{9} & \frac{1}{9} & \frac{1}{9}\\
\frac{1}{9} & \frac{1}{9} & \frac{1}{9}\\
\frac{1}{9} & \frac{1}{9} & \frac{1}{9}
\end{bmatrix}
$$

- 5*5均值滤波
$$
\begin{bmatrix}
\frac{1}{25} & \frac{1}{9} & \frac{1}{9} & \frac{1}{25} & \frac{1}{25} \\
\frac{1}{25} & \frac{1}{9} & \frac{1}{9} & \frac{1}{25} & \frac{1}{25} \\
\frac{1}{25} & \frac{1}{9} & \frac{1}{9} & \frac{1}{25} & \frac{1}{25} \\
\frac{1}{25} & \frac{1}{9} & \frac{1}{9} & \frac{1}{25} & \frac{1}{25} \\
\frac{1}{25} & \frac{1}{9} & \frac{1}{9} & \frac{1}{25} & \frac{1}{25} \\
\end{bmatrix}
$$

- 7*7均值滤波
$$
\begin{bmatrix}
\frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} \\
\frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} \\
\frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} \\
\frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} \\
\frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} \\
\frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} \\
\frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} & \frac{1}{49} 
\end{bmatrix}
$$

具体细节参考：
- [图像滤波](https://zhuanlan.zhihu.com/p/50238655)
- [图像处理参考](refs/Basic_RS_Image.docx)

---
|[Home](Subject.md) |
