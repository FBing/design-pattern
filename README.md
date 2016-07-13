# Design-patterns
## 一、Singleton
### 1.模式定义
确保一个类仅有一个实例，并且提供一个访问它的全局访问点。
<br>
### 2.代码示例
[示例1:单例模式](src/main/java/com/ricky/designpattern/singleton/ch2/Singleton1.java)<br>
[示例2:单例模式-饿汉式](src/main/java/com/ricky/designpattern/singleton/ch1/Singleton.java)<br>
[示例3:单例模式-双重检查](src/main/java/com/ricky/designpattern/singleton/ch3/Singleton2.java)<br>
[示例4:单例模式-静态内部类](src/main/java/com/ricky/designpattern/singleton/ch4/Singleton3.java)<br>
<br>

## 二、Builder
### 1.模式动机
无论是在现实世界中还是在软件系统中，都存在一些复杂的对象，它们拥有多个组成部分，如汽车，它包括车轮、方向盘、发动机等各种部件。而对于大多数用户而言，无须知道这些部件的装配细节，也几乎不会使用单独某个部件，而是使用一辆完整的汽车，可以通过建造者模式对其进行设计与描述，建造者模式可以将部件和其组装过程分开，一步一步创建一个复杂的对象。用户只需要指定复杂对象的类型就可以得到该对象，而无须知道其内部的具体构造细节。

在软件开发中，也存在大量类似汽车一样的复杂对象，它们拥有一系列成员属性，这些成员属性中有些是引用类型的成员对象。而且在这些复杂对象中，还可能存在一些限制条件，如某些属性没有赋值则复杂对象不能作为一个完整的产品使用；有些属性的赋值必须按照某个顺序，一个属性没有赋值之前，另一个属性可能无法赋值等。

复杂对象相当于一辆有待建造的汽车，而对象的属性相当于汽车的部件，建造产品的过程就相当于组合部件的过程。由于组合部件的过程很复杂，因此，这些部件的组合过程往往被“外部化”到一个称作建造者的对象里，建造者返还给客户端的是一个已经建造完毕的完整产品对象，而用户无须关心该对象所包含的属性以及它们的组装方式，这就是建造者模式的模式动机。
### 2.模式定义
将一个复杂对象的构建与它的表示分离，使得同样的构建过程可以创建不同的表示。

建造者模式是一步一步创建一个复杂的对象，它允许用户只通过指定复杂对象的类型和内容就可以构建它们，用户不需要知道内部的具体构建细节。建造者模式属于对象创建型模式。根据中文翻译的不同，建造者模式又可以称为生成器模式。
<br>
### 3.模式结构
建造者模式包含如下角色：<br>
* Builder：抽象建造者接口，定义创建一个Product对象所需的各个部件的操作。
* ConcreteBuilder：具体的建造者实现，实现各个部件的创建，并负责组装Product对象的各个部件，同时还提供一个让用户获取组装完成后的产品对象的方法。
* Director：指挥者，也称为导向者，主要用来使用Builder接口，以一个统一的过程来构建所需要的Product对象。
* Product：产品，表示被建造者构建的复杂对象，包含多个部件。

![GitHub](http://images.cnblogs.com/cnblogs_com/feipeng/Pic11.jpg "Builder Pic")

###4.代码示例
[示例1:PersonBuilderDemo.java](src/main/java/com/ricky/designpattern/builder/PersonBuilderDemo.java)<br>
[示例2:CarDemo.java](src/main/java/com/ricky/designpattern/builder/CarDemo.java)<br>
[示例3:IvrEngineDemo.java](src/main/java/com/ricky/designpattern/builder/IvrEngineDemo.java)<br>
[示例4:MessageDemo.java](src/main/java/com/ricky/designpattern/builder/MessageDemo.java)<br>
<br>
### 5.优缺点
#### 优点
* 在建造者模式中， 客户端不必知道产品内部组成的细节，将产品本身与产品的创建过程解耦，使得相同的创建过程可以创建不同的产品对象。
* 可以更加精细地控制产品的创建过程。将复杂产品的创建步骤分解在不同的方法中，使得创建过程更加清晰，也更方便使用程序来控制创建过程。
* 增加新的具体建造者无须修改原有类库的代码，指挥者类针对抽象建造者类编程，系统扩展方便，符合“开闭原则”。

#### 缺点
* 使用Builder模式是肯定会增加代码量的。此外，尽管客户端的代码可读性明显改善，但随之而来的客户端代码变得更加冗长。
* Builder会增加个类代码，这也意味着开发者在给类增加属性时有时会忘记给该属性添加支持的builder。

<br>
### 6.与工厂模式的区别

<br>
### 7.适用场景
在以下情况下可以使用建造者模式：<br>
* 需要生成的产品对象有复杂的内部结构，这些产品对象通常包含多个成员属性。
* 需要生成的产品对象的属性相互依赖，需要指定其生成顺序。

### 8.资料
[java-design-patterns](https://github.com/iluwatar/java-design-patterns)<br>



