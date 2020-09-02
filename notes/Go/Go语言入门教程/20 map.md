# 20 map

map不会被复制，`delete()`函数用于删除集合的元素，参数为 map 和其对应的 key。
Go语言没有提供set集合，可以使用map代替set。
```go
temperature := map[string]int{
    "Earth": 15,
    "Mars":  -65,
}

temp := temperature["Earth"]
fmt.Printf("On average the Earth is %v° C.\n", temp)

temperature["Earth"] = 16
temperature["Venus"] = 464

fmt.Println(temperature)

moon := temperature["Moon"]
fmt.Println(moon)

if moon, ok := temperature["Moon"]; ok {
    fmt.Printf("On average the is %v° C.\n", moon)
} else {
    fmt.Println("Where is the moon?")
}

// On average the Earth is 15° C.
// map[Earth:16 Mars:-65 Venus:464]
// 0
// Where is the moon?
```
## 使用make()对map进行预分配
除非你使用复合字面值来初始化map，否则必须使用内置的make()来为map分配空间。
创建map时，make()可接受一个或两个参数，第二个参数用于指定key的数量。
使用make()创建的map的初始长度为0。
