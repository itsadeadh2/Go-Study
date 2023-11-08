## Go Study
*Compilation of info/projects that I'll be gathering during my go study.*

### TODO:
> Lookup how to manage different Go versions. I already know it is possible to do so, but I wonder if there is a tool like `n` that makes the process less tedious.

> Get more info about how to run a specific file, also, how does go identifies which file to run by context with the `.`

> Look up what is the **Novel type system**

> Look up the **Garbage collection**

> Look up the **Run-time reflection**

### Main benefits of Go
- Concurrency friendly (good for multicore/networked machines)
- Novel type system
- Compiles quickly
- Garbage collection
- Run-time reflection
- Statically Typed


### Installing go
Installing go can be easily done by following the steps on the [website](https://go.dev/doc/install).  


### Managing Modules
To manage the dependencies we use the go.mod file. This file should be included in the source code.  
To create a go.mod automatically, we can run the `go mod init <package><module>` command.

**Installing Modules**
- `go mod tidy`
	* We can import the modules directly into the code and run `go mod tidy` afterwards to have go retrieve the package for us.
- `go get <packagename>`
	* We can also use the `go get <package name>` command to find and pull dependencies into a project. 

 After running any of these commands, a `go.sum` file will be generated as well. This file is used to contain the checksum of the content of the specific modules versions.


### Running code
 - `go run .` to run based on context
 - `go run <filename>` to run specific file  


 

### Organize later:
- The `:=` syntax declares and initializes a value at the same time. It also automatically determines the variable type based on the value being assigned. To initialize an empty variable we do `var variable <type>`
- A module is a collection of packages that are release, versioned and distributed together. Modules may be downloaded directly from version control repositories or from module proxy servers.
- The module `root directory`  is the directory that contains the go.mod file.
- The `main module` is the module containing the directory where the go command is invoked
- Go code is grouped into packages, and packages are grouped into modules.
- In Go a function whoose name starts with a capital letter can be called by a function not in the same package.
- In go code executed as an application must be in a `main` package
- Go allows for return of multiple values
- We can return an "error" object and check for its content to determine if a function call failed. Very similar to how we handle errors for callbacks in nodejs.
- go comes with a log package out of the box. If nothing is specified, it automatically adds timestamps for each log. the `Fatal` method on the log module also stops the execution.
- go has `slices` wich are arrays with dynamic sizes. To declare a slice we do the following `[]<type>{val1, val2, val3}`.
- As a statically typed language, maps need to be defined indicating the types of the keys and also the values. The syntax for it is `map[<key type>]<value type>`.
- To do for loops in a given array in go we need to use the `range` keyword (much like `enumerate` in python). `range` will return the index and a **copy** of the current item of the iteration.
	* Since the range keyword returns a **copy** of the item, we cant use the item to modify the array
		```go
		names := []string{"John", "Doe"}
		for idx, value := range names {
			value = "Jean" // even though we change the value in here, it doesnt modify the original array
		}
		// names would still be ["John", "Doe"]
		```
	* Instead, we should use the `index` returned by range to modify the array
		```go
		names := []string{"John", "Doe"}
		for idx, value := range names {
			names[idx] = "Jean" 
		}
		// names would now be ["Jean", "Jean"]
		```
- To create tests in python we use the `testing` module. We then define the functions to run the tests and pass a `pointer` of `*testing.T` as an argument for the function. We can then use `t.Fatalf` to raise exceptions when the conditions doesnt match. To run the tests we run the `go test` command.

- The `go run` command, compiles and run programs on demand.Its useful for development when we are making frequent changes but it doesnt generate a binary executable. To do that we need to run the `go build` or the `go install` command. `go build` generates an executable that you can run on the command line or just by clicking on it. `go install` generates the executable inside the _go install_ path (run `$ go list -f '{{.Target}}'` to see the target install path for the given module). If we include this path on the `PATH` envvar we can then run the program by just calling it on a terminal. (To include the path on windows use `$env:PATH+=";path_to_append"`)

- To manage the workspace we can use the [go work](https://github.com/golang/tools/blob/master/gopls/doc/workspace.md) tool. This is useful for when we work on multiple packages at the same time, it allows us to specify the directories (modules) that we want to be included into the workspace. Without it we may have issues with the editors to properly locate dependencies in each of the modules.

- When using the workspace config, if we have a matching package locally go will actually look into the local package instead of the cached module downloaded with `go get`.

### Study Roadmap
- [Go Docs](https://go.dev/doc/tutorial/)
	* 🟢 [Getting started](https://go.dev/doc/tutorial/getting-started.html)
	* 🟢 [Create a Module](https://go.dev/doc/tutorial/create-module.html)
	* 🟢 [Getting started with multi-module workspaces](https://go.dev/doc/tutorial/workspaces.html)
	* 🟡 [Accessing a relational database](https://go.dev/doc/tutorial/database-access)
	* 🔴 [Developing RESTful API with Go and Gin](https://go.dev/doc/tutorial/web-service-gin)
	* 🔴 [Getting started with generics](https://go.dev/doc/tutorial/generics)
	* 🔴 [Getting started with fuzzing](https://go.dev/doc/tutorial/fuzz)
	* 🔴 [Getting started with govulncheck](https://go.dev/doc/tutorial/govulncheck)
	* 🔴 [Find and fix vulnerable dependencies with VS Code Go](https://go.dev/doc/tutorial/govulncheck-ide)
	* 🔴 [A Tour of Go](https://go.dev/tour/)
	* 🔴 [Managing Dependencies](https://go.dev/doc/modules/managing-dependencies)
	* 🔴 [Developing and publishing modules](https://go.dev/doc/modules/developing)
- Books
	* 🔴 [The Go Programming Language](https://www.gopl.io/)
	* 🔴 [Get Programming with Go](https://www.manning.com/books/get-programming-with-go)
	* 🔴 [Go Programming Blueprints](https://github.com/matryer/goblueprints)
	* 🔴 [Introducing Go](http://shop.oreilly.com/product/0636920046516.do)
	* 🔴 [Concurrency in Go](https://www.oreilly.com/library/view/concurrency-in-go/9781491941294/)

  
**ctrl shift v to preview**