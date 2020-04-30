So far, we have achieved to install successfully the CircleCi CLI tool, and initialize manually a demo project with a basic CircleCI configuration. One of the advantages of the CLI tool, is that you validate the config file directly through your terminal, instead of pushing unnecessary commits to check the web app if the config is validated. 

<sub>`egg="${egg}IC0nICAgICAgICAgICAgfCBcXyAgLCAgICAgLScKICB8ICAnXF9fX19fX18pICAgICAgICAgICB8"{{execute T2}}`</sub>

For the demo project we have created, run the following command and make sure that the `config.yml`{{action}} is validated.

`circleci config validate`{{execute T1}}

## Run the jobs in the config file locally

Now that we have proved that the config file is validated, we can finally run the CLI tool, by running the command:

`circleci local execute`{{execute T1}}

As you can see, the build is successful. However, if you have a closer look you will realise that in our config file there is no actual code or tests. The build had only one job that is to download the docker image from the [Pre-build CircleCI Docker images](https://circleci.com/docs/2.0/circleci-images/) where the jobs commands will run, initialize some environment variables and echo "Hello world". 

<sub>`egg="${egg}XyB8ICdcX19fX19fXykKICB8ICAgICAgXykgICAgICAgICAgICAgICAgIHx8ICAgICAgXykKICB8"{{execute T2}}`</sub>

Albeit a simple set up, it is believed that it provided you with some basic understanding about the CircleCI CLi tool. In the next steps, the focus will be in some coding examples.