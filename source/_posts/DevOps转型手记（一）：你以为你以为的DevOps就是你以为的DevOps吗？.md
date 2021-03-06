---
title: DevOps转型手记（一）：你以为你以为的DevOps就是你以为的DevOps吗？
abbrlink: ec6461d
date: 2018-10-23 21:13:07
categories:
  - DevOps转型手记
tags:
  - DevOps
---

## 前言

自接触并学习DevOps起，到交付DevOps相关的培训和咨询服务至今已差不多一年时间。

最近一段时间正在帮助我们的一个重要客户实现DevOps转型，在此过程中，每一天都会有新的发现和新的感悟。

客户方的负责人开玩笑给我说：“如果我们能成功，固然很好，但是如果不尽如人意，大不了写本书呗！”

我觉得好有道理！

于是，秉着“到此一游总要留下点什么”以及“写不了一本书也要写个册子”的精益思想，开始把感悟到的东西都记录下来写成文章，一方面供自己总结精进，一方面供他人参考借鉴。

这些文章不会有严格的顺序，纯粹想到了就写，容日后编撰成册吧。

<!-- more -->

## 你以为你以为的DevOps就是你以为的DevOps吗？

> “您对DevOps一定有误解……”

我每次我在面对需要做转型的团队的时候，我都会先问在场的所有人一个问题：“大家所理解的DevOps到底是什么？”

得到的答案五花八门，常见的主要有以下几种：

- “没听说过。”
- “听说过但是不了解。”
- “DevOps就是要做敏捷。”
- “DevOps是一种套路。”
- “DevOps就是让开发人员（Dev）和运维人员（Ops）一起工作。”
- “DevOps就是CI/CD。”
- “DevOps就是做一个平台，让我们能够在上面方便开发。”
- “DevOps就是一大堆工具做自动化。”

这些回答，与前些年“敏捷”一词风风火火的时候，对于大多数人“敏捷就是Scrum”的理解是何其相像！

其实，这也不能完全怪大家，尤其是DevOps在今天来说，依然处于一场“迷之盛宴”的阶段。

## DevOps的迷之盛宴

这场“迷之盛宴”中有几类典型的“教派”在其中“群魔乱舞”：

- 忽悠神教
- 套路神教
- 平台神教

接下来，让我们挨个说起。

### 忽悠神教

> “你们这些方面与DevOps的要求相比，还有很大差距……（没了）”

正如“敏捷”火爆时候的满大街各种连敏捷实践都没做过的所谓“认证敏捷教练”，还有“区块链”出来以后满大街套着“区块链”字眼招摇撞骗的创业项目。每一次某种概念突然火爆的时候，总是少不了这样一些人：

- 他们以炒作概念为生，但绝不负责落地。
- 他们喜欢制定种种度量或认证标准敛财，然后到处去做评估赚钱。
- 他们夸夸其谈，但是怂于实践。

这些人干的事情就是：到处“念歪经”、“传歪经”，钱到手了立刻拍拍屁股走人。

记得我所接触的第一个试点团队，团队看到我们的第一个反应是：“怎么又来了一波搞DevOps的”。在初期的几次接触中，明显能够感受到团队对于这一次工作抱有相当的抵触和不信任感。

当我拿到“某国际知名咨询公司（该公司压根没啥技术实践）”之前针对该团队的评估报告的时候，我的第一个反应就是：“WTF?”

该评估报告本质上就是一个基于打分表的问卷调查，寥寥几个维度加上不同的标准，做了做问卷调查和简单的访谈，就为团队打了个分，定了个性。然后到了该有改进方案部分，直接粘贴了几个不知道从哪里找来的广告般的可视化面板的截图，然后标注了一个醒目的单词“Sample”。然后就再也没有然后了……

团队告诉我们，大家根据这份评估结果，努力的在可视化和自动化方面做了很多尝试，但是“并没有感到有太大的变化”。

后来，随着和团队几次深入的交流、对实际代码和实践进行分析，我们发现该团队的开发环节完全掌控在一个以产品垄断为基础的强势供应商手上，产品的封闭程度也非常之高（纯Win32图形化操作，所有的中间数据和最终数据都被存为了专有格式的二进制文件，合同限制团队只能得到开发之后编译的二进制文件而不是代码）。如果不能把开发环节控制在自己手上的话，永远都难以优化Dev而只能优化Ops，这显然是不能实现从Dev到Ops顺畅的价值流动的。而团队在其他环节上已经根据自身的理解采取了多方面的努力和尝试，采购了专门针对图形化应用的测试工具编写了自动化验收测试，甚至还每人都购买和阅读了《凤凰项目》一书。

所以我们的最终评估认为，该团队已经做出了很多努力，受制于现实约束，进一步优化的空间十分有限。

以上就是一个我亲眼见到的“拍拍屁股就走”的例子，如果按照他们的方式再来一次“忽悠”型的咨询，还真不知道会对这个团队造成怎样的伤害。

### 套路神教

> “我听不懂，我就只想知道怎么验收？什么时候能做完？”

我相信有很多人同我一样会经常遇到上面这样的提问，往往出自于某个具有领导角色的人口中。在他们的心中，DevOps是一种工具性的存在，只要按照说明书操作，就理应能够“实现”。

而从“DevOps三步工作法”来看，DevOps的最终目标之一，是对组织文化进行改造，建立一种相互信任、持续改进和不断创新的组织文化[^1]：

> 第一步：实现开发到运维工作快速地从左向右流动；
>
> 第二步：在从右向左的每个阶段中，应用持续、快速的工作反馈机制；
>
> 第三步：建立具有创意和高度信任的企业文化，支持动态的、严格的科学实验；

![DevOps三步工作法](https://huhao-dev.oss-cn-beijing.aliyuncs.com/2020-01-20-114446.png)

（我习惯将以上三步简称为：优化价值流动；优化反馈机制；建立持续改进的文化）

而既然说到了组织，我们知道每一个组织他们所面对的自身实际、目标和挑战是不同的，所以这个世界上并不存在“DevOps灵丹妙药”，每个组织都需要严肃认真的对待和分析自身实际，走出满足自身需要的转型之路。

另一方面，持续改进告诉的是让我们变得“更好”，所以并不会出现“做完了”的情况。

但可惜的是，这个行业里有太多不顾核心问题而急于赚钱的人，他们最擅长的就是提供一套“标准化”的解决方案去迎合这种急功近利的心态，并建立一种“只要按照这种套路做下去，就能实现DevOps”的迷信。

心急吃不了热豆腐，天下也没有免费的午餐。相比“摸着石头过河”来说，好在我们还有很多行业标杆可以参考。

### 平台神教

> “没有什么DevOps的问题是用一套平台不能解决的！”

之前参加了大大小小不同的DevOps社区活动，也去不同类型的企业做过DevOps方面的培训或交流，最让我印象深刻的是，几乎各大企业都在做自己的DevOps平台，并且各种服务商也在大力的推销自己的产品。

首先，DevOps平台本身并没有什么问题，通常将运维融入日常开发工作的方式有以下三种[^1]：

> - 创建共享服务，提高开发生产力。
> - 将运维工程师融入服务团队。
> - 为每个服务团队分派运维联络人。

其中“创建共享服务”指的就是通过创造集中式平台或者工具链的方式，通过自动化的方式降低开发过程中开发人员对于基础设施的注意力损耗，建立更快速的反馈和响应力。

在这种指导思想下，开发工程师最好能够在运维工程师的帮助下实现这样一种理想中的工作状态：

1. 随便找到一台能够使用Web浏览器的设备，通过浏览器打开云端集成开发环境。
2. 使用云端集成开发环境针对实例化需求编写测试代码并实现。
3. 将编写完成的代码提交进本地版本控制的变更集，同时触发属分布式持续集成和自动化构建流水线。
4. 当分布式流水线无误通过后，触发后续的自动化/手动测试、部署等环节并交付上线。
5. 在整个过程中，开发人员应当保持对业务实现的高度关注，而尽可能的不去关注基础设施可能产生的干扰。

然而，这种看似理想的工作状态在引入人工智能后将会产生另一个“黑暗的”版本：

1. 在所使用的框架和平台不断进步的情况下，开发人员所编写的代码将越来越多的由胶水代码构成。
2. 基于大量的人工智能学习和训练，需求分析人员开始使用基于业务场景的自动化测试用例生成工具生成测试用例。
3. 人工智能学习和抽象更多的胶水代码案例，根据测试用例自动生成胶水代码。
4. 最终只会写胶水代码的开发工程师被人工智能所取代，“码农”终于失业了。

当然了，“黑暗”是针对“只会写胶水代码”的人而言的，如果是一个具有分析、设计能和驾驭整个端到端交付能力的“高级开发人员”来说，甭提有多爽快了。

话说回来，既然平台的前景这么广阔，哪里有问题呢？

问题恰好就出在了盲目夸大平台的作用，而忽略了“实现开发到运维工作快速地从左向右流动”这个地方。

根据我的观察，目前绝大多数的集中式品台都是由各大公司的运维部门主导开发完成的，我见过完成度非常高的平台，也见过完成度比较低的平台，但是他们都具有一个关键的基础，就是自动化构建和部署流水线（Pipeline），而流水线的一个必要条件就是：要有自动化测试。

那么问题来了：**有多少公司的开发和测试团队具备良好的自动化测试能力？**

对不起，亲眼所见，仅就国内而言，不多……

上到知名互联网企业，下到中小型传统IT企业，先姑且不说测试驱动开发，仅是有自动化测试的连过半都没有。

没有自动化测试兜底，你告诉我，开发到运维咋个快速流动嘛！更别谈持续反馈了，要不要用手点的方式表演个快速回归看看？

所以，这也是我们所见到的大多数所谓“DevOps平台”很难落地的原因。至于为啥今天做平台那么火爆，我个人有个非常不负责任的理解就是：

作为长期被忽视的运维工程师们，好不容易打了一次翻身仗，愈战愈勇用，加上之前所说的套路化迷思，最后从上到下集体妄图用工具和平台一统天下……最终促进人工智能替代胶水代码工程师的伟大未来。**（我就是开个玩笑，别打我！）**

说到这里，我就想起了之前评估过的一个团队，做了大量基础设施搭建工作的运维工程师用非常无奈的眼神看着我说的话：

> “我们工具都搭好了，可是开发就是不用……”（因为没有自动化构建也没有自动化测试）

阻挡平台落地的因素有很多，自动化测试是我见到的最惨烈的一个。

## DevOps到底是什么？

穿过浮躁，回归本质，让我们来看看：DevOps到底是什么？

其实DevOps思想是建立在软件行业经过实践验证的一系列旨在提升响应力的思想和实践的融合过程之上的（所谓“DevOps大融合”），它们包括且不限于[^1]：

> - 精益运动
> - 敏捷运动
> - Velocity大会运动（最为有名的就是演讲“每日10次部署：Dev和Ops在Flicker的协作”）
> - 敏捷基础设施运动
> - 持续交付运动
> - 丰田套路运动
> - 精益创业运动
> - 精益用户体验运动
> - Rugged Computing运动

所以，DevOps即是一种“融合思想”，里面含有了大量需要长期学习、理会、实践的东西。

而其中最为核心且占主导地位的，在我看来就是“精益思想”和“持续交付”。我们在DevOps转型过程中能够看到的绝大多数问题都基本不超出这两种思想的范围（当然他们也是建立在一系列思想和实践之上的）。换句话说，如果你所遇到的问题在这两种思想中找不到答案，那你的DevOps实践水平已经相对其他组织来说非常高了。

另一方面，DORA团队在近4年的研究基础上，总结了5类共24项能够影响和推动软件交付效能的关键能力，并且绘制了关系图，这5类能力为[^2]：

> - 持续交付
>   - 对所有生产工件使用版本控制
>   - 自动化部署过程
>   - 实现持续集成
>   - 使用基于主干的开发方法
>   - 实现自动化测试
>   - 管理测试数据
>   - 将安全性集成到软件和测试阶段
>   - 实现持续交付
> - 架构
>   - 使用松耦合架构
>   - 构建自治团队
> - 产品和流程
>   - 收集和实施客户反馈
>   - 通过价值流可视化工作流动
>   - 小批量工作
>   - 培养和支持团队实验
> - 精益管理和监控
>   - 使用轻量级变更审批流程
>   - 监控应用和基础架构以支持业务决策
>   - 主动检查系统健康状况
>   - 通过限制在制品改进流程和管理工作
>   - 可视化工作以便监控质量和促进团队沟通
> - 文化
>   - 支持生机型文化
>   - 鼓励和支持学习
>   - 鼓励和支持团队间的合作
>   - 提供使工作有意义的资源和工具
>   - 支持或体现变革型领导力

![Overall Research Program](https://huhao-dev.oss-cn-beijing.aliyuncs.com/2020-01-20-114505.jpg)

怎么样？是不是感觉24项关键能力每个拿出来都够喝一壶的？

你看，DevOps融合了这么多种实践和思想，还需要锻炼这么多关键能力，那些希望能够有个“明确完成时间”的想法是不是显得很可笑了？

总而言之，DevOps所代表的就是一种追求能够从组织、文化、技术角度等多个方向上，利用新的思想和工具，全面提升IT组织响应力，同时让客户和员工都满意的价值追求。

当然，如果一定要问我DevOps转型到一个理想状态需要多长时间的话，我会说：

> “谁知道呢，根据统计，一个企业完成精益转型需要5年时间，作为DevOps转型来说，没个奋战3-5年的心理准备，还是洗洗睡吧……”

## 结语

作为DevOps转型的推动者，在这喧嚣浮躁的阶段，我们应当看清现实，树立正确的DevOps价值观，用实践检验真理，我相信喧嚣过后，总是会大浪淘沙，去伪存真。

而对于那些正因为各种原因“被转型”的人们，我想说：莫急，不慌，多学习。

[^1]: 出自《DevOps Handbook》，文字来自中译版《DevOps实践指南》。
[^2]: 内容和图片出自《Accelerate》: The Science of Lean Software and DevOps》。

---

## 欢迎关注我的微信公众号

微信搜索：`枪炮与代码`，或者搜索公众号ID：`guns_n_code`

![枪炮与玫瑰](https://huhao-dev.oss-cn-beijing.aliyuncs.com/2020-01-20-wechat.png)