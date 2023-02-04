# Getting Started with Julia

Julia is an open source, high-level, strongly typed, dynamic, functional programming language designed for numerical analysis and computational science. Julia attempts to solve the "Two-Language" problem allowing to coding everything in a single language balancing both performance (as in C or Fortran) and productivity (as in Python).

## Setup

Please download Julia from https://julialang.org/downloads/ and follow the installation instructions presented at https://julialang.org/downloads/platform/. Install the current stable release.

Follow one of the following instructions to setup development environment

### Visual Studio Code (https://code.visualstudio.com/)

- [Download and install VS Code](https://code.visualstudio.com/download/)
- Start VS Code, click View->Command Palette... and type View: Show Extensions to go to the extension manager
- In the extension manager search and install “Julia Language Support” extension

### Jupyter Notebook

- star console and type the following command

```julia
using Pkg
Pkg.add("IJulia")

using IJulia
IJulia.notebook(dir=".")
```

### Pluto Notebook

```julia
using Pkg
Pkg.add("Pluto")

using Pluto
Pluto.run()
```

## Using Julia REPL

- `julia>` : Julia REPL to interact with Julia Engine
- `shell>` : Enter through ";" for using shell command at REPL
  - Alternatively create and run command object 
  
```julia
cmd = `echo hello` 
run(cmd)
```

- `help>` : Enter through "?" for using help, search through documentation
- `(ENVNAME) pkg>`: Entered through "]" for using [Pkg.jl](https://pkgdocs.julialang.org/), Julia's Package Manager, which activates the environment, and work with package registry, Alternatively import or use `using Pkg`
  - `activate myEnv` : creates and activates a new environment tracked by manifest file
  - `Pkg.activate(; temp=true)`: create temp env will be deleted when the julia process is exited
  - `add Distributions Plots` : add packages, specify git repository URL to refer to unregistered packages
  - `rm Distributions Plots`: remove packages
  - `update Plots`: Update Packages
  - `instantiate` : Download all pacakges declared in Manifest.toml if it exists else resolve from Project.toml
  - `Pkg.gc(; collect_delay::Period=Day(7), io::IO=stderr)`  #s weep over all known Manifest.toml and Artifacts.toml, makring "orphaned" artifacts and packages, and removing them if the pacakges are unsued for collect_delay period.
- `(reverse-i-search)` Enter through "^R" (Ctrl+R) for using previous commands matching a pattern
- forward-i-search
- Go to normal mode with `BACKSPACE`

Other common commands

- "^L" (Ctrl+L) clear screen
- "^D" (Ctrl+D) exit REPL
- "^C" (Ctrl+C) abort

; at the end of expression suppresses REPL output

One can access REPL through Julia cell in Jupyter Notebook as well

## Reference

- [Julia Language Manual](https://docs.julialang.org/en/v1/)
- [MIT Introduction to Computational Thinking](https://computationalthinking.mit.edu/) talks about CS, Maths Applications using Julia.
