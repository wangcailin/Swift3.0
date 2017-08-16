#### 常量
```shell
let name = value
```
#### 变量
```shell
var name = value
```
#### Int和类型推断
3这样的整数,在Swift中称为`Intger`类型的值,简写`Int`
形式：var name : Int = 3 由于Swift有类型推断,类型可以省略不写
```shell
let name : Int = 3   等同于   let name = 3
```
#### 浮点型(小数)
Swift中默认浮点型是`Double`(双精度)

#### 类型安全
类型一旦定义,其类型不可更改 即:`不能给变量一个不同类型的值`
```shell
var name = 3.5 -> name = "mis" 类型错误
```

#### 元组(Tuple):定义变量的一个组合
形式(一般):`(3,'天','Swift','3.0')`
形式(前缀):`(day:3,unit:'天',lang:'Swift',ver:'3.0')`
```shell
var xyz = (1,2,3)  调取 zxy.0 value 1
var (x,y,z) = (1,2,3)
var name = (day:3,unit:'天',lang:'Swift',ver:'3.0')
    调取:name.day
```
#### 可选类型(Optional):代表变量可能有值的情况
如:用户资料的选填部分
形式:`var name : 类型?,默认是无值(nil)`
```shell
var addr : String? = "上海交通大学"
```
#### 基础操作符
 - [x] 赋值操作符 `=`
 - [x] 数学操作符 `+ - * / %`
 - [x] 组合赋值 赋值与数学操作符的组合 `+= -= *= /=`
 - [x] 比较运算符 `> >= < <=`
 - [x] 逻辑操作符 `||(或) &&(与) !(非)`

 #### 字符串和字符
  - 字符串是有序的字符集合,或者叫文本
```shell
  判断字符串是否为空
  var a = ""     a.isEmpty
```
  - String是字符串类型,Character是字符类型
```shell
var a:Character = "我"  定义一个字符
#可以对一个字符串的Characters属性进行循环,来访问其中单个字符
let c = "今天是星期日"
c.characters是个集合
for s in c.characters{
  print(s)
}
#显示效果是 今 天 是 星 期 日
```
  - 2个字符串可以通过+来连接
```shell
var a = "shell"
var b = a + "Hello word"
#向字符串添加字符用append方法
let num = "123"
a.append(num)
```
  - 通过字符串插值可以组合成一个长字符串
