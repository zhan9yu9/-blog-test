# DOM事件委托笔记

## 自定义事件

js代码示例

    button1.addEventListener('click', ()=>{
    const event = new CustomEvent("frank", {"detail":{name:'frank', age: 18}}) // 声明事件 CustomEvent就是自定义事件（写事件名字和事件内容）
    button1.dispatchEvent(event) // 触发事件
    })
    button1.addEventListener('frank', (e)=>{  //监听frank事件
    console.log('frank')
    console.log(e)
    })
    
## 事件委托

一.什么是事件委托

事件委托也被称为事件代理,在jQuery里称为事件委派

二、事件委托的原理

1.事件委托就是利用函数的冒泡冒原理，把事件绑定在父元素上面，把所有本该子元素各自处理的事情交给父元素统一处理，达到性能优化的效果

2.不要给每个子节点设置事件监听器,而且事件监听器设置在其父节点上,然后利用冒泡原理设置每个子节点

三.事件委托的作用

只操作了依次DOM,提高了程序的性能，可以大量节省内存占用，减少事件注册

四.事件委托的核心原理

给父节点添加监听器,利用事件冒泡影响每一个节点

### 举例

* 场景一：你要给100个按钮添加点击事件，咋办？答：监听这100个按钮的祖先，等冒泡的时候判断target是不是这100个按钮中的一个。

  代码举例： http://js.jirengu.com/mudesoceme/1/edit?html,js,output
  
 * 场景二：你要监听目前不存在的元素的点击事件，咋办？答：监听祖先，等点击的时候看看是不是想要监听的元素即可。
 
   代码举例： http://js.jirengu.com/tijiduvame/1/edit?html,js,output
  
  优点：省监听数（内存），可以监听动态元素
  
  ## 封装事件委托
  
封装事件委托：（借助场景二的例子）=>改进后（递归判断）：

代码链接：http://js.jirengu.com/jabotecuvo/1/edit?html,js,output
