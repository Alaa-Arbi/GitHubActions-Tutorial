# GitHubActions-Tutorial
This is a repo, in which I track learning about GitHubActions

CI/CD steps recommendations:
- Ensure the code passes all unit tests.
- Perform code quality and compliance checks to make sure the source code meets the organization's standards.
- Check the code and its dependencies for known security issues.
- Build the code by integrating new source code from (potentially) multiple contributors.
- Ensure the software passes integration tests.
- Specify the version of the new build.
- Deliver the new binaries to the appropriate filesystem location.
- Deploy the new binaries to one or more servers.
- Determine if any of these tasks don't pass, and report the issue to the proper individual or team for resolution.


There are three types of GitHub actions: 
- container actions: can only be run in a Linux environment that GitHub hosts
- JavaScript actions: can run these actions in a VM (virtual machine) in the cloud or on-premises. JavaScript actions support Linux, macOS, and Windows environments.
- composite actions: allow you to combine multiple workflow steps within one action.

A workflow must have at least one job. A job is a section of the workflow associated with a runner. A runner can be GitHub-hosted or self-hosted, and the job can run on a machine or in a container. You specify the runner with the runs-on: attribute. Here, you're telling the workflow to run this job on ubuntu-latest. Each job has steps to complete. In our example, the step uses the action actions/checkout@v1 to check out the repository. What's interesting is the uses: ./action-a value, which is the path to the container action that you build in an action.yml file.

GitHub runners: GitHub hosted (standard and larger) vs self-hosted 

Referencing actions in Workflows:
- from published Docker container image on Docker Hub
- from public repository (make sure to use the full commit SHA)
- from same repository as your workflow file
- from enterprise marketplace
- from private repositories, but they require proper authentication and permissions

  <img width="633" height="328" alt="image" src="https://github.com/user-attachments/assets/f5c869b6-6328-4a79-a7b0-403967516c11" />
There are several components that work together to run tasks or jobs within a GitHub Actions workflow. In short, an event triggers the workflow, which contains a job. This job then uses steps to dictate which actions will run within the workflow. A job is a section of the workflow that will be associated with a runner.


Configuring Workflows: 
 - on a Schedule
 - for manual events: use "workflow_dispatch" event
 - Activity that occurs outside of GitHub: "repository_dispatch"
 - Webhook events: Webhooks in GitHub send a POST request to the URL listed with details of any subscribed events. 
