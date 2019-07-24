#### slice(),substr(),substring()三种提取字符串
#### 1、slice()

```
slice()方法可提取字符串的某个部分，并以新的字符串返回被提取的部分。

语法：str.slice(start,end)，截取str从start到end的所有字符（包含起始位置，不包含结束位置）

说明：start和end都可以是负数，如果是负数，就从字符串的尾部开始算起，例如-1就是最后一个字符，-2就是倒数第二个字符，一次类推

如果未指定end参数，则截取从 start 到原字符串结尾的字符串
```

```
例子：
var str = 'abcde leodonna'
   console.log(str.slice(1,8))//bcde le
   console.log(str.slice(1,-2))//bcde leodon
   console.log(str.slice(-4,-1))//onn
   console.log(str.slice(8))//odonna

```
#### 2、substring() 

```
substring()方法用于提取字符串中介于两个指定小标之间的字符

语法：str.substring(start,end) 截取str从start到end的所有字符（包含起始位置,但不包含结束位置)

说明：两个参数都必须是非负整数，如果参数start与end相等，那么该方法返回的就是一个空字符串，如果start比end大，那么该方法在提取字符串之前会先交换这两个参数

如果未指定end参数，则截取从start到原字符串结尾的字符串
```

```
例子：
var str = 'abcde leodonna'
   console.log(str.substring(1,8))//bcde le
   console.log(str.substring(4))//e leodonna
   console.log(str.substring(4,1))//bcd
```
