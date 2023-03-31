# Female Invest Devops - Technical Interview Home Assignment

The application has been deployed to Azure and two different environments have been set up, one for production and one for testing.

Production environment: https://femaleinvestdevops.azurewebsites.net/info

Testing environment: https://femaleinvestdevops-testing.azurewebsites.net/info

A workflow has been created using GitHub Actions which automatically deploys to Azure based on these rules:

- Whenever new code is commited to a pull request (or any other branch except "main") it automatically deploys to the test environment

- After all the checks pass, there is a possibility to merge the pull request into the main branch. When that happens the code is automatically deployed to production.

In this setup, developers are supposed to push code to personal "feature" branches/pull requests and test their changes on the testing environment and release to production afterwards. This allows for reverting easily to previous releases by reverting a commit on the main branch and pushing again, which will effectively deploy the previous version to production again.

The cloud setup also allows for splitting traffic between production and testing environments for testing purposes, as well as swapping deployment slots for virtually zero downtime.

I am overall pleased with the result of the assignment and finally I would like to list some possible future improvements to the architecture:

- Adding unit, integration and end-to-end tests. Require all tests to pass before merging into main. The current solution actually supports Jest tests but has been configured to pass without any tests for now.

- Automatically creating reports based on test results and posting them as pull request comments.

- Setting up auto-scaling based on the number of requests. Scaling up and/or out based on the needs of the system.

- Optimizing deployment time by eliminating redundant files and/or building on host.
