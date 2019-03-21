使用float会是这个盒子脱离文档流，使父容器的高度塌陷，会影响后面的页面布局
-清除浮动的方法
1.在父元素底部加入一行代码
<div style="clear: left"></div>
2在父容器div加入浮动
<div class="content clearFix">
.clearFix{
        float: left;
    }
但不建议使用 ，因为它也会影响后面的页面布局
3.