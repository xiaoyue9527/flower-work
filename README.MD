# 小微书前端

> 注意，v1.1和v1.2对应的是一次课程的上下课时，有可能会出现1.X

## 快速开始

### 下载view中的html文件

### 使用 LoadHTMLGlob() 或者 LoadHTMLFiles()

例如：

```go
func main() {
	router := gin.Default()
	router.LoadHTMLGlob("templates/*")
	//router.LoadHTMLFiles("templates/template1.html", "templates/template2.html")
	router.GET("/index", func(c *gin.Context) {
		c.HTML(http.StatusOK, "index.tmpl", gin.H{
			"title": "Main website",
		})
	})
	router.Run(":8080")
}
```