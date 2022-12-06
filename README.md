- *为LUA新增获取中文字符串的长度方法*
- **

----

# Go strings package for [gopher-lua](https://github.com/yuin/gopher-lua)

[hello.go](hello.go):

```go
package main

import (
	"github.com/yuin/gopher-lua"

	strings "github.com/592530326/glua-strings"
)

func main() {
	L := lua.NewState()
	defer L.Close()

	strings.Preload(L)

	if err := L.DoString(code); err != nil {
		panic(err)
	}
}
```

[hello.lua](hello.lua):

```lua
local strings = require("strings")
local a = "你好吗111"
print(strings.Len(a))
print(strings.ToUpper("abc"))

for i, s in ipairs(strings.Split("aa,b,,c", ",")) do
	print(i, s)
end
```

Run example:

    $ go run hello.go

## License

The MIT License.
