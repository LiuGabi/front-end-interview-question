#### <a name='js-quesition'>Js 相关问题</a>

1. 请解释事件代理 (event delegation)？
    1. 事件代理允许避免向特定节点添加事件侦听器,取而代之的是将事件侦听器添加到一个父级。 该事件监听器分析冒泡的事件以找到子元素的进行匹配。
    ```
    if（e.target && e.target.nodeName ==“LI”）
    ```  
    
2. 请解释 JavaScript 中 `this` 是如何工作的？
    1. `this` 永远指向函数运行时所在的对象

3. 请解释原型继承 (prototypal inheritance) 的原理？

4. 你怎么看 AMD vs. CommonJS？

5. 请解释为什么接下来这段代码不是 IIFE (立即调用的函数表达式)：`function foo(){ }();`？要做哪些改动使它变成 IIFE?

6. 描述以下变量的区别：`null`，`undefined` 或 `undeclared`？该如何检测它们？

7. 什么是闭包 (closure)，如何使用它，为什么要使用它？
    

8. 请举出一个匿名函数的典型用例？

9. 你是如何组织自己的代码？是使用模块模式，还是使用经典继承的方法？

10. 请指出 JavaScript 宿主对象 (host objects) 和原生对象 (native objects) 的区别？

11. 请指出以下代码的区别：`function Person(){}`、`var person = Person()`、`var person = new Person()`？

12. `.call` 和 `.apply` 的区别是什么？

13. 请解释 `Function.prototype.bind`？

14. 在什么时候你会使用 `document.write()`？

15. 请指出浏览器特性检测，特性推断和浏览器 UA 字符串嗅探的区别？

16. 请尽可能详尽的解释 Ajax 的工作原理。

17. 使用 Ajax 都有哪些优劣？

18. 请解释 JSONP 的工作原理，以及它为什么不是真正的 Ajax。

19. 你使用过 JavaScript 模板系统吗？如有使用过，请谈谈你都使用过哪些库？

20. 请解释变量声明提升 (hoisting)。

21. 请描述事件冒泡机制 (event bubbling)。

22. "attribute" 和 "property" 的区别是什么？

23. 为什么扩展 JavaScript 内置对象不是好的做法？

24. 请指出 document load 和 document DOMContentLoaded 两个事件的区别。

25. `==` 和 `===` 有什么不同？

26. 请解释 JavaScript 的同源策略 (same-origin policy)？如何实现下列代码：
```javascript
[1,2,3,4,5].duplicator(); // [1,2,3,4,5,1,2,3,4,5]
```

27. 什么是三元表达式 (Ternary expression)？“三元 (Ternary)” 表示什么意思？

28. 什么是 `"use strict";` ? 使用它的好处和坏处分别是什么？


29. 请实现一个遍历至 `100` 的 for loop 循环，在能被 `3` 整除时输出 **"fizz"**，在能被 `5` 整除时输出 **"buzz"**，在能同时被 `3` 和 `5` 整除时输出 **"fizzbuzz"**。

30. 为何通常会认为保留网站现有的全局作用域 (global scope) 不去改变它，是较好的选择？

31. 为何你会使用 `load` 之类的事件 (event)？此事件有缺点吗？你是否知道其他替代品，以及为何使用它们？

32. 请解释什么是单页应用 (single page app), 以及如何使其对搜索引擎友好 (SEO-friendly)。

33. What is the extent of your experience with Promises and/or their polyfills?

34. 使用 Promises 而非回调 (callbacks) 优缺点是什么？

35. 使用一种可以编译成 JavaScript 的语言来写 JavaScript 代码有哪些优缺点？

36. 你使用哪些工具和技术来调试 JavaScript 代码？
    1. 主要使用浏览器控制台和断点

37. 你会使用怎样的语言结构来遍历对象属性 (object properties) 和数组内容？

38. 请解释可变 (mutable) 和不变 (immutable) 对象的区别。
  1. 请举出 JavaScript 中一个不变性对象 (immutable object) 的例子？
  2. 不变性 (immutability) 有哪些优缺点？
  3. 如何用你自己的代码来实现不变性 (immutability)？

39. 请解释同步 (synchronous) 和异步 (asynchronous) 函数的区别。
    1. 同步就是指一个进程在执行某个请求的时候，若该请求需要一段时间才能返回信息，那么这个进程将会一直等待下去，直到收到返回信息才继续执行下去
    2. 异步是指进程不需要一直等下去，而是继续执行下面的操作，不管其他进程的状态。当有消息返回时系统会通知进程进行处理，这样可以提高执行的效率。

40. 什么是事件循环 (event loop)？
  1. 请问调用栈 (call stack) 和任务队列 (task queue) 的区别是什么？
    * 简单说，就是在程序中设置两个线程：一个负责程序本身的运行，称为"主线程"；另一个负责主线程与其他进程（主要是各种I/O操作）的通信，被称为"Event Loop线程"（可以译为"消息线程"）。
  
41. 解释 `function foo() {}` 与 `var foo = function() {}` 用法的区别？
    1. 匿名函数, 编译后变量 fun_name 被提前，但是它的值 fun_body 不会被提前。匿名函数只有在被调用时才被初始化。定义之后才能用。
    ```
    var fun_name = function() { /* fun_body */ }; 
    ```
    2. 编译后函数声明和他的赋值都会被提前。即函数声明过程在整个程序执行之前的预处理就完成了，所以只要处于同一个作用域，就可以访问到，即使在定义之前调用它也可以。
    ```
    function fun_name() { /* fun_body */ };
    ```

