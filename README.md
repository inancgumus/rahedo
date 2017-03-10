# rahedo

If you want to keep things simple and don't want to use a framework like Capistrano, then this deployer is for you.

With this deployer you don't need to use Amazon servers for the assets as with most of the other deployers. **You can deploy to any cdn**. 


# How to use?

Use **Installer** task to init a Rails app after cloning from a git repo for the first time.

- Initializes the bundler
- Creates, migrates, seeds and prepares development and test db
- Adds git remotes
- Precompiles assets

You can call this task by passing the name of the repository or _the current directory name (of your Rails project) will be assumed_.

```bash
./install railsappname
```


# How to deploy?

Use **Deployer** task to deploy your app to any Heroku environment.

Environment should be defined in `config/environments/environment-name.rb` (_There are two classic environments for a Rails app at the start which are: staging and production_).

## Usage:

```bash
./deploy [environment]                     \
         [--without-assets]                \
         [--without-app]                   \
         [--without-assets-compilation]    \
         [last git deployment commit id]
```

**Explanation of the Parameters:**

* **environment**: Staging, production, ...
* **without assets**: Assets will not be deployed
* **without app**: App will not be deployed (You can use this to only deploy assets or just refresh the remote copy)
* **without assets compilation**: Assets will not be compiled locally
* **last git deployment commit id**: Use this to reverse the remote deployment to any version of your app


**Don't forget**: For the all the tasks you first need to make adjustments for your own needs. And you will also need to `chmod +x` to make them executable.

## License

The code is released under an MIT license. See the [LICENSE](./LICENSE) file for more information.

## Contributing

Your contributions are very welcome here. I'm waiting for your PRs.
