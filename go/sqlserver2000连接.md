# 连接sqlserver2000
!!!机器必须安装sudo apt-get install freetds-dev

```go
package main

import (
	"fmt"
	"log"

	"github.com/jinzhu/gorm"
	_ "github.com/minus5/gofreetds"
)

func main() {
	user := "sa"
	password := "ljyy2018"
	dbName := "issyytv3"
	host := "47.107.144.119:4796"

	db, dbErr := gorm.Open("mssql", fmt.Sprintf("user=%s;pwd=%s;database=%s;host=%s", user, password, dbName, host))

	if dbErr != nil {
		log.Fatal(dbErr)
	}
	defer db.Close()

	fmt.Println("连接成功")

	sql := "SELECT vip_name FROM t_rm_vip_info WHERE vip_name LIKE '%丁%'"
	var vipName []string

	if err := db.Raw(sql).Pluck("vip_name", &vipName).Error; err != nil {
		log.Fatal(err)
	}

	for _, name := range vipName {
		fmt.Println(name)
	}
}

```