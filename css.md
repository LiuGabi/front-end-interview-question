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
