# OpenCVDemo

![OpenCV for iOS](http://upload-images.jianshu.io/upload_images/2251123-b1539f93bb74b474.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 关于OpenCV

## 简介

> OpenCV (Open Source Computer Vision Library)是一个在BSD许可下发布的开源库，因此它是免费提供给学术和商业用途。有C++、C、Python和Java接口，支持Windows、Linux、MacOS、iOS和Android等系统。OpenCV是为计算效率而设计的，而且密切关注实时应用程序的发展和支持。该库用优化的C/C++编写,可以应用于多核处理。在启用OpenCL的基础上，它可以利用底层的异构计算平台的硬件加速。
>
> ​                                                                                                                      from opencv.org

## OpenCV的模块

从[官方文档]([http://docs.opencv.org/2.4/modules/core/doc/intro.html)中我们可以看到其包含模块以及对iOS的支持情况。

>* core：简洁的核心模块，定义了基本的数据结构，包括稠密多维数组 Mat 和其他模块需要的基本函数。

>* imgproc：图像处理模块，包括线性和非线性图像滤波、几何图像转换 (缩放、仿射与透视变换、一般性基于表的重映射)、颜色空间转换、直方图等等。

 >* video：视频分析模块，包括运动估计、背景消除、物体跟踪算法。

>* calib3d：包括基本的多视角几何算法、单体和立体相机的标定、对象姿态估计、双目立体匹配算法和元素的三维重建。

>* features2d：包含了显著特征检测算法、描述算子和算子匹配算法。

>* objdetect：物体检测和一些预定义的物体的检测 (如人脸、眼睛、杯子、人、汽车等)。

>* ml：多种机器学习算法，如 K 均值、支持向量机和神经网络。

>* highgui：一个简单易用的接口，提供视频捕捉、图像和视频编码等功能，还有简单的 UI 接口 (iOS 上可用的仅是其一个子集)。

>* gpu：OpenCV 中不同模块的 GPU 加速算法 (iOS 上不可用)。

>* ocl：使用 OpenCL 实现的通用算法 (iOS 上不可用)。

>* 一些其它辅助模块，如 Python 绑定和用户贡献的算法。





## 我们可以利用OpenCV在iOS上做什么

基于OpenCV，iOS应用程序可以实现很多有趣的功能，也可以把很多复杂的工作简单化。一般可用于：

  * 对图片进行灰度处理（官方示例）

  * 人脸识别，即特征跟踪（官方示例）

  * 训练图片特征库（可用于模式识别）

  * 提取特定图像内容（根据需求还原有用图像信息）

…… 



# 导入OpenCV

------

opencv目前分为两个版本系列：opencv2.4.x和opencv3.x。

导入项目的两种方式：

## 1.从官网下载框架，引入工程。

1. 前往[OpenCV官网](http://opencv.org)或[OpenCV中文官网](http://opencv.org.cn)下载相关iOS版本framework文件，从项目引入，

1. 导入OpenCV依赖库

  * libc++.tbd

  * AVFoundation.framework

  * CoreImage.framework

  * QuartzCore.framework

  * Accelerate.framework

  * CoreVideo.framework

  * CoreMedia.framework

  * AssetsLibrary.framework



1. 引入相关头文件

```
#import <opencv2/opencv.hpp>
#import <opencv2/imgproc/types_c.h>
#import <opencv2/imgcodecs/ios.h>
#import <opencv2/highgui/highgui_c.h>
```

**注：使用OpenCV的类必须支持C++的编译环境，把.m文件改为.mm即可。**

## 2.使用CocoaPods安装。

很简单。

```

pod 'OpenCV'

```
