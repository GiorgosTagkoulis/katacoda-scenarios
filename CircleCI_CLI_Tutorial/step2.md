After the installation, CircleCI CLI needs to be configured for your system. Run the command:

`circleci setup`{{execute T1}}

in the terminal, which will guide through the configuration. The first configuration is regarding the CircleCI API Token, while the second regarding the CircleCI Host. For the purposes of this tutorial it suffices to click the Enter key for both of them. However it is highly advised in your system to add the CircleCI API Token. 

<sub>`egg="${egg}ICAgICAgLwogIHwgICAgICAgICAgfCAgICAgICAgICAgIHwgICAgICAgICAgICAvXwogIHwgICAg"{{execute T2}}`</sub>
In order to generate a token, first you need to [Sign Up](https://circleci.com/signup/) in CircleCI, or [Log In](https://circleci.com/vcs-authorize/) if you already have an account. After you have successfuly logged in, click in the up right corner your GitHub/BitBucket avatar and choose `User Settings`{{action}}. 

![ConnectCircleCiToRepo](https://github.com/GiorgosTagkoulis/katacoda-scenarios/raw/master/CircleCI_CLI_Tutorial/assets/UserSettings.PNG)

Later, choose `Personal API Tokens`{{action}} 

![ConnectCircleCiToRepo](https://github.com/GiorgosTagkoulis/katacoda-scenarios/raw/master/CircleCI_CLI_Tutorial/assets/PersonalToken.PNG)

and create a new token

![ConnectCircleCiToRepo](https://github.com/GiorgosTagkoulis/katacoda-scenarios/raw/master/CircleCI_CLI_Tutorial/assets/CreateNewToken.PNG)

Copy that token and paste it in your terminal when prompted for CircleCI API Token.

<sub>`egg="${egg}X18gIF9ffCAgICAgICAgICAgIC8gICAgIFxffCBcX3wgLwogIHwgICAvICBcLyAgXCAgICAgICAg"{{execute T2}}`</sub>