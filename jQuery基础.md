###引入jQuery：
<script src="js/jquery.js" ></script>
<script>编写代码</script>


###选择器：
$("")


###jquery方法：
css()不常用


###attr方法：
attr("属性名","属性值")


###li:eq(1)：
找到li的第二个像素(0开始计)


###addClass方法 :
addClass("给元素添加的class名")


###removeClass方法：
removeClass("删除元素的class名")


###鼠标单击事件:
click(function(){
    执行代码
})


###
.index()获取元素的索引(0开始计)


###数组例：
var arr = ["1.png","2.png","3.png"]


###移入事件：
mouseenter
###移出事件：
mouseleave
###简写：
hover(function(){

},function(){

})


###移动事件：
mousemove(function(e){

})
e是事件对象
e.pageX x轴坐标
e.pageY y轴坐标
console.log("字符串"+变量)


#css隐藏：
display:none;
###hide方法：
hide(设置毫秒)将元素由右下到左上隐藏
###show方法：
show(设置毫秒)将元素由左上到右下显示
###slideUp方法：
slideUp(设置毫秒)将元素由下到上隐藏
###slideDown方法：
slideDown:(设置毫秒)将元素由上到下显示
###改变透明度
隐藏:fadeOut方法
显示:fadeIn方法


###animate方法：
自定义动画方法
例：
animate({
    样式:"像素"
    },设置毫秒)


###find方法：
find("元素名")查找后代元素


###常用属性节点：
attr、addClass、removeClass


###val方法：
var a=$("input").val()
获取input的value值并赋值
$("input").val("设置的value值")

###设置文本节点：
text方法：
获取和设置文本节点(用法参照val方法)


###html方法：可以获取元素中的所有内容，包括文本节点和其他html标签的文本添加和删除元素节点：
    append方法可在元素中追加新元素：
    $("ul").append("<li>apple</li>")
    remove方法将元素删除


###delegate方法：把事件委托处理
delegate("选择器"，"事件名称"，执行时间函数)

委托给父级例：
$("ul").delegate("li","click",function(){

})


###siblings方法：获取同级的其他元素
事件中的$(this)指事件绑定的元素