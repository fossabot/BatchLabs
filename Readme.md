# BatchLabs
[![Build Status](https://travis-ci.org/Azure/BatchLabs.svg?branch=master)](https://travis-ci.org/Azure/BatchLabs)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Ftimotheeguerin%2FBatchLabs.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Ftimotheeguerin%2FBatchLabs?ref=badge_shield)

**Note: BatchLabs is in beta. We don't provide any installer/packaged binaries as of now. You will need to build this app yourself.**

This is the readme for the 'master' branch which contains the latest changes, 'stable' may differ from this [Stable readme](https://github.com/Azure/BatchLabs/tree/stable)

## Description

Batch Labs is a tool to manage your Azure Batch accounts. The goal is to implement a great user experience that will help you debug, monitor and manage your pools, jobs and tasks.
It will also include expermiental features such as `Batch Templates` in the aim to improve your Batch experience. We are open to any feedback, ideas and contributions you might have.

## Getting started
#### 1. Prerequisites
- **Install node.js version `6.9` or greater. [Download](https://nodejs.org/en/download/)**
- Install python **3.6** (doesn't need to be in the path if that breaks your environment)

#### 2. Clone the repo
- At stable branch `git clone -b stable https://github.com/Azure/BatchLabs`
- Or for the latest changes `git clone https://github.com/Azure/BatchLabs`

Move to the directory `cd BatchLabs`

#### 3. Build the app with all in one command line(Windows only)
Call this command and it will check you have everything setup correctly and build the app.
```
.\scripts\install\install-windows
```
**You can skip all the other steps**

#### 4. Install the dependencies
```bash
npm install -g yarn
yarn install
pip3 install -r python/requirements.txt # or pip if on windows or only have python 3.6 installed
```
Note: You can also use `npm install` at your own risk. However please do not submit an issue if you didn't use `yarn install`. Yarn will make sure you have the right set of dependencies, which reduces the likelihood of any unexpected build issues relating to third party packages.

#### 4.5 Setup some configuration(Only in certain case)
If you didn't installed python in the path you will need to let batchlabs know where it is.
Set an environment variable called `BL_PYTHON_PATH` with that path to the python executable.
Batchlabs will look first to see if this environemnt variable is set if not try `python3` and then `python` to find an installation of python 3.6

#### 5. Build and run the application
```bash
# Make an executable, this will bundle all needed dependencies including node and python
npm run build-and-pack

# Manual
npm run build:prod
npm run electron:prod

# To debug errors
npm run build
npm run electron
```

## Developers
[Dev docs](docs/readme.md)

For developers, you can set up a development environment as follows:
**Use `yarn install` instead of `npm install`. This ensures a consistent build environment with the right set of dependencies [Migrating from npm to yarn](https://yarnpkg.com/lang/en/docs/migrating-from-npm/)**

Start the dev server
```bash
npm run dev-server
```

Start electron
```bash
# In the command line
npm run dev-electron

# In VSCode just press F5
```

The dev-server and dev-electron support hot reload for a better development experience. Simply saving a file will cause the UI to refresh to your updated changes.

*Note:* Changes to any files in the node client directory ('src/client') require restarting the application.

If you're using VSCode (recommended) we suggest you use the following extensions:
* Debugger for Chrome
* EditorConfig for VS Code
* TSLint

Please also take a look at the [coding guidelines](coding-guidelines.md) for this repo for best practices.

## Testing

[Testing doc](docs/testing.md)

## Editor

In vscode install the editorconfig extension

## Detailed commands:
**Magic command (starts the server and electron in dev mode)**
```
npm run dev
```

Build project
```
npm run build
```

Run app
```
npm run electron
```

Run watch (this will build files on save)
```
npm run watch
```

Run dev server (this will handle the refresh of files and later should have live reload)
```
npm run dev-server
```

Run dev electron (to use the dev server you need to run this)
```
npm run dev-electron
```

## License

Batch labs is licensed under MIT [See license](LICENSE)
Some icons are under Creative Commons Attribution-ShareAlike 3.0 Unported [See license](app/assets/images/logos/LICENSE)


[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Ftimotheeguerin%2FBatchLabs.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Ftimotheeguerin%2FBatchLabs?ref=badge_large)