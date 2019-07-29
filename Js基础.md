# Js基础：

### 变量的命名规范
``` js
var age = 17;
var num1 = 198;
var num2 = 200;
var price = 25.6;
var _name = "小明";
var $fruit = "苹果";
var firstName = "Lily";
var message = "I love javascript";
```

* 变量名只能包括字母、数字、下划线和美元符号，切不能以数字开头。若以数字开头或包含其他特殊符号，系统会报错。
* 变量首字母小写，且要有语义，如右图所示，年龄用age，价格用price，消息用message。随意命名变量虽然不会报错，但会严重影响代码的可读性。
* 推荐使用驼峰命名，如果变量名由多个单词组成，则第二个单词开始首字母大写。

####求余表达式的返回值是两个数相除的余数
``` js
var result = 10 % 3;  //10除以3，得3与1 所以10 % 3表达式的值是1；
console.log(result);  //输出结果为1
```

#### 自增表达式可以使一个变量在原值的基础上加1
``` js
var num1 = 0;
num1++;  
console.log(num);

```

#### 自减表达式可以使一个变量在原值的基础上减1
``` js
var num2 = 0;
num2--;
console.log(num2);
```

**自增运算符和自减运算符可以向上面的例子，写在变量的后面，也可写在变量的前面，写在前后意义不同**

``` js
var num1 = 10;
var num2 = 10;
console.log(num1++);  //输出10
console.log(++num2);  //输出11
```

自增和自减运算符如果写在变量后面，那么表达式的返回值是变量本身，然后变量自增或自减，运算符写在变量前面，那么变大时的返回值直接就是变量自增或自减后的结果。

### 逻辑运算符
|运算符|操作|类型|
|------|----|--------|
|&&|逻辑与|any,any=>any|
||||逻辑或|any,any=>any|
|!|逻辑非|bool,bool|

逻辑运算符进行布尔运算，经常和关系运算符一起配合使用，逻辑运算符将多个关系表达式组合起来组成一个更复杂的表达式。

* 逻辑与（&&）（demo05.html）
``` js
var x = 10;
var y = 20;
console.log(x>30 && y>30); //第一个表达式为false直接返回false
console.log(x<30 && y>30); //第一个表达式是true,第二个为false,返回false
console.log(x<30 && y<30); //第一个表达式是true,第二个也是true,返回true
```

* 逻辑或（||）（demo06.html）
``` js
var x = 10;
var y = 20;
console.log(x>30 || y>30); //第一个表达式为false,第二个也是false，则返回false
console.log(x<30 || y>30); //第一个表达式是true，直接返回true
console.log(x>30 || y<30); //第一个表达式是false,第二个也是true,返回true
```

* 逻辑非（!）（demo07.html）
``` js
var x = true;
var y = false;
console.log(!x);   //非真为假
console.log(!y);   //非假为真
```

**通过控制运算符来实现数学运算**

``` js
var num1 = 10;
var num2 = 20;
var sign = "+";  //通过修改操作符，输出不同的结果
var result = 0;  //result用来存储计算的结果，现在设置一个初始值0
if(sign === "+"){
    result = num1 + num2;
    console.log(result)
}else if(sign === "-"){
    result = num1 - num2;
    console.log(result)
}else if(sign === "*"){
    result = num1 * num2;
    console.log(result)
}else if(sign === "/"){
    result = num1 / num2;
    console.log(result)
}else{
    console.log("请输入正确的运算符")
}
```

``` js
var num = 0;   //通过修改num的值控制执行哪行语句
switch(num){
    case 0:
        console.log("num的值是零");  //当n===0,执行
        break;
    case 1:
        console.log("num的值是一");  //当n===1,执行
        break;
    case 2:
        console.log("num的值是二");  //当n===2,执行
        break;
    case 3:
        console.log("num的值是三");  //当n===3,执行
        break;
    default:                         
        console.log("其他");         //当n的值不是0,1,2,3,执行
        break;
}
```

### 条件运算符
如果是简单的判断，我们可以使用条件运算符

``` js
表达式?第一个值:第二个值
```

如果表达式为true,表达式的返回值是第一个值，如果表达式为false,那么表达式的返回值是第二个值,示例代码如下所示（demo09.html）

``` js
var num1 = 10;
var num2 = 20;
var result = num1 > num2 ? 100 : 200;
//如果num1大于num2，条件表达式的值为100，若num1小于等于num2时，条件表达式的值为200；
console.log(result);
```

###  for语句
for语句的语法如下：
``` js
for(初始值;布尔值;计数器){
    //语句块
}
```
在for语句中，如果布尔值是true,就会一直执行语句块中的内容，为了防止死循环，需要有一个计数器，当数值达到指定值，布尔值就会变成false，循环便停止了。
``` js
for(var i = 0;i<10;i++){  
    // i的初始值是0
    // 判断i是否小于10，如果小于10则执行花括号中的代码
    // 每次执行完花括号中的代码后，i的值加1
    console.log(i);
}
```

### while语句
while语句语法如下所示：
``` js
while(bool){
    //bool为true,循环执行
}
```
当bool为true的时候，花括号中的内容会循环执行。为了防止死循环，需要在循环的过程实现类似for计数器的功能，让循环在有限的次数内定制。
``` js
var n = 0;
while(n<10){
    console.log(n);
    n++;
}
```
在每次循环的过程中都会让n的值加1，这样当n的值等于10，循环便停止，下面我来使用while语句输出100以内所有正整数的加和（demo04.html）
``` js
var n = 0;
var sum = 0;
while(n<=100){
    sum += n;
    n++;
}
console.log(sum);
```

#### continue
continue可以结束本次循环，直接进入到下一次循环，例如我们用for循环语句来实现输出0~5,7~9九个数字（跳过6）
``` js
for(var i = 0;i<10;i++){
    if(i===6){
        continue;
    }
    console.log(i);
}
```
上面的代码通过判断，实现当i的值为6的时候，跳过本次循环，直接接入下一次循环。

用continue来实现计算100以内所有不能被7整除的正整数加和。

``` js
var sum = 0;
for(var i = 0;i<=100;i++){
    if(i%7===0){
        continue;
    }
    sum += i;
}
console.log(sum);
```
#### break
在学switch语句中，我们已经解除到了break，它可以让分支语句在结束一个case之后，跳出switch语句，break同样可以用在循环语句当中，当代码执行到break时，直接结束循环。
``` js
for(var i = 0;i<10;i++){
    if(i===6){
        break;
    }
    console.log(i);
}
```
如上面的代码所示，当控制带输出5之后，循环结束。


#### 函数的基本概念
函数是一个可执行的语句块，定义的时候不执行，调用的时候执行，使用"函数名()"的形式可以调用函数。
``` js
function fun(){   //定义函数,函数名为fun
    //函数体
}
fun();            //调用函数
```


#### 传递参数
下面编写一个函数sum,输出10和20两个数之和。
``` js
function sum(){
    var num1 = 10;
    var num2 = 20;
    var result = num1 + num2;
    console.log(result);
}
sum();
```

在上面例子中我们调用sum函数，可以成功在控制台输出计算结果，但是函数内部的代码是固定的，虽然可以多次使用，但是每次使用输出的都是10和20的加和，为了让函数更加灵活


``` js
function fun(str){
    console.log("hello" + str);
}
fun("world");
```
在定义函数的括号中，我们添加了一个参数str,这个参数叫做形参。它在函数内部像一个变量一样。但是在函数调用之前他是没有值的。当调用函数的时候，调用函数的括号中我们也添加了一个参数"world"，这个参数叫做实参，他可以是任意数据类型的值。函数被调用后，形参str被赋予了实参"world"的值，然后执行console.log便会在控制台输出"helloworld"


``` js
function sum(num1,num2){
    console.log(num1 + num2);
}
sum(10,20);
```
当我们调用函数的时候，实参和形参是一一对应的，10对应的是num1,20对应的是num2,函数执行后会在控制台输出10和20的加和。


``` js
function sum(n){
    var sum = 0;
    for(var i = 0;i<=n;i++){
        sum += i;
    }
    console.log(sum);
}
sum(100);
sum(567);
```
我们通过一个函数规定了一种计算方式，我们使用函数的只要输入一个值，函数就会计算出一个准确的结果。


#### 函数的返回值
在上面的例子中，我们输入了一个参数，函数就可以在控制台输出我们希望得到的结果，但是在实际开发中，很多情况我们要的不是在控制台输出得到的结果，而单纯的只是为了获取这个值，那么我们就需要用到函数的返回值。

在函数中，我们可以通过return关键字指定一个返回值，函数有了return，当函数被调用的时候就可以把调用的结果赋值给另一个变量了。
``` js
function fun1(){
    
}

function fun2(){
    return "hello fun";
}

var str1 = fun1();
var str2 = fun2();

console.log(str1);  //输出undefined
console.log(str2);  //输出"hello fun"
```
在上面的例子中，函数fun1没有返回值，所有将fun1调用的结果赋值给str1,str1的值为undefined，函数fun2有返回值，返回值是"hello fun"，所以当fun2被调用后，将函数运行的结果赋值给str2,str2的值就是"hello fun"

计算四则运算的结果
``` js
function count(num1,sign,num2){
    var result = 0;
    switch(sign){
        case "+":result = num1 + num2;break;
        case "-":result = num1 - num2;break;
        case "*":result = num1 * num2;break;
        case "/":result = num1 / num2;break;
        default:console.log("请输入真确的操作符")
    }
    return result;
}
console.log(count(10,"*",20));
```


#### 自定义对象
我们可以通过一对花括号来创建一个对象
``` js
var obj = {};
```

在花括号中，我们可以为对象定义属性，下面我们来写一个猫的对象
``` js
var cat = {               //定义一个对象cat,它有两个属性，name和age
    name:"喵喵",
    age:2
}
//有两种方法可以获取到对象的属性值：1、对象名.属性名；2、对象名["属性名"]
console.log(cat.name);    
console.log(cat["name"]);
```


#### 方法
通过上面的例子我们可以知道name的属性值是字符串类型，age的属性值是数值类型。其实对象的属性值可以是任何数据类型，甚至可以是函数，如果对象的属性值是函数，那么我们叫这个属性为这个对象的方法。

``` js
var cat = {
    name:"喵喵",
    age:2,
    sayName:function(){
        console.log("我是喵喵");
    }
}
cat.sayName();
```

#### this关键字
在上面的例子中，我们可以给cat的那么属性重新赋值，代码如下；
``` js
var cat = {
    name:"喵喵",
    age:2,
    sayName:function(){
        console.log("我是喵喵")
    }
}
cat.name = "小白";
console.log(cat.name);    //输出"小白"
cat.sayName();            //输出"我是喵喵"

```

因为猫的名字已经改变，但是sayName方法里面的名字并没有一同变化，我们可以通过this关键字实现修改了名字，方法里面的名字也会改变。


在对象的方法中使用this，可以指向这个对象本身
``` js
var cat = {
    name:"喵喵",
    age:2,
    sayName:function(){
        console.log("我是"+this.name)
    }
}
cat.sayName();            //输出“我是喵喵”
cat.name = "小白";
console.log(cat.name);    //输出"小白"
cat.sayName();            //输出“我是小白”
```


#### 方法传参
给对象的方法传递参数和给函数传递参数是一样的，下面我们来定义一个会算数的猫
``` js
var cat = {
    name:"喵喵",
    age:2,
    sayName:function(){
        console.log("我是"+this.name)
    },
    count:function(num1,num2){
        console.log(num1+num2);
    }
}

cat.sayName();
cat.count(10,20);
```
我们在之前代码的基础上，有添加了一个count方法可以让猫可以计算两个数的加和，我们只要传入实参，猫就能计算结果。


#### 数组的基本概念
数组是一个特殊的对象，对象的概念是属性的集合，而数组是元素的有序集合。我们可以通过一个中括号来定义一个数组。
``` js
var numlist = [1,3,5,7,9];
```

在上面的代码中我们定义了一个数组，数组有5个元素，五个元素多是数值型。我们可以通过数组的变量名配合中括号来获取数组的元素


``` js
var numlist = [1,3,5,7,9];
console.log(numlist[0]);   //输出数组的第一个元素
console.log(numlist[4]);   //输出数组的第五个元素
```

中括号中的数字叫做数组的下标，我们可以通过下标获取数组的元素，要注意的是下标是从零开始的。


数组是特殊的对象，它有自己的属性和方法，其中最常用的属性就是length，它可以获取数组元素的个数。

``` js
var numlist = [1,3,5,7,9];
console.log(numlist.length) // 输出5
```

数组中的元素可以是任意类型的，但是我们一般将数组中的元素设置成相同数据类型，


``` js
var friends = ["小明","小亮","小红"];
console.log(friends[0]);  //小明
console.log(friends[1]);  //小亮
console.log(friends[2]);  //小红
console.log(friends.length);  //3
```


#### 遍历数组
数组中的元素可能很多，元素的个数也可能发生变化，所以需要输出数组所有元素的时候，手动用下标输出每一个值，我们需要一种更自动的方法来查询数组中的每一个元素，这就是遍历数组，我们可以使用for循环来遍历数组。

``` js
var friends = ["小明","小亮","小红","张三","李四","王五"];
for(var i = 0;i<friends.length;i++){
    console.log(friends[i]);     //输出数组中的所有元素
}
```

使用for...in语句同样可以遍历数组
``` js
var friends = ["小明","小亮","小红","张三","李四","王五"];
for(var i in friends){
    console.log(friends[i]);
}
```


#### 数组的常用方法

* 添加元素push：
我们可以使用push方法想数组中追加元素
``` js
var friends = ["小明","小亮"];
friends.push("小红");
console.log(friends);   //输出["小明","小亮","小红"];
```

我们可以使用for语句循环箱数组中插入内容：
``` js
var arr = [];
for(var i = 0;i<10;i++){
    arr.push(i);
}
console.log(arr);   //输出[0,1,2,3,4,5,6,7,8,9]
```

* 数组连接成字符串join：
通过join方法可以将数组链接成一个字符串
``` js
var friends = ["小明","小亮","小红","张三","李四","王五"];
var str1 = friends.join();    //用逗号分隔
var str2 = friends.join("");  //没有分隔
var str3 = friends.join("+"); //用加号分隔
console.log(str1);
console.log(str2);
console.log(str3);
```


#### 弹出框方法
为了模拟客户端的输入和输出，我们在这里使用浏览器的弹出框。浏览器的弹出框方法有三个，分别是alert、prompt、confirm。
* alert是最简单的弹出框，我们在之前的课程中使用过，它可以向用户显示一条消息，并等待用户关闭对话框。
``` js
alert("hello world");
```

* confirm也会向用户显示一条消息，但是用户可以通过点击“确定”或“取消”按钮，并返回一个布尔值。
``` js
var result = confirm("点确定返回true,点取消返回false");
console.log(result);   //点击不同按钮，控制台输出结果不同
```

* prompt也可以像用户显示一条消息，等待用户输入字符串后，返回这个字符串，如果用户点击取消，则返回null。
``` js
var result = prompt("请输入你的名字：")
console.log(result);   
```

#### 数学计算
我们利用上面弹出框来实现一个数学计算的功能,步骤如下：
1. 弹出输入框，输入第一个数字
2. 弹出输入框，输入操作符
3. 弹出输入框，输入第二个数字
4. 弹出对话框，显示计算结果
5. 如果输入错误会有相应的错误提示

上面是我们的程序的需求，我们来一步步完成这个功能。首先，我们先实现弹出框的功能，为了确定我们输入的内容被成功获取，我们将输入的内容在控制台输出。
``` js
var num1 = Number(prompt("请输入第一个数字"));   //为了方便计算，将获取的字符串转换成数值类型
var sign = prompt("请输入+-*/中的任意操作符");
var num2 = Number(prompt("请输入第二个数字"));
console.log(num1);
console.log(sign);
console.log(num2);
```

我们已经成功的获取到了需要计算的数字和操作符，下面我们要编写一个用来实现四则运算的函数帮助我们计算记过。
``` js
var x = 10;
var y = 20;
var sign = "+";
var result;

function count(n,s,m){    //n是第一个数字，s是操作符，m是第二个数
    switch(s){
        case "+":return n+m;break;
        case "-":return n-m;break;
        case "*":return n*m;break;
        case "/":return n/m;break;
    }
}

result = count(x,sign,y);
console.log(result);
```
count函数就是我们要的函数，它可以实现通过两个数字和一个操作符作为参数，然后返回值是计算的结果。上面我们已经对函数进行了测试，可以实现计算功能。下一步，我们需要将函数放到我们提示框功能内。并通过它计算出结果。

``` js
var num1 = Number(prompt("请输入第一个数字"));   //为了方便计算，将获取的字符串转换成数值类型
var sign = prompt("请输入+-*/中的任意操作符");
var num2 = Number(prompt("请输入第二个数字"));
var result;

function count(n,s,m){    //n是第一个数字，s是操作符，m是第二个数
    switch(s){
        case "+":return n+m;break;
        case "-":return n-m;break;
        case "*":return n*m;break;
        case "/":return n/m;break;
    }
}

result = count(num1,sign,num2);
alert(result);
```

上面我们已经实现了1~4的需求，但是现在的程序还很脆弱，如果我们随意输入的话，程序并不会给出友好的提示，所以我们需要为程序添加一些对错误输入的提示消息。

#### DOM的基本概念
* 文档对象模型
* 定义了树状结构
* 定义了接口，可以用来操作树状结构

#### 样式操作
我们可以通过DOM提供的querySelector方法来获取元素，然后进一步操作它的样式;
``` html
<h1>DOM样式测试</h1>
<script>
    var h1 = document.querySelector("h1");  
    //querySelector的返回值是一个DOM对象，该方法可以通过选择器获取元素，若选择器找到多个元素，则返回第一个。
    h1.style.color = "red"; 
    //DOM对象的style属性可以设置元素内联样式。
</script>
```


若需要通过js设置多个元素的样式，可以使用querySelectorAll方法。

``` html
<ul>
    <li>香蕉</li>
    <li>苹果</li>
    <li>鸭梨</li>
</ul>
<script>
    var ali = document.querySelectorAll("li");
    //querySelectorAll方法的返回值是一个类数组的集合，里面保存的是获取的所有元素，所以如果希望为每一个元素设置样式，需要遍历这个集合。
    for(var i = 0;i<ali.length;i++){
        ali[i].style.color = "red";
    }
</script>
```


#### 三、绑定事件
事件就是文档或者浏览器窗口发生的一些特定的交互瞬间，例如：用户点击网页会触发点击事件（click），用户在元素上移动会触发鼠标移动事件（mousemove）等。下面我们来定义一个点击事件，当我们点击一个按钮的时候，弹出"hello world"。
``` html
<button>按钮</button>
<script>
    var btn = document.querySelector("btn");
    btn.onclick = function(){
        console.log("hello world");
    }
</script>
```
我们将一个函数赋值给一个事件，当这个事件被触发的时候，这个函数就会被执行。


#### 四、操作属性
我们可以通过JavaScript获取和设置元素属性，例如input的value属性值，或者img的src属性。

首先我们来实现一个效果，在文本框中输入字符串，然后点击按钮用在控制台输出我们输入的字符串
``` html
<input type="text">
<button>输出</button>
<script>
    var input = document.querySelector("input");
    var btn = document.querySelector("button");
    btn.onclick = function(){
        var text = input.value;    //获取input的value属性
        console.log(text);
    }
</script>
```
我们还可以通过赋值的方式为一个元素设置属性。
``` html
<img src="images/img1.jpg" alt="">
<button>切换图片</button>
<script>
    var img = document.querySelector("img");
    var btn = document.querySelector("button");
    btn.onclick = function(){
        img.src = "images/img2.jpg";
    }
</script>
```
当点击按钮的时候，通过赋值的方式把另一张图片的地址赋值给img标签的src属性，就实现了图片切换的效果

#### 五、数学计算案例
下面我们来实现一个能完成数学计算的程序，页面有四个文本框和一个按钮，我们在第一个文本框输入一个数字，在第二个文本框输入一个操作符，第三个文本框再输入一个数字，然后当我们点击计算按钮的时候，会在第四个文本框计算出结果,这个例子和我们学习switch语句的时候写的例子很像，但是那时候我们没有可操作的页面，现在我们把计算功能写在一个函数中。
``` html
    <input type="text" id="num1">
    <input type="text" id="sign">
    <input type="text" id="num2">
    <input type="text" d="result">
    <button>计算</button>
    <script>
        var num1 = document.querySelector("#num1");
        var sign = document.querySelector("#sign");
        var num2 = document.querySelector("#num2");
        var result = document.querySelector("#result");
        var btn = document.querySelector("button");
        btn.onclick = function(){
            var n = Number(num1.value);    //将字符串类型转换成数字类型
            var m = Number(num2.value);
            var r = count(n,sign.value,m);
            result.value = r;
        }
        function count(n,s,m){    //n是第一个数字，s是操作符，m是第二个数
            switch(s){
                case "+":return n+m;break;
                case "-":return n-m;break;
                case "*":return n*m;break;
                case "/":return n/m;break;
            }
        }
    </script>
```


#### 节点的分类
* 元素节点
* 属性节点
* 文本节点

#### 文本节点
在html中我们有一个h1标签和一个按钮，h1标签内已经有了一段文本。当我们点击按钮的时候，在h1标签中插入“hello world”
``` html
<h1>内容：</h1>
<button>添加文本节点</button>
<script>
    var h1 = document.querySelector("h1");
    var btn = document.querySelector("button");

    btn.onclick = function(){
        var textNode = document.createTextNode("hello world");
        //createTextNode方法可以创建一个文本节点
        h1.appendChild(textNode);
        //appendChild方法可以将textNode节点添加到h1标签中。
    }
</script>
```

在DOM种还有另一个属性可以更方便地获取和设置文本节点，这个属性是innerHTML


``` html
<h1>内容：</h1>
<button>添加文本节点</button>
<script>
    var h1 = document.querySelector("h1");
    var btn = document.querySelector("button");
    btn.onclick = function(){
        h1.innerHTML = "hello world";
        //设置h1的文本节点，innerHTML的内容会完全覆盖原节点的内容
    }
</script>
```


对比着两种方法，第一种方法需要创建文本节点，然后通过appendChild方法将节点追加到之前文本内容的后面，第二种方法则是直接用innerHTML覆盖之前文本节点的内容。如果要实现demo01的功能，需要改写一下事件内的代码
``` js
var str = h1.innerHTML;//获取文本内容
h1.innerHTML =str + "hello world"; //原文本内容与新文本内容连接
```


#### 创建和添加元素节点
创建原始节点可以使用createElement方法，添加元素节点仍然可以用appendChild方法
``` html
<button>添加节点</button>
<ul>
    <li>香蕉</li>
    <li>苹果</li>
    <li>鸭梨</li>
</ul>
```
我们要是先一个功能，当点击按钮的时候，在列表中添加一个li元素

``` js
var btn = document.querySelector("button");
var ul = document.querySelector("ul");
btn.onclick = function(){
    var li = document.createElement("li"); //创建一个元素节点，li元素
    ul.appendChild(li); //在ul元素中添加li元素
}
```
在这个案例中，我们已经成功地在ul标签中添加了li元素，但是li元素并没有文本节点，我们进一步改进点击事件中的内容：

``` js
var li = document.createElement("li"); 
li.innerHTML = "鸭梨";
ul.appendChild(li); 
```
通过上面的代码，我们已经可以在ul中添加带有文本节点的li元素了，但是文本节点是固定的“鸭梨”，我们还可以进一步通过一个文本框，让用户自己填写要插入的内容

``` js

```

#### 删除元素节点
我们可以通过removeChild方法删除元素,下面的例子我们来实现点击按钮，删除h1标签的效果
``` html
<button>删除</button>
<div class="box">   
    <h1>待删除的内容</h1>
</div>
<script>
    var btn = document.querySelector("button");
    var box = document.querySelector(".box");
    var h1 = document.querySelector("h1");
    btn.onclick = function(){
        box.removeChild(h1);
    }
</script>
```
通过上面的代码可以知道，删除一个元素需要知道他的父级元素，然后通过父级元素的removeChild方法删除子集元素，那么如果不确定删除的元素的父级是哪有个元素，我们该如何获取元素的父级元素呢，可以使用parentNode方法，我们之前爱来改写上面的代码

``` html
<button>删除</button>
<div>   
    <h1>待删除的内容</h1>
</div>
<script>
    var btn = document.querySelector("button");
    var h1 = document.querySelector("h1");
    btn.onclick = function(){
        var box = h1.parentNode;
        box.removeChild(h1);
    }
</script>
```



下面我们来实现一个删除水果列表中水果的功能，html代码如下
``` html
<ul>
    <li><span>香蕉</span> <span class="del">删除</span></li>
    <li><span>苹果</span> <span class="del">删除</span></li>
    <li><span>鸭梨</span> <span class="del">删除</span></li>
    <li><span>芒果</span> <span class="del">删除</span></li>
    <li><span>草莓</span> <span class="del">删除</span></li>
</ul>
```

我们要实现点击删除按钮的时候，删除span父级的li元素

``` js
var aDel = document.querySelectorAll(".del");
for(var i = 0;i<aDel.length;i++){
    aDel[i].onclick = function(){
        var parent = this.parentNode
        parent.parentNode.removeChild(parent)
    }
}
```


### 绑定事件
想要给一个元素绑定事件，我们有两种方法：使用内联事件或事件监听器。在之前的课程中，我们一直使用的是内联事件来为元素绑定事件，例如一个按钮的点击事件，代码如下。
``` js
btn.onclick = function(){}   //绑定鼠标单击事件
```

我们还可以用使用事件监听器为元素绑定事件，代码如下
``` js
btn.addEventListener("click",function(){});
```
下面我们用两种方法为按钮绑定事件

``` html
<button id="btn1">按钮1</button>
<button id="btn2">按钮2</button>
<script>
    var btn1 = document.querySelector("#btn1");
    var btn2 = document.querySelector("#btn2");

    btn1.onclick = function(){
        console.log("我是按钮1");
    }

    btn2.addEventListener("click",function(){
        console.log("我是按钮2");
    })
</script>
```
两种方法都能实现相同的效果，能成功的为按钮绑定了点击事件，但区别是使用addEventLitener可以无限制第为元素绑定事件，而内联事件后面的会覆盖前面的

``` js
var btn1 = document.querySelector("#btn1");
var btn2 = document.querySelector("#btn2");

btn1.onclick = function(){
    console.log("我是按钮1");
}
btn1.onclick = function(){
    console.log("我是按钮1,第二次绑定");
}

btn2.addEventListener("click",function(){
    console.log("我是按钮2");
})

btn2.addEventListener("click",function(){
    console.log("我是按钮2,第二次绑定");
})
```

第一个按钮第二次绑定的事件覆盖了第一次绑定的事件，第二个按钮两次绑定的事件都能被触发。

### 事件冒泡与事件捕获
接下来我们用事件监听器为三个div元素绑定点击事件，最外层的div宽高是300px，中间的div宽高都是200px，最内层的div宽高都是100px，那么思考一下，点击最内层的div，事件会如何触发，是只触发最内层的div，还是从内到外依次触发，还是从外到内依次触发。
``` html
<div class="box1">
    <div class="box2">
        <div class="box3"></div>
    </div>
</div>
```

``` css
.box1{
    width:300px;
    height:300px;
    background-color: yellow;
}
.box2{
    width:200px;
    height:200px;
    background-color: blue;
}

.box3{
    width:100px;
    height:100px;
    background-color: red;
}
```

``` js
var box1 = document.querySelector(".box1");
var box2 = document.querySelector(".box2");
var box3 = document.querySelector(".box3");

box1.addEventListener("click",function(){
    console.log("我是box1")
})
box2.addEventListener("click",function(){
    console.log("我是box2")
})
box3.addEventListener("click",function(){
    console.log("我是box3")
})
```
通过上面的例子我们可以看到，事件是从最内层开始触发，然后依次向外，输出的顺序是box3-box2-box1。导致这种顺序的原因是因为：事件流有事件捕获阶段和事件冒泡阶段，事件捕获阶段是从最外层元素开始一层一层进入到事件目标（也就是我们点击的那个元素），到达事件目标后，进入事件冒泡阶段，事件从最内层流向最外层，事件默认情况下在冒泡阶段触发，所以我们看到的是先输出box3,最后输出box1。

我们也可以将事件设置为捕获阶段触发，
``` js
box1.addEventListener("click",function(){
    console.log("我是box1")
},true)
box2.addEventListener("click",function(){
    console.log("我是box2")
},true)
box3.addEventListener("click",function(){
    console.log("我是box3")
},true)
```
只要在添加事件方法中添加第三个参数为true,事件就会在捕获阶段被触发，这样输出的顺序就变成了box1-box2-box3。但是在日常开发中，我们几乎不用做此修改，让事件在冒泡阶段触发就可以了。

### 事件委托
利用事件流的原理，我们可以实现事件委托，事件委托可以简单第理解为将子集的事件委托给父级来处理，我们先来看一个简单的例子
``` html
<div class="btnBox">
    <button class="btn1">按钮1</button>
    <button class="btn2">按钮2</button>
</div>
```
网页中有两个按钮，他们的父级是一个div标签，现在我们希望给这两个按钮绑定事件，当我们点击按钮的时候输出按钮的文本内容，按照我们之前学过的知识，可以有如下写法
``` js
//第一种写法
var btn1 = document.querySelector(".btn1");
var btn2 = document.querySelector(".btn2");
btn1.addEventListener("click",function(){
    console.log(this.innerHTML)
})
btn2.addEventListener("click",function(){
    console.log(this.innerHTML)
})
```
这种方法简单易懂，但是存在重复，两个按钮触发事件执行的代码完全一样，我们可以过去到所有按钮，再通过遍历绑定事件
``` js
var btnArray = document.querySelectorAll("button");
for(var i = 0;i<btnArray.length;i++){
    btnArray[i].addEventListener("click",function(){
        console.log(this.innerHTML)
    })
}
```
通过遍历我们优化了代码，但是仍然存在问题，首先，如果按钮的数量特别多，每一个按钮都绑定依次事件会非常影响程序的性能，其次，就算不考虑性能，通过这种方法绑定事件，如果使用js新增了一个按钮，这个按钮因为初始化的时候没有绑定事件，所以无法点击。为了解决上述问题，我们可以使用事件委托的方式来实现上面的功能
``` js
var btnBox = document.querySelector(".btnBox");
btnBox.addEventListener("click",function(event){
    var target = event.target;    //通过事件对象获取事件目标
    console.log(target.innerHTML);
})
```
在事件监听函数中，我们可以在形参的位置获取到事件对象event，事件对象中包含了事件相关的信息，通过event.target可以获取到我们的事件目标，在这个例子中事件目标就是我们点击的按钮，而我们事件绑定的是按钮的容器，这样就可以将自己元素的事件委托给父级来处理。



### 计时器方法概述
计时器方法可以实现在指定的时间过后，单词或重复调用函数的功能，setTimeout可以实现函数在指定毫秒数后单词执行，setInterval可以实现函数在指定毫秒数后重复执行，语法如下所示：
``` js
setTimeout(function(){
    //一秒后执行
},1000);

setInterval(function(){
    //一秒后执行，并且每隔一秒重复执行
},1000)
```

### 二、setTimeout
下面我们来实现一个效果，页面加载3秒后在控制台输出hello world
``` js
setTimeout(function(){
    console.log("hello world");
},3000)
```

当计时器开始计时后，我们可以使用clearTimeout方法让计时器停下来，下面我们来定义一个按钮，当页面加载后，如果我们在3秒钟之内点击按钮，计时器会停止，不会输出hello world，如果不点击按钮，3秒钟之后就会输出hello world。

``` js
var btn = document.querySelector("button");
var t = setTimeout(function(){
    console.log("hello world");
},3000)
btn.onclick = function(){
    clearTimeout(t);
}
```

setTimeout方法会返回一个整数类型的值，通过这个值，我们可以停止计时器。我们将setTimeout方法的返回值赋值给一个变量，当点击按钮的时候，使用clearTimeout方法，传入t，这样计时器就会停止，hello world就不会在控制台输出。

### setInterval
setInterval的用法与setTimeout的用法非常类似，都是传入两个参数，第一个参数是计时器执行的函数，第二个参数是毫秒数。下面我们来实现一个效果，每3秒钟在控制台输出依次hello world
``` js
setInterval(function(){
    console.log("hello world");
},3000)
```
从代码可以看出，setInterval与setTimeout完全相同，区别在于setInterval参数中的函数没个指定毫秒数后都会重复执行。当我们不希望计时器重复执行的时候，就可以使用clearInterval方法来停止计时器。
``` js
var btn = document.querySelector("button");
var t = setInterval(function(){
    console.log("hello world");
},3000)
btn.onclick = function(){
    clearTimeout(t);
}
```
下面我们来实现一个效果，让控制台输出每隔1秒按顺序输出正整数，从数字1开始输出
``` js
var n = 1;
function showNumber(){
    console.log(n);
    n++;
}
setInterval(showNumber,1000);
showNumber();    //调用函数，可以在页面加载时直接输出1。
```
上面的代码与之前有一点区别，我们并没有直接给setInterval传递一个匿名函数，而是先定义了一个函数showNumber，然后将showNumber传递给setInterval，这两种写法效果是一样的，但是如果将匿名函数传入setInterval，这个函数将不能被调用。

在上面代码的结尾，我们在页面加载之后调用了一次showNumber，目的是为了让页面加载的时候就输出1，否则我们将要等待一秒之后才能看到控制台输出1。

这个案例会一直输出数字，下面我们来改进这个例子，当数字为10的时候就停止，效果看起来有些想之前讲过的for循环输出数字，但用计时器输出可以实现每个1秒输出一个数字，而不是连续的输出。
``` js
var n = 1,t=0;
function showNumber(){
    console.log(n);
    if(n === 10){
        clearInterval(t);
    }
    n++;
}
t=setInterval(showNumber,1000);
showNumber(); 
```
我们通过一个if语句判断n的值，当n到达10的时候，就停止计时器，这样计时器就不会再继续输出数字了。

我们还可以继续用按钮控制计时器，这次我们定义一个h1标签存放数字，再用两个按钮来实现“开始计数”和“停止计数”功能

``` html
    <h1>0</h1>
    <button id="start">开始计数</button>
    <button id="stop">停止计数</button>
    <script>
        var btnStart = document.querySelector("#start");
        var btnStop = document.querySelector("#stop");
        var h1 = document.querySelector("h1");
        var t;
        btnStart.onclick = function(){
            clearInterval(t);                       //防止连续点击开始计时，导致创建多个计时器
            t = setInterval(function(){
                var number = Number(h1.innerHTML);  //将h1的文本节点转换成数字
                number++;
                h1.innerHTML = number;
            },300); 
        }

        btnStop.onclick = function(){
            clearInterval(t);
        }
    </script>
```


在网页中我们经常会看到指定秒数跳转到其他网页，我们可以用计时器方法来实现这个功能

``` html
<p><span class="seconds">5</span>秒后跳转到百度</p>
<script>
    var seconds = document.querySelector(".seconds");
    setInterval(function(){
        var s = Number(seconds.innerHTML);
        s--;
        seconds.innerHTML = s;
        if(s === 0){
            location.href = "http://baidu.com";  //location.href可以实现页面跳转
        }
    },1000)
</script>
```


### 内置对象概述
javascript为我们提供了很多内置对象，这些内置对象为我们提供了很多语言的基本功能。我们之前学过的数组就是JavaScript的内置对象，除了数组我们还应该了解的内置对象有：Math、Date、RegExp。

需要说明的是document对象是DOM提供的对象，不属于JavaScript内置对象，window对象是BOM中的对象，同样不属于JavaScript内置对象。

### Math
Math对象不像数组那样需要我们手动去创建，我们在JavaScript程序中直接写Math代表的就是Math对象。我们可以通过Math对象直接获取圆周率。
``` js
var pi = Math.PI;
console.log(pi);
```
Math对象提供了很多方法来简化我们的数学运算，下面简单列举几个方法
``` js
var pi = Math.PI;   
var num1 = Math.floor(pi);  //向下取整
var num2 = Math.ceil(pi);   //向上取整
var num3 = Math.round(pi);  //四舍五入
var num4 = Math.abs(-pi);   //获取绝对值
var num5 = Math.random();   //获取0~1之间的随机数
console.log(num1);
console.log(num2);
console.log(num3);
console.log(num4);
console.log(num5);
```
在Math对象的方法中，floor和random两个方法比较常用，我们可以通过这两个方法获取我们想要的随机数范围。例如我们想要1~10的十个随机数，
``` js
var number = Math.floor(Math.random()*10 + 1);
console.log(number);
```

下面我们来实现一个猜数字的游戏，JavaScript随机生成一个1~100之间的数字，我们通过文本输入框输入我们所猜的数字，猜的数字不管是大于结果，还是小于结果，还是等于结果，都会有相应的提示，代码如下
``` html
<input type="text" id="number">
<button id="guess">猜数字</button>
<script>
    var target = Math.floor(Math.random()*100+1); //生成1~100的随机数。
    var btn = document.querySelector("#guess");
    var number = document.querySelector("#number");
    btn.onclick = function(){
        var value = Number(number.value);
        if(value > target){
            alert("大于结果");
        }else if(value < target){
            alert("小于结果");
        }else if(value === target){
            alert("回答正确");
        }
    }
</script>
```

### Date
Date对象是JavaScript用于处理日期和时间的对象，我们可以通过Date对象获取当前的时间，需要说明的是Date对象获取的时间是本机的时间。
``` js
var dateNow = new Date();
var year = dateNow.getFullYear();    //获取年，不能用getYear()方法，此方法已经被废弃
var month = dateNow.getMonth();      //获取月份 从0开始，一月份返回的值是0
var date = dateNow.getDate();        //获取日期
var hours = dateNow.getHours();      //获取小时
var minutes = dateNow.getMinutes();  //获取分钟
var seconds = dateNow.getSeconds();  //获取秒
var day = dateNow.getDay();          //获取星期
console.log(year);
console.log(month);
console.log(date);
console.log(hours);
console.log(minutes);
console.log(seconds);
console.log(day);
```
我们可以通过JavaScript将当前的时间显示在网页上
``` js
var h1 = document.querySelector("h1");
var dateNow = new Date();
var hours = dateNow.getHours();      
var minutes = dateNow.getMinutes();  
var seconds = dateNow.getSeconds(); 
var strTimeNow = hours + ":" + minutes + ":" + seconds;
h1.innerHTML = strTimeNow;
```
上面的例子我们成功将当前的日期显示在h1标签中，但是我们显示的时间是获取的那个时间点，显示的时间是静止不动的，我们可以通过计时器方法让我们显示的时间与实际时间同步。
``` js
var h1 = document.querySelector("h1");
function getTime(){     
    var dateNow = new Date();
    var hours = dateNow.getHours();      
    var minutes = dateNow.getMinutes();  
    var seconds = dateNow.getSeconds(); 
    var strTimeNow = hours + ":" + minutes + ":" + seconds;
    h1.innerHTML = strTimeNow;
}
getTime();
setInterval(getTime,1000);
```
我们将过去时间的代码放到了一个函数中，然后通过计时器方法每秒执行一次这个函数，这样我们显示出来的日期就想电子钟一样每秒与真实事件同步一次。

我们还可以通过参数创建一个指定时间的日期对象，我们修改一下demo05的代码
``` js
var dateNow = new Date("2017-5-1 17:30:20");  //创建指定日期和时间的对象
var year = dateNow.getFullYear();   
var month = dateNow.getMonth();     
var date = dateNow.getDate();       
var hours = dateNow.getHours();      
var minutes = dateNow.getMinutes(); 
var seconds = dateNow.getSeconds(); 
var day = dateNow.getDay();
```

我们在编写程序的时候，有的时候会希望获取一个唯一的时间点，我们可以使用getTime方法或得。

``` js
var dateTarget = new Date("2017-5-1 17:30:20");
var dateNow = new Date();
var target = dateTarget.getTime();
var now = dateNow.getTime();
console.log(target);
console.log(now);
```
通过getTime方法可以获取时间戳，时间戳是指格林威治时间1970年01月01日00时00分00秒(北京时间1970年01月01日08时00分00秒)起至现在的总毫秒数，我们可以用时间戳表示一个不会重复的时间点。



### 需求分析
通过需求的描述，我们知道程序中有两个时间，一个是当前时间，一个是目标时间，当前时间是不断变化的，目标时间不会变化。倒计时始终记录的是当前时间和目标时间的时间差。那么如何计算两个时间的时间差呢，我们可以通过时间戳来实现。
``` js
var target = new Date("2017-8-5 22:30");
var targetTime = target.getTime();

function getTimeNow(){      
    var now = new Date();
    var nowTime = now.getTime();
    console.log(targetTime - nowTime);
}

setInterval(getTimeNow,1000);
```

我们已经输出了距离目标时间的时间戳，现在我们需要一个函数将毫秒数转换成天、小时、分钟和秒。

``` js
var ms = 17420000;      //定义一个毫秒数
function getResultTime(ms){
    var days = Math.floor(ms / (24 * 60 * 60 * 1000));  //计算出天数
    var ms1 = ms % (24 * 60 * 60 * 1000); //计算出天后还剩多少毫秒
    var hours = Math.floor(ms1 / (60 * 60 * 1000)); //计算出小时
    var ms2 = ms % (60 * 60 * 1000); //计算出小时候还有多少毫秒
    var minutes = Math.floor(ms2 / (60 * 1000)); //计算出分钟
    var ms3 = ms % (60 * 1000); //计算出分钟后还有多少毫秒
    var seconds = Math.floor(ms3 / 1000); //计算出秒数
    return {                               //返回值是一个对象，这个对象包括了日、小时、分钟、秒
        days:days,
        hours:hours,
        minutes:minutes,
        seconds:seconds
    }
}
var time = getResultTime(ms);
console.log(time.days);
console.log(time.hours);
console.log(time.minutes);
console.log(time.seconds);
```

下面我们可以通过这个行数，将我们得到的距离目标时间的毫秒数，计算出距离目标时间的天、小时、分钟和秒，并将时间更新到页面上。
``` html
<h1></h1>
<script>
    var h1 = document.querySelector("h1");
    var target = new Date("2017-8-5 22:30");
    var targetTime = target.getTime();
    var ms;
    function getTimeNow(){      
        var now = new Date();
        var nowTime = now.getTime();
        ms = targetTime - nowTime;
        var time = getResultTime(ms);
        var timeResult = time.days + "天" + time.hours + "小时" + time.minutes + "分钟" + time.seconds + "秒";
        h1.innerHTML = timeResult;
    }

    setInterval(getTimeNow,1000);

    function getResultTime(ms){
        var days = Math.floor(ms / (24 * 60 * 60 * 1000));  
        var ms1 = ms % (24 * 60 * 60 * 1000); 
        var hours = Math.floor(ms1 / (60 * 60 * 1000)); 
        var ms2 = ms % (60 * 60 * 1000); 
        var minutes = Math.floor(ms2 / (60 * 1000)); 
        var ms3 = ms % (60 * 1000); 
        var seconds = Math.floor(ms3 / 1000); 
        return {                               
            days:days,
            hours:hours,
            minutes:minutes,
            seconds:seconds
        }
    }
    
</script>
```


### 正则表达式概述
正则表达式用于匹配字符串，例如我们想验证某一个字符串是否为邮箱格式，可以使用正则表达式判断；我们希望特换一片文章中的所有英文字母，可以使用正则表达式；我们想截取一片文章中的某些内容，也可以使用正则表达式。

正则表达式对象RegExp是JavaScript中的内置对象，我们可以像创建数组一样创建它。

``` js
var arr = new Array();   //创建数组
var reg = new RegExp();  //创建正则表达式
```

在开发中，我们一般用简写的方法创建正则表达式，同样和数组比较，代码如下

``` js
var arr = [1,2,3];   //创建数组
var reg = /123/;     //创建正则表达式
```


### 正则表达式语法
正则表达式可以用来匹配字符串，我们可以把正则表达式看做是一种规则，如果字符串中的内容符合这种规则，就会匹配，如果不符合这个规则，就不会匹配。
``` js
var reg = /123/;  //创建了一个正则表达式，这个正则表达式可以匹配字符串"123"
var str = "123";  //创建字符串"123"
console.log(reg.test(str));  //test方法可以测试字符串是否成功匹配，匹配返回true，不匹配返回false
```
我们可以看到程序在控制台输出了true，因为reg定义的时候就是为了匹配字符串123的。我们再来看下面的例子
``` js
var reg = /123/;
var str = "012345";
console.log(reg.test(str));  //仍然返回true
```
我们将字符串改成了"12345"，返回结果仍然返回true，这是因为我们定义的正则表达式可以匹配任何包含"123"的字符串，为了证实这个说法，我们可以使用exec方法来输出匹配的内容
``` js
var reg = /123/;
var str = "012345";
console.log(reg.exec(str)); //exec方法返回一个数组，数组中包含匹配的内容，如果未匹配，返回null
```
这段代码在控制台输出了一个数组，数组的第一个元素是匹配的内容，大家可以看到匹配的内容是"123"，数组还带有两个属性，index表示从字符串中第几个字母开始匹配，input表示匹配的字符串的值。

有的时候，我们希望我们写的正则表达式只能匹配"123"，如果是字符串包含"123"页不匹配，如果希望这样的话，我们需要改进我们的正则表达式

``` js
var reg = /^123$/;  //^表示开头，$表示结尾，两个符号之间是匹配的内容
var str = "012345";
console.log(reg.exec(str));
```
这样就可以只能匹配字符串"123"，但是如果正则表达式是直接把要匹配的内容写在正则表达式里，那意义也不是很大，接下来我们用正则表达式强大的语法来匹配各种字符串。

* 设定匹配范围
正则表达式可以通过[]设定匹配的范围,代码如下
``` js
var reg = /[123]/;  //匹配123中的任意一个字符
var str = "02468";  
console.log(reg.exec(str));
```
通过指定范围，正则表达式成功匹配了字符串中的数字2。

* 匹配数字
正则表达式可以在匹配范围中定义[0-9]来设定匹配数字
``` js
var reg = /[0-9]/;  //匹配一位数字
var str = "02468";  
console.log(reg.exec(str));
```
虽然字符串中都是数字，但是一个[]只能表示匹配一位数字，所以这里匹配的是0

* 匹配字母
正则表达式可以在匹配范围中定义[a-z]来设定匹配字母
``` js
var reg = /[a-z]/;  //匹配一位字母
var str = "012345abcde";  
console.log(reg.exec(str));
```
与匹配数字类似，上面的正则表达式可以匹配一位字母。

* 匹配多位
上面的匹配内容匹配的都是一位数字或字母，我们可以通过+来指定匹配多位
``` js
var reg = /[a-z]+/;  //匹配多位字母
var str = "012345abcde";  
console.log(reg.exec(str));
```
上面的代码表示匹配多位字母，所有abcde都成功的被匹配

* 匹配指定位数
有的时候我们需要匹配指定位数的字符，可以通过{}指定匹配的位数
``` js
var reg = /[a-z]{3}/;  //匹配3位字母
var str = "012345abcde";  
console.log(reg.exec(str));
```


下面我们来定义一个正则表达式来匹配一个邮箱格式的字符串,我们先来确定一下邮箱的格式：
* 5~12位的数字字母下划线开头
* 后面接@
* 后面接2~5位的数字和字母
* 后面接.
* 后面接com
``` js
var reg = /^[a-zA-Z0-9\_]{5,12}\@[a-zA-Z0-9]{2,5}\.com$/; 
var str = "test123@qq.com";    //邮箱  
console.log(reg.exec(str));
```
很多特殊符号在正则表达式都有特殊含义，为了取消它的特殊含义，我们需要在特殊符号之前加“\”将其转义。、

### 表单验证
通过上面的学习，我们已经对正则表达式有了初步的了解，下面我们来实现一个表单验证邮箱的功能，验证通过或者不通过，都要在文本框后面输出结果。
``` html
<input type="text">
<span></span>
<script>
    var input = document.querySelector("input");
    var span = document.querySelector("span");
    var reg = /^[a-zA-Z0-9\_]{5,12}\@[a-zA-Z0-9]{2,5}\.com$/; 
    input.onblur = function(){
        if(reg.test(this.value)){
            span.innerHTML = "验证通过";
        }else{
            span.innerHTML = "验证失败";
        }
    }
</script>
```