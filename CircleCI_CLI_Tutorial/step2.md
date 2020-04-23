## Create Configuration

We start of by creating the configuration file.

Tip: Make sure you are in the foo_ci folder, can be done with the command
`cd ~/foo_ci`{{execute}}

Then create directory called .circleci
`mkdir .circleci`{{execute}}

Then change file to the new directory
`cd .circleci`{{execute}}

And last create config.yml
`touch config.yml`{{execute}}

Add the following content to the config.yml 
`echo '
version: 2.0
jobs:
  build:
    docker:
      - image: circleci/ruby:2.4.2-jessie-node
    steps:
      - checkout
      - run: echo "Hello World"' > config.yml`{{execute}}
