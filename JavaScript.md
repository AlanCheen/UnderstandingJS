# JavaScript



## 变量 作用域

全局变量实际上被绑定到`window`的一个属性。
```
var name = "程序亦非猿";
alert(window.name);//程序亦非猿
```

JS 的函数也是其实也是`window`的一个变量，比如`alert()`。

#### 名字空间

由于全局变量会绑定到`window`上，所以当不同的 JS文件拥有同名的方法时，就会造成命名冲突。

减少冲突的一个方法是把自己的所有变量和函数全部绑定到一个全局变量中。

```
var MY = {};
MY.foo = function{};
```


this 指向 对象 或 window,要搞清楚
that 可以保存 this 避免指向问题

装饰器

利用函数的本身方法`apply()`，我们还可以动态改变函数的行为。
```
foo.apply(obj,arg[])
```


## 函数


NOTE：单独调用函数，比如 getAge()，此时，该函数的this指向全局对象，也就是window. 要十分小心。

## 高阶函数

可以接受函数作为参数的叫做 高阶函数。

```
function add(x, y, f) {
    return f(x) + f(y);
}
```


### 常用操作符 map/reduce/filter/sort

https://research.google.com/archive/mapreduce.html

map  将一个函数作用于数组的每一个元素(自己的理解)。

```
//平方
function pow(x) {
    return x * x;
}

var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
arr.map(pow); // [1, 4, 9, 16, 25, 36, 49, 64, 81]

```

reduce  Array的reduce()把一个函数作用在这个Array的[x1, x2, x3...]上，这个函数必须接收两个参数，reduce()把结果继续和序列的下一个元素做累积计算

```
var arr = [1, 3, 5, 7, 9];
arr.reduce(function (x, y) {
    return x + y;
}); // 25
```

filter 使用一个函数作用于数组的元素，过滤掉不符条件的元素，保留符合条件的元素(return true的保留，false的放弃)。

删掉偶数，只保留奇数：

```
var arr = [1, 2, 4, 5, 6, 9, 10, 15];
var r = arr.filter(function (x) {
    return x % 2 !== 0;
});
r; // [1, 5, 9, 15]
```

sort 排序 

- 默认把所有元素先转换为String再排序；
- 字符串根据ASCII码进行排序；
- sort()方法会直接对Array进行修改，它返回的结果仍是当前Array。

所以 '10'排在'2'的前面 ，小写字母`a`排在大写字母`A`的后面，因为`a`的ASCII码在`A`之后。

sort 也是高阶函数，所以自定义排序方法。

```
var arr = [10, 20, 1, 2];
arr.sort(function (x, y) {
    if (x < y) {
        return -1;
    }
    if (x > y) {
        return 1;
    }
    return 0;
}); // [1, 2, 10, 20]
```

### 闭包 Closure

自我感觉 闭包是定义在函数内部的函数。

高阶函数除了可以接受函数作为参数外，还可以把函数作为结果值返回。

返回闭包时牢记的一点就是：返回函数不要引用任何循环变量，或者后续会发生变化的变量，这时要用 `let`。

理解闭包： http://www.ruanyifeng.com/blog/2009/08/learning_javascript_closures.html


### 箭头函数 Arrow Function

ES6新增，箭头函数相当于匿名函数，并且简化了函数定义。


```
x => x*x;
```

相当于

```
function(x){
	return x*x;
}
```

无参，多个参数，多行代码,返回对象：

```
()=>3;

(x,y)=>{
	if(x>y){
		return x-y;
	}else{
		return x+y;
	}
}

(x,y,...rest)=>{}

(x)=>({foo:x})

```

语法感觉跟 lambda 表达式差不多。

NOTE：箭头函数内部的this是词法作用域，由上下文确定。

箭头函数完全修复了this的指向，this总是指向词法作用域，也就是外层调用者obj。

就不会出现指向 obj 还是 window的问题了。

由于this在箭头函数中已经按照词法作用域绑定了，所以，用call()或者apply()调用箭头函数时，无法对this进行绑定，即传入的第一个参数被忽略。

### generator

generator（生成器）是ES6标准引入的新的数据类型。一个generator看上去像一个函数，但可以返回多次。

generator由function*定义（注意多出的*号），并且，除了return语句，还可以用yield返回多次。


## 对象



用 typeOf 获取对象类型 ，相当于 Java的 instanceOf 吧。


```
typeof 123; // 'number'
typeof NaN; // 'number'
typeof 'str'; // 'string'
typeof true; // 'boolean'
typeof undefined; // 'undefined'
typeof Math.abs; // 'function'
typeof null; // 'object'
typeof []; // 'object'
typeof {}; // 'object'
```

用 typeOf 不能区分 null，数组[]，对象{}。

包装对象：Number String Boolean (不推荐用)

规则：

- 不要使用new Number()、new Boolean()、new String()创建包装对象；

- 用parseInt()或parseFloat()来转换任意类型到number；

- 用String()来转换任意类型到string，或者直接调用某个对象的toString()方法；

- 通常不必把任意类型转换为boolean再判断，因为可以直接写if (myVar) {...}；

- typeof操作符可以判断出number、boolean、string、function和undefined；

- 判断Array要使用Array.isArray(arr)；

- 判断null请使用myVar === null；

- 判断某个全局变量是否存在用typeof window.myVar === 'undefined'；

- 函数内部判断某个变量是否存在用typeof myVar === 'undefined'。


## RegExp

表达式 。


## JSON

JSON是JavaScript Object Notation的缩写，它是一种数据交换格式。

UTF-8 字符串规定必须用双引号"",Object的键也必须用双引号""。

- number：和JavaScript的number完全一致；
- boolean：就是JavaScript的true或false；
- string：就是JavaScript的string；
- null：就是JavaScript的null；
- array：就是JavaScript的Array表示方式——[]；
- object：就是JavaScript的{ ... }表示方式。


序列化：JSON.stringify(boject); //可以把对象转成json 

JSON.stringify(boject, null, '  '); // 输出带缩进 更好看

第二个参数用于控制如何筛选对象的键值，如果我们只想输出指定的属性，可以传入Array：

指定只输出指定的属性 name skills ：

```JSON.stringify(xiaoming, ['name', 'skills'], '  ');```

还可以传入 convert 处理数据：

JSON.stringify(xiaoming, convert, '  ');


反序列化 ： JSON.parse() 可以把它变成一个JS对象。



