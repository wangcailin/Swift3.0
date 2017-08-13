#### 常量
```
let name = value
```
#### 变量
```
var name = value
```
#### Int和类型推断
3这样的整数,在Swift中称为`Intger`类型的值,简写`Int`

形式：var name : Int = 3 由于Swift有类型推断,类型可以省略不写
```
let name : Int = 3   等同于   let name = 3
```
#### 浮点型(小数)
Swift中默认浮点型是`Double`(双精度)

### 类型安全
类型一旦定义,其类型不可更改 即:`不能给变量一个不同类型的值`
```
var name = 3.5 -> name = "mis" 类型错误
```

#### 元组(Tuple):定义变量的一个组合
形式(一般):`(3,'天','Swift','3.0')`

形式(前缀):`(day:3,unit:'天',lang:'Swift',ver:'3.0')`
```
var xyz = (1,2,3)  调取 zxy.0 value 1
var (x,y,z) = (1,2,3)
var name = (day:3,unit:'天',lang:'Swift',ver:'3.0')
    调取:name.day
```
#### 可选类型(Optional):代表变量可能有值的情况
如:用户资料的选填部分

形式:`var name : 类型?,默认是无值(nil)`
```
var addr : String? = "上海交通大学"
```
