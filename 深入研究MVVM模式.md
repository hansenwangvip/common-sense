![image](https://github.com/hansenwangvip/common-sense/assets/18462980/5b7d1706-8455-42ee-8846-7c219a679cb7)# 深入研究MVVM模式

软件架构模式，解决软件工程的问题。架构模式这个词属于软件工程，从建筑工程衍生而来。

其中一个经典的架构模式就是MVC模式。

## 先了解MVC模式
MVC：Model–view–controller，它是一个模式，一个理念，而不是一项技术。

MVC模式在概念上强调 Model, View, Controller 的分离，各个模块也遵循着由 Controller 来处理消息，Model 掌管数据源，View 负责资料显示的职责分离原则。

Model：负责访问资料，例如：使用DTO作为独立的资料对象，使用ORM框架来访问资料，再通过不同的仓库进行分隔。
Controller：负责处理消息，职责分离，每个Controller的分工不一样，所以各个Controller分割在独立的文件中。
View：负责显示资料，大部分为前端应用，比如JSP、Angular.js。

一个JavaScript的MVC模式示例：
```js
/** 模拟 Model, View, Controller */
var M = {}, V = {}, C = {};

/** Model 负责存放资料 */
M.data = "hello world";

/** View 负责将资料输出给用户 */
V.render = (M) => { alert(M.data); }

/** Controller 作为连接 M 和 V 的桥梁 */
C.handleOnload = () => { V.render(M); }

/** 在网页读取的时候呼叫 Controller */
window.onload = C.handleOnload;
```

## 核心在VM

所以MVVM的核心问题在于VM。
MVVM表示的是 Model-View-ViewModel

Model：模型层，负责处理业务逻辑以及和服务器端进行交互
View：视图层：负责将数据模型转化为UI展示出来，可以简单的理解为HTML页面
ViewModel：视图模型层，用来连接Model和View，是Model和View之间的通信桥梁

![image](https://github.com/hansenwangvip/common-sense/assets/18462980/e9ac5cad-a16f-4194-80d7-5c03c0d46d12)

而类似于Vue.js这类框架的核心功能就是实现了VM这一端，让前端实现了三层的分离，即所谓的“数据驱动”。开发者只需要关注数据和视图的绑定，然后修改数据即可让视图随之生效。

## 总结
在工程领域，工程师（开发者）都在持续地改进研发效率，MVVM就是在不断地钻研中提出来的架构模式。在前端领域大幅提高了复杂web应用的研发效率，解放了前端工程师的心智负担。

## 参考资料
- https://zh.wikipedia.org/wiki/MVVM
- https://github.com/a1029563229/InterviewQuestions/tree/master/javascript/33
- https://vue3js.cn/interview/vue/vue.html
