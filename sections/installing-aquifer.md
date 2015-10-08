# Installing Aquifer

Aquifer is an npm module, and can be installed by running:

```bash
npm install -g aquifer
```

## Installing for development
You can install Aquifer directly from the git repository. This is useful if you want to contribute to Aquifer core, or test upcoming versions.

* Ensure that node.js is installed.
  * We suggest using [nvm](https://github.com/creationix/nvm).
  * Be sure that your `NODE_PATH` environment variable is set correctly.
* Clone this repository into any directory.
* Within the Aquifer repository directory, run `npm link`.
* Run `aquifer` in your terminal, and ensure that it returns CLI documentation.
