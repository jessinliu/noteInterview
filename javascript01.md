## ES
> ES全称ECMAScript，ECMAScript是ECMA制定的标准化脚本语言

## 动态类型和数据类型
#### 数据类型
1. 基本数据类型：undefined、boolean、number、string、biglnt、symbol、null(返回object)
2. 引用数据类型：Object（Array类型,Function类型,RegExp类型,Object类型，Date类型，Math类型）

## 数据结构
> 引用数据类型可用于**数据结构**：new Object，new Array，new Map，new Set，new WeakMap，new WeakSet，new Date，和几乎所有通过 new keyword

## 判断数据类型的方法
#### typeof
> 优点：区分基本数据类型
> 缺点：不能将Object、Array和Null区分，这都返回Object
1. `typeof`的作用？
   区分基本数据类型，科返回7种数据类型：`number、string、boolean、undefined、object、function`，以及es6新增`symbol`
2. `typeof`能正确区分数据类型吗？
   不能。对于原始类型，除了`null`都能正确判断；对于引用类型，除了`function`都不能，都会返回`"Object"`
3. `typeif`注意事项
   + typeof 返回值为 string格式
   + typeof 为定义的变量不会报错， 返回undefined
   + typeof(null)-> "object"
   + typeof(NaN) -> "number" 

#### instanceof
> 优点：能区分Array，object，Function，适合判断自定义的类实力对象
> 缺点：number，boolean，string基本数据类型不能判断
1. `instanceof`判断对象的原型链上是否存在构造函数的原型。只能判断引用类型
2. `instanceof`常用来判断`A`是否为`B`实例

#### Object.prototype.toString.call()
> 优点：精准判断数据类型
> 缺点：写法复杂，需要进行封装

## ==的隐式转换规则
1. `==`只需要值相等，无需类型相等；`nulll,undefined`在`==`下互相等且自身等

## number能表示的整数的最大范围
1. 安全的整数范围：15位数以下，最大的整数是Number.MAX_SAFE_INTEGER(9007199254740991)，最小的整数是Number.MIN_SAFE_INTEGER(-9007199254740991)
2. ID很多都是超出这个范围的，所以最好是string类型

## 2.toFixed()
> (2).toFixed()

## 查询某个对象是否有某个属性的方法
#### 使用in关键字
该方法可以判断对象的自有属性和继承来的属性是否存在
#### 使用对象的hasOwnProperty()方法
该方法只能判断自有属性是否存在，对于继承属性会返回false
#### 使用undefined判断
自有属性和继承属性均可判断
```
var o = {x:1}
o.x!==undefined;//true
o.y!==undefined;//false
o.toString!==undefined;//true
```
> 该方法存在一个问题，如果属性的值就是undefined的话，该方法不能返回想要的结果，如下：
```
var o = {x:undefined}
o.x!==undefined;//false,属性存在，但是值是undefined
o.y!==undefined;//false
o.toString!==undefined;//true

```

#### 在条件语句中判断
```
var o = {}
if(o.x) o.x += 1 // 如果x是undefined,null,false," ",0或NaN,它将保持不变

```

#### propertyIs





















