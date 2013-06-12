---
layout: post
title: "下载WWDC2013的视频"
categories:
- iOS
tags:
- WWDC


---


今年特别好的是可以在线看。

但是我比较蛋疼，我想在路上或者吃饭的时候看。

所以就蛋疼的想去下载。目前看到的视频可以直接抓包得到m3u8的地址
比如这个：
<p>http://devstreaming.apple.com/videos/wwdc/2013/204xex2xvpdncz9kdb17lmfooh/204/0400/0400.m3u8
</>

然后可以得到所有ts文件的地址比如:
<p>http://devstreaming.apple.com/videos/wwdc/2013/204xex2xvpdncz9kdb17lmfooh/204/0400/0400_00001.ts</p>

然后就可以直接用ffmpge合并转成mp4导入手机了 ...LOL

关键命令如下

先把ts文件转成mpg格式
<p>for f in *.ts ;do ./ffmpeg -i  $(pwd)/$f -y -qscale:v 1  ＃path＃/$f ;done </p> 

把所有的文件合并为一个完整的mpg文件
<p>ffmpeg -f concat -i <( for f in ＃path＃/*.ts ; do echo "file '$(pwd)/$f'"; done )  -y -c copy  output.mpg </p>

转换成mp4
<p>ffmpeg -i  output.mpg -qscale:v 2 -y -strict -2  output.mp4 </p>

P.S.国内下载几百个零散文件很慢。所以我是直接在linode的服务器上搞的。写好shell以后很快就可以搞下来，时间主要浪费在转换格式和从linode上弄回来。我在家里从linode下载大概1m/s的速度。
不过视频并不是高清的。凑合看看。收藏还是等apple后面发布了。

