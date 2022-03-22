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
3. `typeof`注意事项
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

#### propertyIsEnumerable()
propertyIsEnumberable()是hasOwnProperty()的增强版，这个方法的用法与hasOwnProperty()相同，但当检查属性是自有属性（非继承）且这个属性是可枚举的，才会返回true

## splice和slice区别
#### slice:截取
- 截取数组为主，也可以截取字符串
- 返回新的数组，也含截取的元素
- 不改变原数组
#### splice:数组增删改
- 只能对数组进行增删改，字符串无效
- 返回新的数组，内容是被删减的元素
- 会改变原数组

## ==和===区别
- ===是严格相等，要求数据类型和值都要相等；==只需要值相等
- ==会发生隐式转换，===不会发生隐式类型转换

## 构造函数和普通函数的区别
## 类数组和数组区别
> 类数组：类数组对象，就是指可以通过索引属性访问元素并且拥有`length`属性的对象
> 区别：
 1. 类数组不具备数组的方法（splice，split，push）
 2. 类数组是一个普通对象，数组类型是Array
> 为什么设置类数组：类数组对象的设计目的更多是只让你**遍历和访问下标**，而不是取添加或删除元素

## null与undefined的区别
- null表示一个“无”的对象，也就是该初不应该有值；而且undefined表示未定义
- 在转换为数字时结果不同，Number(null)为0，而Number(undefined)为NaN
#### 使用场景上
1. null:
   + 作为函数的参数，表示该函数的参数不是对象
   + 作为对象原型链的终点
2. undefined:
   + 声明变量未赋值，等于undefined
   + 调用函数时，未提供参数值，该参数等于undefined
   + 对象没有赋值属性，该属性的值为undefined
   + 函数没有返回值时，默认返回undefined

## a.b.c.d 和 a['b']['c']['d']，哪个性能更高？
[参考](https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/111)














