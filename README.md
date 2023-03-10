# 深入大规模架构原理与实战


## TIPS

各位朋友您好，如果您在观看此拙作，请 关注 github仓库：https://github.com/isno/isno.github.io

我预计将删除github pages，并在 github 放入 markdown 原文。




## 简介


爱奇艺海外业务最初上线的时候，很多工作是从零开始的，我们花了很大的力气做了网络层和服务层的建设，在做在这些工作的时候，我们注意到一些规划或者设计如果某个层存在短板则很影响全局。产品质量的改善很整体且体系化的工作，具体到实践中就是不断解决短板。

市场上的技术书籍往往局限在某个专业领域，很少有讲问题解决的体系化链路。

比如说，在改善用户视频起播效率工作中，我们关注了 DNS、CDN、TCP连接、流媒体传输控制、应用层改善、后端Server的处理延迟还有机房BGP对等接入等等改善工作。

从这些技术的描述可以看出，“产品质量”绝对不是单方面某个技术栈就能搞定的，而是一个从上至下整体性很强的工作。我们关注行业内的一些技术话题：比如JAVA、微服务再或者云原生，无论这些技术或者理念多么先进，它们的服务目的只有一个：解决问题。宏观角度的问题，也一定是这些技术相辅相佐才能完成。

在刚开始本书起草时，我也一直在犹豫，要不要开这个话题？

讲 TCP、网络、微服务...都有专业的书籍出版，我没办法比他们写地更专业更出彩，广度发散性话题也很难驾驭。在我思考了很久之后，我强迫这样说服自己：能运用这些技术解决问题，能给别人启发，能捎带理解原理，在工作实践中举一反三既是目的。

**笔者在技术大纲中规划了四个技术层面的话题：网络、应用层、负载均衡和网关、云原生与服务治理、FinOps（企业资源降本实践），通过这几个层面的内容撰写，向读者阐述如何构建一个稳定可用、成本可控的服务体系。**

本书绝大部分内容为无状态服务的描述，由于主题覆盖性以及笔者本人的认知和水平有限，难免存在不足或不严谨之处，也希望能得到读者的指正。

