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

* 其它转Number
  * Plan A：调用Number()，即 a = Number(a);
    * 若字符串是纯数字，则会转为数字
    * 若有非数，则为NaN
    * 若是空串，或为空格，则为0
    * true -> 1，false -> 0，null -> 0，undefined -> NaN  
  * Plan B：parseInt()
    * 将串中有效的整数取出，转为Number，如 a = parseInt(a);
  * Plan C：parseFloat()
    * 操作与parseInt相同，不仅能获取整数，还能获取小数
  * 若对非String使用parseInt，parseFloat，会将其先转为String，后再进行判断，如
    * a = true; a = parseInt(a); console.log(typeof a); // Number console.log(a); // NaN

* 其它转Boolean
  * 数字 -> Bool，除0，NaN外，均为true
  * 字符串 -> Bool，除空串外，均为true
  * Null,Undefined -> Bool，为false
  * Object -> Bool,true 

对象
---
* 基本数据类型都是单一的值，值与值之间没有联系
* 对象作为复合的数据类型，对象可保存多个不同数据类型的属性
  * 内建对象
    * 由ES标准中定义的对象，在任何ES中均可使用，如Math，String...
  * 宿主对象
    * 由js的运行环境提供的对象，主要是浏览器提供，如DOM,BOM
  * 自定义对象
    * 由开发人员自行创建

* 对象的创建
  * 用new调用的函数，是构造函数constructor
  * 构造函数，专门用于创建对象

* 属性
  * 对象中保存的值，即属性
  * 属性的添加/修改：对象.属性名 = 属性值
  * 属性的读取：对象.属性名
    * 若读取的属性不存在，不会报错，而会返回undefined
  * 属性的删除：delete 对象.属性名


* 特殊属性名
  * 对象["属性名"] = 属性值，读取也使用该法
  * []中可直接传递一个变量，如，obj["123"] = 789; var n = "123"; console.log(obj[n]); // 789

* 属性值
  * js对象的属性值，可以是任意数据类型，也可以是一个对象 
  * 检查一个对象是否有指定属性： "属性名" in 对象

基本数据类型，引用数据类型的存储方式
---
* js中的变量保存在栈内存中
* 基本数据类型的值存在栈内存中
  * 值之间独立存在，修改一个变量不影响其他变量
* 对象保存在堆内存中
  * 每创建一个新对象，就开辟出一个新的内存空间，而变量保存的是对象的内存地址（引用地址）
  * 若两个变量保存的是同一个对象的地址，则修改时会互相影响
* 当比较两个基本数据类型的值时，直接比较值，若比较引用数据类型的值时，则比较对象的内存地址

对象字面量创建对象
* var obj = {属性名:属性值}; //键值对

函数
---
* 函数属于对象
  * 可用于封装一些功能，需要时执行
* 函数声明创建函数
  * function 函数名(形参){}
* 函数表达式创建函数
  * var 函数名 = function(形参){}
* 形参
  * 多个形参之间，逗号隔开
  * 声明形参，相当于在函数内部声明对应的变量，但不赋值！！
* 实参
  * 调用函数时，在()中指定实参
  * 实参会赋值给函数中对应的形参
  * 调用函数时，解析器不会检查实参数量！多余实参不会被赋值！
  * 若实参的数量少于形参，则无对应实参的形参的值为undefined



   

 
