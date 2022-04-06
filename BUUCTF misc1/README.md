## 金三胖
gif逐帧看
## 二维码
没有扫出来啥有用信息

binwalk分离出个加密txt ，4number，爆破即可

![](https://img-blog.csdnimg.cn/04e8896789bb4246a4463f64c62e02b6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16)
![](https://img-blog.csdnimg.cn/2ce64df08b374d71bd5561cefb3ef134.png)



注意将CTF换成flag  

## 你竟然赶我走
010底部

## N种方法解决
下载附件得到是exe文件，我的电脑我打不开，重命名txt打开 是个base64 但是转码是PNG的文本内容，

所有这个是图片转base64 ，还是我第一次遇到
![](https://img-blog.csdnimg.cn/707d747070d9421e98889d3b7eea4865.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16)



## 大白
题目：看不到图？ 是不是屏幕太小了

010修改图高

## 基础破解


4数字暴力破解 + bsae64解码

## 乌镇峰会种图
题目：乌镇互联网大会召开了，各国巨头汇聚一堂，他们的照片里隐藏着什么信息呢？

010底部就是flag，以为不是预期解，看了wp还真是差不多这样写，



## 文件中的秘密 
小明经常喜欢在文件中藏一些秘密。时间久了便忘记了，你能帮小明找到该文件中的秘密吗？
![请输入图片描述][1]
备注



## LSB
第一次做lsb隐写，了解了一下后操作，这应该是最简单的类型

最低位处理后文本中没有flag 就保存一个png 得到一个二维码是flag 
![请输入图片描述][2]


## wireshark
黑客通过wireshark抓到管理员登陆网站的一段流量包（管理员的密码即是答案) 

很顺利找到 
![请输入图片描述][3]


## rar
这个是一个rar文件，里面好像隐藏着什么秘密，但是压缩包被加密了，毫无保留的告诉你，rar的密码是4位纯数字。

无脑去爆破，寄了

zip伪加密
010伪加密去除



保存不成功 直接另存新文件 

## qr
直接扫码（写题解练打字）

## 被嗅探的流量
追踪流里藏着flag

## 镜子里面的世界
以为突破口在 这些data上面 ，但好像没有用
![请输入图片描述][4]
正解依然是lsb
![请输入图片描述][5]


  

## nwalk 分离 
四位数字密码爆破
 
## 小明的保险箱
binwalk 分离 四位数字密码爆破

## 爱因斯坦
binwalk 分离  密码隐藏在注释里，此地无银三百两
![请输入图片描述][6]


## easycap
追踪流打开

## 隐藏的钥匙
路飞一行人千辛万苦来到了伟大航道的终点，找到了传说中的One piece，但是需要钥匙才能打开One Piece大门，钥匙就隐藏在下面的图片中，聪明的你能帮路飞拿到钥匙，打开One Piece的大门吗？

看这题目还以为是修改高度，没想到010打开后有这玩意
![请输入图片描述][7]
##另外一个世界

![请输入图片描述][8]
二进制转ASCII，   刚开始还换错了，又找半天信息，狗屁网站

## FLAG
binwalk 分离无果 stegslove发现是个压缩包
![请输入图片描述][9]


保存个zip出来了但是提示文件破坏，打开后是txt文本 ，里面找到了flag 
![请输入图片描述][10]
 

## 假如给我三天光明

![请输入图片描述][11]
这玩意是盲文啊，涨知识了，
![请输入图片描述][12]


 密码 kmdonowg ,解压到一个.wav文件

工具打开
![请输入图片描述][13]


摩斯密码

-.-./-/..-./.--/.--././../-----/---../--.../...--/..---/..--../..---/...--/-../--.. 

之前的解码网站又拉了，又换了网站才出来

记得换成小写

          

##神秘龙卷风
爆破出来后

![请输入图片描述][14]

brainfuck

[brainfuck解码网站][15]

## 后门查杀
小白的网站被小黑攻击了，并且上传了Webshell，你能帮小白找到这个后门么？(Webshell中的密码(md5)即为答案)。

新知识 webshell查杀工具D盾[D盾下载][16]

用D盾打开题目附件，查看已知后门
![请输入图片描述][17]


## 数据包中的线索
复制这一堆去图片转bsae64 

![请输入图片描述][18]

## 荷兰宽带数据泄露            
     新的工具新知识routerpassview           查看路由器信息

  看wp知道username的值就是flag 
![请输入图片描述][19]
           

## 来首歌吧
熟悉的操作
![请输入图片描述][20]

    ..... -... -.-. ----. ..--- ..... -.... ....- ----. -.-. -... ----- .---- ---.. ---.. ..-. ..... ..--- . -.... .---- --... -.. --... ----- ----. ..--- ----. .---- ----. .---- -.-.

[摩斯密码 摩斯密码表 摩尔斯电码转换 (ip138.com)][21]



## webshell后门
朋友的网站被黑客上传了webshell后门，他把网站打包备份了，你能帮忙找到黑客的webshell在哪吗？(Webshell中的密码(md5)即为答案)。

依旧是D盾扫
![请输入图片描述][22]


## 面具下的flag
图片下面分离出了一个zip文件 ，然后伪加密处理一下

得到一个flag.vmdk ，打不开就直接.txt了
![请输入图片描述][23]


 得到个这玩意 ，一段brainfuck 一段 ook，尝试去解密了，brain解了一点，ook解不出

方法肯定是错了

 看了正确姿势，学习一下新知识点

在kali里使用7z解压flag.vmdk（不晓得为啥）

> 7z x flag.vmdk -o./

![请输入图片描述][24]


[Brainfuck/Ook][25]



flag{N7F5_AD5_i5_funny!}

## 九连环
套娃啊

binwalk分离出压缩包，里面还是加密的压缩包，是伪加密，

打开后给了一张图片，和一个加密的flag.txt

我想密码就是图片里隐藏的信息吧，试了常见的方式啥都没出来

好吧，又是新知识

kali安装一下 steghide

> apt-get install steghide

命令：

> steghide extract -sf 文件

![请输入图片描述][26]

 找这个ko.txt 还废了点劲，gbk能看到
![请输入图片描述][27]
 


​


  [1]: https://img-blog.csdnimg.cn/9ee448659d7348b1947746cc6c23e000.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [2]: https://img-blog.csdnimg.cn/b7b91139e40b4f6a952e5e1146159163.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [3]: https://img-blog.csdnimg.cn/6482a0c0d4bd4725adf907233f6c0ea0.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [4]: https://img-blog.csdnimg.cn/e11d2922a88e4cfc91efed3525129473.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_17,color_FFFFFF,t_70,g_se,x_16
  [5]: https://img-blog.csdnimg.cn/20337b8fc0b3402d8b7a0d021f403311.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [6]: https://img-blog.csdnimg.cn/c312f26ad16b4fe2a66b9a4c67c8deb6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_19,color_FFFFFF,t_70,g_se,x_16
  [7]: https://img-blog.csdnimg.cn/0ed3be629c074497bc1d446ebdee7bfb.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [8]: https://img-blog.csdnimg.cn/717494b991f84ebeb2bc1b5cdc65ca7e.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [9]: https://img-blog.csdnimg.cn/711484a76a3c4c2dbee8644a53c6fc56.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [10]: https://img-blog.csdnimg.cn/87e464cb40fc4c2bb4b5f895d7514d59.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [11]: https://img-blog.csdnimg.cn/953c1ead929c4923b455a4aad28bd32b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [12]: https://img-blog.csdnimg.cn/img_convert/c55414215bfa585c99837f85660181e0.png
  [13]: https://img-blog.csdnimg.cn/3e41f0bc4521469e8bc7610f28058882.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [14]: https://img-blog.csdnimg.cn/7f1eb6d6d01942a29fb91e2cc1558901.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [15]: https://copy.sh/brainfuck/
  [16]: https://www.d99net.net/
  [17]: https://img-blog.csdnimg.cn/3767a482cb814e31a5b1c31b1788725c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [18]: https://img-blog.csdnimg.cn/db4b5f903270480b84bfe64c39040510.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [19]: https://img-blog.csdnimg.cn/8717aa37da1d42abbf2fadd56ba3320c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [20]: https://img-blog.csdnimg.cn/e9c4bf255d6c4ba3885bb787451c2cb7.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [21]: https://www.ip138.com/mosi/
  [22]: https://img-blog.csdnimg.cn/48d7b453007c44a0b8b28ec603fe7f3b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [23]: https://img-blog.csdnimg.cn/0f1a8670637b4b9e969cdea87dfeb458.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [24]: https://img-blog.csdnimg.cn/3072e4500a9445cda872049ff965b416.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16
  [25]: https://www.splitbrain.org/services/ook
  [26]: https://img-blog.csdnimg.cn/f41084d26ed14283b3293dadb68bc14b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_19,color_FFFFFF,t_70,g_se,x_16
  [27]: https://img-blog.csdnimg.cn/ab064e6211f2449e8000c8d1a9359e71.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_17,color_FFFFFF,t_70,g_se,x_16
