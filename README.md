# go-mail

Simple library to check if email format is valid. You can obfuscate email with asterisk, so it'll be hidden.

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
