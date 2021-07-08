#Advanced
---
什么是回调函数？
---
* 自行定义
* 开发者没有调用
* 但自身执行了

常见的回调函数：
---
* DOM事件回调函数
* 定时器回调函数
* Ajax回调函数
* 生命周期回调函数

IIFE：Immediately-Inoked Function Expression(立即执行函数)
---
* 隐藏实现
* 不会污染外部命名空间
* 用于编码js模块

prototype
---
* 每个函数都有一个prototype属性，默认指向一个空的Object对象，即原型对象
* 原型对象中有一个属性constructor指向函数对象
* 给原型对象添加属性的作用：
    * 函数的所有实例对象，自动拥有原型中的属性(方法)
* 显示原型
    * 每个函数都有一个prototype属性，即显示原型属性
* 隐式原型
    * 每个实例对象都有一个_ _ proto _ _ 属性，即隐式原型属性
* 对象的隐式原型的值与气对应构造函数的显示原型的值相等！
* speical
    * 函数的prototype属性，指向的对象，默认为空的Object实例对象
    * 所有函数都是Function的实例(包括Function)
    *   

