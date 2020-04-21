
CircleCi is a Continuous Integrations (CI) tool that empowers software engineering teams to be more productive through intelligent automation. 

Continuous integration is a practice that encourages developers to integrate their code into a `master` branch of a shared repository early and often. Instead of building out features in isolation and integrating them at the end of a development cycle, code is integrated with the shared repository by each developer multiple times throughout the day. Every time a developer commits to a shared mainline, the commit triggers an automated build and test. If build and test fails, it can be repaired quickly improving team productivity and efficiency.

CircleCI integrates with many Version Control Systems (VCS) like GitHub, GitHub Enterprise, and Bitbucket and every time a developer commits his code, CircleCI creates a pipeline and automatically runs it in a clean container, allowing the developer to test every commit. It is possible the whole team to be notified through CircleCi's slack integration, leading to quick fixes and faster deployment time.

In this tutorial, the focus is on how to install the command line interface (CLI) of CircleCI locally in your systems, set it up, validate your configuration and test a job before pushing it to a VCS. 