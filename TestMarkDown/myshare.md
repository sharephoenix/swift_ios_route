
<!-- 没有思想，没有框架，没有设计模式，遇见问题解决问题会比较好。 -->

任何好的思想都需要大量的 用例去验证在当下的产品和需求中是否合理。
概念的交流的基础：我们还是需要这道一些基本概念的，不然，相互之间就无法交流了。

## 我理解的设计模式
* 框架、设计模式、架构
    1. 框架：通常指常用的代码。
    2. 设计模式：长值得是设计重用
    3. 架构：结余框架和设计模式之间，部分设计重用，部分代码重用，分析重用。
* 设计模式有什么用
    1. 设计模式，是开发先辈们，在开发中长期积累的经验，给我们留下的宝贵财富。
    2. 设计模式可以让我们站在巨人的肩膀上，思考。
* 曾经遇见的几个和设计模式有关的坑
    1. 响应式编程，滥用 ReactiveCocoa 导致全工程的 信号传递。堆栈混乱，出现问题时候很难定位。性能快速下降。
    2. 误解 ViewController 就是 MVC 框架中的 Controller。
    3. 滥用 xib，xib 的界面复用功能。导致，一般的新人，根本看不懂逻辑。
* MVC From JSP From Document/View
  1. 模型（Model） 用于封装与应用程序的业务逻辑相关的数据以及对数据的处理方法。“ Model ”有对数据直接访问的权力，例如对数据库的访问。“Model”不依赖“View”和“Controller”，也就是说， Model 不关心它会被如何显示或是如何被操作。但是 Model 中数据的变化一般会通过一种刷新机制被公布。为了实现这种机制，那些用于监视此 Model 的 View 必须事先在此 Model 上注册，从而，View 可以了解在数据 Model 上发生的改变。（比如：观察者模式（软件设计模式））
  2. 视图（View）能够实现数据有目的的显示（理论上，这不是必需的）。在 View 中一般没有程序上的逻辑。为了实现 View 上的刷新功能，View 需要访问它监视的数据模型（Model），因此应该事先在被它监视的数据那里注册。
  3. 控制器（Controller）起到不同层面间的组织作用，用于控制应用程序的流程。它处理事件并作出响应。“事件”包括用户的行为和数据 Model 上的改变。
    <img src="./images/share0/mvc.png"/>
* M V VM
    <img src="./images/share0/mvvm.png">
* 对设计模式的使用的想法
    1. 每个设计模式，都有自己，本来的使用场景，切记不可以完全套用
    2. 每个设计模式，都需要在根据业务，做出少许的变动
* 目前流向的框架有哪些
   1. MVC、M V VM、MVP 的区别是什么？
   2. MVC、M V VM、MVP 和我们理解的他们有什么不同？
    1. 对我来说没啥区别, 都是把代码合理分离的思想。只要是能够, 更好的完成代码功能都是好的设计模式。这些都是为了分担 原来 C 的负担，或者为了 让 C 更倾向于那一块的责任

* 我常用的设计模式
    1. 单例、工厂、组合、代理、命令、观察者、状态、MVC....

* 框架 是为了解决什么问题的？ （我不会问什么是 “框架”）
  1. 框架是为了让整个项目，可以按照已经约定好的规则，让程序员写出统一的代码。
  2. 统一数据流的方向 和 事件分发。
  3. 统一界面管理，和界面中对应的事件管理。尽量可以在 多层级中的任何 View 中都可以访问到事件，下发响应的指令。

* 殊途同归，所有框架都是为了，数据流 的清晰，使开发者有一个基本的开发思路，团队中可以根据框架的思路，编写出统一数据流的，代码结构。
  
***
# 我的工程原则
    1. 低耦合 高内聚 弱耦合。
    2. 不同的人开发的内容之间，弱耦合。
    3. 不同的业务之间，弱耦合。
    4. 切记过度开发，过度思考。
    5. 能用简单方法实现的方法，坚决不适用复杂的实现方式。
    6. 项目发生，业务耦合或者内码耦合，及时找时间重构。
    7. 他人维护代码，尽量可以快速的找到，代码的逻辑。（UI 颗粒化,code 颗粒化）

## 我的项目开发框架模型图。

<img src="./images/share0/history_design_struct.png">

## 我的框架组件，和项目框架，没有耦合
  <img src="./images/share0/widgets.png">

* 项目开发模式是要根据业务需求不断演化 重构出来。
* 没有完美的开发框架和开发模式。
***
## 对于 看项目奖代码 目前想要得到 “回答” 和 “疑惑”
    1. 部分 的 protperty 和 function 没有 private 标志。
    2. 系统默认的 internal 是否需要添加?如果不需要添加，我们看别人的代码如何才能很快的找到 外部可以调用的代码.
    3. 对于生命周期 的 方法放在 category 中怎么看
    4. http://www.xiaoheiban.cn/agreements.html  http://test.xiaoheiban.cn/Help-xhbGuide?type=bag_guide 有一个这个链接直接放在了界面中，我的理解应该放在，统一的配置文件中
    5. MyselfInfoViewController 这个界面中 username 属性
    6. GrowthClassroomChooseViewController DoSurveyViewController 有些类中有很多 其他的类，在开头部分，不太习惯
    7. PunchRecordDetailViewController 扩展类有点多，有说明扩展类的功能就比较好了
    8. PunchFrequencySettingViewController 属性放在 类的中间
    9. open private(set) lazy var 这个标志的用法没有找到啊