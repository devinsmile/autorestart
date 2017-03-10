```
package main

import (
	"fmt"
	"time"

	"github.com/i19/autorestart"
)

func worker() {
	for i := 0; i <= 3; i++ {
		time.Sleep(time.Second)
		fmt.Println(i)
	}
	panic("Panicing ... ")
}

func main() {
	autorestart.Run(worker)
}
```

```
go run main.go
Startting ..... 
0
1
2
3
Panic: Panicing ... 
Startting ..... 
0
1
2
3
Panic: Panicing ... 
Startting ..... 
0
1
2

```
