# JavaScript





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

#### 高阶函数

可以接受函数作为参数的叫做 高阶函数。

```
function add(x, y, f) {
    return f(x) + f(y);
}
```


#### 常用操作符 map/reduce/filter

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




