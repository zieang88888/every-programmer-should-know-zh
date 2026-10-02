# Web 基础（12 条）

> Web 是大多数程序员的日常战场：字符编码、正则、SEO、可用性……这些「基础课」决定你写的东西别人能不能用、能不能看懂。

## 字符编码与 Unicode（Unicode and Character Sets）

> 中文解读：所有文本在计算机里都是一串数字，Unicode 给每个字符一个统一编号（码点），UTF-8/UTF-16 决定这些编号怎么存。字符集没搞对，「乱码」就会像幽灵一样缠着你。

- **一句话总结**：写代码时永远显式声明编码，默认 UTF-8，绝不要把「编码」和「字符集」混为一谈。
- **必知理由**：乱码问题排查成本极高；数据库、API、文件、数据库连接串四处都可能踩坑，一次搞懂终身受益。
- **推荐阅读**：[The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets](https://www.joelonsoftware.com/articles/Unicode.html)

## ASCII 编码（ASCII，视频）

> 中文解读：ASCII 是最早的字符编码标准，用 7 位二进制表示 128 个英文字母、数字和控制符。它是所有现代编码的「地基」，看懂它才能明白后来的 UTF-8 为什么能向下兼容。

- **一句话总结**：ASCII 是英文世界的原始密码本，128 个字符奠定了一切编码的起点。
- **必知理由**：面试常被追问「UTF-8 为什么兼容 ASCII」；不懂它，遇到字节取值范围、0x20 空格这类底层问题就会发懵。
- **推荐阅读**：[ASCII (video)](https://www.youtube.com/watch?v=B1Sf1IhA0j4)

## UTF-8 编码（UTF-8，视频）

> 中文解读：UTF-8 是变长编码，按字符复杂度用 1~4 个字节存储，英文字符只占 1 字节且与 ASCII 完全一致。它是今天互联网的事实标准，也是省存储、防乱码的关键。

- **一句话总结**：UTF-8 用「长短不一」的字节把全世界文字装进同一套编码，又省空间又兼容老系统。
- **必知理由**：几乎所有接口、文件、前端传输都默认 UTF-8；搞不清变长规则，算字符串长度、处理截断和 emoji 时必踩坑。
- **推荐阅读**：[UTF-8 (video)](https://www.youtube.com/watch?v=vLBtrd9Ar28)

## Unicode 区域数据（Unicode Common Locale Data Repository，CLDR）

> 中文解读：CLDR 是 Unicode 维护的「区域语言数据库」，规定了不同国家地区的日期、货币、排序和翻译习惯。做国际化（i18n）时，它就是你的标准答案库。

- **一句话总结**：想让产品在全球都「看起来对」，就别自己硬编码格式，去查 CLDR。
- **必知理由**：自己拼日期、货币格式迟早翻车；知道 CLDR 的存在，做国际化时直接对接现成数据，能少造半年轮子。
- **推荐阅读**：[Unicode Common Locale Data Repository (CLDR)](http://cldr.unicode.org/)

## 同形字攻击（Homoglyphs）

> 中文解读：同形字指长得几乎一样、实则不同的字符（如用西里尔字母 а 冒充英文 a）。攻击者靠它伪造域名、仿冒账号，肉眼几乎分不出来。

- **一句话总结**：「长得像」不等于「是同一个」，同形字钓鱼就是靠字形撞脸骗你点链接。
- **必知理由**：做安全相关功能（注册名校验、链接展示）时必须能识别这种攻击；日常自己也得有这根弦，别被高仿域名钓了。
- **推荐阅读**：[Homoglyph](https://github.com/codebox/homoglyph/)

## 正则表达式快速入门（Learn regex the easy way）

> 中文解读：这份教程从最基础的符号讲起，由浅入深覆盖匹配、分组、量词等核心语法。正则是处理文本的「瑞士军刀」，入门门槛高，但学会后效率翻倍。

- **一句话总结**：正则看着像天书，其实按符号一个个啃，两周就能脱胎换骨。
- **必知理由**：日志清洗、表单校验、文本提取全靠它；面试手写正则是高频考点，不会就眼睁睁看着机会溜走。
- **推荐阅读**：[Learn regex the easy way](https://github.com/ziishaned/learn-regex)

## 正则表达式游戏（Regex Crossword）

> 中文解读：这是一个把正则当「填字游戏」来玩的练习站，每关都要求你写出能匹配指定格子、同时排除另一批格子的表达式，玩着玩着就把正则练熟了。

- **一句话总结**：与其背语法，不如去网站上把正则当游戏刷关，体感式进步最快。
- **必知理由**：正则「看得懂」和「写得出」是两回事；这种交互式练习专治眼高手低，写复杂规则时才不会脑子卡壳。
- **推荐阅读**：[Regex Crossword](https://regexcrossword.com/)

## SEO 常识（What Every Programmer Should Know About SEO）

> 中文解读：SEO 不是玄学，而是让搜索引擎能读懂、愿意推荐你页面的一系列工程细节：语义化标签、加载性能、结构化数据。程序员懂一点，才能和产品、运营说同一种语言。

- **一句话总结**：别把 SEO 全丢给运营，页面结构和性能写对，自然流量就已经赢了一半。
- **必知理由**：很多「上线后没人来」的问题其实是前端埋的坑（缺 title、渲染慢、链接爬不到）；懂点 SEO 既能避免背锅，也能主动优化。
- **推荐阅读**：[What Every Programmer Should Know About SEO](https://katemats.com/blog/what-every-programmer-should-know-about-seo)

## Web 可用性（Don't Make Me Think）

> 中文解读：这本书的核心就一句话——用户用你的网站时不该需要动脑子。它讲导航、布局、文字如何做到「一目了然」，是产品和前端的通用入门圣经。

- **一句话总结**：好的网页是「不用想就能用」，让用户每一次点击都不纠结。
- **必知理由**：功能再强，用户找不到按钮也是白搭；懂可用性原则，code review 时能一眼看出交互设计的硬伤。
- **推荐阅读**：[Don't Make Me Think, Revisited](https://www.goodreads.com/book/show/18197267-don-t-make-me-think-revisited)

## JavaScript 工作原理（How JavaScript works 系列：引擎/内存/事件循环）

> 中文解读：这个系列拆解了 JS 引擎如何编译执行代码、内存如何管理回收、事件循环如何调度异步任务。理解这些，「为什么这段异步代码的输出是这个顺序」就不再靠猜。

- **一句话总结**：搞懂引擎、调用栈和事件循环，JS 的异步行为从此有迹可循。
- **必知理由**：事件循环、闭包、内存泄漏是面试必考；不知道底层机制，排查 setTimeout / Promise 顺序问题只能靠玄学调试。
- **推荐阅读**：[How JavaScript works (Part 1)](https://medium.com/sessionstack-blog/how-does-javascript-actually-work-part-1-b0bacc073cf)

## 设计原则（Inventing on Principle，视频）

> 中文解读：这是 Bret Victor 的经典演讲，核心观点是「开发者应当能即时看到自己代码的后果，并围绕这条原则重塑工具与创作方式」。它逼你思考：你的工具链是不是在拖慢你的思考。

- **一句话总结**：好工具应让想法「即时可见」，别让抽象和等待掐断你的灵感。
- **必知理由**：它不教具体语法，而是塑造你对「开发体验」和「反馈闭环」的品味；看过的人往往会重新审视自己写代码、做工具的方式。
- **推荐阅读**：[Inventing on Principle (video)](https://vimeo.com/906418692)

## 正则资源库（RegexHQ）

> 中文解读：RegexHQ 是一个收集各类正则实现、教程和在线测试工具的索引站。不同语言的正则引擎差异不小，遇到具体场景先查这里，往往比自己硬写更靠谱。

- **一句话总结**：正则别闭门造车，先去 RegexHQ 看看现成方案和各语言差异。
- **必知理由**：跨语言写正则时，引擎差异（贪婪匹配、lookbehind）经常坑人；有个靠谱资源库在手，能少踩很多「在 A 语言能跑、到 B 就崩」的坑。
- **推荐阅读**：[RegexHQ](https://github.com/regexhq)