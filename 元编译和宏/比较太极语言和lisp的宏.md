# 比较太极语言和lisp的宏

太极语言下的宏功能具有和lisp同样强大的能力。


### 回引表达式使用不同的符号

太极语言在回引表达式中使用的符号和lisp中不同。

* <code>`</code>：与lisp作用相同，引导一个回引表达式
* `^`: 相当于lisp下的逗号`,`
* '^&': 相当于lisp下的`,@`

lisp中宏调用和函数调用没有记法上的区别，如果不了解宏定义，程序员无法直接从调用位置判断是宏调用或者是函数调用。

太极语言的宏是元编译的一个特例。宏调用在元编译阶段被执行以产生目标代码。

### 宏定义的区别
lisp的宏定义：`(defmacro macro (parameters...) macroBody)`

### 宏调用的区别
lisp的宏调用：(macroName args...)

### 宏扩展的区别
(macroexpand macroName args...)


### 实现上的区别

lisp的宏一般通过如下方法实现：在编译时间，编译环境中记录了宏的名字和它对应的定义。编译的时候，如果遇到的调用是一个宏，则根据环境中记录的信息进行宏扩展并编译扩展后的表达式。这个过程可能发生递归或者说嵌套，即扩展后的表达式包含另外的宏调用，因此需要进一步的宏扩展。

从下述链接可以得到一些关于lisp及其方言scheme的宏实现知识。
ftp://ftp.cs.utexas.edu/pub/garbage/cs345/schintro-v13/schintro_130.html
http://stackoverflow.com/questions/3465868/how-to-implement-a-lisp-macro-system

太极语言最初的宏实现类似于上述方法。在发现一般化的元编译技术后，就放弃了上述宏实现方法，改为将宏作为一组元算符利用元编译的思想重新实现。

