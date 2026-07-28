+++
date = '2026-07-11T14:37:37+08:00'
draft = false
title = '本地上传github操作'
+++

## 上传GitHub指令
```
git add .  
git commit -m "blog"  
git push
```

## 本地查看blog
```
hugo server -D
```


## blog封面照片
```
image = 'cover.png'
```
如果需要给blog加上封面，请在+++ +++之中加入image
<!--
![alt text](920155234b5de694e7fbe17816275af-1.jpg)  
![一人之下头像](test-pic.webp)
-->

## blog加上iamge
先在index.md文件下建立文件夹images，将照片放在images里
比如照片power-supply.png
### HTML格式
```
<figure style="text-align: center;">
  <img src="images/power-supply.png"
       alt="开关电源设计结构图"
       width="700">
  <figcaption>图1 开关电源设计结构图</figcaption>
</figure>
```
### markdown格式
```
![开关电源设计结构图](images/power-supply.png)  
![图片说明](图片路径)
```





