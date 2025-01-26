# Setting up a dev container for Rust

* Primary author: [Ashley Pearson](https://github.com/uncapearso2)
* Reviewer: [Mariana Rodriguez-Pacheco](http://github.com/marianarp754)


# Prerequisites
1. GitHub Account
2. Git Installed
3. VS Code Installed
4. Docker Installed

# Step 1 Create Local Directory & Get Started with Git
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

# Step 2 Setup GitHub
2.1: Log in to GitHub and head to the Create a New Repository page

2.2: Fill in the following:
Repo Name: rust-hello-comp423
Description: "Getting started with Rust - Hello COMP423"

2.3: Create Repository

# Step 3 Link GitHub
3.1: Add your GitHub repo as a remote:
````bash
git remote add origin https://github.com/<username>/rust-hello-comp423.git
````

3.2: Check default branch is main using subcommand `git branch`. If it is not, rename it using `git branch -M main`.

3.3: Push local commits to GitHub
````bash
git push -u origin main
````

# Step 4 Setup Development Container
4.1 
