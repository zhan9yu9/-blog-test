 # JS的基本语法
 
 ## 一、表达式和语句
 
 * 表达式

1+2 值为三

add(1,2) 值为函数返回值

console.log 为函数本身

console.log(3)为undefined

* 语句

var a=1

* 区别

1、表达式一般都有值，语句可能有也可能没有

2、语句一般会改变环境（声明、赋值）

3、但是以上两条并不绝对

## 二、标识符的规则

第一个字符可以是 Unicode字母 或者 $ 或 _ 或 中文，后面的字符可以是以上或者数字

## 三、if else 语句

语法：if(表达式){语句1}else{语句2}

存在变态情况：

①：表达式内写成赋值语句eg：a=1

②：语句1中加入if else

③：语句2中加入if else

④：缩进不注意

如：

    a=1;
    if(a==1)
    console.log('a');
       console.log('a=2');
    与下面等价都输出a=2
    a=1;
    if(a==1)
    console.log('a');
    console.log('a=2');
 
 推荐写法： if（表达式）{语句}else if（表达式）{ }  else{语句}
 
 ## 五、break和continue
 
* break：退出循环

* continue：跳过本次循环

## 六、label

语法：

    foo:{
    console.log(1);
    break foo;
    console.log(‘本次不输出’)；
    }
    console.log(2);
    
 面试会遇到的问题： {  fool:1 } 是什么？    回答：意思是这不是个对象，仅仅打出标签1。当var = a {  fool:1 } 时，就是一个对象
