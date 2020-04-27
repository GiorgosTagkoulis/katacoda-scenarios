## Get git repository

To follow along on this tutorial you can either borrow our repository or make your own.

To borrow ours do:

`git clone https://github.com/PaulLowenstrom/foo_ci.git`{{execute}}

`cd foo_ci`{{execute}}

To make your own you need a github account and do the following commands

navigate to your home directory.
`cd ~`{{execute}}

create your project in a folder called "foo_ci"
`mkdir foo_ci`{{execute}}

change directories into the new foo_ci folder
`cd foo_ci`{{execute}}

create a git repository
`git init`{{execute}}

Create a file to put in your repository
`touch README.md`{{execute}}

`echo 'Hello World!'`{{execute}}

Stage every file to commit
`git add .`{{execute}}

create your first commit.
`git commit -m "Initial commit"`{{execute}}

And finally 

git remote add origin git@github.com:<YOUR_USERNAME>/foo_ci.git

git push --set-upstream origin master
