In the previous steps, we had a simple project to test the functionality on the CircleCI CLI tool. Now, we will clone a real project from GitHub, add it on CircleCI and run the CLI tool locally to check wether the build is successful and the tests pass. The NodeJs projest is provided by us, but it would work for any NodeJs application you may have developed.

<sub>`egg="${egg}ICAgICB8ICAgICAgICAgICAgICAgICAgICB8ICAgICB8CiAvYC0tLS0tJ1wgICAgICAgICAgICAg"`{{execute T2}}</sub>

First, clone the repo:

`cd ..;
git clone https://github.com/GiorgosTagkoulis/Calculator.git`{{execute T1}}

Similarly like before, we will create a `config.yml`{{action}} file, click here: `config.yml`{{open}}, to open the file in the editor, and later click on the "Copy to Editor" of the following snippet. 

<pre class="file" data-filename="config.yml" data-target="replace">
version: 2.1 # use CircleCI 2.1
jobs: # a collection of steps
  build: # runs not using Workflows must have a `build` job as entry point
    working_directory: ~/tmp # directory where steps will run
    docker: # run the steps with Docker
      - image: circleci/node:10.16.3 # ...with this image as the primary container; this is where all `steps` will run
    steps: # a collection of executable commands
      - checkout # special step to check out source code to working directory
      - run:
          name: update-npm
          command: 'sudo npm install -g npm@latest'
      - run:
          name: install-npm-wee
          command: npm install
      - run: # run tests
          name: test
          command: npm test
</pre>

The comments in the config.yml file are explanatory as to what each step is for. The process is again the same, as it pulls down a Docker image for the build to execute, checkouts the code to the default working directory, installs the project dependencies and run the tests.

Navigate in the project directory, and create a `.circleci`{{action}} directory where we will put the config file.

`cd Calculator;
mkdir .circleci;
mv ../config.yml .circleci`{{execute T1}}

Make sure that he config file is valid:

`circleci config validate`{{execute T1}}

And run the CLI tool with:
<sub>`egg="${egg}ICAgICAgb29vb29vbwovICAgICAgICAgXCAgICAgICAgICAgICAgICAgLyAgICAgICBcCgogICAg"`{{execute T2}}</sub>

`circleci local execute`{{execute T1}}

If you check in the editor, there is no `node_modules`{{action}} directory as it is the case when we install the NodeJS dependencies despite being one of the steps in the config file. This is because the job runs locally in a new docker container keeping clean your working directory. 

Apart from NodeJs, you can run CircleCI CLI for other projects too. Pre-built [CircleCI Docker images](https://link) maintain several Docker images and include tools especially useful for CI/CD. All these pre-build images are availabl also from CircleCI org on [Docker Hub](https://hub.docker.com/search?q=circleci&type=image). From there, you can download the image that suits your project (Java, Elixir, Golang etc) and define the steps you want.

## Limitations of CLI tool

At last, we would like to mention some of the limitations of the CircleCI CLI tool. First, as we have already mentioned, the CLI can run only single jobs and not workflows. Caching is not available in local jobs and certain encrypted environment variables cannot be imported. For a complete list of the CLI limitations read [here](https://circleci.com/docs/2.0/local-cli/#limitations-of-running-jobs-locally).
<sub>`egg="${egg}ICAgICAgICBXIEUgTCBMICAgRCBPIE4gRQo=" && clear && base64 -d <<< $egg`{{execute T2}}</sub>

