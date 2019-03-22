使用float会是这个盒子脱离文档流，使父容器的高度塌陷，会影响后面的页面布局
-清除浮动的方法
1.在父元素底部加入一行代码
<div style="clear: left"></div>
2在父容器css中加入浮动样式
<div class="content clearFix">
.clearFix{
        float: left;
    }
但不建议使用 ，因为它也会影响后面的页面布局
3.在父容器中使用伪类 after，
.content::after{   /*或者用clearFix 类名*/
      content: "";
      clear: both;
      display: block;
}
4.利用BFC 简称（块级格式化上下文）的效果来弥补父容器的高度塌陷
.content{
    overflow:hidden;auto;scroll
}
5.尼古拉斯大师 方法 ，把父容器的display设置为table，可以创建一个匿名表格单元
直接触发bfc效果     不建议使用，会出现一系列问题
.content{
    display:table;
}
