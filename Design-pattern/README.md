#设计模式
---
####设计模式(Design Pattern) 是一套被反复使用、多数人之知晓的、经过分类编目的、代码设计经验的总结。
####使用设计模式是为了可重用代码、让代码更容易被他人理解、保证代码可靠性。

---

***设计模式四个基本要素***

  1. 模式名称(pattern name)，用一两个词描述模式的问题、解决方案和效果<br/>
  2. 问题(problem)，描述应该在何时使用模式<br/>
  3. 解决方案(solution)，描述设计的组成成分，它们之间的关系及各自的职责和协作方式<br/>
  4. 效果(consequences)，描述模式应用的效果及使用模式应权衡的问题<br/>
  
***设计模式分类***

__1. 创建型__<br/>
  * Factory Method  工厂方法模式
  * Abstract Factory 抽象工厂模式   
  * Builder   建造者模式
  * Prototype    原型模式
  * Singleton  单例模式
  
__2.结构型__<br/>
  * Adapter 适配器模式
  * Bridge  桥接模式
  * Composite  组合模式
  * Decorator 装饰模式
  * Facade  外观模式
  * Flyweight 享元模式
  * Proxy  代理模式
  
__3.行为型__<br/>
  * Interpreter 解释器模式
  * Template Method 模板方法模式
  * Chain of Responsibility 责任链模式
  * Command 命令模式
  * Iterator  迭代器模式
  * Mediator  中介者模式
  * Memento 备忘录模式
  * Observer  观察者模式
  * State 状态模式
  * Strategy  策略模式
  * Visitor  访问者模式
  
***如何选择设计模式***

* 考虑设计模式是怎样解决设计问题的
* 浏览模式的意图部分
* 研究模式怎样互相关联
* 研究目的相似的模式
* 检查重新设计的原因
* 考虑你的设计中哪些是可变的

***如何使用设计模式***

* 大致浏览一遍模式
* 回头研究结构部分、参与者部分和协作部分
* 看代码示例部分，看看这个模式代码形成的具体例子
* 选择模式参与者的名字，使他们在应用上下文中有意义
* 定义类
* 定义模式中专用于应用的操作名称
* 实现执行模式中责任和协作的操作
  
  
###Singleton 单例模式

* 确保一个类最多有一个实例，并提供一个全局访问点
* 有些对象我们只需要一个：线程池、缓存、硬件设备等
* 如果多个实例会有造成冲突、结果的不一致性等问题
* 实现例子：静态变量 、全局变量
 
###MathFactory 工厂方法模式

***定义了一个创建对象的接口，但由子类决定要实例化的类是哪一个。工厂方法让类把实例化推迟到子类***
* 工厂接口。工厂接口是工厂方法模式的核心，与调用者直接交互用来提供产品。在实际编程中，有时候也会使用一个抽象类来作为与调用者交互的接口，其本质上是一样的。
* 工厂实现。在编程中，工厂实现决定如何实例化产品，是实现扩展的途径，需要有多少种产品，就需要有多少个具体的工厂实现。
* 产品接口。产品接口的主要目的是定义产品的规范，所有的产品实现都必须遵循产品接口定义的规范。产品接口是调用者最为关心的，产品接口定义的优劣直接决定了调用者代码的稳定性。同样，产品接口也可以用抽象类来代替，但要注意最好不要违反里氏替换原则。
* 产品实现。实现产品接口的具体类，决定了产品在客户端中的具体行为。

###AbstractFactory  抽象工厂模式

***抽象工厂模式是工厂方法模式的升级版本，他用来创建一组相关或者相互依赖的对象。***
* 他与工厂方法模式的区别就在于，工厂方法模式针对的是一个产品等级结构；而抽象工厂模式则是针对的多个产品等级结构。
* 在编程中，通常一个产品结构，表现为一个接口或者抽象类，也就是说，工厂方法模式提供的所有产品都是衍生自同一个接口或抽象类，而抽象工厂模式所提供的产品则是衍生自不同的接口或抽象类。
* 在抽象工厂模式中，有一个产品族的概念：所谓的产品族，是指位于不同产品等级结构中功能相关联的产品组成的家族。抽象工厂模式所提供的一系列产品就组成一个产品族；
* 而工厂方法提供的一系列产品称为一个等级结构。
* 抽象工厂模式除了具有工厂方法模式的优点外，最主要的优点就是可以在类的内部对产品族进行约束。所谓的产品族，一般或多或少的都存在一定的关联，抽象工厂模式就可以在类内部对产品族的关联关系进行定义和描述，而不必专门引入一个新的类来进行管理。
* 但产品族的扩展将是一件十分费力的事情，假如产品族中需要增加一个新的产品，则几乎所有的工厂类都需要进行修改。所以使用抽象工厂模式时，对产品等级结构的划分是非常重要的。
*  无论是简单工厂模式，工厂方法模式，还是抽象工厂模式，他们都属于工厂模式，在形式和特点上也是极为相似的，他们的最终目的都是为了解耦。在使用时，我们不必去在意这个模式到底工厂方法模式还是抽象工厂模式，因为他们之间的演变常常是令人琢磨不透的。经常你会发现，明明使用的工厂方法模式，当新需求来临，稍加修改，加入了一个新方法后，由于类中的产品构成了不同等级结构中的产品族，它就变成抽象工厂模式了；而对于抽象工厂模式，当减少一个方法使的提供的产品不再构成产品族之后，它就演变成了工厂方法模式。所以，在使用工厂模式时，只需要关心降低耦合度的目的是否达到了。
 
###Observer 观察者模式
***发布/订阅模式，观察者模式定义了一种一对多的依赖关系，让多个观察者对象同时监听某一个主题对象。这个主题对象在状态发生变化时，会通知所有观察者对象，使它们能够自动更新自己。***  <br/>

__1.解决问题：__
将一个系统分割成一个一些类相互协作的类有一个不好的副作用，那就是需要维护相关对象间的一致性。我们不希望为了维持一致性而使各类紧密耦合，这样会给维护、扩展和重用都带来不便。观察者就是解决这类的耦合关系的。<br/>

__2.模式中的角色__
* 抽象主题（Subject）：它把所有观察者对象的引用保存到一个聚集里，每个主题都可以有任何数量的观察者。抽象主题提供一个接口，可以增加和删除观察者对象。
* 具体主题（ConcreteSubject）：将有关状态存入具体观察者对象；在具体主题内部状态改变时，给所有登记过的观察者发出通知。
* 抽象观察者（Observer）：为所有的具体观察者定义一个接口，在得到主题通知时更新自己。
* 具体观察者（ConcreteObserver）：实现抽象观察者角色所要求的更新接口，以便使本身的状态与主题状态协调。<br/>

__3.优点:__
观察者模式解除了主题和具体观察者的耦合，让耦合的双方都依赖于抽象，而不是依赖具体。从而使得各自的变化都不会影响另一边的变化。
<br/>

__4.缺点:__
依赖关系并未完全解除，抽象通知者依旧依赖抽象的观察者。<br/>

__5.适用场景__
* 当一个对象的改变需要给变其它对象时，而且它不知道具体有多少个对象有待改变时。<br/>
* 一个抽象某型有两个方面，当其中一个方面依赖于另一个方面，这时用观察者模式可以将这两者封装在独立的对象中使它们各自独立地改变和复用。

###Adapter 适配器模式
***将一个类的接口转换成客户希望的另外一个接口。***<br/>

__1.解决的问题__<br/>
* 即Adapter模式使得原本由于接口不兼容而不能一起工作的那些类可以在一起工作。

__2.模式中的角色__<br/>
* 目标接口（Target）：客户所期待的接口。目标可以是具体的或抽象的类，也可以是接口。
* 需要适配的类（Adaptee）：需要适配的类或适配者类。
* 适配器（Adapter）：通过包装一个需要适配的对象，把原接口转换成目标接口。　

__3.优点__<br/>
* 通过适配器，客户端可以调用同一接口，因而对客户端来说是透明的。这样做更简单、更直接、更紧凑。
* 复用了现存的类，解决了现存类和复用环境要求不一致的问题。
* 将目标类和适配者类解耦，通过引入一个适配器类重用现有的适配者类，而无需修改原有代码。
* 一个对象适配器可以把多个不同的适配者类适配到同一个目标，也就是说，同一个适配器可以把适配者类和它的子类都适配到目标接口。

__4.缺点__<br/>
* 对于对象适配器来说，更换适配器的实现过程比较复杂。

__5.应用场景__<br/>
* 系统需要使用现有的类，而这些类的接口不符合系统的接口。
* 想要建立一个可以重用的类，用于与一些彼此之间没有太大关联的一些类，包括一些可能在将来引进的类一起工作。
* 两个类所做的事情相同或相似，但是具有不同接口的时候。
* 旧的系统开发的类已经实现了一些功能，但是客户端却只能以另外接口的形式访问，但我们不希望手动更改原有类的时候。
* 使用第三方组件，组件接口定义和自己定义的不同，不希望修改自己的接口，但是要使用第三方组件接口的功能。

###Proxy 代理模式
***为其他对象提供一种代理以控制对这个对象的访问***<br/>

___代理模式一般涉及到的角色有：___<br/>
* 抽象角色：声明真实对象和代理对象的共同接口；
* 代理角色：代理对象角色内部含有对真实对象的引用，从而可以操作真实对象，同时代理对象提供与真实对象相同的接口以便在任何时刻都能代替真实对象。同时，代理对象可以在执行真实对象操作时，附加其他的操作，相当于对真实对象进行封装。
真实角色：代理角色所代表的真实对象，是我们最终要引用的对象。 







