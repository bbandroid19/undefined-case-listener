# accelerator-case-listener

The accelerator-case-listener which listens to case object data publised to Anypoint MQ and invokes respective APIs. The JSON payload is progressed to Case Process API. On successful request the message in Anypoint MQ is manually acknowleged and during failure the message is not acknowleged.

Invokes accelerator-jira-sys-api for JIRA to SFDC Case update to query the issue details from JIRA using the issue id.

## Prerequisite Setup

 - Create client application in Anypoint MQ if not created and copy the client id and client secret.
 - Create Below Queues if not created
        1) accelerator-salesforce-case-queue
        2) accelerator-salesforce-case-dl-queue
        3) accelerator-salesforce-update-case-queue
        4) accelerator-salesforce-update-case-dl-queue
        5) accelerator-salesforce-case-update-jira-dl-queue
        6) accelerator-salesforce-case-update-jira-queue
      

## Installation instructions for Studio

The following instructions assume you have already configured your Maven 
`settings.xml` file according to the Setup Guide.

- Clone the project using any Github client or Anypoint Studio Git plugin
- Import the project into your workspace
- Modify the `config-local.yaml` properties appropriately
- To run the project, right-click the project and select Run As --> Mule Application

## Deployment instructions for CloudHub

Ensure the Maven profile `CloudHub-DEV` has been properly configured in your 
`settings.xml` file. In particular, make sure the Anypoint MQ client ID and secret 
are provided.

Update the `config-dev.yaml` properties appropriately and then use one of the following 
scripts to deploy application to Cloud Hub:
   
- packageDeploy.sh or deployOnly.sh (Mac/Linux)
- packageDeploy.cmd or deployOnly.cmd (Windows)
