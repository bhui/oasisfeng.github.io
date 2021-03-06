---
id: 228
title: 折腾nForce Remix Driver
date: 2007-04-04T01:48:53+00:00
author: oasisfeng
layout: post
guid: http://blog.oasisfeng.com/2007/04/04/nforce-remix-driver/
permalink: /2007/04/04/nforce-remix-driver/
dsq_thread_id:
  - "250427129"
  - "250427129"
categories:
  - Computer
  - Software
---
因为新安装LAN接入宽带的缘故，重新启用了封存已久的nForce3内置网卡。（此前一直用的无线接入，所以板载网卡基本闲置）

搜索驱动程序的时候发现nVidia的nForce3芯片组官方驱动竟然还是2005年11月的版本，虽然nForce3早已退出市场，但没有新驱动使用的滋味就好像有被遗弃一般。无意中，一款由国外网友squall_leonhart制作的nForce2/3/4系列mod驱动程序吸引了我的注意。他将目前nVidia为nForce4及以上型号所发布的驱动程序可以用于nForce2/3的组件提取出来，制成了这个mod驱动。目前最新的版本是11.10：（驱动之家等国内网站收录的还是9.35的版本）
  
<http://www.ngohq.com/submit-news-members/8174-nforce-11-10-unified-remix-x32-x64.html>

初试这款驱动便在安装时碰了一块大石头……安装Ethernet Driver组件至一半时，系统直接无任何征兆的复位。之后WinXP启动过程中蓝屏，提示网络适配器驱动故障。惊恐之余发现安全模式还算能正常进入，立即卸载了网卡驱动。这时再来细读驱动包的Readme时才发现一个重要的提示：**“必须首先干净的卸载原网卡驱动”**。（汗，又一次着了不看文档的道……）

这一次按部就班的完成了安装过程，一路有惊无险。重启WinXP后，一切看起来都工作正常并充满了新驱动带来的“活力”（八成还是心里暗示……）。欣喜之余，不禁感叹nVidia的无情，明明ForceWare都可以受益于统一驱动构架，但nForce2/3系列却被早早的遗弃，而这款mod驱动用事实证明了nForce4的驱动其实还是完全适用的，也不知道nVidia究竟是出于什么考虑。

还没切身感受到新驱动所带来的变化时，没想到又遭打击。PPPoE的网络连接在运作没多久后就“罢工”了 ，源源不断送出消息包的同时，接收的消息包统计却止步不前。断开连接后甚至无法再次创建PPPoE，只能用禁用-激活网卡的方式强制恢复。可惜，前面遇到的故障并非偶然，每一次连接不到10分钟就会遭遇“断流”。

这一次学乖了，先看驱动包的Readme和发布帖子中的说明，又找到如下一句话：“ if you have problems with ethernet 65.xx please use 9.53 unified <span class="highlight">remix</span>”。Shiiiiit! 无福享受最新版本，看来只好回退到老的9.53版了……

安装9.53后，上述问题依旧，一怒之下索性干脆将Ethernet Driver组件替换回官方5.11驱动包中的版本。没想到的是，“断流”的问题俨然阴魂不散的缠住我不放了，纵使我想要全身而退亦不可得……

一个晚上的时间就这样花在不停的替换尝试各版本的驱动程序上了，最终让我无意中找出了问题的根源——nForce的Ethernet Driver和Look&#8217;n&#8217;Stop发生了冲突，只要安装网卡驱动时拒绝Look&#8217;n&#8217;Stop随之而来的安装提示就不会再遭遇“断流”的困扰。而实际上，至少到目前位置，也没有发现任何Look&#8217;n&#8217;Stop的功能因据装附属驱动而受到影响的情况。

揪出“祸根”后，重新装上最新的11.10版remix驱动也表现一切正常！

最后，总结一下与remix驱动有关的几点：

(1) nForce3官方“最新”的5.11驱动在我的WinXP中只要修改网卡属性就会毫不留情的立即重启，无论是从设备管理器还是Web界面中进行修改。

(2) Remix 9.53版的Network Access Manager无法安装，提示“在本机无效” ，不清楚是我的个别遭遇还是nForce3使用remix驱动的共通问题。

(3) 使用nVidia驱动中自带的测速功能对新旧版本的SATA速度进行了测试，没有发现误差之外的性能提升。（分别用两块硬盘在SATA-1模式下进行的测试：希捷7代 120G、希捷10代 320G）据国外论坛的网友称，新版本的GART driver带来了3D性能的明显提升，这个我倒没测试，但愿如此。

(4) 使用官方驱动包时，我的uTorrent 1.6.1 Stable版本在启动过程中提示nVidia的网卡驱动与之有冲突，可能导致内存泄露和CPU占用过高。不过我倒暂时还没遇到上述问题，而安装Remix版本的驱动后则没有了这个提示。

(5) Remix 11.10版的Ethernet Driver和Network Access Manager在nForce3上无法开启“防火墙”组件（可能因为nForce4的硬件防火墙驱动与nForce3不兼容吧），所以如果希望使用nForce3的硬件防火墙功能，则Ethernet Driver和NAM组件必须使用官方nForce3的驱动包。

> **Update (2007.4.7) :** 经过几天的“试用体验”之后，彻底对nForce3所谓的“硬件防火墙”失望了。安装硬件防火墙驱动（NAM）后，无论是否激活防火墙，网络的稳定性都会受到影响。具体表现为刚连上网的一小段时间内，网络使用正常，但只要累积连接数上升（比如用BT或Emule），则连接稳定性急剧下降，导致网络浏览和下载速度都很不理想。想要保持稳定性的唯一途径就是频繁的重连网络……
> 
> 至于nVidia所声称的低CPU占用率，我实在不敢苟同，至少光是一个nSvcAppFlt进程就与我的软件防火墙Look&#8217;n&#8217;Stop不相上下，而内存占用更是达到24M余（Look&#8217;n‘Stop才3M多）。在网上搜索了一下相关的信息，发现针对nForce3的硬件防火墙果然是骂声一片，看来uTorrent的声明也并非全无道理。
> 
> Sigh&#8230; 又被nVidia欺骗了，放弃这个华而不实的“硬件防火墙”，还是老老实实用回我的Look&#8217;n&#8217;Stop吧。X(

(6) Remix版本的网卡驱动由于不是WHQL认证的版本，所以无法直接在网络连接试图中禁用网卡（提示“一个或多个不支持即插即用的协议”）。不要紧，用设备管理器的禁用-启动功能则一切正常。