PainfreeReleases
=================

[![Build Status](https://api.travis-ci.org/spekulatius/PainfreeReleases.svg?branch=master)](https://travis-ci.org/spekulatius/PainfreeReleases)
[![Latest Stable Version](https://poser.pugx.org/spekulatius/PainfreeReleases/version.svg)](https://github.com/spekulatius/PainfreeReleases/releases)
[![Latest Unstable Version](https://poser.pugx.org/spekulatius/PainfreeReleases/v/unstable.svg)](https://packagist.org/packages/spekulatius/PainfreeReleases)
[![Scrutinizer Code Quality](https://img.shields.io/scrutinizer/g/spekulatius/PainfreeReleases.svg)](https://scrutinizer-ci.com/g/spekulatius/PainfreeReleases?branch=master)
[![Total Downloads](https://poser.pugx.org/spekulatius/PainfreeReleases/downloads.svg)](https://packagist.org/packages/spekulatius/PainfreeReleases)
[![License](https://poser.pugx.org/spekulatius/PainfreeReleases/license.svg)](https://github.com/spekulatius/PainfreeReleases/blob/master/license.md)

PainfreeReleases makes maintaining a [CHANGELOG absolute painfree](https://github.com/spekulatius/PainfreeReleases).

:construction: *This package is still in development. Please be careful and patient, if you decide to use it.*


Features: What does it actually do?
--------------------------------

The basic idea here is pretty simple: Instead of running

```
git tag 1.2.3
```

you run

```
painfreereleases 1.2.3
```

to generate a new release in the CHANGELOG.md-file. In detail it does the following steps for you:

* Generates you a [CHANGELOG.md-file](https://github.com/spekulatius/PainfreeReleases/blob/master/CHANGELOG.md) out of your git tags and commits.
* commits it,
* and tags your release.


Requirements: What do you need?
-------------------------------

Any regular developer machine using Linux should work. Maybe Mac OS. Windows? No idea.

The only direct requirement is PHP:

 * PHP 5.4.0

Note: During the installation of PainfreeReleases [Composer](https://getcomposer.org) will be installed/updated and used to manage the dependencies.


Installation: How do I get this?
--------------------------------

*Each* user (usually developer) needs to run the following command to install *and* configure the package for *each* project:

1. change into *your project folder* and
2. adjust and run the following commands to *install and set up* painfreereleases for your project/machine:

    ```bash
    # install or update composer - we need this to manage the dependencies
    curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer;

    # install the package as a global dependency and symlink it.
    mkdir -p ~/.composer/spekulatius/painfreereleases;
    git clone git@github.com:spekulatius/PainfreeReleases.git ~/.composer/spekulatius/painfreereleases
    cd ~/.composer/spekulatius/painfreereleases
    composer install
    sudo chmod +x ~/.composer/spekulatius/painfreereleases/painfreereleases;
    sudo ln -s ~/.composer/spekulatius/painfreereleases/painfreereleases /usr/local/bin/painfreereleases;

    # run the initial steps
    painfreereleases init;

    # commit the change
    git add composer.json composer.lock CHANGELOG.md;
    git commit -m 'DOC: Adding PainfreeReleases :sunny:'
    ```



[Roadmap: See where PainfreeReleases goes](https://github.com/spekulatius/PainfreeReleases/issues)
-------------------------------------

Please see the issues for planned enhancements and the roadmap.

* Adding tests :/
* "Ignore tags" option with regex match. e.g. "^archive" to not process any tags matching this.
* Making grouping based on keywords config manageable
 * Groups should have a priority for order in the output
* Custom log message decorators to allow styling of the output e.g. with links to the issue tracker.
* Different output formats, also allowing to push to gitlab, github or bitbucket.


License :relieved:
-------

For information regarding the license see [license.md](https://github.com/spekulatius/PainfreeReleases/blob/master/license.md).
