# Fake-data-generator Contributing Guide

Hi! We're really excited that you are interested in contributing to Fake-data-generator. Before submitting your contribution, please make sure to take a moment and read through the following guidelines:

+   [Code of Conduct](https://github.com/Cambalab/fake-data-generator/blob/master/.github/CODE_OF_CONDUCT.md)
+   [Issue Reporting Guidelines](#issue-reporting-guidelines)
+   [Pull Request Guidelines](#pull-request-guidelines)
+   [Development Setup](#development-setup)
+   [Project Structure](#project-structure)

## Issue Reporting Guidelines

- Always use our [**bug**](https://github.com/Cambalab/fake-data-generator/issues/new?assignees=&labels=&template=bug_report.md&title=) or [**feature**](https://github.com/Cambalab/fake-data-generator/issues/new?assignees=&labels=&template=feature_request.md&title=) templates to create an issue.

## Pull Request Guidelines

+  The `master` branch is just a snapshot of the latest stable release. All development should be done in dedicated branches. **Do not submit PRs against the `master` branch.**

+  Checkout a topic branch from the relevant branch, e.g. `develop`, and merge back against that branch. Please follow this convention for the new branch: `issueNumber-githubUsernaame-commitTitle`.

+  Most of the contributed work should generally target the `lib` folder.

+  It's OK to have multiple small commits as you work on the PR - We may squash them before merging if necessary.

+   Make sure `npm run test:unit` passes. (see [**development setup**](#development-setup))

+   If adding a new feature:
    +   Add accompanying test case (at the moment a unit test would be enough).
    +   Provide a convincing reason to add this feature. Ideally, you should open a suggestion issue first and have it approved before working on it.

+   If fixing bug:
    +   If you are resolving a special issue, please follow the branch naming convention mentioned above.
    +   Provide a detailed description of the bug in the PR. Live demo preferred.
    +   Add appropriate test coverage if applicable.

## Development Setup

You will need [**Node.js**](http://nodejs.org) **version 8+**.

After cloning the forked repository, run:

```bash
npm install
```

### Committing Changes

We don't expect any strict convention, but we'd be grateful if you summarize what your modifications content is about when writing a commit.

### Commonly used NPM scripts

``` bash
# run unit tests
npm run test:unit

# run the unit test coverage
npm run test:coverage

# build all dist files
npm run build
```

There are some other scripts available in the `scripts` section of the `package.json` file.

The test:unit script will run the unit tests. **Please make sure to have this pass successfully before submitting a PR.** Although the same tests will be run against your PR on the CI server, it is better to have it working locally.

## Project Structure

+   **`dist`**: contains built files for distribution. Note this directory is only updated when a release happens; they do not reflect the latest changes in development branches.

+   **`test`**: contains all tests. The unit tests are written with [**Chai**](https://www.chaijs.com/) and run using [**Mocha**](https://mochajs.org/).

+   **`lib`**: contains the source code. The codebase is written in ES2015.

  +   **`create-file`**: contains simple disc writing operations.

  +   **`create-model`**: decides whether the script should create one or more documents.
  
  +   **`get-model`**: related to types of input models the script will receive.

  +   **`parse-model`**: most of the main code lives here. This is the place where new features may be added. Contains parsing operations for different types of structures.

  +   **`helpers`**: utility functions shared by the main source code.

## Attribution

This Contributing Guidelines were adapted from the [Vue.js Contributing Guide][vue-js-contributing-guide].

[vue-js-contributing-guide]: https://www.contributor-covenant.org
