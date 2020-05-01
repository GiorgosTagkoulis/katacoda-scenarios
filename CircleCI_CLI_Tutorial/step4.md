So far, we have achieved to install successfully the CircleCi CLI tool, and initialize manually a demo project with a basic CircleCI configuration. One of the advantages of the CLI tool, is that you validate the config file directly through your terminal, instead of pushing unnecessary commits to check the web app if the config is validated. 

<sub>`egg="${egg}IC0nICAgICAgICAgICAgfCBcXyAgLCAgICAgLScKICB8ICAnXF9fX19fX18pICAgICAgICAgICB8"`{{execute T2}}</sub>

For the demo project we have created, run the following command and make sure that the `config.yml`{{action}} is validated.

`circleci config validate`{{execute T1}}

## Run the job in the config file locally

Now that we have proved that the config file is validated, we can finally procceed to run our first job with the CLI tool. It is important to note that in order for the CLI tool to run, you need to have Docker installed in your system. Then in the root of your project (where the hidden directory circleci is), run the command:

`circleci local execute`{{execute T1}}

As you can see, the build is successful. However, if you have a closer look you will realise that in our config file there is no actual code or tests. The build has only one job that is to download the docker image from the [Pre-build CircleCI Docker images](https://circleci.com/docs/2.0/circleci-images/) where the job commands will run, initialize some environment variables and echo "Hello world".

It is worth noting that the CLI tool run only single jobs and not workflows or pipelines. The reason is that workflows run jobs concurrently in multiple machines for faster and more complex builds. However with the CLI you can run single jobs that are part of a workflow in a config file (a feature which is outside the scope of this tutorial). 

In general the CLI tool uses Docker to pull down the requirements for the build and then executes the CI steps you have defined in the config file locally. 

<sub>`egg="${egg}XyB8ICdcX19fX19fXykKICB8ICAgICAgXykgICAgICAgICAgICAgICAgIHx8ICAgICAgXykKICB8"`{{execute T2}}</sub>

Albeit the set up in this step was rather simple, it is believed that it provided you with some basic understanding about the CircleCI CLI tool. In the next steps, the focus will be in some coding examples.