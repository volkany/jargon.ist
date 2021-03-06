---
title: async
tags:
- programlama
- golang
- thread
---

Türkçe olarak anlatmak istersek **Eşzamansız** programlama olarak tanımlanabilir. Basitçe tek bir [thread](/thread) üzerinde bir çok fonksiyonu veya isteği karşılamak mümkündür ama standart yapıda işlemler sıraya girerek görevlerini yerine getirir. Buna [SYNC](/sync) (senkron) denir. Async'de ise bu işler birbirlerinden ayrı sıraya girmeden aynı anda başlatılabilir. Her işlem bir birine bağlı olmadan bağımsız şekilde çalışır.

### Go Dilinde örnek
Goroutines kullanarak *Go Programlama Dili* nde örnek yapabiliriz. Resmi dökümanlar ve örnekler için [buraya](https://tour.golang.org/concurrency/1) bakabilirsiniz.

### ASYNC

```go
package main
import "fmt"
func main() {
 fmt.Println("1")
 fmt.Println("2")
 fmt.Println("3")
 fmt.Println("4")
 fmt.Println("5")
 fmt.Println("6")
 fmt.Println("7")
 fmt.Println("8")
 fmt.Println("9")
 fmt.Println("10")
}
```
#### Çıktı
```
1
2
3
4
5
6
7
8
9
10
```

### SYNC (Go-Routines ile)
```go
package main
import "fmt"

func main() {
    go func() {
    fmt.Println("1")
    fmt.Println("2")
    fmt.Println("3")
    }()

    fmt.Println("4")
    fmt.Println("5")
    fmt.Println("6")
    fmt.Println("7")
    fmt.Println("8")
    fmt.Println("9")
    fmt.Println("10")
}
```
#### Çıktı
```
4
5
6
1
7
8
2
9
3
10
```
