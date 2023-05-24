# Cli

Cli一个帮助用户快速建立命令行程序的框架

More info [Github](https://github.com/yz-im/cli)

## 快速开始
### 依赖
- Go 1.13 or above
### 安装
```go
go get github.com/yz-im/cli
```
### 引入
```go
import "github.com/yz-im/cli"
```
### 样例代码
```go
package main

import (
	"fmt"

	"github.com/yz-im/cli"
)

func run() cli.RunFunc {
	return func(basename string) error {
		return LaunchMyBiz()
	}
}

func LaunchMyBiz() error {
	fmt.Println("biz is launched !")
	return nil
}

func main() {
	app := cli.NewApp(
		"my app",
		app.WithRunFunc(run())
	).Run()
}
```
## api-reference
### App
```go
// 新建一个带option的App
func NewApp() *App
```
```go
// 新建一个默认App
func Default() *App
```
```go
// App run
func (a *App) Run()
```
