# Vue实例

## 创建一个 vue 实例

每个Vue应用都是通过Vue函数传入一些选项对象创建一个新的Vue实例开始的。

```js
var vm = new Vue({
  // 选项
})
```

所有的Vue组件本质上都是Vue实例。

## 数据与方法

创建了一个Vue实例之后，Vue会将data对象的property传入到Vue的**响应式系统**。当这些property值发生改变时，视图会产生“响应”。

需要注意的是，只有初始化Vue实例时，就已经存在于data对象的property才会是响应式的。所以如果一开始不确定某个property的值，可以先定义把这个property的值设为null。

Vue实例也会返回一些有用的实例属性和方法，为了和用户自定义的property区分开来，Vue实例的属性是带有前缀`$`的。

## 实例生命周期钩子

每个Vue实例在创建时，都会经历一系列的初始化过程：设置数据监听、编译模板、把Vue实例挂载到DOM并在数据变化时更新DOM等等。在这个过程中，会运行一系列叫生命周期钩子的函数。我们可以在对应的钩子添加相应的代码满足实际需要。

不要在选项 property或生命周期钩子上使用箭头函数表示，这会导致this的指向错误，而不是指向当前vue实例。

created：vue实例被创建完成之后运行的钩子，这时数据已经初始化完成。

mounted：vue实例被挂载到DOM之后运行的钩子

updated：数据更新，DOM更新后运行的钩子。