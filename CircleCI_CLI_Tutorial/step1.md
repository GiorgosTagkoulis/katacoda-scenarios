The CircleCI CLI is a command line interface that provides many of CircleCI's advanced and powerful tools in your terminal. From the [official documentation](https://circleci.com/docs/2.0/local-cli/), we get that some of the features of CircleCI CLI include:

- Debug and validate your CI config
- Run jobs locally
- Query CircleCI's API
- Create, publish, view and manage Orbs (they are explained later in the tutorial)

<sub>`egg="ICB8XC9cL1wvXC9cL3wgICAgICAgICAgICAgICAgIC9cICAvXAogIHwgICAgICAgICAgfCAgICAg"{{execute T2}}`</sub>
In order to install the CircleCI CLI tool, in your terminal run the following command (by clicking on it, the command will run in the interactive shell on the right): 

`curl -fLSs https://raw.githubusercontent.com/CircleCI-Public/circleci-cli/master/install.sh | bash`{{execute T1}}

By default, it is installed to the `/usr/local/bin`{{action}} directory so if you do not have write permissions to this directory, make sure to add `sudo`{{action}} to the above command.

<sub>`egg="${egg}ICAgICAgICBfX18vICBcLyAgXF9fXwogIHwgICAgICAgICAgfCAgICAgICAgICAgIHwgICAgICAg"{{execute T2}}`</sub>
