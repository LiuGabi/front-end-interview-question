## <a name='html-quesition'>HTML 相关问题</a>

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

