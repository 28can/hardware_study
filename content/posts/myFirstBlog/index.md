+++
date = '2026-07-11T14:37:37+08:00'
draft = false
title = '本地上传github操作'
+++

## 上传GitHub指令

```powershell
git add .  
git commit -m "blog"  
git push
```

### 推送失败  

`git push`之后出现以下问题：  

```bash
client_loop: send disconnect: Connection reset by peer  
-客户端在发送断开连接信息时，连接被对方重置。
send-pack: unexpected disconnect while reading sideband packet  
-Git 在读取远程返回的数据包时，连接意外中断。
fatal: the remote end hung up unexpectedly  
-致命错误：远程服务器意外断开了连接。
```

处理办法：  

```bash
git rev-parse HEAD
git ls-remote origin refs/heads/main
-如果两条命令显示的哈希相同，并且开头都是：
-f72cb78
-说明实际上已经推送成功，不需要再操作。
git push origin main
```

## 本地查看blog

```powershell
hugo server -D
```

## blog封面照片

```bash
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

```bash
<figure style="text-align: center;">
  <img src="images/power-supply.png"
       alt="开关电源设计结构图"
       width="700">
  <figcaption>图1 开关电源设计结构图</figcaption>
</figure>
```

### markdown格式  

```bash
![开关电源设计结构图](images/power-supply.png)  
![图片说明](图片路径)
```

## 添加公式，识别latex

在+++ +++之间加入

```bash
math = true
```

## 围栏代码块

在三个反引号```之后添加 `powershell`、`bash` 或 `text`，可以指定代码块的语言。

- Windows PowerShell 命令：推荐使用 `powershell`
- Git Bash、Linux、macOS 终端：推荐使用 `bash`
- 不需要语法高亮的普通内容：使用 `text`