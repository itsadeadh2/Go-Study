## Go Study
*Compilation of info/projects that I'll be gathering during my go study.*

### Main benefits of Go
- Concurrency friendly (good for multicore/networked machines)
- Novel type system (look into)
- Compiles quickly
- Garbage collection (look into)
- Run-time reflection (look into)
- Statically Typed


### Installing go
Installing go can be easily done by following the steps on the [website](https://go.dev/doc/install).  


### Managing Modules
To manage the dependencies we use the go.mod file. This file should be included in the source code.  
To create a go.mod automatically, we can run the `go mod init` command.

**Installing Modules**
- `go mod tidy`
	* We can import the modules directly into the code and run `go mod tidy` afterwards to have go retrieve the package for us.
- `go get <packagename>`
	* We can also use the `go get <package name>` command to find and pull dependencies into a project. 

### Running code
 - `go run .` to run based on context
 - `go run <filename>` to run specific file  
 

### Organize later:
- A module is a collection of packages that are release, versioned and distributed together. Modules may be downloaded directly from version control repositories or from module proxy servers.
- The module `root directory`  is the directory that contains the go.mod file.
- The `main module` is the module containing the directory where the go command is invoked
- Go code is grouped into packages, and packages are grouped into modules.
- In Go a function whoose name starts with a capital letter can be called by a function not in the same package.
- In go code executed as an application must be in a `main` package
- Go allows for return of multiple values
- We can return an "error" object and check for its content to determine if a function call failed. Very similar to how we handle errors for callbacks in nodejs.
- go comes with a log package out of the box. If nothing is specified, it automatically adds timestamps for each log. the `Fatal` method on the log module also stops the execution.

### TODO:
> Lookup how to manage different Go versions. I already know it is possible to do so, but I wonder if there is a tool like `n` that makes the process less tedious.

> Should the `go.sum` file also be commited?

> Get more info about how to run a specific file, also, how does go identifies which file to run by context with the `.`


  
**ctrl shift v to preview**