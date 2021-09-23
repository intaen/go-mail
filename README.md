# go-mail

Simple library to check if email format is valid. Email service provider that can be check here is gmail, outlook, and hotmail. It's format adjust from their term&condition.
### Gmail
* Minimal 6 chars
* Can't use two or more period '.'
* Can't contains special characters such as `~!#$%^&*()+=:;"'\?<>{}[]

### Outlook/Hotmail
* There's no minimal chars
* Can use '.', '-', '_'
* Can't contains special character such as `~!#$%^&*()+=:;"'\?<>{}[]
Here, youcan obfuscate email with asterisk, so it'll be hidden.

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
	isValid, localpart, domain := IsEmailValid(email)
	if isValid {
		obfemail := ObfuscateEmail(localpart, domain)
		fmt.Println(obfemail)
	}
	// Result: true, testing.gomail, gmail
    	// Result: te***********l@gmail.com
}
```
