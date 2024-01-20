To create a new Go project with module versioning, you can follow these steps:

1. **Create a New Project Directory:**
   - Start by creating a new directory for your project. You can name it whatever you like.

```bash
mkdir mygoapp
cd mygoapp
```

2. **Initialize Go Modules:**
   - Use the `go mod init` command to initialize Go modules. This command creates a `go.mod` file that will keep track of your project's dependencies and their versions.

```bash
go mod init github.com/yourusername/mygoapp
```

   Replace `github.com/yourusername/mygoapp` with the actual path where your code will be hosted.

3. **Write Your Code:**
   - Create your Go files and write your code. For example, you can create a file named `main.go`:

   ```go
   package main

   import "fmt"

   func main() {
       fmt.Println("Hello, Go Modules!")
   }
   ```

4. **Add Dependencies:**
   - If your project relies on external packages, you can use the `go get` command to add them to your project. For example:

   ```bash
   go get github.com/somepackage/somepackage
   ```

   This will download the specified package and update your `go.mod` file.

5. **Run Your Code:**
   - You can use the `go run` command to execute your Go program:

   ```bash
   go run .
   ```

   If everything is set up correctly, you should see the output of your program.

6. **Versioning:**
   - Go modules automatically manage versions of dependencies. When you add a dependency using `go get`, the version is recorded in the `go.mod` file. You can also specify version ranges in the `go.mod` file.

   ```go
   require (
       github.com/somepackage/somepackage v1.2.3
   )
   ```

   To update dependencies, you can use the `go get` command again.

   ```bash
   go get -u
   ```

   This will update your project to the latest versions of its dependencies.

Remember that Go modules are the preferred way to manage dependencies starting from Go 1.11. They simplify versioning and dependency management in Go projects.