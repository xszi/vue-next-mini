# vue-next-mini

初次渲染： 挂载
更新渲染： 打补丁

对 vue3 的 ts 支持友好的原因不是因为 vue3 是采用 ts 编写的，而是因为 vue3 里面做了很多工作让开发人员可以方便的使用 ts，比如类型的准备。

todo：

- 看下 vue3，渲染相关的官方文档
- sfc 工具

插件liveserver启动html
pnpm文档查阅
源码sourceMap开启及原理 （-s）
debugger断点调试


创建vue-next-mini
代码格式化prettier
模块打包器rollup
配置路径映射

如何阅读源码

不要纠结于搞懂每一行代码
确定一条主线看下去，不管边缘的代码


# 第四章

去
Q1: vue2和vue3在响应式设计上有什么区别？为什么会有这些变化

object.defineProperty可以监听指定对象上指定属性的getter和setter行为；

vue2中响应性的限制：

1. 当为对象新增一个没有在data中声明的属性时，新增的属性不是响应性的；
2. 当为数组通过下标的形式新增一个元素时，新增的元素不是响应性的；

object.defineProperty缺陷：

1. 只可以监听指定对象指定属性的getter和setter；
2. 被监听了getter和setter的属性，被叫做该属性具有了响应性；

意味着，我们必须知道对象中存在该属性，才能为该属性指定响应性；

安全的使用 Proxy，还需要配合 Reflect 一起才可以，因为一旦我们在被代理对象内部，通过 this 触发 getter 和 setter时，也需要被监听到。

mdn看下proxy(代理)文档，reflect(拦截， proxy的最佳拍档，靠谱)

与大多数全局对象不同 Reflect 并非一个构造函数，所以不能通过 new 运算符对其进行调用，或者将 Reflect 对象作为一个函数来调用。Reflect 的所有属性和方法都是静态的（就像 Math 对象）。


一些 Vue 编译器用来提高虚拟 DOM 运行时性能的主要优化：

1. 静态提升；
2. 更新类型标记；
3. 树结构打平；