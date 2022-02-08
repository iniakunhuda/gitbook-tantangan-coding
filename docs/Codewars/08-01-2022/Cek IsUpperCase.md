
> :bulb: 8 kyu
>
> :clock1: x menit
>
> :pencil2: Aku belajar tanpa pake libs


## Problem


```go
MyString("ABCDEFGHIJKLMNOPQRSTUVWXYz").IsUpperCase()
// false

MyString("WHAT DOES THE FOX SAY").IsUpperCase()
// true
```

## Solution

```go
type MyString string

func (s MyString) IsUpperCase() bool {
	res := false

	for _, v := range s {
		if string(v) == " " {
			continue
		}

		if v >= 'A' && v <= 'Z' {
			res = true
		} else {
			return false
		}
	}

	return res
}
```

## Best Solution

```go

import "strings"

type MyString string

func (s MyString) IsUpperCase() bool {
  return string(s) == strings.ToUpper(string(s))
}

```