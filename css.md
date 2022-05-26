# CSS知识总结

## CSS需要注意的地方

1、所有符号都是英文符号，区分大小写。最后必须以;结束。

2、不存在块级元素和内联元素，所有元素都可以是内联或者块级元素。其中inline元素中不能写border。

3、不要设置width=100%

4、写代码前必须要写border！！

5、Margin合并 只有上下重叠没有左右重叠。

6、css第一行写*{margin：0；padding：0；box-sizing：borderbox;}

## CSS知识点

1、CSS语法

css语法分为样式语法和at语法。

选择器{

            样式名1:样式值1;

            样式名2:样式值2;

        }

2、css的文档流与盒模型

文档流：

normal flow正常文档流

inline元素的文档流为从左到右且到达最右边会换行，不接受宽度设置，可以由line-height间接确定高度

block元素另起一行从上到下，默认自动就算宽度，可以用width指定。不要设置width=100%，高度与内部文档流元素决定，但是也可以设置height。

inlne-block元素也是从左到右但是达到最右边不会分成两块。宽度结合前两者特点可以设置width，高度与block类似，可以设置height。

盒模型：

css盒模型里包含margin、border、padding和content。盒模型分为两种，一种是content box 一种是border box。两种的区别是content box的宽度只包含了content；border box的宽度包含到border，分别为border、padding和content。
比如一个div的宽度和高度为105px，内边距为10px，边框为5px，外边距为30px。content box下显示的div所占的总宽度和总高度（包括外边距、边框、内边距、内容）为105 + 15 + 5 + 30 = 155px，border box下显示的div所占的总宽度和总高度（包括外边距、边框、内边距、内容）为105+ 30 = 135px。

3、浏览器渲染原理

根据 HTML构建 HTML树 (DOM)

根据CSS构建CSS树 (CSSOM)
将两棵树合并成一颗渲染树 (render tree)

Layout 布局（文档流、 盒模型、计算大小和位置）

Paint 绘制（把边框颜色、文字颜色、阴影等面出来）

Compose 合成（根据层叠关系展示画面）

4、CSS 动画的两种做法（transition 和 animation）

* transition过渡 （不是所有属性都能进行Transition）

作用：补充中间帧

语法:transition: 属性名 | 时长 | 过渡方式 | 延迟

注意⚠️：指定第一个数字默认指定为时长，第二个数字默认才是延迟时间
拓展：1s = 1000ms（毫秒）

过渡方式：linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier | step-start | step-end | steps

* animation动画

用法:声明关键帧、添加动画

animation语法

animation：动画名 | 时长 | 过渡方式 | 延迟 | 次数 | 方向 | 填充模式 | 是否暂停 |

* 动画名：指定执行某个动画

* 时长：s 或者 ms

* 过渡方式：与transition取值是一样的

* 次数：数字（3或者2.4）或者 infinite（无限循环）

* 方向：normal 默认正常、reverse 相反方向、alternate 默认正常方向循环（需要配合次数）、alternate-reverse 默认相反方向循环（需要配合次数）

* 填充模式：none 默认、forwards 最后静止不动（保持最后一帧）、backwards （需配合延迟属性）立即应用第一个关键帧的样式，延迟结束后，执行动画、both (forwards+backwards相结合 需配合延迟属性）立即应用第一个关键帧的样式，延迟结束后，执行动画，动画结束后保持最后一帧

* 是否暂停：pause（暂停动画）、running（恢复运行动画）

@keyframes写法

一般写法

    @keyframes 动画名 {
      from {
    transform: translateX(0%);
    }

    to {
    transform: translateX(100%);
    }
    }
    
百分数写法（推荐）

    @keyframes 动画名 {
    0% { top: 0; left: 0; }
    30% { top: 50px; }
    68%, 72% { left: 50px; }
    100% { top: 100px; left: 100%; }
    }
