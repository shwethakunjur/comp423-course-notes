# Setting up a dev container for Rust

* Primary author: [Shwetha Kunjur](https://github.com/shwethakunjur/comp423-course-notes)
* Reviewer: [Riya Chawan](https://github.com/riyachawan/comp423-course-notes.git)

---

### Prerequisites:
Before starting, make sure you have:

* Docker installed.
* Visual Studio Code installed.
* The Dev Containers extension for VS Code installed.

---

### Steps:

**Create a new directory and initialize git**

```
mkdir rust-dev-container
cd rust-dev-container
git init
```

**Add a Dev Container**

* Add a directory called .devcontainer and add a configuration file within this directory called devcontainer.json that contains the following content:
```{.yaml .copy}
{
    "name": "Rust Development Environment",
    "image": "mcr.microsoft.com/devcontainers/rust:latest",
    "customizations": {
        "vscode": {
            "extensions": [
                "rust-lang.rust-analyzer"
            ]
        }
    }
}
```


* "name" sets the name of the Dev Container.

* "image" defines the Docker image to be used for the Rust environment.

* "customizations" installs the Rust Analyzer extension for VS Code.

!!! Note
    Make sure Docker is running before proceeding

**Start your environment**

* Open the command palette in VS Code. In the menu bar, select View > Command Palette.

* Enter the following command >Dev Containers: Open Dev Container. This will start building your dev container.


**Once your Dev Container starts, check that rustc is installed**

* Open the terminal.
* Run:
```{.yaml .copy}
rustc --version
```
> This will output the current version of Rust installed.


**Create a new Rust project using Cargo**

!!! Note
    Cargo is the official Rust package manager and build tool.

* Run the following command to create a new binary project:
```{.yaml .copy}
cargo new hellocomp423 --vcs none
```

* cargo new: Initializes a new Rust project.
* hellocomp423: This is the name of your project.
* --vcs none: This prevents Cargo from initializing a new Git repository automatically in the project.


**Add the following code for your Hello COMP423 program:**

```{.yaml .copy}
fn main ()
{
    println!("Hello COMP423");
}
```

**Compile and Run your program**

Option 1: Use cargo build to Compile the Project

* Run the following command to compile your project:
```{.yaml .copy}
cargo build
```
> This will generate an executable in the target folder. 

* Then you can run it by using:
```{.yaml .copy}
./target/debug/hellocomp423
```

* The output should be:
```
Hello COMP423
```

Option 2: Use cargo run to both compile and run your project

* Run the following command to compile and run your project in one step:
```{.yaml .copy}
cargo run
```
> This will compile the project and then immediately run the executable.

* The output should be:
```
Hello COMP423
```

You now have a Rust development environment!