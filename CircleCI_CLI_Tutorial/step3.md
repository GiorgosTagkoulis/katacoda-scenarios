There are two ways to configure CircleCI to start building your project. The first one is through CircleCI's [web application](https://circleci.com/dashboard) (follow [these step](https://circleci.com/docs/2.0/getting-started/#section=getting-started) for guidance) where CirclecI automatically adds the necessary directories and files in your GitHub repository. Briefly explained, after you have logged in, from the left menu you need to choose `ADD PROJECTS`{{action}} and from the list you choose the project you want to set up and click on `Set Up Project`{{action}}, as it is shown below in the picture.

![ConnectCircleCiToRepo](https://github.com/GiorgosTagkoulis/katacoda-scenarios/raw/master/CircleCI_CLI_Tutorial/assets/CircleCIConnectToRepo.png)

Later on, you only need to click on `Start Building`{{action}}.

![ConnectCircleCiToRepo](https://github.com/GiorgosTagkoulis/katacoda-scenarios/raw/master/CircleCI_CLI_Tutorial/assets/StartBuilding.PNG)

The other way is manually by creating a `.circleci`{{action}} directory at the root of your project and adding a `config.yml`{{action}} file in it. The configuration for the entire pipeline process, from build to deploy, is written in the config.yml file which is written with YAML syntax.

Since this tutorial is going to run the job locally, we will continue with the latter case.

## Initialize project

First we ned to create a directory for our project. Run the command:

`mkdir hello-world`{{execute}}

Now we will create a `config.yml`{{action}} file, which later will be added to the project. Click on: `config.yml`{{open}}, to open the file in the editor, and later click on the "Copy to Editor" in the following snippet. 

<pre class="file" data-filename="./hello-world/.circleci/config.yml" data-target="replace">
version: 2.1
jobs:
  build:
    docker: 
      - image: circleci/node:4.8.2 # the primary container, where your job's commands are run
    steps:
      - checkout # check out the code in the project directory
      - run: echo "hello world" # run the echo command
</pre>

This is a simple set up which will have a workflow with only one job, that is to print "Hello-world".

As it was explained earlier, we need a `.circleci`{{action}} directory with a `config.yml`{{action}} file in it. For this, run the commands:

`cd hello-world; mkdir .circleci; mv ../config.yml .circleci`{{execute}}

The `config.yml`{{action}} now contains the correct information. Check from the terminal by typing:

`cat .circleci/config.yml`{{execute}}

In your own system, in an empty directory simply create `.circleci`{{action}} directory with a `config.yml`{{action}} in it, and copy the above snippet in it.