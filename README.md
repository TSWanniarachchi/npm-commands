# NPM Commands

A reference guide to essential terminal commands and options for effective npm usage.

## Table of Contents
- [Basic NPM Commands](#basic-npm-commands)
- [Creating Package](#creating-package)

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
