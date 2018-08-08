#emmet总结

1、生成后代元素：> 大于号表示后面要生成的内容是当前标签的后代

命令：nav>ul>li

每个命令输完后按下Tab键即可快速得到代码

 `<nav>    <ul>        <li></li>    </ul></nav>`
 
2、生成兄弟元素：+ 加号表示后面的元素和前面的元素是兄弟元素

命令：div+p+bq   得到代码如下：

<div></div><p></p><blockquote></blockquote>
3、生成上级元素：^   表示^后面的元素与^前面的元素的父元素是平级，即兄弟元素。一个^表示提升一个层级，两个提升两级

命令：div+div>p>span+em^bq  得到代码如下：

`<div></div><div>    <p><span></span><em></em></p>    <blockquote></blockquote></div>`

命令：div+div>p>span+em^^bq  得到代码如下：

`<div></div><div>    <p><span></span><em></em></p></div><blockquote></blockquote>`

4、生成类名： .    Emmet 默认的标签为 div ，如果我们不给出标签名称的话，默认就生成 div 标签。Emmet会根据父标签进行判定。比如在`<ul>`中输入.item，就会生成`<li class="item"></li>`。

命令：.container 得到代码如下：

`<div class="container"></div>`

如果想生成多个类名可连续写

命令： .container.wrapper.more  得到代码如下：

`<div class="container wrapper more"></div>`

5、生成ID：#

命令：#container  得到代码如下：

`<div id="container"></div>`

6、生成分组：()    用括号进行分组，这样可以更加明确要生成的结构，特别是层次关系

命令：(.foo>h1)+(.bar>h2)  得到代码如下：

`<div class="foo">    <h1></h1></div><div class="bar">    <h2></h2></div>`

7、重复生成多份：*   *号后面是想重复生成的份数

命令：ul>li*5    得到代码如下：

`<ul>    <li></li>    <li></li>    <li></li>    <li></li>    <li></li></ul>`

8、对生成内容依次编号：$    $就表示一位数字，只出现一个的话，就从1开始。如果出现多个，就从0开始。如果我想生成三位数的序号，那么要写三个$

命令：ul>li.item$*5   得到代码如下：

`<ul>    <li class="item1"></li>    <li class="item2"></li>    <li class="item3"></li>    <li class="item4"></li>    <li class="item5"></li></ul>`

只能这样单调的生成序号？对于强大的 Emmet 来说，肯定不会了，我们也可以在 $ 后面增加 @- 来实现倒序排列：命令：ul>li.item$@-*5  得到代码如下：

`<ul>    <li class="item5"></li>    <li class="item4"></li>    <li class="item3"></li>    <li class="item2"></li>    <li class="item1"></li></ul>`

同样，我们也可以使用 @N 指定开始的序号

命令：ul>li.item$@3*5  得到代码如下：

`<ul>     <li class="item3"></li>     <li class="item4"></li>     <li class="item5"></li>     <li class="item6"></li>     <li class="item7"></li></ul>`

至于ul>li.item$@-3*5 生成什么你们自己琢磨吧！

9、生成自定义属性：[attr]   中括号里面的内容是你想添加的属性

命令：td[rowspan=2 colspan=3 title]  得到代码如下：

`<td rowspan="2" colspan="3" title=""></td>`

10、生成文本内容：{}  大括号里面是你想添加的文本内容

命令：a{Click me}  得到代码如下：

`<a href="">Click me</a>`

命令：p>{Click }+a{here}+{ to continue}  得到代码如下：

`<p>Click <a href="">here</a>to continue</p>`