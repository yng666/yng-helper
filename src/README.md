# YngHelper
基于PHP7.1+

## 安装
```sh
composer require yng/yng-helper
```


#### 字符串用法
```php
use Yng\Helper\Str;
// 检查字符串中是否包含某些字符串
Str::contains($haystack, $needles)

// 检查字符串是否以某些字符串结尾
Str::endsWith($haystack, $needles)

// 获取指定长度的随机字母数字组合的字符串
Str::random($length = 16)

// 字符串转小写
Str::lower($value)

// 字符串转大写
Str::upper($value)

// 获取字符串的长度
Str::length($value)

// 截取字符串
Str::substr($string, $start, $length = null)
```



#### 数组用法
```php
use Yng\Helper\Arr;
//模型查询的结果也为真
Arr::accessible($value);

Arr::add($array, $key, $value);
//如下操作
$arr  = [];
$arr = Arr::add($arr,'name.66.aaa','yngphp'); //本行结果$arr['name'][66]['aaa'] = 'yngphp'
Arr::add($arr,'name','yngphp_哈哈哈');//本行不会产生影响,因为'name'已存在.


// 将数据集管理类转换为数组
Arr::collapse($array);


// 排列数组组合
$arr = Arr::crossJoin(['dd'],['ff'=>'gg'],[2],[['a'=>'mm','kk'],'5']);//上面行没有什么意义,但是可以看到该函数的作用,数组索引被忽略,数组得值被全部组合
$arr = Arr::crossJoin(['a','b','c'],['aa','bb','cc','dd']);//这一行可以看到组合的效果,返回一个二维数组,第二维每个数组是的给定值排列,比如(a,aa),(a,bb),(a,cc)...直到(c,dd)

```

更多的用法请参考源码