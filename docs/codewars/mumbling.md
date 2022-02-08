## Problems

```go
Accum("ZpglnRxqenU")
// "Z-Pp-Ggg-Llll-Nnnnn-Rrrrrr-Xxxxxxx-Qqqqqqqq-Eeeeeeeee-Nnnnnnnnnn-Uuuuuuuuuuu"
```

## Solution

```go
import (
	"strings"
)

func Accum(s string) string {
	var result string

	// looping range s
	for i, v := range s {

		var word string

		loop := i
		word += strings.ToUpper(string(v))

		// looping range word
		for loop > 0 {
			word += strings.ToLower(string(v))
			loop--
		}

		if i > 0 {
			result += "-"
		}
		result += word
	}

	return result
}
```