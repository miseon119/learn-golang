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

## Structs with functions

```golang
package main
import "log"

type myStruct struct {
    FirstName string
}

func (m *myStruct) printFirstName() string {
    return m.FirstName
}

func main() {
    var myVar myStruct
    myVar.FristName = "John"
    log.Println("myVar is set to ", myVar.printFirstName() )
}

```

## Maps and Slices

### Map

create a map
```golang
package main

func main() {
    myMap := make(map[string]string)
    //myMap := make(map[string]int)
    
    myMap["dog"] = "samson"
}
```

### slices

create slices
```golang
package main
import "log"
func main() {
    var mySlice []string
    //var mySlice []int
    mySlice.append(mySlice, "Jone")
    mySlice.append(mySlice, "Mary")
    mySlice.append(mySlice, "Bob")
    
    // sort.Ints(mySlice)
}
```
or 
```golang
package main
import "log"
func main() {
    numbers := []int{1,2,4,5,6,7,8}
    log.Println(numbers[0:2])
}
```

