# JS 对象遍历方法对比---for...in/for...of/forEach

## for...in
> * 作用：用于遍历对象可枚举属性的属性名（包括继承来的属性和用户添加的额外属性，但不包括数组的length属性）
> * 对于数组对象，`for...in` 实际遍历的是数组的index，而并非数组的value
> * `for...in` 不适用与遍历 `Map` 和 `Set` 对象

## for...of(ES6新增方法)
> * 作用：用于遍历可迭代对象（`Array,Map,Set,String,TypedArray,arguments,NodeList`）的属性名称，只包含对象本身定义时的属性（包括继承来的属性但不包括用户后期添加的额外属性）
> * 对于 `Array` 对象和 `Set` 对象，`for...of` 遍历的是他们实际的value值
> * 对于 `Map` 对象，`for...of` 遍历的是对象中的每一个键值对

## forEach
> * `forEach()` 是数组的一个方法，用于遍历数组的每一项，并对每一项执行一个 `callback` 函数；`forEach()` 没有返回值，返回值总是 `undefined`。
> * 对于 `Array` 对象，`callback` 函数为：`function(element,index,arr){}`；
> * 对于 `Set` 对象，`callback` 函数为：`function(element,sameElement,set){}`；因为它没有 `index` 值，所以回调函数的前两个参数都是元素本身。
> * 对于 `Map` 对象，`callback` 函数为：`function(key,value,map){}`
> * `forEach` 中不能中断循环(使用break语句或使用return语句)