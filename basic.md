# Basic 

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

## if 

```golang
package main
func main() {
    var isTrue = true
    
    if isTrue {
    	log.Println("isTrue is ", is True)
    }else {
    	log.Println("isTrue is ", is True)
    }

//    else if{
//    	log.Println("isTrue is ", is True)
//   }
}

```

## switch

```golang
    switch myvar {
    
    case "cat":
       log.Println("cat ")
    case "dog":
       log.Println("dog ")
    case "pig":
       log.Println("pig ")
    default:
       log.Println("nothing ")
    }
```

## for loop

```golang
	for i := 0; i <= 10; i++ {
	   log.Println("nothing ")
	}
```

```golang
  animals := []string{"dog", "fish", "horse", "cow", "cat"}
  
  for i, animals := range animals {
    log.Println("nothing ")
  }
  
    for _, animals := range animals {
    log.Println("nothing ")
  }

```

for loop a Map
```golang
    animals := make(map[string][string])
    animals["dog"] = "Fido"
    animals["cat"] = "Fluffy"
    
    for _, animals := range animals {
        log.Println("nothing ")
    }
```

## interface

```golang
type Animal interface {
    Says() string
    NumberOfLegs() int
}
type Dog struct {
    Name string
    Breed string
}
type Gorilla struct {
    Name string
    Color string
    NumberOfTeeth int
}

func main() {
    dog := Dog {
    Name: "Samson"
    Breed: "German Shephered"
    }
    PrintInfo(&dog)
}

func PrintInfo(a Animal){
    fmt.Println("This animal says ", a.Says(), "and has ", a.NumberOfLegs(), " legs")
}

func (d *Dog) Says() string {
    return "Woof"
}
func (d *Dog) NumberOfLegs() int {
    return 4
}
func (d *Gorilla) Says() string {
    return "Ugh"
}
func (d *Gorilla) NumberOfLegs() int {
    return 2
}
```

## channel

```golang
package main

import (
	"log"

	"github.com/tsawler/myniceprogram/helpers"
)

const numPool = 1000

func calculateValue(intChan chan int) {
	randomNumber := helpers.RandomNumber(numPool)
	intChan <- randomNumber
}

func main() {
	intChan := make(chan int)
	defer close(intChan)

	go calculateValue(intChan)

	num := <-intChan
	log.Println(num)
}

```
