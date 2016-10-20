# 前端面试问题
答案仅供参考。另外这些问题更能够检测自己对技能掌握的不足之处。


## 目录
1. [HTML 相关问题](#html-quesition)

#### <a name='html-quesition'>HTML 相关问题</a>

1. What does a `doctype` do?
    1. 申明文档类型，例如申明 HTML5 类型用 `<!DOCTYPE html>`
    2. 目的：告诉浏览器解析器用什么类型的标准来解析文档
    
2. Difference between full standards mode, almost standards mode and quirks mode?
    1. Web 浏览器中的布局引擎现在使用三种模式：full standards mode、almost standards mode、quirks mode
    2. full standards mode: 呈现的行为是遵循 HTML 和 CSS 规范描述的行为
    3. almost standards mode: 只有少数的怪异实现
    4. quirks mode: 布局模拟 Navigator 4 和 Internet Explorer 5 for Windows 中的非标准行为，这些行为不会破坏 Web 上现有的行为
    
3. Difference between HTML and XHTML?
    1. XHTML 代表 Extensible Hyper Text 标记语言
    2. XHTML 几乎与 HTML 相同
    3. XHTML 比 HTML 更严格
    4. XHTML 是 HTML 定义为 XML 应用程序
    5. 所有主流浏览器都支持 XHTML
    6. XML 语法比 HTML 更加严格，因此 XML 使得作者更加精准的工作，不得不解决以下问题：
        * 所有元素和属性必须以小写形式显示
        * 所有属性值必须加引号
        * 非空元素必须要有一个结束标记
        * 空元素使用空格和尾部斜杠终止
        * 在严格 XHTML 中，所有行内元素必须包含在块元素当中
        * HTML 中允许大小写，以及部分没有结束标签的元素，即 HTML 的错误边缘比 XHTML 宽。因此 XHTML 更容易被创作和维护，因为结构清晰，问题语法更容易被发现

3. Problems with using `application/xhtml+xml`?
    1.
    
