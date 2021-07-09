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
   * Object的原型对象是原型链的尽头
      * Object.prototype.__proto__; // null

原型链的属性问题
---
* 读取对象的属性值时：
  * 会自动到原型链中查找
* 设置对象属性值时：
  * 不查找原型链，若当前对象中无此属性，则直接添加该属性并设置值
* 方法一般定义在原型中，属性一般通过构造函数定义在对象本身上  

执行上下文
---
* 全局执行上下文
  * 在执行全局代码之前：将window，确定为全局执行上下文
  * 对全局数据进行预处理
    * var定义的全局变量->undefined，添加为window的属性
    * function声明的全局函数->赋值，添加为window的方法
  * this->赋值(window)
  * 开始执行全局代码
    * console.log(a1,window.a1);  // undefined,undefined
    * a2();                       // 'a2()'，函数提升
    * console.log(this);          // window
    * var a1 = 3;
    * function a2(){ console.log('a2()') }
    * console.log(a1);            // 3

* 函数执行上下文
  * 在调用函数，准备执行函数体之前：
  * 创建对应的函数执行上下文对象(虚拟的，存于栈中)
  * 对局部数据进行预处理
    * 形参变量->赋值变实参->添加为上下文的属性
    * arguments->赋值->添加为上下文属性
    * var定义的局部变量->undefined->添加为上下文的属性
    * function声明的函数->赋值->添加为上下文的方法
    * this->赋值给调用函数的对象
  * 开始执行函数体代码
    * function fn(a1){
    *   console.log(a1);          // 2
    *   console.log(a2);          // undefined，变量提升
    *   a3();                     // 'a3()'，函数提升
    *   console.log(this);        // window
    *   console.log(arguments);   // 伪数组(2,3)
    *   var a2 = 3;
    *   function a3(){
    *     console.log('a3()');
    *   }
    * }
    * fn(2,3);    

