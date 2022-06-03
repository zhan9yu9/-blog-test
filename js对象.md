# JS对象基本用法

## 声明对象的两种语法

### 1、let声明
* 遵循块作用域，即使用范围不能超出 { }

* 不能重复申明

* 可以赋值，也可以不赋值

* 必须先声明再使用，否则报错

* 全局声明的 let 变量，不会变成 window 的属性

* for 循环配合 let 有奇效

### 2、const声明

* 跟 let 几乎一样
* 只有一条不一样：声明时就要赋值，赋值后不能改

### 写法：

let obj = { 'name': 'Rain', 'age': 18 }

let obj = new Object({'name': 'Rain'})

console.log({ 'name': 'Rain, 'age': 18 })

## 如何查看对象的属性

* Object.keys(obj) 查看自身所有属性

* Object.values(obj) 查看自身所有值

* Object.entries(obj) 查看自身所有属性+值

* console.dir(obj) 查看自身+共有属性

* obj.hasOwnProperty('toString') 判断一个属性是自身的还是共有的

### 两种方法查看属性：
* obj['key']

* obj.key

* obj['key'] 不等于obj[key] ，一个是字符串一个是变量

* obj['key'] = obj.key


## 如何修改或增加对象的属性

delete 命令用于删除对象的属性，删除成功后返回 true

    var obj = { p: 1 };
    Object.keys(obj);  //['p']
    delete obj.p;      //true
    obj.p;             //undefined
    Object.keys(obj);  //[]
    
上面代码中，delete 命令删除对象 obj 的 p 的属性。删除后，再读取 p 的属性就会返回 undefined，而且 Object.keys 方法的返回值也不再包含该属性

注意，删除一个不存在的属性，delete 不会报错，而且返回 true

    var obj = {};
    delete obj.p; //true
    
上面代码中，对象 obj 并没有 p 属性，但是 delete 命令照样返回 true。因此，不能根据 delete 命令的结果，认定某个属性是存在的。

只有一种情况，delete 命令会返回 false，那就是该属性存在，且不得删除

    var obj = Object.defineProperty({}, "p"{
    value:123,
    configurable:false,
    });

    obj.p //123
    delete obj.p //false
    
上面代码之中，对象 obj 的 p 属性是不能删除的，所以 delete 命令返回 false

注意：delete 命令只能删除对象本身的属性，无法删除继承的属性！

## 'name' in obj和obj.hasOwnProperty('name') 的区别

1、'name' in obj 是查看name这个属性名是否在对象中，出现false时，则表示不含有属性名。当查看'toString' in obj 时也返回true，所以隐藏属性无法使用此写法。

2、obj.hasOwnproperty('name') 只会在这个属性是自身时返回true，不管隐藏属性。

    'toString' in obj //true,in是查看，但并不知道是自身还是共有属性
    obj.hasOwnProperty('toString') //false 说明toString不是自身属性
    var obj={name='frank',age:18} //undefined
    obj.hasOwnProperty('name') //true
    obj.hasOwnProperty('toString') //false

