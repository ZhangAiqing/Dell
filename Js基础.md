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
