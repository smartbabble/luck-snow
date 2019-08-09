###### 声明

---

遵守基本互联网礼仪,文明和谐,尊重原创

---

 #### python风格规范

 #### python语言规范

 #### python函数设计规范
 - partial构造新的函数
 - 抛出异常，而不是返回错误与结果
 - 谨慎使用None值返回值
 - 使用空对象模式，降低处理成本
 - 生成器代替返回列表
 - 限制递归使用，递归层级限制，不支持尾递归优化
 
 #### pyton的oop思想设计与面向对象的SOLID设计原则
 - S：单一职责原则（Single responsibility principle）,类的职责越多则类的复杂度越高，实现方法。
   - 拆分大类为小类
   - 使用函数
 - O：开放-关闭原则（Open–closed principle）对扩展开放，对修改封闭,关键在于抽象能力。
   - 使用类继承来改造代码
   - 使用组合与依赖注入来改造代码
   - 使用数据驱动思想来改造代码,（代码更简洁,可定制性差）
 - L: 里氏替换原则(Liskov Substitution Principle)是继承和复用的基石。
 - I: 接口分离原则(The Interface Segregation Principle)，依赖性应当是建立在最小的接口上的，细化接口。
 - D: 依赖倒置原则(The Dependency Inversion Principle)，程序要依赖于抽象接口，要对抽象进行编程，不要依赖于具体实现

###### 参考资料:

[Google开源风格指南](https://zh-google-styleguide.readthedocs.io/en/latest/contents/)

[python工匠](https://github.com/piglei/one-python-craftsman)
