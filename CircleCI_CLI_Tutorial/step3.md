## Create Configuration

The configuration contains the entire pipeline process, from build to deploy. It is written in the config.yml file and is placed at the root of your project in the .circleci folder. The config.yml is written with YAML syntax.

If you use our github repo you already have the config.yml

We start of by creating the configuration file. Create a folder called .circleci.

Add the following content to the config.yml 
```
version: 2.1
jobs:
  build:
    docker: 
      - image: circleci/node:4.8.2 # the primary container, where your job's commands are run
   steps:
      - checkout # check out the code in the project directory
      - run: echo "hello world" # run the echo command
```
In this case, we have done it for you when you pulled down the repository. You can check if the config.yml contains the correct information using.

`cat .circleci/config.yml`{{execute}}


## Validate and test it works

`circleci config validate`{{execute}}


`circleci local execute`{{execute}}
