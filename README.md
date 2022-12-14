# Aeon

Welcome to the Aeon Theme development repository.

![Aeon](https://repository-images.githubusercontent.com/537639296/331524d2-317c-4f3c-ad1d-71525b7f9050)


##### Table of Contents

- [Introduction](#introduction)
- [Description](#description)
- [Getting Started with Aeon](#getting-started-with-aeon)
- [Requirements](#requirements)
- [Deploying WordPress Locally](#deploying-wordpress-locally)
- [Development Environment Commands](#development-environment-commands)
- [How to start the development environment for the first time](#how-to-start-the-development-environment-for-the-first-time)
- [How to watch for changes](#how-to-watch-for-changes)
- [How to run a WP-CLI command](#how-to-run-a-wp-cli-command)
- [How to run the tests](#how-to-run-the-tests)
- [To restart the development environment](#how-to-restart-the-development-environment)
- [How to stop the development environment](#how-to-stop-the-development-environment)
- [How to start the development environment again](#how-to-start-the-development-environment-again)
- [Credentials](#credentials)
- [Contributing](#contributing)
- [Development](#development)
- [Experimenting](#experimenting)
- [Resources](#resources)
- [Demos](#demos)
- [Roadmap](#roadmap)
- [Credits](#credits)
- [Suggestions?](#suggestions)


## Introduction

Aeon is a hybrid theme that provides a reliable, performant foundation by seamlessly combining React and Vanilla JS with Flexbox Grid as part of its core. 


## Description

Aeon is a hybrid theme that combines performance with a robust, lightweight React and Vanilla JS foundation. On the other hand, Flexbox turns it into a fully responsive, flexible, and easy-to-extend theme that pursues to deliver quality over quantity.

The best coding standards empower it, making it an ideal theme for building scalable sites, from personal blogs to professional portfolios and mid- to large-business websites.

Multisite compatible and WooCommerce, SEO, and LMS ready, it has been carefully crafted to uphold performance, accessibility, and usability in mind.

Built to be compatible with well-coded plugins and all major page builders, including Elementor, Beaver Builder, Visual Composer, and Brizy, and most importantly, made to last an eternity.


### Getting Started with Aeon

To get started with Aeon development:

1. Set up a [WordPress](#deploying-wordpress-locally) instance.
2. Download [Aeon](https://github.com/atmostfear-entertainment/aeon/releases/tag/alpha).
3. Unzip, and upload this repository into your `/wp-content/themes/` directory.

Just in case you find the method to install WordPress locally too overwhelming, then we would recommend experimenting with [wp-env](https://developer.wordpress.org/block-editor/getting-started/devenv/), [Local](https://localwp.com/) or [DevKinsta](https://kinsta.com/devkinsta/).


#### Requirements

- [Aeon](https://github.com/atmostfear-entertainment/aeon/releases/tag/alpha)
- [WordPress 6.0+](https://wordpress.org/download/)
- PHP 7.4+
- License: [GPLv2](https://www.gnu.org/licenses/gpl-2.0.html) or later.


> **Warning**
> Please note that the documentation below is based partially on the upcoming Aeon's [Full Site Editing](https://developer.wordpress.org/block-editor/getting-started/full-site-editing/) features.


Some Aeon features and/or [pull requests](https://github.com/atmostfear-entertainment/aeon/pulls) may require the [Gutenberg plugin](https://wordpress.org/plugins/gutenberg/) trunk and will be described or tagged accordingly.

To optionally run tests locally, it will also be required:

- [Node.js](https://nodejs.org/en/)
- [Composer](https://getcomposer.org/)

You can install the test-specific development dependencies by running `npm i && composer install`.

The following test commands are then available:

- `npm run lint:css` lints and autofixes where possible the CSS
- `composer run analyze [filename.php]` statically analyzes PHP for bugs
- `composer run lint` checks PHP for syntax errors
- `composer run standards:check` checks PHP for standards errors according to [WordPress Coding Standards](https://developer.wordpress.org/coding-standards/)
- `composer run standards:fix` attempts to automatically fix errors


### Deploying WordPress Locally

Just in case you prefer to install WordPress from the ground up:

You will need a basic understanding of how to use the command line on your computer. This will allow you to set up the local development environment, start it and stop it when necessary, and run the tests.

You will need Node and npm installed on your computer. Node is a JavaScript runtime used for developer tooling, and npm is the package manager included with Node. If you have a package manager installed for your operating system, setup can be as straightforward as:

* macOS: `brew install node`
* Windows: `choco install nodejs`
* Ubuntu: `apt install nodejs npm`

If you are not using a package manager, please check the [Node.js download page](https://nodejs.org/en/download/) for installers and binaries.

You will also need [Docker](https://www.docker.com/products/docker-desktop) installed and running on your computer. Docker is the virtualization software that powers the local development environment. Docker can be installed just like any other regular application.


### Development Environment Commands

Ensure [Docker](https://www.docker.com/products/docker-desktop) is running before using these commands.


#### How to start the development environment for the first time

Start by cloning the current repository using `git clone https://github.com/WordPress/wordpress-develop.git`.

Then in your terminal move to the repository folder `cd wordpress-develop` and run the following commands:

```
npm install
npm run build:dev
npm run env:start
npm run env:install
```

Your WordPress site will accessible at http://localhost:8889. You can see or change configurations in the `.env` file located at the root of the project directory.


#### To watch for changes

If you are making changes to Aeon core files, you should start the file watcher in order to build or copy the files as necessary:

```
npm run dev
```

To stop the file watcher, please press `ctrl+c`.


#### To run a [WP-CLI](https://make.wordpress.org/cli/handbook/) command

```
npm run env:cli <command>
```

WP-CLI has a plenty of [useful commands](https://developer.wordpress.org/cli/commands/) you can use to work on your Aeon site.

Where the documentation mentions running `wp`, run `npm run env:cli` instead. For example:

```
npm run env:cli help
```


#### How to run the tests

These commands run the PHP and end-to-end test suites, respectively:

```
npm run test:php
npm run test:e2e
```


#### How to restart the development environment

You may want to restart the environment if you have made changes to the configuration in the `docker-compose.yml` or `.env` files.

You can restart the environment with:

```
npm run env:restart
```


#### How to stop the development environment

You can stop the environment when you are not using it to preserve your computer's power and resources:

```
npm run env:stop
```


#### How to start the development environment again

Starting the environment again is a single command:

```
npm run env:start
```


## Credentials

These are the default environment credentials:

* Database Name: `wordpress_develop`
* Username: `root`
* Password: `password`

To login to the site, navigate to http://localhost:8889/wp-admin.

* Username: `admin`
* Password: `password`

To generate a new password (recommended):

1. Go to the Dashboard.
2. Click the Users menu on the left.
3. Click the Edit link below the admin user.
4. Scroll down and click 'Generate password'. Either use this password (recommended) or change it, then click 'Update User'. If you use the generated password be sure to save it somewhere (password manager, etcetera).


## Contributing

Before contributing, please read the contributors' [Code of Conduct](https://github.com/atmostfear-entertainment/aeon/blob/main/CODE_OF_CONDUCT.md) and [Contributing](https://github.com/atmostfear-entertainment/aeon/blob/main/CONTRIBUTING.md) for information about how to open bug reports, contribute patches, test changes, write documentation, or get involved in any way you can.

If after reading you still wish to contribute with code, the list of [open issues](https://github.com/atmostfear-entertainment/aeon/issues) is a superb place to start scrutinising for tasks. However, [pull requests](https://github.com/atmostfear-entertainment/aeon/pulls) are preferred when linked to an existing issue.

Be advised that contributing is not just for developers. We welcome anyone willing to contribute with code, [testing](#getting-started), triage, discussion, designing while building patterns and templates, making Aeon more accessible, etcetera. So please, feel free to look through [open issues](https://github.com/atmostfear-entertainment/aeon/issues), and join wherever you feel most comfortable.


## Development
  
Aeon aims to load fewer assets as much as possible. With a very performant approach, it relies on the [Block Editor](https://developer.wordpress.org/block-editor/how-to-guides/themes/block-theme-overview/) and [Global Styles](https://developer.wordpress.org/block-editor/how-to-guides/themes/theme-json/) to provide you with the grand part of the visuals, and will progressively move toward a more Full Site Editing experience.

We strongly advise refraining from building any custom-built PHP or JavaScript-based workarounds for functionality that either Aeon or the [Block Editor](https://developer.wordpress.org/block-editor/how-to-guides/themes/block-theme-overview/) might provide. Aeon is the first of its kind, hybrid, minimalistic, lightweight, performant and aimed at individuals with color vision deficiency. So please, let us keep its code as simple as possible.

According to those last two points, Aeon has no unnecessary build process.

If you have [contributed](CONTRIBUTORS.md) to Aeon, due credit will be given. we will be updating [CONTRIBUTORS.md](CONTRIBUTORS.md) periodically with the names of contributors; however, feel free to open a [pull request](https://github.com/atmostfear-entertainment/aeon/pulls) or [issue](https://github.com/atmostfear-entertainment/aeon/issues) if we somehow omitted someone.


## Experimenting

If you wish to experiment with custom code, we will encourage you to install and use the Aeon Child for further custom customisation, or further extend it with code snippets.

| Repository | Description |
| --- | --- |
| [Aeon Child Theme](https://github.com/atmostfear-entertainment/aeon-child) | Official Aeon Child Theme |
| [Aeon Code Snippets](https://github.com/atmostfear-entertainment/aeon-snippets) | Official Aeon Code Snippets |


## Resources

Here are some resources that may be helpful to context for learning more about developing block-based themes:

- [Create a Block Theme (tutorial)](https://developer.wordpress.org/block-editor/how-to-guides/themes/create-block-theme/)
- [Full site editing development in the Gutenberg Repository](https://github.com/WordPress/gutenberg/labels/%5BFeature%5D%20Full%20Site%20Editing)
- [Block-based Theme Documentation](https://developer.wordpress.org/block-editor/how-to-guides/themes/block-theme-overview/)
- [Global Styles and theme.json Documentation](https://developer.wordpress.org/block-editor/how-to-guides/themes/theme-json/)
- [Global Styles development in the Gutenberg Repository](https://github.com/WordPress/gutenberg/issues?q=is%3Aissue+is%3Aopen+label%3A%22Global+Styles%22)
- [theme.json Documentation](https://developer.wordpress.org/block-editor/how-to-guides/themes/theme-json/)


## Demos

Unfortunately, at the moment, we do not have any demos yet. Even so, we will be toiling on quite a few uniquely crafted demos without following what typically is offered within the ecosystem.


## Roadmap

Fortunately, Aeon has a [public roadmap](https://trello.com/b/x75Zqk7W/aeon-theme-roadmap) that can be accessed to observe both its development and progress.


## Credits

The thumbnail on this README.md file:

["AEON"](https://www.midjourney.com/) generated on Midjourney by Atmostfear Entertaiment SAS, CCO


## Suggestions?

If you would wish to propose any improvements to this repository, please feel free to open an [issue](https://github.com/atmostfear-entertainment/aeon/issues) or [pull request](https://github.com/atmostfear-entertainment/aeon/pulls).