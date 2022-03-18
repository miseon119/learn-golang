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

## Type

```golang
package main
import ("time")

type User struct {
    FirstName string
    LastName string
    PhoneNumber string
    Age int
    BirthDate time.time
}
func main() {
    user := User {
        FirstName: "Bob",
	LastName: "James",
    }
}
```
