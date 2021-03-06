# 博客园自动上传图片

​	最近用Typora写博客，发现包括博客园在内的其他博客之类的网站，无法一次把文章整体上传，图片需要一张一张的上传，麻烦的要死，所以就萌生了搞个自动上传图片工具的想法。

​	本工具，只需要输入一次cookie信息即可，不用重复登陆。

​	可以把博客园当成图床来使。

# 整体思路

## 寻找上传图片的接口
![image-20200508115700805](https://github.com/lisztomania-Zero/cnblogs-Automatically-upload-pictures/blob/master/%E5%9B%BE%E7%89%87/image-20200508115700805.png)

![image-20200508101855127](https://github.com/lisztomania-Zero/cnblogs-Automatically-upload-pictures/blob/master/%E5%9B%BE%E7%89%87/image-20200508101855127.png)

## 经过抓包发现上传接口

![image-20200508102521047](https://github.com/lisztomania-Zero/cnblogs-Automatically-upload-pictures/blob/master/%E5%9B%BE%E7%89%87/image-20200508102521047.png)

## 编写脚本

大家看代码哈！很简陋的代码，能用。后续再改进。

经过优化，使用了多线程，速度一下上去了。

##  Cookie获取

### Chrome

访问（显示要登陆的时候，登陆一下）：https://upload.cnblogs.com/imageuploader/upload?host=www.cnblogs.com&editor=4#md-editor

然后按F12

![image-20200512001414455](https://github.com/lisztomania-Zero/cnblogs-Automatically-upload-pictures/blob/master/%E5%9B%BE%E7%89%87/image-20200512001414455.png)

再按Ctrl+R，点击一下图示所圈

![image-20200512001502330](https://github.com/lisztomania-Zero/cnblogs-Automatically-upload-pictures/blob/master/%E5%9B%BE%E7%89%87/image-20200512001502330.png)

鼠标滑轮向下滑，找到图示所圈，复制相应的Cookie即可

![image-20200512001657851](https://github.com/lisztomania-Zero/cnblogs-Automatically-upload-pictures/blob/master/%E5%9B%BE%E7%89%87/image-20200512001657851.png)

## 使用方法

python cnblogs_upload.py

.Cnblogs.AspNetCore.Cookies:输入此cookie

.CNBlogsCookie:输入此cookie

file_path:输入文件绝对路径

稍等片刻即可



## 效果展示

![image-20200508105948839](https://github.com/lisztomania-Zero/cnblogs-Automatically-upload-pictures/blob/master/%E5%9B%BE%E7%89%87/image-20200508105948839.png)

![image-20200508110243175](https://github.com/lisztomania-Zero/cnblogs-Automatically-upload-pictures/blob/master/%E5%9B%BE%E7%89%87/image-20200508110243175.png)
