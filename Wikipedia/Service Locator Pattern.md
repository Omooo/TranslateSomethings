---
Service Locator Pattern（服务定位模式）
---

#### 原文链接

[https://en.wikipedia.org/wiki/Service_locator_pattern](https://en.wikipedia.org/wiki/Service_locator_pattern)

#### 概述

> The **service locator pattern** is a [design pattern](https://en.wikipedia.org/wiki/Design_pattern_(computer_science)) used in [software development](https://en.wikipedia.org/wiki/Software_development_tool) to encapsulate the processes involved in obtaining a service with a strong [abstraction layer](https://en.wikipedia.org/wiki/Abstraction_layer). This pattern uses a central registry known as the "service locator", which on request returns the information necessary to perform a certain task.[[1\]](https://en.wikipedia.org/wiki/Service_locator_pattern#cite_note-1) Proponents of the pattern say the approach simplifies component-based applications where all dependencies are cleanly listed at the beginning of the whole application design, consequently making traditional dependency injection a more complex way of connecting objects. Critics of the pattern argue that it is an [anti-pattern](https://en.wikipedia.org/wiki/Anti-pattern#Software_design) which obscures dependencies and makes software harder to test.[[2\]](https://en.wikipedia.org/wiki/Service_locator_pattern#cite_note-2)[*[better source needed](https://en.wikipedia.org/wiki/Wikipedia:NOTRS)*]

服务定位器模式是软件开发中使用的一种设计模式，用于封装获得具有强抽象层的服务所涉及的过程。此模式使用一个称为“服务定位器”的中央注册表，它根据请求返回执行特定任务所需的信息。该模式的支持者表示，该方法简化了基于组件的应用程序，在整个应用程序设计的开始就清楚地列出了所有依赖项，从而使传统的依赖项注入成为连接对象的更复杂的方式。这种模式的批评者认为，它是一种反模式，它模糊了依赖关系，使软件更难测试。

#### 优势

> - The "service locator" can act as a simple [run-time](https://en.wikipedia.org/wiki/Run_time_(program_lifecycle_phase)) [linker](https://en.wikipedia.org/wiki/Linker_(computing)). This allows code to be added at run-time without re-compiling the application, and in some cases without having to even restart it.
> - Applications can optimize themselves at run-time by selectively adding and removing items from the service locator. For example, an application can detect that it has a better library for reading JPG images available than the default one, and alter the registry accordingly.
> - Large sections of a library or application can be completely [separated](https://en.wikipedia.org/wiki/Separation_of_concerns). The only link between them becomes the registry.
> - An application may use multiple structured service locators purposed for particular functionality/testing. Service locator does not mandate one single static class per process.
> - The solution may be simpler with service locator (vs. dependency injection) in applications with well-structured component/service design. In these cases the disadvantages may actually be considered as an advantage (e.g. no need to supply various dependencies to every class and maintain dependency configurations).

* Service Locator 可以看作一个简单的运行时链接器。它允许代码能够在运行时被添加，而不需要重新编译应用程序，在某些情况下也不需要重启应用程序。
* 应用程序可以在运行时通过选择性地从服务定位器中添加和删除项来优化自身。例如，应用程序可以发现比默认库更好的读取 JPG 图片库可用，并相应的改变注册表。
* 库或应用程序的大部分可以完全分离。它们之间的唯一链接是注册表。
* 应用程序可以使用多个结构化服务定位器，用于特定功能/测试。服务定位器不要求每个进程有一个静态类。
* 在具有良好结构的组件/服务设计的应用程序中，使用服务定位器（相对于依赖注入），解决方案可能更简单。在这些情况下，缺点实际上可以被视为优点（例如，不需要为每个类提供各种依赖性并维护依赖性配置）。

#### 劣势

> - The registry hides the class' dependencies, causing [run-time errors](https://en.wikipedia.org/wiki/Run-time_error) instead of compile-time errors when dependencies are missing (similar to using [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection)). But each library is compiled, just the discovery of the concrete Class might not be found and cause an error, it's more a deployment issue than a Service Locator issue.
> - The registry makes code harder to [test](https://en.wikipedia.org/wiki/Software_testing), since all tests need to interact with the same global service locator class to set the fake dependencies of a class under test. However, this is easily overcome by injecting application classes with a single service locator interface. Simulator can be implemented to simulate each interface provided by the service locator, so it's easy to swap the real implementation with a simulator.

* 注册表隐藏类的依赖项，当缺少依赖项时，会导致运行时错误而不是编译时错误（类似于使用依赖项注入）。但是，每个库都是编译的，只是可能找不到具体类的发现并导致错误，这更像是部署问题，而不是服务定位器问题。
* 注册表使代码更难测试，因为所有测试都需要与同一个全局服务定位器类交互，以设置被测试类的伪依赖关系。但是，通过使用单个服务定位器接口注入应用程序类可以很容易地克服这一问题。可以实现模拟器来模拟服务定位器提供的每个接口，因此很容易将实际实现与模拟器交换。

#### 另见

* 依赖注入
* 依赖反转原则
* Java Naming and Directory Interface
