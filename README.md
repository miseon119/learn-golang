# learn-golang

## variable

```golang
var i int
var wahtToSay string
```

## pointer
```golang
package main
import "log"

func main() {
	var myString string

ChangeUsingPointer(&myString)

}

func ChangeUsingPointer(s *string) {
	newVaule := "Red"
	*s = newVaule
}
```
