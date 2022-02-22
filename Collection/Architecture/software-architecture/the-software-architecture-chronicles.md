# 软件架构编年史

原文: https://www.jianshu.com/p/b477b2cc6cfa

> 译者：最早看到的是作者的[这篇](https://herbertograca.com/2017/11/16/explicit-architecture-01-ddd-hexagonal-onion-clean-cqrs-how-i-put-it-all-together/)文章([译文](https://www.jianshu.com/p/d3e8b9ac097b))，其中的那副[信息图](https://docs.google.com/drawings/d/1E_hx5B4czRVFVhGJbrbPDlb_JFxJC8fYB86OMzZuAhg)可谓集软件架构之大成。后来发现这是作者学习和思考软件架构发展史的系列文章之一。“以史为鉴，可以知兴替”，阅读历史就是学习的过程。翻译也不例外，我也是通过阅读和翻译来学习软件开发的历史，联系作者获得授权之后便有了这一系列译文。

这是[软件架构系列](https://herbertograca.com/tag/software-architecture/)的第一篇文章。我将我对软件架构的学习过程和思考以及我是如何运用这些知识的写成这一系列文章。

我把这一系列文章称为“软件架构编年史”，并不是因为我觉得自己的文笔不错，而是想用一种有趣的方式旧调重弹！😀

在第一篇文章里，我将谈谈我撰写这一系列的原因和接下来的计划。

&nbsp;

## 学习历史的重要性

> 不学习历史的人注定要重复错误。
>
> —— 温斯顿.丘吉尔

我发现从历史中学习十分重要，历史可以教给我们很多东西。在个人层面，我们(最终有望)从自己的失败中学习。在国家层面，历史帮助形成我们的文化，创造群体思想，“我们”的思想，国家的同一性。它还能帮助我们从祖先的错误中学习，比如错信一些人的疯狂思想，想想第二次世界大战...

对我们开发者来说，历史帮助我们在前辈们的知识上前进。它帮助我们从前辈们的知识：错误、经历和经验中学习。它帮助我们“站在巨人的肩膀上”更上一层楼！

在我向更好开发者前进的成长之路上，我浏览过许多文章，观看过许多会议演讲，也阅读过许多书籍。我尽可能地站在巨人的肩膀上！

然而我一直有一个困惑，这些观点发展出其它许多观点，又继续发展出更多的观点...这就好比“传话游戏”，论文、文章或者书籍原本要表达的思想最后终会被扭曲。

于是我开始在互联网上淘宝，寻找表达这些概念的原始论文、文章和书籍，我觉得它们是我工作中最重要的概念，我自己也时常思考它们。

在我尝试以某种考古方式理解这些概念如何形成的过程中，我的思考就形成了这一系列文章。

撰写这些文章强迫我大量阅读和思考这些主题，这帮我理解现代软件开发中使用的技术。我希望这些文章内帮到更多后来的开发者。

然而，如果你读到任何不理解或者有异议的内容，请让我知晓。我对这些主题的讨论持完全开放的态度，希望可以从他人那里学习，当我被证明犯错时我会改变我的观点。

&nbsp;

## 软件架构编年史系列

01. 软件架构编年史(译) //原文

02. 软件架构预述(译) //原文

03. 编程语言的演化(译) //原文

04. 架构风格 vs. 架构模式 vs. 设计模式(译) //原文

05. 单体架构(译) //原文

06. 分层架构(译) //原文

07. MVC 及其变种(译) //原文

    - 1979 – Model-View-Controller(译) //原文

    - 1987/2000 – PAC / Hierarchical Model-View-Controller(译) //原文

    - 1996 – Model-View-Presenter(译) //原文

    - 1998 –”Model 1″ & “Model 2” (译) //原文

    - 2005 – Model-View-ViewModel(译) //原文

    - ???? – Model-View-Presenter-ViewModel(译) //原文

    - 2008 – Resource-Method-Representation(译) //原文

    - 2014 – Action-Domain-Responder(译) //原文

08. EBI 架构(译) //原文

09. 包与命名空间(译) //原文

10. 领域驱动设计(译) //原文

11. 端口和适配器架构(六边形架构)(译) //原文

12. 洋葱架构(译) //原文

13. 整洁架构(译) //原文

14. 事件驱动的架构(译) //原文

15. 从 CQS 到 CQRS(译) //原文

16. 面向服务的架构(SOA)(译) //原文

17. 清晰架构(01)：融合 DDD、洋葱架构、整洁架构、CQRS...(译) //原文

18. 清晰架构(02)：超越同心圆分层 (译) //原文

19. 清晰架构(03)：在代码中展现架构和领域 (译) //原文

20. 清晰架构(04)：用文档描述架构 (译) //原文

21. 一个项目的演进：从 MVP 到 P

22. 4 + 1 架构视图模型

23. 架构的质量属性

&nbsp;

## 时间线

下面是我在阅读所有这些主题的文章和书籍之后总结的一条软件开发发展的粗略的时间线。我找到的关于确切时间的参考资料都作为链接加入了时间线，拿不准的时间我都加上了“~”，表示“大约”是这个时间。我们还可以在维基百科的[编程范式](https://en.wikipedia.org/wiki/Programming_paradigm)主页上找到大量相关的内容。

这里列出的大多数话题都将在这个系列中谈及。

- 20 世纪 50 年代

  - 非结构化编程

  - ~1951 – 汇编

- 20 世纪 60 年代

  - 结构化编程

  - 分层: 用户界面、业务逻辑数据存储都在一层。

  - ~1958 – Algol

- 20 世纪 70 年代

  - 过程式/函数式编程

  - ~1970 – Pascal

  - ~1972 – C

  - 1979 – MVC 模式(Model-View-Controller)

- 20 世纪 80 年代

  - 面向对象编程 (但其思想在 20 世纪 60 年代晚期已经第一次提出)

  - 分层: 两层，第一层是用户界面，第二层是业务逻辑和数据存储

  - ~1980 – C++

  - CORBA – 通用物件请求代理架构(尽管1991年才推出第一个稳定版，但最早使用可以追溯到 20 世纪 80 年代)
  
  - ~1986 – Erlang
  
  - ~1987 – Perl
  
  - 1987 – PAC 即 HMVC 模式(Hierarchical Model-View-Controller)
  
  - 1988 – LSP(里氏替换原则) (~SOLID)

- 20 世纪 90 年代

  - 分层: 三层，第一层是用户界面，第二层是业务逻辑(以及浏览器作为客户端时的用户界面展现逻辑)，第三层是数据存储

  - ~1991 – 消息总线

  - ~1991 – Python

  - 1992 – EBI 架构(Entity-Boundary-Interactor) 即 EBC 或 EIC

  - ~1993 – Ruby

  - ~1995 – Delphi, Java, Javascript, PHP

  - 1996 – MVP 模式(Model-View-Presenter)

  - 1996 – OCP, ISP, DIP (~SOLID), REP, CRP, CCP, ADP

  - 1997 – SDP, SAP

  - ~1997 – 面向方面编程

  - ~1997 – Web 服务

  - ~1997 – ESB – 企业服务总线 (尽管创造该术语的书籍2004年才出版，但这个概念早已被使用)

- 21 世纪 00 年代

  - 2002 – SRP (~SOLID)

  - 2003 – 领域驱动设计

  - 2005 – MVVM 模式(Model-View-ViewModel)

  - 2005 – 端口和适配器架构即六边形架构

  - 2006? – CQRS 与 ES (命令查询职责分离与事件溯源)

  - 2008 – 洋葱架构

  - 2009 – 微服务(Netflix)

- 21 世纪 10 年代

  - 2010 – DCI 架构(Data-Context-Interaction)

  - 2012 – 整洁架构

  - 2014 – C4 模型

译者注：C4模型的介绍可以参考我的同事仝键的介绍文章“可视化架构设计——C4 介绍”。
