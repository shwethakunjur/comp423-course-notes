# Setting up a dev container for Rust

* Primary author: [Shwetha Kunjur](https://github.com/shwethakunjur/comp423-course-notes)
* Reviewer: [Riya Chawan](https://github.com/riyachawan/comp423-course-notes.git)

```
Prerequisites:
Before starting, make sure you have:
* Docker installed.
* Visual Studio Code installed.
* The Dev Containers extension for VS Code installed.
```

Steps:

Create a new directory and initialize git

* mkdir rust-dev-container

* cd rust-dev-container

* git init


Add a Dev Container configuration file called .devcontainer.json that contains the following content:


```
{

    "name": "Rust Development Environment"

    "image": "mcr.microsoft.com/devcontainers/rust:latest"

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

* "image" defines the Docker image to be used (Rust).

* "customizations" installs extensions for VS Code.


Start your environment

* Install VS Code

* Open your directory where you configured your Dev Container in VS Code

* Install the Dev Containers VS Code extension.

* Open the command palette in VS Code. In the menu bar, select View > Command Palette.

* Enter the following command >Dev Containers: Open Dev Container. This will start building your dev container.


Once your Dev Container starts, check that rustc is installed.

* Open the terminal.

```
Run rustc -h. 
```

Create a new file called hellocomp423.rs.

* Add the following code:

```
fn main ()
{
    println!("Hello COMP423");
}
```

Compile your program

```
rustc hellocomp423.rs
```

* This will generate an executable called hellocomp423

Run your program

```
./hellocomp423
```

* The application should print out "Hello COMP423" to the console.

You now have a Rust development environment!