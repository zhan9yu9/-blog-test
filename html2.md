# 《HTML常用标签》

## a标签的用法

a标签的属性有href、target、download、rel=noopener四种。href的作用是超链接，href的取值有网址、路径、伪协议和ID；target是绝对该链接在哪一个窗口打开，
有_blank（新页面打开）、_ self（当前页面打开）、_ top（如果有两个窗口，在最顶层页面打开）、_ parent（当前链接所在的iframe的上一层打开）

## img 标签的用法

img的作用是发出get请求，展示一张图片。有alt/height/width/src四个属性，src后面可以是网络地址也可以是相对路径或者绝对路径，alt后面的内容是当
src加载失败之后所呈现的内容。width和height是改变图片的宽和高。max-width：100%（响应式）是指可以让图片根据窗口大小自动适应。

## table 标签的用法

table是表格，里面只能有thead、tbody、tfoot三个标签。<tr>是代表table里的一行，<th>表示表头。<td>表示表格里的内容例如：
  
      <table>
        /thead>
       <tbody>
        <tr>
            <td>英语</td>
            <td>翻译</td>
        </tr>
           <tr>
               <td>hyper</td>
               <td>超级</td>
           </tr>
           <tr>
               <td>target</td>
               <td>目标</td>
           </tr>
           <tr>
               <td>reference</td>
               <td>引用</td>
           </tr>
       </tbody>
       <tfoot>
           <tr>
            <td>空</td>
           <td>空</td>
           </tr>
       </tfoot>
   </table>
  
  双表头的写法为：
  
      <table>
        <thead>
            <tr>
                <th></th>
                <th>小红</th>
                <th>小明</th>
                <th>小影</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th>数学</th>
                <td>80</td>
                <td>90</td>
                <td>100</td>
            </tr>
            <tr>
                <th>语文</th>
                <td>70</td>
                <td>100</td>
                <td>100</td>
            </tr>
            <tr>
                <th>英语</th>
                <td>90</td>
                <td>100</td>
                <td>80</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <th>总分</th>
                <td>200</td>
                <td>200</td>
                <td>200</td>
            </tr>
        </tfoot>
    </table>
  
  ## 其他感想
  
  target的取值比较绕，还需要在理解一下。有点遗忘前面的内容了。
