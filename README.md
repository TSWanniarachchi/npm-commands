# NPM Commands

A reference guide to essential terminal commands and options for effective npm usage.

## Table of Contents
- [Basic NPM Commands](#basic-npm-commands)
- [Creating Package](#creating-package)
- [Managing Packages](#managing-packages)
- [Listing Installed Packages](#listing-installed-packages)
- [Updating Packages](#updating-packages)
- [Removing Packages](#removing-packages)
- [NPM Scripts](#npm-scripts)

<hr>

<a name="basic-npm-commands"></a>

## Basic NPM Commands

Check version number of npm:

```
npm -version
```

Or use shorthand:

```
npm -v
```

Get help on npm:

```
npm help
```

Quick help for specific command:

```
npm <command> -h
```

Example:

```
npm install -h
```

Search npm documentation and return the result:

```
npm help -search <command>
```

Example:

```
npm help -search install
```

Read documentation of any specific package online (official):

```
npm docs <package>
```

Example:

```
npm docs lodash
```

Update npm to latest version:

```
npm install npm@latest -g
```

<hr>

<a name="creating-package"></a>

## Creating Package

Initialize project and create package.json file:

```
npm init
```

:bulb: **Note:** Follow the wizard dilligently.

Initialize project and create package.json file with default values:

```
npm init --yes
```

Or use shorthand:

```
npm init --y
```

Set default author name for package.json:

```
npm config set init -author-name ‘your-name’
```

Set default license for package.json:

```
npm set init -license ‘MIT’
```

Show default author name:

```
npm config get init -author-name
```

Show default license:

```
npm get init -license
```

Delete default author name:

```
npm config delete init -author-name
```

Delete default license:

```
npm config delete init -license
```

### package.json File:

The package.json file is a crucial part of a Node.js project. It serves as a manifest that contains metadata about the project and its dependencies, scripts, and configurations. This file is essential for managing the project's dependencies, scripts, and other settings.

**Package name:** If you plan to publish your package, the most important things in your package.json are the name and version fields as they will be required. The name and version together form an identifier that is assumed to be completely unique.

Changes to the package should come along with changes to the version. If you do not plan to publish your package, the name and version fields are optional.

**Rules:**

- The name must be less than or equal to 214 characters. This includes the scope for scoped packages.
- The name can not start with a dot or an underscore.
- New packages must not have uppercase letters in the name
- The name ends up being part of a URL, an argument on the command line, and a folder name. Therefore, the name can’t contain any non-URL-safe characters.

**Version:** Version number of your package.

**Description:** It’s a string. This helps people discover your package, as it’s listed in npm search.

**Entry point:** We write a file which includes the main logic of the package/module.

**Test command:** Write test tool name.

**Git repository:** Address of git repo.

**Keywords:** It’s an array of strings. This helps people discover your package as it’s listed in npm search.

**Author:** Name of Author.

**License:** You should specify a license for your package so that people know how they are permitted to use it, and any restrictions you are placing on it.

### package-lock.json File:

The package-lock.json file is automatically generated when you run npm install in a project that has a package.json file. This file serves as a detailed manifest that ensures consistent installs across environments by locking the exact versions of the dependencies and their sub-dependencies.

<hr>

<a name="managing-packages"></a>

## Managing Packages

Install everything in package.json:

```
npm install
```

Or use shorthand:

```
npm i
```

Install a package:

```
npm install <package name>
```

Or use shorthand:

```
npm i <package name>
```

Example:

```
npm install lodash
```

Install a package as devDependency:

```
npm install <package name> --save-dev
```

Or use shorthand:

```
npm install -D <package name>
```

Example:

```
npm install lodash --save-dev
```

Uninstalling local packages:

```
npm uninstall <package name> --save
```

Or

```
npm un <package name> --save
```

Or

```
npm remove <package name> --save
```

Or

```
npm rm <package name> --save
```

Example:

```
npm rm lodash --save
```

Install global packages:

```
npm install <package name> g
```

Uninstall global packages:

```
npm uninstall <package name> g
```

Or

```
npm un <package name> g
```

Or

```
npm remove <package name> g
```

Or

```
npm rm <package name> g
```

Example:

```
npm rm lodash g
```

Install a package based on its tag:

```
npm install <package name>@<tag> --save-dev
```

Example:

```
npm install lodash@latest --save-dev
```

Install a package to specific version:

```
npm install <package name>@<version> --save-dev
```

Example:

```
npm install lodash@2.1.1 --save-dev
```

Install a package to exact specific version:

```
npm install <package name>@<version> --save-exact
```

Example:

```
npm install lodash@2.4.1 --save-exact
```

### Flags:

**-P :** Production (--save-prod)

**-D :** devDependencies (--save-dev)

**-O :** Optional (--save-optional)

**-E :** Save exact

**-g :** Global

**-S :** Save

**--no-save:** Prevents saving to dependencies

<hr>

<a name="listing-installed-packages"></a>

## Listing Installed Packages

List locally installed packages (includes all dependencies):

```
npm list
```

Or use shorthand:

```
npm ls
```

Restrict the depth of the tree by 1:

```
npm list --depth 1
```

:bulb: **NOTE:** _It gives you only immediate dependencies of the packages._

<br>
Restrict the depth of the tree by 0:

```
npm list --depth 0
```

:bulb: **NOTE:** _It gives you the list of all the packages and no dependencies for that particular package._

<br>
List globally installed packages (includes all dependencies):

```
npm list --global
```

Or

```
npm list -g
```

Restrict the depth of the tree by 0 (global packages):

```
npm list -g --depth 0
```

Or

```
npm list --global true --depth 0
```

Lists the dependencies which are outdated:

```
npm outdated
```

<hr>

<a name="updating-packages"></a>

## Updating Packages

Updates all listed packages to the latest release version:

```
npm update
```

Update specific package:

```
npm update <package> --save
```

Example:

```
npm update lodash --save
```

Update only dev dependencies:

```
npm update --dev --save-dev
```

Update all the packages globally:

```
npm update -g
```

Update specific package globally:

```
npm update -g <package>
```

Example:

```
npm update -g lodash
```

<hr>

<a name="removing-packages"></a>

## Removing Packages

Remove all unused packages(It remove modules not listed in package.json):

```
npm prune
```

More info: [@stackoverflow](https://stackoverflow.com/questions/21417014/npm-command-to-uninstall-or-prune-unused-packages-in-node-js)

<hr>

<a name="npm-scripts"></a>

## NPM Scripts

NPM scripts allow you to automate tasks in your project by running commands defined in the `scripts` section of your `package.json` file.

Popular npm script command:

- `npm start`
- `npm test`
- `npm build`

### npm start:

Runs the command specified in the "start" property of the `scripts` object in `package.json`. If no `start` script is defined, npm will attempt to run `node server.js`.

Example:

```json
{
  "scripts": {
    "start": "node app.js"
  }
}
```

To run this script:

```
npm start
```

### npm test:

Runs the command specified in the "test" property of the scripts object in package.json. This is typically used for running tests.

Example:

```json
{
  "scripts": {
    "test": "jest"
  }
}
```

To run this script:

```
npm test
```

### npm build:

Runs the command specified in the "build" property of the scripts object in package.json. This is often used for building the project for production.

Example:

```json
{
  "scripts": {
    "build": "webpack --mode production"
  }
}
```

To run this script:

```
npm run build
```

Other popular npm inbuilt script command are:

- `npm stop`
- `npm restart`
- `npm prestart`
- `npm poststart`

<hr>

