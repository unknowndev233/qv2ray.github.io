---
title: 给中国大陆用户的一些建议
---

# 给中国大陆用户的一些建议

**注意：本章节独立于英语原文，是给中国大陆用户单独提供的文本。**

## Windows 操作系统的安全建议

目前，绝大多数代理工具都使用明文配置文件（比如 JSON 格式、YAML 格式）来存储代理服务器的信息。如果你的电脑被某些不值得信任的软件（比如某某卫士、某某毒霸，或者某某管家）、或者病毒程序给控制了，那么不排除你的代理服务器被 GFW 干掉的可能，甚至你的个人信息还有可能会被上报，从而被“相关部门”约谈喝茶写保证书。

有鉴于此，我们建议 Qv2ray 的使用者们能够了解并听从以下建议。

### 开启用户账户控制（UAC）

[用户账户控制（UAC）](https://zh.wikipedia.org/wiki/%E4%BD%BF%E7%94%A8%E8%80%85%E5%B8%B3%E6%88%B6%E6%8E%A7%E5%88%B6)是内置于 Windows Vista 以及更新版本操作系统（如 Windows 7、Windows 10）的一个内置功能，它用于系统的权限控制。当有一个程序试图更改系统关键配置、安装或卸载程序以及改动系统关键文件的时候，UAC 会弹出一个提示窗，询问用户是否接受此项更改。

**但是，大多数人电脑上这个功能是关闭的**。造成这种情况的原因有二。其一，一部分游戏玩家不喜欢看到游戏反作弊系统启动的时候冒出个弹窗，于是就网上找了教程，把 UAC 关闭了；其二，大多数人主动或者被动地下载了具有 Ghost WinX 等字样的系统，而这些系统为了方便会直接使用内置的超级管理员（Administrator）账户登录，这就给系统造成了安全隐患。

:::tip Administrator 账户
Windows 系统内置的超级管理员账户，默认情况下该用户账户无需通过 UAC 确认即可进行在一般情况下需要使用管理员权限才能进行的操作。不过，该账户默认是禁用的，从微软官方镜像安装的 Windows 系统都会在第一次开机的时候要求用户自行建立普通管理员账户，而普通管理员账户改动系统需要通过 UAC 弹窗确认。
:::

> **开启 UAC**
> 1. 下载 [DISM++](https://github.com/Chuyu-Team/Dism-Multi-language/releases/) 并解压，注意，你需要解压全部的文件。
> 2. 运行 DISM++，转到当前系统的“系统优化”、“安全相关设置”，将 UAC 调整为“提示我（推荐）”，同时启用用于内置管理员账户的管理员批准模式。这样一来，即使是 Administrator 账户在调用系统管理员权限的时候也需要弹窗确认。
> 3. 通过开始菜单的重启命令重启系统。

### 拒绝国产毒瘤

所谓国产毒瘤其实是指国内的各类流氓软件。很不幸的是，大部分中国网民都是国产毒瘤用户。

#### TOP-1 最毒的有：

猎豹移动旗下各类软件，主要包含金山毒霸、猎豹浏览器与驱动精灵；以及 2345 系列。

**猎豹移动**

随手来点和猎豹移动有关的网页：

> 1. [如何卸载金山毒霸-知乎](https://www.zhihu.com/question/35558854/answers/updated)
> 2. [猎豹浏览器被 Avast 报毒](http://bbs.duba.net/thread-4191273995-1-1.html)
> 3. [驱动精灵是深藏功与名的流氓软件嘛？？-知乎](https://www.zhihu.com/question/26615909)

一句话，金山毒霸已经是为了自己的金山银山而不顾用户安全与隐私之毒瘤恶霸了，其公司同门产品也都是病毒性质的软件——虽然这些个软件有点用处。

**2345 系列**

还是点网页吧，比笔者自己直接说来的靠谱。

> 1. 来自隔壁大流氓百毒的百度知道：[怎样彻底清除掉 2345 这个流氓东西](https://zhidao.baidu.com/question/1987716033979854587.html)
> 2. [如何彻底清除流氓的 2345 安全卫士及 2345SafeCenterSvc 服务？](https://blog.csdn.net/u010098138/article/details/102798992)

#### TOP-2 中等毒的有：

**360 系列**
相对于以上两者，360 表现得“不那么流氓”一些，不过其自动附带全家桶功能可谓业界“一流”。其 360 安全卫士、鲁大师更是拖慢电脑运行速度的高手。不过最重要的是，该公司有参与 GFW 项目的嫌疑，因此最好是不用。

**中国特供版 Adobe Flash Player**
由 重庆重橙网络科技有限公司 代理的版本，Adobe 与之配合做了区域限制的工作。其附带的 `FlashHelper` 具有搜集用户隐私、疯狂弹窗广告等流氓操作，可谓是“入乡随俗”。

#### TOP-3 比较毒的有：

**腾讯电脑管家**
这个软件没有上述软件那么多弹窗，杀毒能力也不错。不过腾讯有扫描 Shadowsocks 端口的前科，故而建议慎用。

::: danger 毒瘤特征：
1. 拖慢电脑，占用后台资源，甚至具有后台刷网站访问量以骗取广告费的行为。
2. 劫持浏览器首页，且电脑用户无法通过浏览器设置改回来。没法改回来的原因是这些毒瘤通过 dll 注入或者注册表修改、组策略修改，或者浏览器的企业管理模式劫持或者锁定了主页。
3. 窃取隐私，追踪用户数据与行为。
4. 疯狂广告弹窗。
:::

当然，以上只不过是笔者所知的常见毒瘤，其它的毒瘤还有很多，需要大家细心去避免。一些不得不用的毒瘤软件可以试着丢在单独的虚拟机里面。虚拟机软件 [VirtualBox](https://www.virtualbox.org/) 是完全的开源软件，可以任意地安装使用；[VMware Workstation 的 Player 版本](https://www.vmware.com/cn/products/workstation-player/workstation-player-evaluation.html) （看清楚，这不是 Pro 版本）则允许非商业的免费使用。

杀毒软件建议使用火绒安全软件、Avast、或者系统自带的 Microsoft Defender 等可信杀毒软件来替代。浏览器可以使用 [国际版 Firefox](http://getfirefox.org)（注意：最好不要使用国内的谋智版火狐）、[Google Chrome](https://www.google.cn/chrome) 或者微软自己的 [新 Edge](https://www.microsoft.com/en-us/edge) 来替代。

## 行为建议

### 不要迷恋“高速下载”与“安全下载”

中国大陆的各大下载站点（比如太平洋、中关村，以及以前的百度）都提供了“高速下载”、“极速下载”等字样的“快速”下载服务，或者是“安全下载”等服务。但是，这些其实都是大坑，因为这些高速下载都需要你下载一个高速下载器，而这个下载器就是一个软件推广器（有时候还兼任广告推送器、数据偷窃器），会给你“附送”一大把你可能（其实是非常有可能）不想要安装的软件。同时，鉴于这些下载站的嬲性，他们往往还恬不知耻地宣称自己是“官方下载”，这一点尤其要注意。一般来说，下载软件都要去软件对应的官网。不过，由于国内的主流搜索引擎是同样地只收钱办事而不理会是非因果，我们建议使用 [Microsoft Bing](https://www.bing.com)、[Magi](https://magi.com/) 或者 [Google](https://www.google.com) 来搜索软件。

>相关阅读
>[下载安装软件中遇到的一些坑——很多用户都踩过](https://www.dcdapp.com/article/6650414698405560839)
>[用百度下载软件，应该如何避免被套路](https://zhuanlan.zhihu.com/p/44237432)
>[如何避免下载一个软件时下载一大堆捆绑文件，感觉到了深深的恐惧？](https://www.zhihu.com/question/272002712)

### 要使用最新的代理软件

代理软件与其它的软件不同，一个广义上的代理软件与 GFW 的关系是道与魔相互 PK 的关系，而其它软件似乎与 GFW 也没啥可冲突的。（此处待咕）