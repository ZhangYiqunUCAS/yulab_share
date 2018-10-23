---
title: "Yulab_cloud full version"
date: 2018-10-19T23:33:59+08:00
draft: true
tags: ["yulab_cloud"]

---

`Yulab_cloud`是使用`NextCloud`为小规模团队文件共享而创建的私有云。内置了文件管理、图片相册、日历联系人、~~两步验证~~、~~RSS阅读~~等丰富的应用。

这里会介绍`Yulab_cloud`的日常使用方法和规则。


## 声明

本网站当前仅供**实验室网络**（有线和WiFi)使用。手机流量和所外网络暂无法访问。

*   1\. 创建该网站的目的是供课题组内分享文件；

*   2\. 全体成员使用共同账号（账号：yuftp， 密码：--------）

*   3\.  上传文件之前，请再次确认。（传错了，想要删除怎么办？[点这里](https://www.baidu.com)）

> 题外话，本站处理能力和存储空间有限，上传2部高清电影就可以整垮这个服务，是的，是真的，真的，我已经试过了。    
> 大家专心传文献，读文献，早发paper，登上人生高峰，迎~~~


## 安装

点击  [>>>这里<<<](http://192.168.206.171/yulab_cloud)  进入`yulab_cloud`的登录界面。


<figure>
  <img src="http://159.226.118.232/open/upload/img/yulab_share_config/yulab_cloud-login-02.png" alt="Yulab share configure 02" width="600" height="450">
</figure>

还有基本使用介绍：

<figure>
  <img src="http://159.226.118.232/open/upload/img/yulab_share_config/yulab_cloud-login-03.png" alt="Yulab share configure 03" width="600" height="450">
</figure>


## 管理文档

+ 1. 请在 `Yulab_Share`文件夹上传|下载文档    
+ 2. 文件尽量包含日期+标题+上传人（例如：`20181024-yulab_cloud_manual-wm.pdf`）    
+ 3. `Photos`    用来存放照片的（参加聚会了，出去开会了，谁又画了一只叮当猫了，等等，都往这里放吧；同样需要你修改好名字，例如：`20181001-做实验的机器猫-LX.jpg`)    
+ 4. `Vectors_new` 保存载体（SnapGene导出的文件.dna)

### Yulab_Share/Archive

```
Archive
+--- Cell_lines     # 课题组公共细胞系
|
+--- Flystock # 共同果蝇stocks
|
+--- HiSeq # 高通量测序相关信息
|
+--- Linux_learning # 生物信息学相关资料
|
+--- Primers # 引物序列
|
+--- Proteins # 纯化蛋白清单
|
+--- Protocol # 常用的protocol
|
+--- Yulab_quip_materials # 课题组试剂耗材清单
```


### Journal_club

每次上传一个文件夹，包含以下内容：

+ 参考文献，和相关的其他文献 （PDF)

+ 阅读报告 (PPT）

+ 阅读笔记 （Word, 这个可以有) 

**修改文件夹名称**， 例如：`20181024-journal_club-gridseq-mm`

### Lab_meeting

每次上传一个文件夹，包含以下内容：

+ 上传各自的 PPT，修改名称：`20181024-lab-meeting-mm.pptx`

+ 其他相关的文档或图片等。


### Vectors

按照 `载体名称 + 基因名称 + 其他说明`的方式进行命名。

当前文件夹下的文件太复杂，命名方式没有规律，难以认识包含什么内容。

**因此**，请同学们自发的来修改，保存到最上层的目录下`Vectors_new`


### Work_report


分享有些分析结果，工作报告等。

## 电脑客户端

既然称作`云`，怎么少得了客户端访问呢。

[官方下载地址](https://nextcloud.com/install/#install-clients)

+ 1. 填入服务器地址：http://192.168.206.171/yulab_cloud

<figure>
  <img src="http://159.226.118.232/open/upload/img/yulab_share_config/desktop-app-login-01.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

+ 2. 选择“登录”

<figure>
  <img src="http://159.226.118.232/open/upload/img/yulab_share_config/desktop-app-login-02.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

+ 3. 填写用户名 ：`yuftp` 和 密码 (咨询管理员）

<figure>
  <img src="http://159.226.118.232/open/upload/img/yulab_share_config/desktop-app-login-03.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

+ 4. 选择 "授权访问"

<figure>
  <img src="http://159.226.118.232/open/upload/img/yulab_share_config/desktop-app-login-04.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

+ 5. 更改 询问确认，若同步文件大于~~500M~~, 改为 50M

在电脑D盘新建一个文件夹： `yulab_cloud`

在本地文件夹右侧填入：`D:\yulab_cloud`

<figure>
  <img src="http://159.226.118.232/open/upload/img/yulab_share_config/desktop-app-login-05.png" alt="Yulab share configure 01" width="600" height="450">
</figure>

接下来正常使用就可以了。


## 手机客户端

从手机的应用市场搜索 "nextcloud" （例如，豌豆荚）并安装。

Enjoy.

