## Problem

:bulb: 8 kyu

:clock1: 5 menit

> Aku belajar pake konsep make di golang


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

## Best Solution

```go

import (
	"strings"
)

func Accum(s string) string {
	parts := make([]string, len(s))

	for i, v := range s {
		parts[i] = strings.ToUpper(string(v)) + strings.Repeat(strings.ToLower(string(v)), i)
	}

	return strings.Join(parts, "-")
}

```