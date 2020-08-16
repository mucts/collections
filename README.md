<p align="center"><img src="https://images.mucts.com/image/exp_def_white.png" width="400"></p>
<p align="center">
    <a href="https://scrutinizer-ci.com/g/mucts/collections"><img src="https://scrutinizer-ci.com/g/mucts/collections/badges/build.png" alt="Build Status"></a>
    <a href="https://scrutinizer-ci.com/g/mucts/collections"><img src="https://scrutinizer-ci.com/g/mucts/collections/badges/code-intelligence.svg" alt="Code Intelligence Status"></a>
    <a href="https://scrutinizer-ci.com/g/mucts/collections"><img src="https://scrutinizer-ci.com/g/mucts/collections/badges/quality-score.png" alt="Scrutinizer Code Quality"></a>
    <a href="https://packagist.org/packages/mucts/collections"><img src="https://poser.pugx.org/mucts/collections/d/total.svg" alt="Total Downloads"></a>
    <a href="https://packagist.org/packages/mucts/collections"><img src="https://poser.pugx.org/mucts/collections/v/stable.svg" alt="Latest Stable Version"></a>
    <a href="https://packagist.org/packages/mucts/collections"><img src="https://poser.pugx.org/mucts/collections/license.svg" alt="License"></a>
</p>

# Collection #

> `Collection`类提供一个便捷的操作数组的封装。

## 创建一个新的集合 ##

一个集合可以使用`collect()`帮助函数基于一个数组被创建 或者直接通过`MuCTS\Collections\Collection`类实例化。

- 一个非常简单的使用`collect()`帮助函数的示例：

```php
$newCollection = collect([1, 2, 3, 4, 5]);
```

- 求和 `sum()`

```php
<?php
// 例子1
collect([1,2,3])->sum();//6
// 例子2
$list = [
    ['name'=>'支付宝','money'=>'10'],
    ['name'=>'微信','money'=>'10.3'],
];
collect($list)->sum('money');//20.3
```

- 返回集合中所有的唯一数据项`unique()`

```php

$collection = collect([1, 1, 2, 2, 3, 4, 2]);
$unique = $collection->unique();
$unique->values()->all();// [1, 2, 3, 4]

// 返回的集合保持原来的数组键，在本例中我们使用values方法重置这些键为连续的数字索引。
// 处理嵌套数组或对象时，可以指定用于判断唯一的键

$collection = collect([
    ['name' => 'iPhone 6', 'brand' => 'Apple', 'type' => 'phone'],
    ['name' => 'iPhone 5', 'brand' => 'Apple', 'type' => 'phone'],
    ['name' => 'Apple Watch', 'brand' => 'Apple', 'type' => 'watch'],
    ['name' => 'Galaxy S6', 'brand' => 'Samsung', 'type' => 'phone'],
    ['name' => 'Galaxy Gear', 'brand' => 'Samsung', 'type' => 'watch'],
]);
 
$unique = $collection->unique('brand');

/*
    [
        ['name' => 'iPhone 6', 'brand' => 'Apple', 'type' => 'phone'],
        ['name' => 'Galaxy S6', 'brand' => 'Samsung', 'type' => 'phone'],
    ]
*/

// 你还可以指定自己的回调用于判断数据项唯一性：
 
$unique = $collection->unique(function ($item) {
    return $item['brand'].$item['type'];
});
 
$unique->values()->all();
 
/*
    [
        ['name' => 'iPhone 6', 'brand' => 'Apple', 'type' => 'phone'],
        ['name' => 'Apple Watch', 'brand' => 'Apple', 'type' => 'watch'],
        ['name' => 'Galaxy S6', 'brand' => 'Samsung', 'type' => 'phone'],
        ['name' => 'Galaxy Gear', 'brand' => 'Samsung', 'type' => 'watch'],
    ]
*/
```
