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
