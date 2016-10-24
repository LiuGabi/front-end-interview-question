# 前端面试问题
答案仅供参考。另外这些问题更能够检测自己对技能掌握的不足之处。


## 目录
1. [HTML 相关问题](#html-quesition)
2. [CSS 相关问题](#css-quesition)
3. [Js 相关问题](#js-quesition)

#### <a name='html-quesition'>HTML 相关问题</a>

1. What does a `doctype` do?
    1. 申明文档类型，例如申明 HTML5 类型用 `<!DOCTYPE html>`
    2. 目的：告诉浏览器解析器用什么类型的标准来解析文档
    
2. Difference between full standards mode, almost standards mode and quirks mode?
    1. Web 浏览器中的布局引擎现在使用三种模式：full standards mode、almost standards mode、quirks mode
    2. full standards mode: 呈现的行为是遵循 HTML 和 CSS 规范描述的行为
    3. almost standards mode: 只有少数的怪异实现
    4. quirks mode: 布局模拟 Navigator 4 和 Internet Explorer 5 for Windows 中的非标准行为，这些行为不会破坏 Web 上现有的行为
    
3. Difference between html and xhtml?
    1. xhtml 代表 Extensible Hyper Text 标记语言
    2. xhtml 几乎与 html 相同
    3. xhtml 比 html 更严格
    4. xhtml 是 html 定义为 xml 应用程序
    5. 所有主流浏览器都支持 xhtml
    6. xml 语法比 html 更加严格，因此 xml 使得作者更加精准的工作，不得不解决以下问题：
        * 所有元素和属性必须以小写形式显示
        * 所有属性值必须加引号
        * 非空元素必须要有一个结束标记
        * 空元素使用空格和尾部斜杠终止
        * 在严格 xhtml 中，所有行内元素必须包含在块元素当中
        * html 中允许大小写，以及部分没有结束标签的元素，即 html 的错误边缘比 xhtml 宽。因此 xhtml 更容易被创作和维护，因为结构清晰，问题语法更容易被发现

4. Problems with using `application/xhtml+xml`?
    1. `content="application/xhtml+xml"`是 xhtml 文档的一种，可能存在一些老的浏览器不兼容
    2. 如果你的网页包含无效的代码，浏览器将显示 xml 解析错误，而 text/html 至少显示可见的内容

5. How do you server a page with multiple languages?
    1. 保证 code 里已经定义了所需要支持的语言
    2. 拥有已经翻译好的所需要支持语言的文本
    3. 服务器能够识别浏览器的语言请求
    4. 命名好翻译文件，方便系统方法定位到这些文件
    5. 当所需要请求的语言没有时，需要提供一种用通用语言来代替的方法。

6. What to consider when design or developing for multilingual sites?
    1. 适用所有语言字符的编码（这意味着数据库下的所有内容都应使用 utf 编码）
    2. 表示用户区域设置的一些方式
    3. 时间和距离测量等使用当地的
    4. 相同意思的不同语言的文本长度不一，要考虑此时网页如何布局
    5. 使用 lang 属性来标记语言的变化，lang 属性可以用于几乎每个 html 属性
    6. 域名的选择
    7. 内容的翻译（使用人工翻译，js翻译不利于搜索引擎）
    8. 访问速度。不同国家之间相互出入口带宽不同，其对应的网站服务器应放在其对应的国家

7. What are `data-*` attributes good for?
    1. html5 新增属性
    2. `data-*` 属性允许在标准 html 元素上存储额外信息，没有其他 hack
    3. 这些自定义数据都可通过属性设置的元素的 `HTMLElement` 接口获取。 `HTMLElement.dataset` 属性提供对它们的访问。
    4. js 访问这些属性简单
    5. 注意
        * 不要存储需要显示和访问的数据，爬虫不能将其编入索引当中
        * 读取 `data-*` 属性行为相比 js 存储数据会慢

8. 把 html5 看做一个开放的平台，它的构建模块有哪些？
    1. 更多语义化标记文本
    2. 新的表单元素
    3. video 和 audio
    4. 新的 js api
    5. canvas 和 svg
    6. 新的通信 api
    7. geolacation api
    8. web worker api
    9. 新的数据存储

9. Difference between a `cookie`, `sessionStorage` and `localStorage`?
    1. `sessionStorage` 和 `localStorage`：
        * 目前为止的两种 web 存储方式
        * 区别：
            * `localStorage` 生命周期是永久的，除非用户清除`localStorage`信息
            * `sessionStorage` 生命周期是当前窗口或标签，一旦窗口或标签被关闭，那么通过`sessionStorage`存储的数据也将被清空
            * 不同浏览器无法共享`localStorage`和`sessionStorage`中的信息
            * 相同浏览器不同页面可共享`localStorage`，但是不能共享`sessionStorage`
            * `sessionStorage` 和 `localStorage`使用相同的 api
    2. cookie:
        * html5 中的 cookie 由基于浏览器的本地存储和会话存储组成，它们有网页本身创建和访问
    3. html5 web storage = 新客户端数据存储选项的通用总括术语：
        * Web存储更安全，更快。数据不包括在每个服务器请求中，但仅在被要求时使用。它也可以存储大量的数据，而不影响网站的性能。
    4. 本地存储 = 持久性并且作用域到域（存储没有到期日期的数据）。目前通常提到两种口味：
        * 'default' = 将事物存储在名称/值对中
    5. Web SQL（aka Web数据库）= 使用SQL数据库
        * 会话存储 = 非持久性并且仅限于当前窗口（存储一个会话的数据）
        * cookies = 以上所有的老学校方式。存储每个域的名称/值对。
        
10. Difference between `<script>`、`<script async>` and `<script defer>`?
    1. `<script>`定义客户端脚本，如 js
    2. 如果`async =“async”`：脚本与页面的其余部分异步执行（脚本将在页面继续解析时执行）
    3. 如果不存在`async`，并且`defer =“defer”`：脚本在页面完成解析时执行
    4. 如果不存在`async或defer`：在浏览器继续解析页面之前，将立即提取并执行脚本
    5. 每个异步脚本在完成下载之后和窗口的加载事件之前的第一次机会执行。这意味着异步脚本可能（并且可能）不按它们在页面中出现的顺序执行。另一方面，延迟脚本被保证以它们在页面中发生的顺序被执行。该执行在解析完成后开始，但在文档的DOMContentLoaded事件之前。
    
11. 为什么通常推荐将 css `<link>`放置在 `<head></head>`之间，而将 js 放置在 `<script>`放置在`</body>`之前？你知道有哪些例子吗？
    1. `<link>`标签只能出现在`<head>`元素当中
    2. 浏览器从上到下依次解析 html 文档，将 `css` 放在头部可以先加载，避免加载 `body` 内容时导致页面一开始样式错乱，然后闪烁。
    3. 若将 javascript 文件放到 head 里面，就意味着必须等到所有的 `javascript` 代码都被下载、解析和执行完成 之后才开始呈现页面内容。这样就会造成呈现页面时出现明显的延迟，窗口一片空白。为避免这样的问题一般将全部 `javascript` 文件放到 `body` 元素中页面内容的后面。
    
12. 什么是渐进式渲染 (progressive rendering)？
    1. 图片加载分为两种方式：（1）线性加载；（2） 交错/渐进式加载
    2. 线性加载：自上而下扫描式
    3. 交错/渐进式加载：先是全部的模糊图片，然后逐渐清晰

13. Have you used different HTML templating languages before?
    1. ejs
    2. jade
    
#### <a name='css-quesition'>CSS 相关问题</a>

1. Difference between class and id in css?
    1. 前缀不同，`#`, `.`
    2. 一个 `id` 一个页面只能用一次；class 可以多次引用
    3. id 可以起到锚点的作用

2. Difference between `reset.css`and`normallize.css`?
    1. `reset.css` 重置所有`user agent`样式，同时进行一些 bug 的修复
    2. `normalize.css` 保留`user agent`样式，修复部分问题样式，比如 `body`默认的`margin`样式
    3. 个人偏重选择 `normalize.css`

3. `float`工作原理？
    1. `float` 属性定义元素在哪个方向浮动，使元素脱离普通文档流
    2. 以往这个属性总应用于图像，使文本围绕在图像周围，不过在 CSS 中，任何元素都可以浮动
    3. 浮动元素会生成一个块级框，而不论它本身是何种元素
    4. 如果浮动非替换元素，则要指定一个明确的宽度；否则，它们会尽可能地窄
    5. 注释：假如在一行之上只有极少的空间可供浮动元素，那么这个元素会跳至下一行，这个过程会持续到某一行拥有足够的空间为止
    6. `.clearfix:after {
            content: "";
            display: block;
            height: 0;
            clear: both;
        }`

4. 描述`z-index`和叠加上下文是如何形成的?
    1. `z-index`属性设置元素的堆叠顺序，数值越大的越靠前
    2. 注意：`z-index`的值可以是负数，并且只在元素设置定位(比如`position:absolute`或`position:relative`)才生效
  
5. `BFC(Block Formatting Context)` 如何工作？
    1. BFC 定义：
        * 从样式上看，具有 BFC 的元素与普通的容器没有什么区别
        * 从功能上，具有 BFC 的元素可以看作是隔离了的独立容器，容器里面的元素不会在布局上影响到外面的元素
        * BFC 具有普通容器没有的一些特性，例如可以包含浮动元素，用`overflow`清除浮动的方法就是触发了浮动元素的父元素的 BFC ，使它可以包含浮动元素，从而防止出现高度塌陷的问题。
        * 简单说，BFC 就是一种属性，这种属性会影响着元素的定位以及与其兄弟元素之间的相互作用
    2. 触发 BFC 方式：
        * 浮动元素，float 除 none 以外的值
        * 绝对定位元素，position（absolute，fixed）
        * display 为以下其中之一的值 inline-blocks，table-cells，table-captions
        * overflow 除了 visible 以外的值（hidden，auto，scroll）
        * "display:table" 本身并不产生 BFC，而是由它产生匿名框，匿名框中包含 "display:table-cell" 的框会产 BFC
        * 在 CSS3 中，BFC 叫做 Flow Root，并增加了一些触发条件：
            * display 的 table-caption 值
            * position 的 fixed 值，其实 fixed 是 absolute 的一个子类，因此在 CSS2.1 中使用这个值也会触发 BFC ，只是在 CSS3 中更加明确了这一点。
        * 注意：BFC 并不是元素，而是某些元素带有的一些属性，因此，是上面这些元素产生了 BFC ，而它们本身并不是 BFC ，这个概念需要区分清楚
    3. BFC 的属性
        * BFC 会阻止外边距折叠
        * BFC 可以包含浮动的元素
        * BFC 可以阻止元素被浮动元素覆盖
  
6. What are the various clearing techniques and which is appropriate for what context?
    1. 设置空标签：
        `<div class="clear"></div>
        .clear {
        clear: both;
        }` 增加无意义的空标签
    2. 添加`:after`伪元素：
        `.clearfix:after {
        content: "";
        display: block;
        height: 0;
        clear: both;
        }`，
        注意：如果不把伪元素的高度设置为0，框内最底部就会多出几行空白像素
    3. 父级元素设置样式：
        `#parent {
        overflow: hidden;
        zoom: 1;
        }`

7. Explain CSS sprites, and how you would implement them on a page or site?
    1. 定义：把网站小图片整合到一张图片里，利用`background-position`把对应的图片显示出来
    2. 优点：
        * 减少请求次数
        * 减少图片的字节数
    3. 缺点：
        * 开发繁琐，难以适应高分辨率图片
    4. 如果只是添加 icon，推荐 font icon

8. 喜欢的图片替代方法是什么？如何选择？
    1. FIR [Demo](https://codepen.io/LiuGabi/pen/LRryJm)
        * 优点：使用 css 而不是标记语法提供图片，更改图片只需更改 css
        * 缺点：需要一组不具备任何语义的 span 标签才能运作
    2. phark [Demo](https://codepen.io/LiuGabi/pen/GjPmza)
        * 优点
            * 不需要额外标签
            * 不影响屏幕阅读器使用者
        * 缺点
            * 关闭浏览器显示图片，同时启用CSS支持时，文字图片均不可显示

9. How would you approach fixing browser-constrained browser-specific styling issues?
    1. 通常浏览器兼容性问题比较多的是IE浏览器，具体问题具体分析
    2. 一般浏览器兼容性问题还可以通过 webkit

10. How do you serve your pages for feature-constrained browsers? What techniques/processes do you use?
    1. 当浏览器的功能受到限制时：
        * 如果是特殊字体的不支持可能就会采取图片替代方法，诸如此类
        * css3 查询功能在很多浏览器上不支持时，可能会使用js来代替
        * 最好的办法是设计师给的设计能避免这个功能

11. The different ways to visually hide content( and make it available only for screen readers )?
    1. `display: none;`缺点：搜索引擎可能认为是来及信息而被忽略
    2. `visibility: hidden;` 缺点：隐藏的内容占据物理空间
    3. `overflow: hidden;` 比较合理的方法，设置宽高为 0

12. Have you ever used a grid system, and if so, what do you prefer?
    1. 用过 bootstrap，[walmartlabs](http://walmartlabs.github.io/web-style-guide/)
    2. 自己也曾根据 grid 原理开发了 24 格化和 48 格化 [个人 grid 原理分析文档](http://wenku.baidu.com/view/333dc548ec3a87c24028c4fb)
    3. 说实话不曾喜欢 grid 布局，个人感觉类名太多，但其原理值得学习和探究

13. Have you ever used or implemented media queries or mobile specific layouts/css?
    1. 媒体类型(media type)
        * all: 适用于所有的设备
        * print: 文本和页面在屏幕上市打印模式
        * screen: 彩色显示器
        * speech: 语音合成器
    2. 媒体特性(media feature)
        * width： viewport width
        * height: viewport height
        * aspect-ratio: viewport的宽高比如：16/9
        * orientation: 宽度和高度的大小关系
        * resolution: pixel density of the output device
        * scan: scanning process of the output device
        * grid: is the device a grid or bitmap
        * color: number of bits per color component of the output device, or zero if the device isn't color
        * color-index: number of entries in the output device's color lookup table, or zero if the device does not use such a table
    3. pc 优先
        * `max-width`
    4. mobile 优先
        * `min-width`
    5. mdedia 逻辑运算符 (and, not, only)

14. Are you familiar with styling svg? svg 和 canvas 的区别？
    1. [styling 属性](https://www.w3.org/TR/SVG/styling.html)
    2. svg:
        * 不依赖分辨率
        * 支持事件处理器
        * 最适合带有大型渲染区域的应用程序
        * 复杂度高会减慢渲染速度（任何过度使用 DOM 的应用都不快）
        * 不适合游戏应用
        * xml 格式

          [示例](http://fixate.it/)
    3. Canvas
        * 依赖分辨率
        * 不支持事件处理器
        * 弱的文本渲染能力
        * 能够以 .png 或 .jpg 格式保存结果图像
        * 最适合图像密集型的游戏，其中的许多对象会被频繁重绘
    
15. How do you optimize your webpages for print?
    1. media print

16. 在书写高效的 css 时需要考虑哪些问题？
    1. 定义类名的语义性
    2. 类的重复使用性
    3. 类的组合使用性
    4. 规范性
    5. 考虑 css 的模块性和通用性
    
17. css 预处理器的优劣？使用过哪些预处理，优劣是什么？
    1. 预处理器作为工具的出现主要是为了给开发者带来便利
    2. 预处理让 css 的书写更具有逻辑性，因此更加便利和快捷
    3. 需要时刻编译，调试不方便，虽然有类似 source map 等工具，但是开发过度依赖第三方插件遇到问题还要去排除是第三方的原因导致
    4. less 和 sass( scss ), 后者逻辑性强于前者

18. 设计中使用非标准字体如何去实现？
    1. 图片代替
    2. Font icon

19. 浏览器如何判断元素是否匹配某个css选择器？
    1. 从后往前判断。
    2. `body.ready #wrapper > .lol233`
    3. 先把所有 class 中有 lol233 的元素拿出来组成一个集合，然后上一层，对每一个集合中的元素，如果元素的 parent id 不为 #wrapper 则把元素从集合中删去。 再向上，从这个元素的父元素开始向上找，没有找到一个 tagName 为 body 且 class 中有 ready 的元素，就把原来的元素从集合中删去

20. 描述伪元素 (pseudo-elements) 及其用途?
    1. css 伪元素用于向某些选择器设置特殊效果
    2. :first-letter、:first-line、:before、:after

21. 请解释你对盒模型的理解，以及如何在 CSS 中告诉浏览器使用不同的盒模型来渲染你的布局?
    1. W3C盒子模型——属性高（height）和属性宽（width）这两个值不包含 填充（padding）和边框（border）
    2. IE盒子模型——属性高（height）和属性宽（width）这两个值包含 填充（padding）和边框（border）
    
22. 请解释 * { box-sizing: border-box; } 的作用, 并且说明使用它有什么好处？
    1. 使所有元素包含padding值在width中
    2. 设置元素宽100%时不用考虑因padding而溢出

23. List as many values for the display property that you can remember?
    1. display: none | block | inline | inline-block | flex | table
    
24. Difference between inline and inline-block?
    1. `inline` 行内元素，不能设置宽度
    2. `inline-block` 行内块级元素，可以设置宽度，`inline-block` 与 `inline-block` 之间会有默认空白间隙

25. Difference between relative、fixed、absolute and static?
    1. `relative` 相对定位
    2. `fixed` 相对窗口，受 `transform` 影响
    3. `absolute` 相对 `relative` 定位元素
    4.`static`默认值

26. CSS 中字母 'C' 的意思是叠层 (Cascading)。请问在确定样式的过程中优先级是如何决定的 (请举例)？如何有效使用此系统？

27. 你在开发或生产环境中使用过哪些 CSS 框架？你觉得应该如何改善他们？
    1. bootstrap
    2. 类名太多

28. 请问你有尝试过 CSS Flexbox 或者 Grid 标准规格吗？
    1. [flex 布局](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)
    2. Grid

29. 为什么响应式设计 (responsive design) 和自适应设计 (adaptive design) 不同？
    1. 响应式设计对设计本身要求高，前端开发人员只需要通过改变css就能对其实现
    2. 自适应设计包括响应式，有时需要结合 js 来改变内容

30. 你有兼容 retina 屏幕的经历吗？如果有，在什么地方使用了何种技术？
    1. 当使用图片作为 Icon 时，高 `devicePixelRatio` 情况需要大几倍的图片代替，并用 media 检测 `devicePixelRatio`
    2. font icon 不需要考虑retina问题
    3. 高清 `<img>`时，使用 `srcset`

31. 请问为何要使用 translate() 而非 absolute positioning，或反之的理由？为什么？
    1. translate() 更自然
    2. 具体情况具体分析
    
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
  
41. 解释 `function foo() {}` 与 `var foo = function() {}` 用法的区别？
    1. 匿名函数, 编译后变量 fun_name 被提前，但是它的值 fun_body 不会被提前。匿名函数只有在被调用时才被初始化。定义之后才能用。
    ```
    var fun_name = function() { /* fun_body */ }; 
    ```
    2. 编译后函数声明和他的赋值都会被提前。即函数声明过程在整个程序执行之前的预处理就完成了，所以只要处于同一个作用域，就可以访问到，即使在定义之前调用它也可以。
    ```
    function fun_name() { /* fun_body */ };
    ```





























