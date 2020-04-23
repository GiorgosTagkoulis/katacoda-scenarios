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

>version: 2.1

>jobs:
>  build:

>    docker: 

>      - image: circleci/node:4.8.2 # the primary container, where your job's commands are run
>    steps:

>      - checkout # check out the code in the project directory
>      - run: echo "hello world" # run the echo command

`echo 'version: 2.0' >> config.yml
echo '  jobs:' >> config.yml
echo '    build:' >> config.yml
echo '      docker:' >> config.yml
echo '        - image: circleci/ruby:2.4.2-jessie-node:' >> config.yml
echo '    steps:' >> config.yml
echo '        - checkout' >> config.yml
echo '        - run: echo "Hello World"' >> config.yml`{{execute}}
