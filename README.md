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

TO BE CONTINUED.