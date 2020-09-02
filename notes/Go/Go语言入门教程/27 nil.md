# 27 nil

range、len、append等内置函数都可以正常处理值为nil的slice。


接口变量的值为nil，只要它的类型不是nil，那么该变量就不等于nil。
```go
var v interface{}
fmt.Printf("%T %v %v\n", v, v, v == nil)

var p *int
v = p
fmt.Printf("%T %v %v\n", v, v, v == nil)

// <nil> <nil> true
// *int <nil> false
```


