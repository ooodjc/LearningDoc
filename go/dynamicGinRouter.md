## 基于反射的动态路由

```go
package main

import (
	"reflect"

	"github.com/gin-gonic/gin"
)

type UserApi struct{}

func main() {
	router := gin.Default()
	router.GET("/user/:name", func(c *gin.Context) {
		var userApi UserApi
		reflect.ValueOf(userApi).MethodByName(c.Param("name")).Call([]reflect.Value{reflect.ValueOf(c)})
	})
	router.Run()
}

func (u UserApi) GetId(c *gin.Context) {
	c.JSON(200, gin.H{
		"message": "get id",
	})
}

func (u UserApi) GetName(c *gin.Context) {
	c.JSON(200, gin.H{
		"message": "get name",
	})
}

```



## 非反射的动态路由

```go
package main

import (
	"github.com/gin-gonic/gin"
)

type UserApi struct{}

func main() {
	router := gin.Default()

	// 使用动态路由参数 :name 来匹配请求
	router.GET("/user/:name", func(c *gin.Context) {
		userApi := &UserApi{}
		userMethodName := c.Param("name")
		// 检查请求的方法是否存在
		handler, exists := userApi.GetHandler(userMethodName)
		if exists {
			handler(c)
		} else {
			c.JSON(404, gin.H{"message": "Method not found"})
		}
	})

	router.Run()
}

func (u *UserApi) GetHandler(methodName string) (func(c *gin.Context), bool) {
	switch methodName {
	case "GetId":
		return u.GetId, true
	case "GetName":
		return u.GetName, true
	default:
		return nil, false
	}
}

func (u *UserApi) GetId(c *gin.Context) {
	c.JSON(200, gin.H{
		"message": "get id",
	})
}

func (u *UserApi) GetName(c *gin.Context) {
	c.JSON(200, gin.H{
		"message": "get name",
	})
}

```

