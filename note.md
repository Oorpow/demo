Basic
=====
JS的组成
-----
* ECMAScript
* DOM(文档对象模型)
* BOM(浏览器对象模型)

Js特点
---
* 解释型语言
* 类似C、Java的语法结构
* 动态语言
* 基于原型的面向对象

基础认知
---
* 字面量
  * 一些不可改变的值，如1，2，3
  * 字面量可直接使用，但一般不用

* 变量
  * 可以用于保存字面量，且变量的值可以任意改变

* 标识符
  * 可以包含：字母，数字，下划线，$
  * 不能以数字开头
  * 不能是ES标准中的关键字或保留字
  * 一般采用驼峰命名

* 注意事项
  * js底层标识符保存时，采用unicode编码，即utf-8含有的内容，均可作为标识符

数据类型 == 字面量的类型
---
* 基本数据类型
  * String
  * Number
    * 所有数值均为NumberLeixing ,包括浮点
    * js中，整数运算基本可以保证精确，但若进行浮点运算，会得到一个不精确的数字  
  * Boolean
  * NULL
    * NULL类型只有一个值，Null
    * Null表示一个空对象 
  * Undefined
    * Undefined类型只有一个值，Undefined
    * 当声明一个变量，但不进行赋值，此时该变量为Undefined 

  * typeof
    * 用于检查一个变量的类型
    * 用法：typeof 变量名 
    * special：typeof null -> object，typeof undefined -> undefined，typeof NaN -> Number

  * NaN
    * 非数，not a number 

* 引用数据类型
  * Object

强制类型转换
---
* 其他类型转String
  * Plan A：调用被转换数据类型的toString()方法，如，var a = 1; a = a.toString();   // a = "1";
    * 该方法不会影响原变量，但会将转换后的结果返回
    * Null,Undefined无toString()方法
  * Plan B：调用String()方法，如,String(a);
    * 对于Number，Boolean来说，调用String()，实际相当于调用toString()
    * 对于Null,Undefined，则会转为"Null"，"Undefined"


  

 
