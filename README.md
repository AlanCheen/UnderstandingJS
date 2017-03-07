# UnderstandingJS


全栈之路，学习前端！


基础知识

html css js dom bom 

div p h1-h6 img span ul dl ol li 等


JS 基础语法知识 

ES6 JSX React Redux Webpack


html+css+js 实战



[CSS](CSS.md)   
[HTML](HTML.md)   


## JS 知识点记录


`多行字符串　ES６　


ＪＳ对象由键值对组成。

delete obj.proName  ; delete 删除对象的属性
‘toString’ in obj   ; in 判断是否有属性，包括继承的
obj.hasOwnProperty('proName')  判断是否有该属性，不包括继承的

//遍历对象的属性
for (var key in obj) {
    alert(key); // 'name', 'age', 'city'
}




`onclick="show(this);return false;"` ，`return false` 来拦截默认行为。