# DOM 事件机制笔记

## 捕获与冒泡

代码示例

    <div class=爷爷>
    <div class=爸爸>
    <div class=儿子>
    文字
    </div>
    </div>
    </div>
    即 .爷爷>.爸爸>.儿子
    给三个div分别添加事件监听 fnYe / fnBa / fnEr

一开始IE5认为先调用fnEr，网景认为先调用fnYe ，最后W3C规定：

浏览器应该同时支持两种调用顺序

首先按爷爷=>爸爸=>儿子顺序看有没有函数监听

然后按儿子=>爸爸=>爷爷顺序看有没有函数监听

有监听函数就调用，并提供事件信息，没有就跳过

#### 从外向内即（爷爷=>爸爸=>儿子）顺序找监听函数，叫事件捕获
#### 从内向外即（儿子=>爸爸=>爷爷）找监听函数，叫事件冒泡
#### 开发者可以自己选择把fnYe(函数）放在捕获阶段还是冒泡阶段

* 取消冒泡
捕获不可取消，但冒泡可以

e.stopPropagation() 可中断冒泡，浏览器不再向上走

* 不可阻止默认动作

Bubbles 的意思是该事件是否冒泡，所有冒泡都可取消

Cancelable 的意思是开发者是否可以阻止默认事件

Cancelable 与冒泡无关

* 如何阻止滚动

scroll 事件不可阻止默认动作

阻止 scroll 默认动作没用，因先有滚动才有滚动事件

要阻止滚动，可阻止 wheel 和 touchstart 的默认动作

注意你需要找准滚动条所在的元素，示例

但是滚动条还能用，可用 CSS 让滚动条 width: 0

CSS 也行

使用 overflow: hidden 可以直接取消滚动条

但此时 JS 依然可以修改 scrollTop

## addEventListener（事件绑定 API）

IE 5*：baba.attachEvent('onclick', fn) // 冒泡

网景：baba.addEventListener('click',fn) // 捕获

W3C：baba.addEventListener('click', fn, bool)

* 如果 bool 不传或为 falsy

就让 fn 走冒泡，即当浏览器在冒泡阶段发现 baba 有 fn 监听函数，就会调用 fn，并提供事件信息

* 如果 bool 为 true

就让 fn 走捕获，即当浏览器在捕获阶段发现 baba 有 fn 监听函数，就会调用 fn ，并提供事件信息

## target v.s. currentTarget

区别

e.target - 用户操作的元素

e.currentTarget - 程序员监听的元素

this 是 e.currentTarget，我个人不推荐使用它

例如：

div > span{文字}——用户点击文字

e.target 就是 span

e.currentTarget 就是 div
