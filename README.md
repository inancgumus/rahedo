heroku-deployer
===============

Tasks for local rails initialization and heroku deployment.

# Install task

Use this task to init a Rails app after cloning from a git repo for the first time. It just makes things easy for you.

* Initializes bundler
* Creates, migrates, seeds and prepares development and test db
* Adds git remotes
* Precompiles assets


# Deploy task

Use this task to deploy a rails app to any Heroku environment.

Environment should be defined in config/environments/environment-name.rb (There are two classic environments for a Rails app at the start which are: staging and production).

**Usage:**

./deploy [environment] [--without-assets] [--without-app] [--without-assets-compilation] [last git deployment commit id]

* **environment: ** Staging, production, ...
* **without assets: ** Assets will not be deployed
* **without app: ** App will not be deployed (You can use this to only deploy assets or just refresh the remote copy)
* **without assets compilation: ** Assets will not be compiled locally
* **last git deployment commit id: ** Use this to reverse the remote deployment to any version of your app


**Don't forget: ** For the all the tasks you first need to make adjustments for your own needs. And you also going to chmod +x for making them executable.
