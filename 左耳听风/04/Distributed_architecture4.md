## 分布式系统关键技术：服务调度

服务调度：
1. 在业务上，要辨别不同服务的关键程度
2. 在运行上，要知晓依赖关系
3. 在架构上，要对其版本进行管理
4. 在周期上，其状态需要闭环管理


没有依赖，就没有伤害。服务间的依赖是一件很易碎的事。依赖越多，依赖越复杂，系统就越易碎。
但是要真正做到服务无依赖，我认为还是比较有困难的，总是会有一些公有服务会被依赖。
我们只能是降低服务依赖的深度和广度，从而让管理更为简单和简洁。
微服务是服务依赖最优解的上限，**而服务依赖的下限是千万不要有依赖环**。解决服务依赖环的方案一般是，依赖倒置的设计模式。
服务的依赖关系是可以通过技术的手段来发现的。


整个架构中有多少种服务、服务的版本是什么样的、服务的版本是什么样的，是在部署中，运行中，故障中，升级中，还是在回滚中，伸缩中，或者是在下线中……

服务注册中心：汇总服务运作的状态和情况

服务的生命周期通常会有以下几个状态：
- Provision，代表在供应一个新的服务；
- Ready，表示启动成功了；
- Run，表示通过了服务健康检查；
- Update，表示在升级中；
- Rollback，表示在回滚中；
- Scale，表示正在伸缩中（可以有 Scale-in 和 Scale-out 两种）；
- Destroy，表示在销毁中；
- Failed，表示失败状态。


服务和资源调度的过程，与操作系统调度进程的方式很相似

服务的弹性伸缩和故障迁移
- 宠物模式，就是一定要救活
- 奶牛模式，就是不用救活了，重新生成一个实例

服务工作流和编排

通过一定的机制把一堆独立工作的进程给协同起来。


「此文章为3月Day4学习笔记，内容来源于极客时间《左耳听风》，强烈推荐该课程！」