This section of the wiki will drive you to the Backend Architecture and how to start doing changes to a Process Tempo project.

== Node JS Version ==
'''<big>v 14.17.1 LTS</big>'''

== If you are using Windows ==
Install the following package globally so it will let you run the API Project with environment variables<syntaxhighlight lang="md">
npm install -g win-node-env
</syntaxhighlight>

== Folder Structure ==
Based on the [[Architecture Principles|hexagonal architecture (see Architecture Principles)]], we will use the next folders:<syntaxhighlight lang="md">
+-- src
|    +-- moduleNameFolder
|        +-- core
|            +-- dto
|            +-- entities
|            +-- interfaces
|                +-- repositories
|                +-- ports
|            +-- services
|
|        +-- infrastructure
|            +-- controllers
|            +-- repositories
|            +-- ports
|
|        moduleName.module.ts
|
|    +-- otherModuleFolder
...
</syntaxhighlight>

== Start a new Microservice Project ==

# Make sure you are using the correct version of [[Backend Startup Guide#node js version|Node JS]] Required for Micro Services.
# Go and pull the last version of [https://bitbucket.org/phil_meredith/pt4-ms-baseproject/src/master/ Base Project] (if you don't have access request it with your project lead)
# Clone the new repo where you want to start a new Microservice. (request repo with your project lead and admin permissions)
# Copy the content from pt4-ms-baseproject to the new pt4-ms repo.
## '''DO NOT COPY:''' '''<u>NODE_MODULES</u>''', '''<u>.GIT</u>'''.
# NPM Install.
# Change '''package.json''' Project name.
# Change '''main.ts''' swagger configuration to your project.
## Change title and description.
## Change tags.
# run the project to check if it compiles.
# Commit and push your changes to Master Branch.
## use as commit message: <u>'''chore: initial commit'''</u>
# Go to Bitbucket repo page.
# Go to branches and create '''develop''' branch from '''master'''
# Go to Repository Settings:
## Add all users to the repo access on User Repository Access with write permissions
### Add your Project Lead and CI/CD Developer as Admins
## Go to branching model
### Set Development branch to:
#### Use specific branch
#### select develop branch
### Set production branch to: Use main branch
## Go to Merge strategies and set it to Squash
## Go to Branch Permissions
### Add a new branch permission:
#### Select by type
##### Choose development branch
#### Set write permissions to all Admins of the repo
#### Set merge via pull request to Everybody
#### Select: Check for at least 1 approval\
#### Select: Check for at least 1 approval from default reviewers
### Add a new branch permission:
#### Select by type
##### Choose Production branch
#### Set write permissions to all Admins of the repo
#### Set merge via pull request to all Admins of the repo
## Go to Default reviewers and add your Project Lead
# Contact your CI/CD Developer to set new CI Rules for the new Repo

=== Modules ===
