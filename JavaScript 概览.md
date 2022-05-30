#  学JS的要求(题外话）

## 软性要求

* 逻辑能力
* 
什么是逻辑能力

三段论逻辑

举个栗子：

JS的数据类型有number/string/null/undefined/bool/symbol/object

JS的函数不是number/string/null/undefined/bool/symbol的任意一种

所以，JS的函数是object

* 质疑自己的能力

大部分时候，错的的是你

* 抽象思维

举个栗子：

你订阅了一份报纸（每天会收到新的报纸）

你关注了偶像明星的微博（每次会收到新的资讯）

你用JS监听了一个按钮的点击事件（每次按钮的点击）

这三件事拥有共同的模式：发布订阅模式

## 硬性要求

* 了解足够多的概念

概览常考：闭包、原型  类、继承 MVC、Flux 高阶函数  前端工程化

* 足够的代码量

* 重视踩坑经历

## JavaScript概述

* 历史与特点

蒂姆·伯纳斯·李（Tim Berners-Lee）—— HTML的发明人

哈肯·维姆·莱（Hkon Wium Lie）—— CSS的发明人

布兰登·艾奇（Brendan Eich）—— JavaScript的发明人

诞生之初，JavaScript只是一个不起眼的小功能，同时，JavaScript有很多bug，学习时要注意辨别

整的JavaScript实现包含三个部分：ECMAScript，文档对象模型，浏览器对象模型

### JavaScript的诞生

1994年，网景公司（Netscape）发布了Navigator浏览器0.9版。这是历史上第一个比较成熟的网络浏览器，轰动一时。但是，这个版本的浏览器只能用来浏览，不具备与访问者互动的能力。
网景公司急需一种网页脚本语言（允许它们直接嵌入网页），使得浏览器可以与网页互动。

布兰登的临危受命——————1995年5月，Netscape（网景）公司做出决策，未来的网页脚本语言必须"看上去与Java足够相似"，但是比Java简单，使得非专业的网页作者也能很快上手
1995年4月，网景公司录用了他，Brendan Eich被指定为这种"简化版Java语言"的设计师。
但是，他对Java一点兴趣也没有。为了应付公司安排的任务，他只用10天时间就把Javascript设计出来了

### JavaScript的命名

Netscape（网景）在最初将其脚本语言命名为LiveScript（一种咖啡Moch摩卡），后来Netscape在与Sun合作之后将其改名为JavaScript
JavaScript最初受Java启发而开始设计的，目的之一就是“看上去像Java”，因此语法上有类似之处，一些名称和命名规范也借自Java

### 浏览器大战

微软的跟进：1996年8月IE3发布，并支持JavaScript浏览器大战，每家浏览器的脚本不太一样。

网景反击：网景向ECMA提交语言标准。JS语言标准不叫JavaSCript，叫做ECMAScript

IE6如日中天：你想象不到IE6这么火。2004年，IE6全球占用率80%，然而，这款浏览器缺不兼容W3C标准

Chrome横空出世：移动市场兴起————智能手机崛起，使得前端极速发展

### ECMAScript标准的制定

时间：

1997年，第一版ECMAScript发布

1999年，第三版发布，这个版本使用最广

第四版流产

2009年，第五版

2015年，第六版，新浏览器都支持这一版本，之后每年发布一版，版本号以年份命名

JS宇ECMAScript的关系：ECMAScript是纸上的标准，JS是浏览器的实现，纸上标准往往落后于浏览器，先实现，在写进标准

# JavaScript的两个阶段

JavaScript兴起：杀手级应用Gmail

JavaScript爆发：V8快如闪电，Chrome的JS引擎叫做V8，2009年，Ryan基于V8创建了Node.js；2010年，Isaac基于Node.js写出了npm；前端工程师可以在浏览器之外执行JS，Node.js快速风靡
同年，TJ受Sinatra启发，发布了Express.js。从此，前端工程师可以愉快写后端应用而有利于简化程序。


# 中国前端的发展

正式出现时间：2010年，中国才有专门的前端岗位

中国的前端一部分来自自学的后端程序员，他们把Java的思想带入JavaScript，面向对象成了JS的主流思想
