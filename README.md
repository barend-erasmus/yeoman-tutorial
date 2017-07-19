# Yeoman Tutorial

Yeoman helps you to kick-start new projects, prescribing best practices and tools to help you stay productive.

Yeoman is a command line tool which enables you the create projects from scaffolding templates referred to as generators. These generators are fully customizable and can also be parameterized.

## Installing Yeoman

Install `yo` using `npm`.

`npm install -g yo`

To test the installation, run:

`yo doctor`

which should result in the following output:

```
Yeoman Doctor
Running sanity checks on your system

√ Global configuration file is valid
√ NODE_PATH matches the npm root
√ Node.js version
√ No .bowerrc file in home directory
√ No .yo-rc.json file in home directory
√ npm version

Everything looks all right!

```

## Installing and Using a Generator

We'll be using the `generator-webapp` for this example.

First install the generator by running:

`npm install -g generator-webapp`

To create a new project, run:

`yo webapp`

You'll be prompted to answer a series of questions where after it will create the required scaffold for the project.

## Creating your Generator

a Yeoman uses Node.js modules with certain attributes as generators. The module name has to be in the format of `generator-name` and the `package.json` file need to contain `yeoman-generator` as a keyword.

This what your directory structure should look like.

```
generator-name
├───package.json
└───generators/
    ├───app/
        ├───templates
        |    └───hello-world.html
        └───index.js
```


This is what your `package.json` should look like.

```
{
  "name": "generator-name",
  "version": "0.1.0",
  "description": "",
  "files": [
    "generators"
  ],
  "keywords": ["yeoman-generator"],
  "dependencies": {
    "yeoman-generator": "^1.0.0"
  }
}
```

This should is what your `index.js` should look like.

```javascript
const Generator = require('yeoman-generator');

module.exports = class extends Generator {
    constructor(args, opts) {
        super(args, opts);
    }

    writing() {

        const obj = {
            name: this.args[0]
        };

        this.fs.copyTpl(
            this.templatePath(),
            this.destinationPath(),
            obj
        );
    }
};
```

For more details click [here](http://yeoman.io/authoring/).
