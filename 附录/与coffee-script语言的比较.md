# 与coffee-script相同点的比较

## 相同点

* 编译到javascript

* 缩进语法

* 支持将for，while等语句作为表达式使用

* 支持隐式变量申明。对新变量赋值自动产生局部变量声明。

* @代表this，::代表prototype

* -> 和 => 定义函数

* 支持省略参数(x, y..., z) ->

* 支持默认参数(a, b, x=1, y=2) ->

* 支持自动返回最后语句的值  

* 支持字符串插补, 在coffee-script中是"...#{expression} ..."。

###不同点

* taijilang超越javascript；coffee-script就是javascript。

  太极语言的丰富的特征使得它不再与javas语言cript具有一一对应的关系，有点类似于C和汇编， 在语言金字塔上位于一个更高的位置。而coffee-script的口号是：coffee-script is just javascript, 它追求的是和javascript的一一对应。

* 太极语言支持lisp风格的宏，coffee-script没有宏功能。

* 太极语言支持元语言，或者说编译时间计算，coffee-script没有元语言功能。

* 太极语言支持动态解析时间计算，动态控制语法。coffee-script没有此功能。

* 太极语言支持根据空格改变算符优先级，coffee-script不支持。

  象 1+2 * 3+4 这样的算式，在太极语言中解释为(1+2)*(3+4), 而在其它编程语言中都是解释为1+(2*3)+4。太极语言的处理顺应了普通人的阅读直觉。

* 太极语言中任何构造都是表达式，即使是break，continue，return。而这三种构造在coffee-script中不能作为表达式使用。

* 太极语言可以声明常量，coffee-script不能。

* 太极语言中，函数作用域内的赋值总是产生函数内部局部变量。而coffee-script则如果外层词法作用域中已经有同名变量，则将不产生局部变量，赋值将针对外层变量有效。coffee-script比javascript进步一层，但是，在某种情况下还是会出现因为无意中覆盖了外层变量而导致难以觉察的编程错误。太极语言中如果需要对外层变量赋值，必须显式使用@@varName。

* 类似于livescript，太极语言可以通过在->和=>前加“|”抑制自动返回最后一语句的值。coffee-script不支持此特征。

* 太极语言中任何字符串都可以是多行字符串。coffee-script中'...'和"..."是单行字符串。即使写在多行也会去除换行符合并成单行。

* coffee-script只支持用#{...}向字符串插补表达式，太极语言有多种方法，并且比coffee-script的更简捷：$expression, {}, [], ()。

* coffeescript支持literature programming，太极语言不支持。

* coffee-script支持#引导的行注释和###...###块注释。太极语言支持//行注释，/.引导的缩进块注释，/*...*/注释和/注释代码块
