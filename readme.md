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

##### Installing Modules
- `go mod tidy`
	* We can import the modules directly into the code and run `go mod tidy` afterwards to have go retrieve the package for us.
- `go get <packagename>`
	* We can also use the `go get <package name>` command to find and pull dependencies into a project.