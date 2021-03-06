# Contribution Guide

Contributions are always welcome, however, it's helpful to read this document
in its entirety before submitting a Pull Request, report a bug, or submit a
feature request.

### Table of Contents

- [Getting Started](#getting-started)
- [Reporting a bug](#reporting-a-bug)
 - [Security disclosures](#security-disclosures)
- [Opening a pull request](#opening-a-pull-request)
- [Writing Documentation](#writing-documentation)

# Getting Started

tf-encrypted's goal is to realize the possibilities of secure,
privacy-preserving machine learning by making it easy for researchers and
practitioners to experiment with various different protocols.

We're always looking for feature ideas, protocol improvements, and
contributions! Please don't hesitate to open an issue or pull request, we'd
love to work with you to better tf-encrypted.

### Setup

**Pre-requisites**

To setup your local development environment, you'll need Python 3.5 or 3.6 and pip along with the following system tools:

- libtool
- g++
- automake
- git
- curl

You can install these using `brew` or your systems package manager (e.g. `yum` or `apt`).

**MacOS**

MacOS will have g++ already installed so omit it from the `brew install` command.

```
brew install libtool automake git curl
```

**Ubuntu**

```
sudo apt install libtool automake git curl g++
```

**Checkout**

You can checkout the project using git:

```
$ git clone https://github.com/mortendahl/tf-encrypted.git
```

**Install Dependencies**

Once the clone is complete, you can switch into the tf-encrypted library using `cd tf-encrypted` and then install the dependencies using `make bootstrap` which will error if any dependencies are missing.

Note: tf-encrypted currently only supports running alongside tensorflow 1.12.0+.

```
$ cd tf-encrypted
$ make bootstrap
```

**Begin Developing**

You should now be able to begin developing! You can check that your setup works by running our tests via `make test`.

### Finding Your First Issue

Looking to contribute to tf-encrypted but not sure what to tackle? We've labelled all of the ready issues with [help wanted](https://github.com/mortendahl/tf-encrypted/labels/help%20wanted). For those just looking to get their feet wet we've labelled bite sized issues with [good first issue](https://github.com/mortendahl/tf-encrypted/labels/good%20first%20issue).

Have an idea but an issue doesn't exist or it's not labelled with `help wanted`? No problem, feel free to kick off the conversation by suggesting a possible solution or by opening a pull request!

If you ever need help, don't hesitate to ask!

# Reporting a bug

Think you've found a bug? Let us know by opening an [issue in our tracker](https://github.com/mortendahl/tf-encrypted/issues) and apply the "bug" label!

### Security Disclosures

Security is a top priority for the project. If you have encounter a security
issue please responsible disclose it by reaching out to us via
[tfencrypted@gmail.com](mailto:tfencrypted@gmail.com).

We will work with you to mitigate the security issue and responsibly disclose
it to anyone using the project.

# Opening a Pull Request

To contribute, [fork](https://help.github.com/articles/fork-a-repo/) `tf-encrypted`, commit your changes, and [open a pull request](https://help.github.com/articles/using-pull-requests/).

You may be asked to make changes to your submission during the review process, we'll work with you on figuring out how to get your pull request ready to be merged and if any changes need to be made.

#### Before submitting

- Run the tests using `make test` which will also lint the code base
- Test your change thoroughly with unit tests where appropriate
- Don't forget to add a relevant line to the [CHANGELOG.md](../CHANGELOG.md)!
- Update the documentation if required inside the `docs` folder and any appropriate doc strings have been added or updated to public functions you changed.

#### Continuous Integration

All pull requests are run against our continuous integration suite on [Circle CI](https://circleci.com/gh/mortendahl/workflows/tf-encrypted). The entire suite must pass before a pull request is accepted.

#### Body

- Supply examples of command behaviour (command output, daemon logs, etc)
- Explain why your particular changes were made the way they are
- Reference the issue your request closes in the body of the PR with `Closes #`

# Writing Documentation

This project uses [Sphinx](http://www.sphinx-doc.org/en/master/) to generate our documentation available on [readthedocs.org](https://tf-encrypted.readthedocs.io/en/latest/index.html).

Whenever a change is made that impacts the behaviour of the API used by
consumers of this project the corresponding documentation should be updated so
users always have up to date documentation that reflects the true behaviour of
the library.

You can build the project locally using the `make docs` command which will
subsequently output the html version of our docs to your `build` folder. You
can view the docs after their built using your browser by running the command
`open build/html/index.html`.
