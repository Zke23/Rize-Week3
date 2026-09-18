### 1. What Triggers this workflow to run?

The workflow is triggered by the configuration settings specified within the .yml file. It runs automatically whenever the user pushes code to the main branch. The "on" decides what triggers the workflow. In this assignment, it's "push", which triggers whenever new commits come in the specified branch. 

### 2. What are the four main steps in this workflow?

As stated within Resource the .yml document, the steps include: getting the code from the repo, validating the HTML files, check for broken links, and uploading the built site for deployment.

## 3. What does the Checkout code do?

It uses the actions/checkout@v4 action to clone my repo code from GithHub onto the virtual runner machine where the workflow executes. If you don't download code first, all of the other steps will fail because they don't have any files to search for. Every push creates a new runner where the code of the push is downloaded. It runs the test, like checking links and validating HTML, then deploys the site. After, GitHub deletes the temporary runner. 

## 4. What is the purpose of the enviroment configuration?

Environment Configuration is used to control how your application is deployed. Development, staging, and production are all methods of which you can control within the configuration. Github environments can provide deployment approvals, and protection rules specific to each environment. It helps prevent mistakes. Furthermore, environments allow for secure management of secrets and environment variables. 

## 5. How does automated deployment improve reliability compared to manual deployment?

Automated deployments help prevent human errors. For example, developers might accidently delete something or execute typos in terminal commands. Developers might forget to run link checkers and or HTML checkers locally before uploads. With automated enviroments, the workflow will hault immediately, preventing mistakes. Automated deployments execute inside a fresh VM every deployment, preventing leftover junk. 

## 6. What would happen if you pushed code to a different branch?

Pushing directly to a branch that is not main, won't trigger any workflow or job. This is because of the configeration within the .yml file that specifies that the push trigger is for main. However, opening a pull request to main will trigger the build-and-test job. This will run all checking and validatiing skipping the deployment until it's merged in. 
