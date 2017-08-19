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

#### 集合类型
一组同类型的值的组合,根据组合的整体特性分为:
 - [x] 有序可重复 - 数组(Array)
```shell
#定义Array类型或[类型]
let array : [Int]

#创建一个有默认值的数组
array = [Int](repeatElement(3,count:5)) => [3,3,3,3,3]

#创建一个有序范围Int数组,Array(起始值...终止值)
let array2 = Array[1...5] => [1,2,3,4,5]

#普通创建数组:[值1,值2,值n]
let places = ["beijing","baoding","hebei"]

#元素计数:count,空否:isEmpty
places.count => 3
places.isEmpty => true

#添加元素append,添加同一个类型数组 +=
places.append("shijiazhuang")
let haiwai = ["NewYork","London"]
places += haiwai  => ["beijing","baoding","hebei","NewYork","London"]

#插入insert:Array.insert("值", at: 下标)
#移除remove:Array.remove(at:下标)

```
 - [x] 无序不重复 - Set
```shell
#定义
```
 - [x] 无序可重复,但每个值有唯一的键 - 字典(Dicionary)
```shell
#定义:Dicionary<键类型,值类型>或[键类型:值类型]
let temp = ["hebei":"baoding","zhongguo","beijing"]

#元素计数:count,空否:isEmpty
#添加或更新:字典变量[键]=值
```
批量处理集合中元素,可以使用for in循环

#### 控制流
用来检查和运算各种条件和逻辑的组合,控制APP的运行流向
 - 循环:for-in,while
```shell
var places = [1,3,5,7]
for s in place{}
for i in 1...100{} => 从1遍历到100
while i < 100{}
```
 - if
 - 早退语句guard else
 - 退出 break,continue
 - switch
#### 函数
形式:func 函数名(参数1:类型,参数2:类型) -> 返回结果类型 {函数体}
```shell
func add(a:Int, b:Int) -> Int{
  return a+b
}

#多返回值(使用元组)
func maxMin() -> (Int, Int){
  return (Int.min, Int.max)
}
```
> 函数类型
函数类型:包含参数和返回类型的简写形式,可以像普通变量那样使用,一般用于函数式编程
形式:(Int, Int) -> Int
```shell
func calculate(x:Int, y:Int, method:(Int, Int) -> Int) -> Int{
  return method(x, y)
}
func add(x:Int, y:Int) -> Int{
  return x + y
}
calculate(x:3, y:4, method:add)  =>  7
```

## 面向对象
用生物学的角度把变量和函数有机组织起来,叫面向对象编程
- 基因:属性和方法(变量和函数)
- 繁殖:完全克隆和基因交换(继承和变异)
- 术语:结构体(struct)和类(class),swift3推荐自己定义的对象使用结构体

#### 属性
属性是一个结构体/类/枚举关联的变量
 - 实例属性:实例化后才能使用
```shell
class 角色 {
  let id = "20170817"
  var money = 0
}
```
 - 计算属性:由其他属性计算得出的,由getter和setter组成
   - getter获取器(必须):描述属性如何计算及返回语句,形式:get{语句和返回}
   - sette设置器(可选):有新值(newValue)后如何影响其他属性,形式:set{语句}
```shell
struct 坐标 {
  var x = 0, y = 0
}

enum 移动方式 {
  case 走
  case 跑
  case 骑
  case 传送
}

class 法师: 角色 {
  var 人物坐标 = 坐标()
  var 人物移动方式 = 移动方式.走
  var 当前坐标: 坐标 {
    get {
      switch 人物移动方式 {
        case .走:
          人物坐标.x += 1
          人物坐标.y += 1
        case .跑:
          人物坐标.x += 3
          人物坐标.y += 3
        case .骑:
          人物坐标.x += 10
          人物坐标.y += 10
        case .传送:
          人物坐标.x += 1000
          人物坐标.y += 1000
      }
      return 人物坐标
    }
    set {
      人物坐标 = newValue
    }
  }
}
var 法师1 = 法师
法师1.当前坐标  =>  x1, y1
法师1.人物移动方式 = .跑
法师1.当前坐标  =>  x4, y4
法师1.人物移动方式 = .传送
法师1.当前坐标  =>  x1004, y1004

#计算属性的setter方法,影响其他属性
法师1.当前坐标 = 坐标(x: 2000, y: 90)
法师1.人物坐标  =>  x2000, y90
```
- 属性监视器:对属性值的变化进行响应
  - willSet:事前响应,新值newValue
  - didSet:事后响应,旧值oldValue
```shell
class 经验 {
  var 总经验 = 0 {
    willSet {
      print("当前总经验是:\(newValue)!")
    }
    didSet {
      print("增加了\(总经验 - oldSet)点经验!")
    }
  }
}
var 经验1 = 经验
经验1.总经验 = 1000  =>  当前经验是1000,增加了1000
经验1.总经验 = 3000  =>  当前经验是3000,增加了2000
经验1.总经验 = 8000  =>  当前经验是8000,增加了5000
```
#### 类型属性
属于类型固有的,实例不能调用
对于类,计算型的类型属性,前面加关键字class可被子类重写override
```
class 生命体 {
  var 遗传方式: String {
    return "RNA"
  }
}
生命体.遗传方式  =>  不能调用

class 生命体 {
  static var 遗传方式: String {
    return "RNA"
  }
}
生命体.遗传方式  =>  RNA

#父类属性覆盖子类
class Human: 生命体 {
  var 遗传方式: String {
    return "DNA"
  }
}
Human.遗传方式  =>  RNA  父类属性覆盖子类

#解决办法
class 生命体 {
  class var 遗传方式: String {
    return "RNA"
  }
}
class Human: 生命体 {
  override class var 遗传方式: String {
    return "DNA"
  }
}
Human.遗传方式  =>  DNA
```
 - 结构体和枚举,关键字static
```shell
struct 逛街 {
  static let 品牌 = "UNICIO"
  static let 网站 = "http://tmall.com?cate="
  var cate = ""

  var shareUrl : String {
    return 逛街.网站 + cote
  }
}
逛街.品牌  => "UNICIO"
let 逛淘宝 = 逛街(cate:"seaFood")
逛淘宝.shareUrl  =>  http://tmall.com?cate=seaFood
```
#### 实例方法
方法是一个类/结构体/枚举关联的函数,分为实例方法和类型方法
 - 实例方法
 定义和使用:与函数相似,self属性:引用实例自身,通常可以不写
```shell
enum Monster : Int {
    case sheep = 10,
    cat = 50,
    snak = 100
}

struct ExpTimes {
    var open = false
    var times = 1
}

class RmbPlayer{
    var exp = 0
    var expTimes = ExpTimes()
    
    func idle() {
        exp += 500
        print("挂机成功1次！总经验为\(exp)")
    }
    
    func kill (monster: Monster, expTimes: Int) {
        exp += (monster.rawValue * expTimes)
        
        print("当前总经验为\(exp)")
    }
}

var xiaobo = RmbPlayer()
xiaobo.idle()  =>  挂机成功1次！总经验为500
xiaobo.kill(monster:Monster.cat, expTimes: 2)  =>  当前总经验为600

var dabo = RmbPlayer()
dabo.idle()  =>  挂机成功1次！总经验为500

```