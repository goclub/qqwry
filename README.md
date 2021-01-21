# QQWry [![Go Reference](https://pkg.go.dev/badge/github.com/xiaoqidun/qqwry.svg)](https://pkg.go.dev/github.com/xiaoqidun/qqwry)

Golang QQWry，内存操作，线程安全，支持缓存的纯真IP查询库

# 查询说明

1. 仅支持ipv4查询
1. city可能是城市，也可能是国家
2. area可能是区域，也可能是运营商

# 使用说明

```go
package main

import (
	"github.com/xiaoqidun/qqwry"
	"log"
)

func main() {
	// 从文件加载IP数据库
	if err := qqwry.LoadFile("qqwry.dat"); err != nil {
		panic(err)
	}
	// 从内存或缓存查询IP
	city, area, err := qqwry.QueryIP("1.1.1.1")
	log.Printf("城市：%s，区域：%s，错误：%v", city, area, err)
}
```

# 特别感谢

- 感谢[纯真IP库](https://www.cz88.net/)一直坚持为大家提供免费IP数据库。
- 感谢[yinheli](https://github.com/yinheli)的[qqwry](https://github.com/yinheli/qqwry)项目，为我提供纯真ip库解析算法参考。

# 授权说明

使用本类库你唯一需要做的就是把LICENSE文件往你用到的项目中拷贝一份。