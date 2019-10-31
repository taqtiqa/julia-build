# julia-build

[![Build Status](https://travis-ci.com/jlenv/julia-build.svg?branch=master)](https://travis-ci.com/jlenv/julia-build)[![Codacy Badge](https://api.codacy.com/project/badge/Grade/d33f741a507b4cee99ab9d4931ae1163)](https://www.codacy.com/manual/taqtiqa-mark/jlenv-julia-build?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=jlenv/julia-build&amp;utm_campaign=Badge_Grade)[![CodeFactor](https://www.codefactor.io/repository/github/jlenv/julia-build/badge)](https://www.codefactor.io/repository/github/jlenv/julia-build) [![Coverage Status](https://coveralls.io/repos/github/jlenv/jlenv/badge.svg?branch=master)](https://coveralls.io/github/jlenv/jlenv?branch=master) [![codecov](https://codecov.io/gh/jlenv/julia-build/branch/master/graph/badge.svg)](https://codecov.io/gh/jlenv/julia-build)

`julia-build` is a command-line utility tool that makes it easy to compile,
install and remove virtually any version of [Julia](https://www.julialang.org),
using downloaded source files.

Julia-build is exposed as a plugin for [jlenv](https://github.com/jlenv/julia-build)
that provides the `jlenv install` command.
Or simply as `julia-build` when used as a standalone program.

## Table of Contents

<!--ts-->
* [Installation](#installation)
* [Upgrading](#upgrading)
* [Usage](#usage)
* [Documentation](#documentation)
<!-- Added by: Mark Van de Vyver, at: Tue 10 Sep 18:47:40 AEST 2019 -->
<!--te-->

## Installation

Manages gcc versions using `update-alternatives`/`alternatives`:

1. Debian/Ubuntu package: `dpkg`
1. RHEL/CentOS/Fedora package: `chkconfig`

```sh
# As an jlenv plugin
mkdir -p "$(jlenv root)"/plugins
git clone https://github.com/jlenv/julia-build.git "$(jlenv root)"/plugins/julia-build

# As a standalone program
git clone https://github.com/jlenv/julia-build.git
PREFIX=/usr/local ./julia-build/install.sh
```

## Upgrading

```sh
# As an jlenv plugin
cd "$(jlenv root)"/plugins/julia-build && git pull
```

## Usage

### Basic Usage

```sh
# As an jlenv plugin
jlenv install --list                    # lists all available versions of Julia
jlenv install v1.0.1                    # installs Julia v1.0.1 to ~/.jlenv/versions

# As a standalone program
julia-build --definitions               # lists all available versions of Julia
julia-build 1.0.1 ~/local/julia-v1.0.1  # installs Julia v1.0.1 to ~/local/julia-1.0.1
```

julia-build does not check for system dependencies before downloading and
attempting to compile the Julia source. Please ensure that [all requiredlibraries](https://github.com/JuliaLang/julia#required-build-tools-and-external-libraries)
are available on your system.
The Chef [jlenv](https://github.com/jlenv/jlenv-cookbook) cookbook automatically
ensures system dependencies are in place.

## Documentation

Please see `julia-build` [documentation page](https://jlenv.github.io/julia-build)
for more detail and solutions to common problems.

## Requested Contributor Conduct

In the interest of fostering an excellent code base, we try to encourage anyone
to participate in our project. Please do likewise.
