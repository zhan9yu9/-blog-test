# JS 函数的执行时机

## 下面会通过代码来介绍一下js函数的执行时机

代码1

    let i 
    for(i = 0; i<6; i++){
    setTimeout(()=>{   
    console.log(i)   
    },0)
    } //结果打印出6个6
    
解释：因为当代码执行到setTimeout，setTimeout是一个定时器它会告诉计算机我会尽快执行，具体的时间，不确定，也可以认为是在你for循环完毕我在执行，
而在for循环执行完毕时此时的i=6然后再执行setTimeout后的代码，由于for循环了6次，也就是说定时器会执行6次，此时i=6，所以打印出6个6。
    
代码2

    for(let i = 0; i<6; i++){
    setTimeout(()=>{
    console.log(i)
    },0)
    }  ///结果打印出0、1、2、3、4、5
    
解释：
因为let变量的作用域只能在当前函数中，所以每次for循环生成的都是一个新的i，setTimeout里输出的i就是这个新的i，这个i是不会变化的，所以输出的就是正常的。

### 除了使用 for let 配合，还有什么其他方法可以打印出 0、1、2、3、4、5？如下：

1.闭包

    let i 
    for(i = 0; i<6; i++){
    !function(j){
    setTimeout(()=>{
    console.log(j)
    },0)
    }(i)
    }
    
2.数组的push

    var arr4=[];
    var  n=0;
    for(vari=0;i<6;i++)
    {
    n+=1;
    arr4.push(n-1)
    }
    console.log(arr4)
    
3.利用 setTimeout 的第三个参数,将i传进去

    let i
    for(i = 0; i<6; i++){
    setTimeout((value)=>{
    console.log(value)
    },0,i)
    }
    
 4.利用 const 关键字
 
    let i
    for(i=0; i<6; i++)
    {
    constx=i
    setTimeout(()=>{
    console.log(x)    
    })
    }
    
### call、apply、bind的用法

* call,apply,bind都可以动态改变函数体内部的this指向，只是用法不同。call接受连续参数，apply接受数组参数，使用方法区别：apply时参数需加上中括号；

如：

    function add(a,b){
    return a+b;
    }
    add.call(add, 5, 3); //8
    add.apply(add, [5, 3]); //8
    
* bind 接受的参数跟 call 一致，只是 bind 不会立即调用。它会生成一个新的函数，你想什么时候调就什么时候调。

如：

    function add(a, b){
    return a+b;
    }
    var foo1 = add.bind(add, 5,3); 
    foo1(); //8
    var foo1 = add.bind(add, 5,3); 
    foo1(); //8
