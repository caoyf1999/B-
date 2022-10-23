# CPU 性能提升的两大关键：**制程和架构**

网址：https://www.bilibili.com/video/BV17U4y1R7Tg

&nbsp;

制程在摩尔定律那视频的笔记讲了，现在面临着瓶颈

（**更小的晶体管意味着运行在更高的时钟频率**，类比电感体积与频率的关系）

&nbsp;

这里主要讲讲**架构的含义** 以及**大小核异构的类比**

&nbsp;

## 架构有两种解释：**指令集架构，微架构**

&nbsp;

**指令集架构**规定了从软件到硬件的翻译规范，定义在软件中可进行哪些操作（比如加减运算，地址跳转）

（后续的硬件实现应该属于**微架构**的范畴了）

&nbsp;

厂商在发布新芯片时提到的某某新架构，是**微架构**

它是指令集架构的一种具体设计和实现

&nbsp;

## 微架构影响性能的类比：

【01:53 类比电子厂的工作流程】

微架构就是设计了流水线，

通过微架构改进 CPU 的工作流水线，CPU 性能也就大大提高了。

&nbsp;

【03:16 功效和能耗的举例】

通过增加工人（制程）和改进流水线（微架构）的方式，也使生产成本（能耗）和生产风险（功效）提高

生产风险是指并不是每天有那么多的任务给工人工作，那就是白发工资了。

&nbsp;

【05:18 调度大小核的办法】

大小核的异构方法，使的在高需求场景下性能不掉队，同时降低了低需求场景下的能耗

但是大小核的调度切换会造成一定的性能损失

以线程为单位进行调度，线程是进程的子集

是 CPU 调度分配任务的最小单位，可以并发运行进程则是操作系统正在进行的一个个程序任务（可以由任务管理器查看）

&nbsp;

【05:44 具体的分配流程】

**监工相当于线程调度器 ITD**，工头是 OS，

熟练工是 P 核，新员工是 E 核

## （监工是项目经理，工头是技术总负责人，熟练工是大牛老员工，新员工是应届生）

[大小核异构的形象解释](http://m.qpic.cn/psc?/V533uQTC1PsA1y3mTS0h0iehDt3y7kXY/ruAMsa53pVQWN7FLK88i5o.DW4JIGwSqtCV0ptByW8cCMJXOBL1rNDi1S2NVoVwN0wNvnjete2DMlayo2PA92PjKt2iDXVEIMZ0iWkkjs*8!/b&bo=gAc4BAAAAAADB5k!&rf=viewer_4)

&nbsp;

13 代酷睿中的 CPU 各级缓存的作用：

[CPU 读写内存](http://m.qpic.cn/psc?/V533uQTC1PsA1y3mTS0h0iehDt3y7kXY/ruAMsa53pVQWN7FLK88i5o.DW4JIGwSqtCV0ptByW8ePFzyhxNihqOoe35RU3JYZdxljL6tCcLLBH9E86A9FE4kHeskiX3XP8akm3N1dfwY!/b&bo=TwPeAQAAAAADB7E!&rf=viewer_4)

由于 CPU 距离内存比较远，所以要**提前预测 可能出现数据读写的地方** (用机器学习方法)

(具体去看老石的视频：https://www.bilibili.com/video/BV1U84y1q7bt)
