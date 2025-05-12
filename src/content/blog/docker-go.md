---
title: 'Building Your Own Container Using Golang and Docker'
description: 'Step-by-step guide to creating a simple containerized Go application and running it with Docker.'
pubDate: '2024-01-02'
heroImage: '/blog-placeholder-2.jpg'
---

# Building Your Own Container Using Golang and Docker

Kubernetes is often used to manage containers, and we know that it's built using Go. I decided to go deeper and create my own container using Golang and Docker—essentially, my own virtual EC2 instance. The steps are actually quite straightforward once Go is installed and the environment variables are properly set.

---

## Setting Up Your Go Environment

One of the trickier parts is setting the PATH to include the **GOPATH**. To simplify this, put your **GOPATH** in the same folder as your Go installation, which will save you some configuration headache. However, if they are in different locations, just add both paths to your system variables, separated by a semicolon.

**Note:** In my setup, I did not get a proper response when checking the second `go env PATH`. I suspect this was due to how I configured the paths, and I wouldn't recommend doing it that way again. I also had to correct this by adding a **GOROOT** and making sure my environment variables referenced the correct paths.

In my system, `%USERPROFILE%` resolves to:

```text
C:\Users\mikep
```

### You can verify your environment setup with these commands:

- `go env PATH`
- `go env GOPATH`
- `go version`

---

## Creating the Go Project

```text
C:\Users\mikep\go\src\my-container-app> mkdir my-container-app
C:\Users\mikep\go\src> cd my-container-app
C:\Users\mikep\go\src\my-container-app> notepad main.go
```

### Below is the code for your `main.go` file:

```go
package main

import (
    "fmt"
    "net/http"
)

func handler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "Hello, World!")
}

func main() {
    http.HandleFunc("/", handler)
    fmt.Println("Starting server on :8080")
    http.ListenAndServe(":8080", nil)
}
```

---

## Creating the Dockerfile

In the same directory as `main.go`, create a `Dockerfile`.  
Note: If you use Notepad, it might save it with a `.txt` extension. You can rename it with:

```text
rename Dockerfile.txt Dockerfile
```

### Here is the Dockerfile:

```dockerfile
# Start with a lightweight Go base image
FROM golang:1.20-alpine as builder

# Set working directory in the container
WORKDIR /app

# Copy Go modules and source code
COPY go.mod go.sum ./
RUN go mod download
COPY . .

# Build the Go application
RUN go build -o main .

# Use a lightweight image for deployment
FROM alpine:3.18

# Set working directory and copy binary from builder stage
WORKDIR /root/
COPY --from=builder /app/main .

# Expose port 8080 and start the application
EXPOSE 8080
CMD ["./main"]
```

---

## Running the Go Application and Docker Image

Now, run the following commands:

```text
C:\Users\mikep\go\src\my-container-app>
```

```sh
go mod init my-container-app
```

```text
go: creating new go.mod: module my-container-app
```

```sh
go run main.go
```

```text
Starting server on :8080
exit status 0xc000013a
```

You can now check it out by visiting your localhost in your browser:  
[http://localhost:8080](http://localhost:8080)

---

## Environment Variable Setup Example

Below are screenshots showing the environment variable setup, ensuring that the `GOPATH` is correctly configured. Make sure you separate paths with a semicolon (`;`).

<!--
![Environment Variables Screenshot 1](assets/images/localstack1.png)
![Environment Variables Screenshot 2](assets/images/localstack2.png)
![Environment Variables Screenshot 3](assets/images/localstack3.png)
-->

---

