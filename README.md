# Introduction
![gomail](https://user-images.githubusercontent.com/58651329/84985674-c69ebf00-b16f-11ea-9cf4-57a7eb4e00c6.png)
We have downloaded and modified this **gomail** package originally from the author **alexcesaro** of [#gomail](https://github.com/go-gomail/gomail) in which the package seems no longer maintaining, that's why we take this very good package to maintain it for other gopher developers.

Gomail is a simple and efficient package to send emails. It is well tested and
documented.

Gomail can only send emails using an SMTP server. But the API is flexible and it
is easy to implement other methods for sending emails using a local Postfix, an
API, etc.

It requires Go 1.2 or newer. With Go 1.5, no external dependencies are used.

# Features
Gomail supports:
- Attachments
- Embedded images
- HTML and text templates
- Automatic encoding of special characters
- SSL and TLS
- Sending multiple emails with the same SMTP connection

# Installation
```
go get -u github.com/itrepablik/gomail
```

## FAQ

### x509: certificate signed by unknown authority

If you get this error it means the certificate used by the SMTP server is not
considered valid by the client running Gomail. As a quick workaround you can
bypass the verification of the server's certificate chain and host name by using
`SetTLSConfig`:

    package main

    import (
    	"crypto/tls"

    	"github.com/itrepablik/gomail"
    )

    func main() {
    	d := gomail.NewDialer("smtp.example.com", 587, "user", "123456")
    	d.TLSConfig = &tls.Config{InsecureSkipVerify: true}

        // Send emails using d.
    }

Note, however, that this is insecure and should not be used in production.

# Usage
This is an example usage of how to send an email using gomail package.
```

```

# License
Code is distributed under MIT license, feel free to use it in your proprietary projects as well.
