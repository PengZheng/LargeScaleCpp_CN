# 设计指南

## 第二章

* 每个物理聚合在设计上应当被视为原子的。（2.2.4）
* 架构内聚的逻辑实体应当被紧密地封装在物理实体内。（2.3）
* 对任何在包级命名空间作用域中声明的逻辑实体的使用应当足以表明定义该实体的组件、包和发布单元。（2.4.6）
* 除了企业级命名空间和直接嵌套的包级命名空间之外，应当避免以架构显著的方式使用 C++ 命名空间。（2.5）
* .h 文件应只包含那些必要的 `#include` 指令（或适当的本地前置类声明）以确保该头文件可独立编译。（2.6）
* 除非有工程上的正当理由，否则每个组件都应只有一个（公共）类。（2.6）
* 避免在一个类的词法作用域内定义嵌套类。（2.7.3）
* 避免声明嵌套类。（2.7.3）
* 在可能的情况下，每个包都应当是一个适当包组的一部分。换言之，尽可能避免独立包。（2.9.3）
* 可容许的包组间依赖应该是最小的并且很少需要增加。（2.9.3）
* 企业内每个（可共享）发布单元的名称应在使用前向管理中心注册（并保留）。（2.10.3）
* 每个测试驱动程序的调用接口都应当有一个符合企业标准的明确定义的子集。（2.14.7）
* 每个测试驱动程序的“用户体验”（在理想情况下）在企业内部应当是标准的。（2.14.7）

## 第三章

* 不断地把为特定应用创建的通用功能分解出来，并且在时间允许的情况下，积极地将其沉淀到我们不断增长的软件资产仓库的物理层级中的合适位置。（3.2.2）
* 除非有令人信服的工程理由，否则要避免将多于一个（公共）类放在同一个组件中。（3.2.5）
* 尤其要避免将预期用户彼此不重合的类放在一起。（3.2.5）
* 避免将预期用户彼此不重合的功能放在一起。（3.2.5）
* 我们设计的每个组件都应具有聚焦的目的。（3.2.5）
* 可复用组件所提供的功能应当是完整的但同时也是最小的。（3.2.5）
* 在定义了可实例化类型的组件中实现的几乎所有（领域特定的）功能都应当是初等的。（3.2.7）
* 作用于可实例化类型的大多数非初等功能都应当在更高层级的工具（utility）结构体中实现。（3.2.7）
* 追求提供最高性能的接口，同时尽可能保持实现选项的开放性和灵活性。（3.2.8.6）
* 相比于直接实现初等的应用级功能，提供低层级的、可复用的初等功能更好。（3.2.8.11）
* 通过确保每个组件的功能完整性来尽力提供足够的初等功能以支持开闭原则：任意应用功能都可以在一个单独的、更高层级的组件中实现（如，由用户实现）。（3.2.8.15）
* 相比于语法，语义和物理依赖更适合作为模块化的标准，尤其是在包这一层级。（3.2.9）
* 除非有令人信服的工程理由，否则要避免在单个组件中定义多个公共类。（3.3.1）
  * 理由一：友元（3.3.1.1）
  * 理由二：循环依赖（3.3.1.2）
  * 理由三：单一解决方案。这些类无法独立复用，需要一起使用才能解决一个给定问题。（3.3.1.3）
  * 理由四：大象之上的跳蚤（3.3.1.4）
* 必须同时更改的软件要并置在一起。（3.3.2）
* 将跨公共组件的紧密协作限制在一个发布单元内。（3.3.6）
* 尽量减少以下情形的发生：在一个给定的程序中因为使用了一个组件而限制或排除了该组件在同一程序中的复用（如用于其他目的）或对其他组件的使用。（3.9.1）
* 避免对组件进行领域特定的条件编译。（3.9.2）
* 避免可复用库组件中特定于应用的依赖。（3.9.3）
* 避免人为约束复用的逻辑结构或模式。（3.9.4）
* 设计软件要避免意外滥用，但不用特意去防范恶意滥用。（3.9.5）
* 避免在定义 main 的文件之外定义全局实体。（3.9.6）
* 避免为了逻辑封装而隐藏头文件。（3.9.6）
* 最大限度地减少和隔离对不可移植软件的创建和使用。（3.9.8）
* 尽量减少对包级本地（私有）组件的需求。（3.9.9）
