# G o 最 主 要 特 性 ：


***
*    1.自动垃圾回收  

***
*    2.更丰富的内置类型
***
*    3.函数多返回值
***
*    4.错误处理
***
*    5.匿名函数和闭包
***
*    6.类型和接口
***
*    7.并发编程
***
*    8.反射
***
*    9.语言交互性
***

# G o 中 命 名 规 范 :
***
    1）首字符可以是任意的Unicode字符或者下划线
    2）剩余字符可以是Unicode字符、下划线、数字
    3）字符长度不限

***

# G o 中 25 个 关 键 字 ：
***
    break        default      func         interface    select
    case         defer        go           map          struct
    chan         else         goto         package      switch
    const        fallthrough  if           range        type
    continue     for          import       return       var
***


# G o 中 37 个 保 留 字 :
***
    Constants:    true  false  iota  nil

    Types:        int  int8  int16  int32  int64  
                  uint  uint8  uint16  uint32  uint64  uintptr
                  float32  float64  complex128  complex64
                  bool  byte  rune  string  error

    Functions:    make  len  cap  new  append  copy  close  delete
                  complex  real  imag
                  panic  recover
***

# G o 中 可 见 性 :
***
    1）声明在函数内部，是函数的本地值，类似private
    2）声明在函数外部，是对当前包可见(包内所有.go文件都可见)的全局值，类似protect
    3）声明在函数外部且首字母大写是所有包可见的全局值,类似public
***

# G o 中 声 明 方 式 :
    var     （声明变量）
    const   （声明常量）
    type    （声明类型）
    func    （声明函数）


# G o 中 内 置 类 型 :

## 值类型：

***
    bool
    int(32 or 64), int8, int16, int32, int64
    uint(32 or 64), uint8(byte), uint16, uint32, uint64
    float32, float64
    string
    complex64, complex128
    array
***

## 引用类型：(指针类型)
    slice   -- 序列数组(最常用)
    map     -- 映射
    chan    -- 管道
***

## 内置函数:
    append  		-- 用来追加元素到数组、slice中,返回修改后的数组、slice
    close   		-- 主要用来关闭channel
    delete    		-- 从map中删除key对应的value
    panic    		-- 停止常规的goroutine  （panic和recover：用来做错误处理）
    recover 		-- 允许程序定义goroutine的panic动作
    imag    		-- 返回complex的实部   （complex、real imag：用于创建和操作复数）
    real    		-- 返回complex的虚部
    make    		-- 用来分配内存，返回Type本身(只能应用于slice, map, channel)
    new        		-- 用来分配内存，主要用来分配值类型，比如int、struct。返回指向Type的指针
    cap        		-- capacity是容量的意思，用于返回某个类型的最大容量（只能用于切片和 map）
    copy    		-- 用于复制和连接slice，返回复制的数目
    len        		-- 来求长度，比如string、array、slice、map、channel ，返回长度
    print、println 	-- 底层打印函数，在部署环境中建议使用 fmt 包

## 内置接口error:
###### 只要实现了Error()函数，返回值为String的都实现了err接口
    type error interface { 
        Error()    String
    }

