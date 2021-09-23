# go-mail

Simple library to check if email format is valid. Email service provider that can be check here is gmail, outlook, and hotmail. It's format adjust from their term&condition.
### Gmail
* Minimal 6 chars, maximum 30 chars
* Can't use two or more period '.'
* Can't contains special characters such as `~!#$%^&*()+=:;"'\?<>{}[]

### Outlook/Hotmail
* There's no minimal chars, maximum local-part 64 chars, maximum domain 255 chars
* Can use '.', '-', '_'
* Can't contains special character such as `~!#$%^&*()+=:;"'\?<>{}[]

Here, you can obfuscate email with asterisk, so it'll be hidden.

## Installation

Download and install library:
```go
go get github.com/intaen/go-mail
```

## Import
Import in your code
```go
import "github.com/intaen/go-mail"
```

## Example
```go
package main

import (
	"fmt"

	"github.com/intaen/go-mail"
)

func main() {
	email := "testing.gomail@gmail.com"
	isValid := IsEmailValid(email)
	if isValid {
		obfemail := ObfuscateEmail(email)
		fmt.Println(obfemail)
	}
	// Result: true
    	// Result: te***********l@gmail.com
}
```
