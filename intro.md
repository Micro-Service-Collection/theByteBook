# 前言

既然翻开这本书，我猜测你大概率是个互联网从业者，我还能猜出这几年你大概率被这些层出不穷的概念包围：云计算、PaaS、FaaS、CaaS、ServiceMesh、Serverless、可观测性、跨内核，当然不能遗漏了各种 Ops，诸如 DevOps、GitOps、AIOps、MLOps 等等。

近几年来，云技术发生了翻天覆地的变化和革新，这也对如何构建上层应用产生重大的影响，分析这些激动人心的技术变革以及讨论如何为业务赋能之前，我们先思考引发这一波技术浪潮的核心驱动力是什么？

## 软件在吞噬世界

互联网投资人 Mark Andreessen 曾发表过一篇文章《Software is Eating The World》，文章内容主要阐述了软件如何影响各个行业。援引原文部分内容：

:::tip <i></i>

我们处于戏剧性和广泛的技术和经济转变的中间，软件公司准备接管大量的经济。
...
十年前，当我在创办的 Netscape 公司时，大概只有 500 万人使用宽带互联网，而现在有超过 20 亿人使用宽带互联网。在接下来的 10 年里，我预计全球至少有 50 亿人拥有智能手机，每个人每天都可以随时随地使用这种手机充分利用互联网。
...
:::

文中列出了被重塑的产业，包括：最大的书店 Amazon、最多人订阅的 Video service Netflix、最大的音乐公司 iTunes 等等。

文章发表于 2011 年，2023 年再来回顾互联网的冲击，感触更加深刻，部分软件变成像水、电、媒一样的基础设施。

## 移动互联网在加剧变化

作者展望互联网规模时，写道：“在接下来的 10 年里，我预计全球至少有 50 亿人拥有智能手机，每个人每天都可以随时随地使用手机充分利用互联网。”

现在，我们已经可以确认 Mark Andreessen 的预测很正确，移动互联网时代的用户规模已经开始向人口基数看齐，开始出现各类亿级 DAU 规模的移动应用。而移动互联网如此巨大的用户规模会对软件开发有什么影响？

<div  align="center">
	<img src="./assets/ppt4.jpg" width = "450"  align=center />
	<p>图 1 Netflix按照规模和变更速度对软件企业划分的总结</p>
</div>

在十年前乃至二十年前的互联网时代，大多数软件企业都位于图 1-8 左边的两个象限：规模或许有大有小，但是变更速度相对今天都不快。当企业发展壮大时，体现的也更多是在规模上，变更速度并不会发生质的变化。而今天的移动互联网时代，则都位于图 1 右边的两个象限：无论规模是大是小，变更速度都要求非常快。并且当企业逐步发展壮大，规模十倍百倍增长时，对变更速度的要求并不会降低，甚至会要求更快。

移动互联网时代，能够成长并发展起来的这些公司，他们的共同点是：

- 快速变更，不断创新，随时调整
- 提供持续可用的服务，应对各种可能的错误和中断
- 弹性可扩展的系统，应对用户规模的快速增长
- 提供新的用户体验，以移动为中心

这样的背景下，对软件开发有了更高的要求，软件开发的方式也不得不跟随时代而变化。

## 时代巨变掀起技术浪潮

软件对各行各业的渗透和对世界的改变，以及移动互联网时代巨大的用户基数下快速变更和不断创新的需求对软件开发方式带来巨大的推动力，我们清晰地看到如此波澜壮阔的技术浪潮：

- 软件正在改变世界
- 移动互联网让这个变革影响到每一个人
- 传统软件开发方式受到巨大的挑战
- 因为云计算以及相关技术的普及，软件上云成为趋势
- 云技术的形态持续在演进

援引 InfoQ 主编徐川老师对云计算的总结

:::tip 云计算技术总结
云计算的技术逐渐发展成为它本来该有的模样，以及与这样的云所匹配的软件架构，还有以及与这样的架构所匹配的开发流程与方法论。
:::

## 大时代下的个体

视角转回到工程师个体，不管你是否能接受，软件行业解决问题的技术一直在变化，并且**这种变化并不是平缓的升级，而是剧烈的革新替代**。例如容器替代虚拟机、服务网格替代 SpringCloud、观测替代监控、Network Policy 替代 iptables 等等。

剧烈变化的背景下，如果我们只专注于手头的工作，不抬头看天，过度关注于某个技术深度和细节，大革命来临的时候，之前关注的细节可能再也没有意义。

所以，本书很少详细描述某个软件如何安装、如何使用，而是**思考问题的本质以及不同的解决方式，尝试找到些许核心原理以及悟透点发展规律**。例如网络优化受制于物理世界的枷锁，分布式系统演进是 CAP 定理的权衡选择，局限于时间与空间法则。容器、服务网格、Cilium、MACVLAN 也不是什么黑科技，只是把计算机的基本原理、方法重新组合，换种形式解决业务变化带来的新问题。

最后，本书的宗旨是希望能说清楚这些问题的本质，解释清楚整个服务架构的发展历程，讨论它们背后遵循的不变原则、探索它们的设计选择。读完本书，相信你对系统的整体运行一定有全新的认识与判断力：方案取舍、架构权衡将得心应手，个中症状处理更加游刃有余。

## 本书适合哪些读者

本书主要针对软件工程师、软件架构师以及技术负责人等，特别是那些需要对系统架构做权衡的人，譬如时常需要选择一些工具去解决某个领域的特定问题。退一步，如果你不需要做这些决定，本书也可以帮助你更好地理解这些技术的优缺点。

阅读本书，最好了解一些请求/响应型（Web）系统原理，熟悉一些常见的网络协议（譬如 TCP、HTTP 等）。如再有一些后端开发经验，这将会对阅读有很大帮助，至于你熟悉何种编程语言倒没有太大关系。

总体上讲，若以下条件适用你，可能会从本书收益：

- 对系统如何运行有着天然的兴趣和探索精神

## 如何阅读本书

本书内容总共分为十章。

- 第一章**从需求的背景、发展的历史开始，漫谈微服务、容器、不可变基础设施、声明式设计、服务网格、DevOps 等云原生技术**。从解决问题的角度理解这些技术，借历史之名审视今天的现实问题，以及思考如何寻找出未来的技术/架构演进之路。
- 第二章从一道**经典的面试题“浏览器打开 url 到页面展现，中间发生了什么？”开始**，逐步探究 DNS、HTTP、SSL、QUIC 和传输层等各个环节原理以及该**如何一步步构建“足够快”的网络服务**。
- 第三章：我们着重修炼内功，深入 Linux 内核网络，**了解 Linux 内核、netfilter、虚拟网络技术**如何对各类的上层应用（Kubernetes、容器、服务网格等等）产生影响。
- 第四章：负载均衡是构建可靠的分布式系统最核心的概念之一，从早期的 LVS 到 Nginx，再到 Kong、APISIX 等，不过无论负载均衡器以何种形式存在，**核心的职责都是“选择谁来处理用户请求”和“将用户请求转发过去”**，本章我们就从这两个角度讲解负载均衡。
- 第五章：早期局限在本机的事务处理还只是个编码问题，但当事务不再局限数据库内上升到各类的业务层，保证分布式系统下整体的原子性与一致性便成了架构设计问题。分布式事务的篇章我们就从 ACID 与 CAP 的矛盾说起，理解 CAP 对分布式系统权衡的影响，以及权衡影响下发展而来的可靠队列、TCC、Sage 等各类柔性事务。 
- 第六章：副本容错模型是应用最广泛的高可用设计理念之一，理解副本模型的关键是理解共识。这一章从**共识问题认识 Paxos**，以**工程实践为目的去了解 Raft 的设计思路**。理解了问题以及这些共识算法的解题思路，自然也能体会到 etcd、consul 以及各类分布式容错系统的设计原理，也能更好地把这些理解应用到现实。
- 第七章：照本宣科地介绍 Kubernetes 架构如何新颖、设计如何优秀，相信并不能给读者们留有什么深刻印象，教条式介绍睡过一觉不会有多少人记起。故事让内容变得有趣，容器技术变革的浪潮中，曾发生过一场”史诗大战“，业界称之为 ”容器编排之争（Container Orchestration Wars）“。这一章我们从故事开始，观察 Kubernetes 诞生与演变的驱动力，深入理解容器的本质。
- 第八章：当非侵入性的服务网格技术从萌芽走向成熟，当 Istio 横空出世，**服务治理与业务完美解耦**，技术理想终于照进现实。服务网格篇，我们从服务间通信层面说清楚 Service Mesh 的本质以及诞生的必然性，讨论当今服务网格产品的生态以及未来。
- 第九章：我们从遥测数据认识可观测性，对比可观测性以及传统监控的区别。再探讨**事件日志、链路追踪和聚合度量**三个领域中等各个方案落地权衡。

## 勘误

由于作者的认知局限，难免产生各种各样的错误。如果阅读文章发现问题，欢迎在 github 给我提交 PR 或者 issue。


## 致谢
