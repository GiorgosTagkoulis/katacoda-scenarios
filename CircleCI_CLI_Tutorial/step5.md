
In the previous steps, we had a simple project to test the functionality on the CircleCI CLI tool. Now, we will clone a real project from GitHub, add it on CircleCI and run the CLI tool locally to see if it passes all the test and the build is successful. The NodeJs projest is provided by us, but it would work for any NodeJs application.

<sub>`egg="${egg}ICAgICB8ICAgICAgICAgICAgICAgICAgICB8ICAgICB8CiAvYC0tLS0tJ1wgICAgICAgICAgICAg"`{{execute T2}}</sub>

First, clone the repo:

`cd ..;
git clone https://github.com/GiorgosTagkoulis/Calculator.git`{{execute T1}}

Similarly like before, we will create a `config.yml`{{action}} file, click here: `config.yml`{{open}}, to open the file in the editor, and later click on the "Copy to Editor" of the following snippet. 

<pre class="file" data-filename="config.yml" data-target="replace">
version: 2.1 # use CircleCI 2.1
jobs: # a collection of steps
  build: # runs not using Workflows must have a `build` job as entry point
    working_directory: ~/mern-starter # directory where steps will run
    docker: # run the steps with Docker
      - image: circleci/node:10.16.3 # ...with this image as the primary container; this is where all `steps` will run
      - image: mongo:4.2.0 # and this image as the secondary service container
    steps: # a collection of executable commands
      - checkout # special step to check out source code to working directory
      - run:
          name: update-npm
          command: 'sudo npm install -g npm@latest'
      - restore_cache: # special step to restore the dependency cache
          # Read about caching dependencies: https://circleci.com/docs/2.0/caching/
          key: dependency-cache-{{ checksum "package-lock.json" }}
      - run:
          name: install-npm-wee
          command: npm install
      - save_cache: # special step to save the dependency cache
          key: dependency-cache-{{ checksum "package-lock.json" }}
          paths:
            - ./node_modules
      - run: # run tests
          name: test
          command: npm test
</pre>

Now navigate in the project directory, and create a `.circleci`{{action}} directory where we will put the config file.

`cd Calculator;
mkdir .circleci;
mv ../config.yml .circleci`{{execute T1}}

Validate:

`circleci config validate`{{execute T1}}

And run:

`circleci local execute`{{execute T1}}
<sub>`egg="${egg}ICAgICAgb29vb29vbwovICAgICAgICAgXCAgICAgICAgICAgICAgICAgLyAgICAgICBcCgo=" && clear && base64 -d <<< $egg`{{execute T2}}</sub>
