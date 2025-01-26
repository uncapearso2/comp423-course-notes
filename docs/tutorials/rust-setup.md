# Setting up a dev container for Rust

* Primary author: [Ashley Pearson](https://github.com/uncapearso2)
* Reviewer: [Mariana Rodriguez-Pacheco](http://github.com/marianarp754)


# Prerequisites
1. GitHub Account
2. Git Installed
3. VS Code Installed
4. Docker Installed


# Git & GitHub Setup
## Step 1 Create Local Directory & Get Started with Git
1.1: Open a terminal

1.2: Create a new directory for the project

````bash
mkdir rust-hello-comp423
cd rust-hello-comp423
````

1.3: Initialize Git repo

````bash
git init
````

1.4: Create README

````bash
echo "# Rust Hello Comp 423" > README.md
git add README.md
git commit -m "Initial commit with README"
````

## Step 2 Setup GitHub
2.1: Log in to GitHub and head to the Create a New Repository page

2.2: Fill in the following:

- Repo Name: rust-hello-comp423

- Description: "Getting started with Rust - Hello COMP423"

2.3: Create Repository

## Step 3 Link GitHub
3.1: Add your GitHub repo as a remote:
````bash
git remote add origin https://github.com/<username>/rust-hello-comp423.git
````

3.2: Check default branch is named main using subcommand `git branch`. If it is not, rename it using `git branch -M main`.

3.3: Push local commits to GitHub
````bash
git push -u origin main
````


# Development Container Setup
## Step 4 Configure Development Container
4.1: Open the `rust-hello-comp423` directory in VS Code through File > Open Folder

4.2: Install the Dev Containers extension for VS Code

4.3: Create a `.devcontainer` directory in the root of your project
!!! note
    The . in the front of this name indicates the directory is hidden.

4.4: Inside the `.devcontainer` directory, create a `.devcontainer/devcontainer.json` file
!!! note
    This file defines the configuration for your development environment including the following:
    
    - name: a descriptive name for your development container
    
    - image: which Docker image to use, for our example we will use the latest version of a Rust environment from Microsoft
    
    - customizations: add configurations to VS Code such as installing the Rust extension
    
    - postCreateCommand: a command to run after the container is created

4.5: Use `devcontainer.json` to configure your development environment with the following information:
````
{
    "name": "COMP423 Course Notes",
    "image": "mcr.microsoft.com/vscode/devcontainers/rust:latest",
    "customizations": {
      "vscode": {
        "settings": {},
        "extensions": ["rust-lang.rust-analyzer"]
      }
    },
    "postCreateCommand": "cargo new hello-comp-423 --vcs none --bin"
  }
````

4.6: Reopen the project in a VSCode Dev Container by using the `Ctrl+Shift+P` shortcut, typing "Dev Containers: Reopen in Container" and selecting the option

4.7: Check for success!
!!! note
    Close your current terminal and open a new one. Run `rustc --version` to check that your dev container is running a recent version of Rust.

# Finalize Hello COMP423 Message
## Step 5 Edit & Compile Message

5.1: Open the directory created by `cargo new` with the `cd hello-comp-423` command

5.2: Open `hello-comp-423/src/main.rs` and edit the `println!` message to say "Hello COMP423"

5.3: Save changes

# Build & Check Out Our Program
## Step 6
6.1: Compile your program with `cargo build`

6.2: Run your program using `./target/debug/hello-comp-423`

6.3: Put it all in one command with `cargo run`
!!! note
    The cargo run command compiles the program and then runs it in just one step!



Written in part with assistance from the COMP423 Starting a Static Website Project with MkDocs webpage.