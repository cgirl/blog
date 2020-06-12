---
title: 区块链是什么  
date: '2017-12-17 16:31:10'  
tags: 读书摘录 区块链
categories: 区块链:定义未来金融与经济新格局
---
## 记账货币

区块链的本质是一种去中心化的记账系统，而比特币正是这个系统上承载的“以数字形式存在”的货币。我们可以认为区块链与比特币之间的关系就是凯恩斯所说的记账货币与货币之间的关系，也可以用菲利克斯-马丁对货币的理解来说明两者的关系--比特币只是记账的表征，而区块链就是背后的一套由信用记录以及用心记录的清算构成的体系。

## 天才的发明

要了解比特币的内在优雅。不是软件使得比特币如此有效，而是经济学。--罗比特-沃伦斯基

因为账本上的内容必须是唯一的，所以就导致记账是一种天然的中心化行为。在通信手段不发达的时代，这是必然的选择；在如今的信息时代，中心化的记账方式依然覆盖了社会的方方面面。然而，中心化的记账却有一些显而易见的弱点：一旦这个中心出现问题，如被篡改、被损坏，整个系统就会面临危机乃至崩溃。

这种中心化的记账方式对中心本身的能力、相应的监管法律和手段以及参与者对其的信任都有极高的要求。

那么区块链是靠怎样的架构设计最终解决了去中心化记账的难题呢？竞争记账机制成为了解决问题的关键。
这里我们先引入一个称为“节点”的概念。在当前的信息时代，负责记账的自然是计算机，而在记账系统中接入的每一台计算机都可以称作节点。

所谓的竞争记账，就是以每个节点的计算能力（“算力”）来竞争记账权的一种机制。在比特币系统中，大约每十分钟进行一轮算力竞赛，竞赛的胜利者获得一次记账的权利，即向区块链这个总账本写入一个新区块的权利。这样，在一定时间内，只有竞争的胜利者才能完成一轮记账并向其他节点同步新增账本信息，这个过程就是区块产生的过程。

不过，算力竞争是要付出成本的，没有激励，节点就没有进行竞争的动力。在中本聪的设计里，每轮竞争胜出并完成记账的节点将可以获得系统给予的一定数量的比特币奖励。这个奖励的过程同时也是比特币的发行过程。节点不停的进行计算，以期获得系统发放的比特币。

最终，区块链通过构造一个竞争-记账-奖励为核心的经济系统，解决了去中心化记账的难题。比特币借助区块链打造了一个正向循环的经济系统，才使得起在没有强大的中心化机构或组织推动的情况下，自然的生长出来并发展壮大。

## 共识机制与价值载体

比特币区块链的共识机制是通过工作证明（POW）来实现的，这种机制的优点是显而易见的，每个节点可以平等地参与竞争，并通过激励构建了一个正循环的经济系统，从而逐渐积累了保护系统安全的庞大算力。

然而对工作量证明机制也有一些批评。一个常见的指责是“浪费”能源，因为节点进行算力竞赛是要消耗电力的。目前，投入挖矿竞争的总算力以及接近投入挖矿竞争的总算力以及接近1300P，挖矿也因此成了能源秘籍型的行业。

所谓公有链，是指比特币区块链这样的完全去中心化的、不受任何机构控制的区块链；而私有链则是指存在一定的中心化控制的区块链。

类似比特币区块链这样的公有链尚不能满足金融机构的一些基本要求，比如了解你的客户（KYC）、反洗钱（AML）等，因此，金融机构对私有链的兴趣更大。目前私有链最著名的例子是R3CEV公司牵头的区块链联名，它已经吸引了全球四十多家大型银行的加入，其中不乏美国银行、摩根大通等巨头的身影。

事实上，自比特币诞生之日起，它的模仿者或者竞争者就层出不穷。其中有很多都只是对比特币简单的复制和模仿，没有任何创新，我们将这种成为山寨币。还有一些并不是简单的模仿，而是有自己的创新和专注的领域，这种类型的币我们称之为竞争币。在数字货币的市值方面，尽管比特币遥遥领先，但之后诞生的莱特币、以太坊的市值都蹭短暂地超过10亿美元。

数字资产和区块链具有天然的亲和性。一般意义上讲，数字资产包含任何形式的以二进制格式存在并且具备所有权属性的东西。而在较为狭义的理解中，数字资产则是指以电子数据形式存在的，在日常生活中持有以备出售的非货币性资产，比如典型是股票、债券等金融产品。

如果说比特币等基于区块链的数字货币是一个刚诞生不久的婴儿，那么基于区块链的非货币形式的价值承载则还是一个孕育中的胚胎。作为价值载体，区块链可以承载的价值是非常丰富的。随着区块链技术的发展和相关基础设施的不断完善，我们相信区块链承载价值的范围不断扩大。

## 当交易变得智能

比特币的脚本语言非常简单，仅有256条指令，其中75个是被保留的，尚未被赋予任何含义。比特币脚本中的指令与其他编程语言类似，包含基本的语法、逻辑。除此之外还包括一些加密指令，如哈密函数、签名验证等。

比特币的多重签名技术就是使用脚本实现可变成交易的一个典型例子。其基本原理是，在系统里创建一个由多个人共同管理的账户，只有达到事先约定数量的人的同意，才能动用该账户的钱，并且这个过程是由系统本身保障执行的，不需要任何第三方介入。

一般来说，一个比特币地址对应一个私钥，动用这个地址中的资金只需要该私钥的掌握者单独发起签名即可。而多重签名技术就是多个私钥的共同签名才能动用一笔资金。比如说，某笔资金对应3个私钥，而必须至少有其中任意2个私钥参与签名才能动用，只有1个私钥参与签名是无效的。这个2/3可以推广到任意的m/n，比如3/5，4/7,6/11等，当然m要小于等于n。

从本质上讲，智能合约工作原理类似于计算机程序的条件执行语句。当一个预先编好的条件被触发时，智能合约执行相关的合同条款。由于区块链的可编程性，因此智能合约在区块链和数字货币上的应用是水到渠成的事情。

智能合约是计算机程序，所以很容易应用于其他需要的场景--增加更加细致的控制条件，完成更复杂的执行逻辑。这点类似传统的合同，我们也可以认为，智能合约就是合同以代码的形式搬到了区块链上，但这就带来了根本的区别：它不需要任何人监督合同的执行，订立合同的双方也无法在合同完成前单方面违约，一切都是按合同的约定自动执行的。相信随着区块链的普及和交易智能化的发展，它将会对未来的交易模式与商业结构带来巨大的影响。

## 将区块链连接起来

中本聪创造区块链的初衷是为了实现一个点对点的电子现金系统。因此，当我们对于区块链的用途有更高的期待时，它的一些局限就体现出来了。

本质上，区块链是不同数字价值的载体，而侧链技术则是连接不同区块链的通路。现在还不能断言最终成熟的侧链技术形态，甚至我们也不知道未来真正大规模应用于区块链件连接的技术是否会以“侧链技术”的名义出现，但是侧链技术的理念及核心功能的发展与成熟是毋庸置疑的。

## 区块链的未来