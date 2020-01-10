# cpp11-example

[![Build Status][travis-badge]][travis-link]
[![codecov][codecov-badge]][codecov-link]
[![MIT License][license-badge]](LICENSE.md)

# Featues

- C++ version: `C++11`
- Build system: [`CMake`](https://cmake.org/)
- C++ compiler: `g++`
- Libraries: `STL` only
- Code coverage report: [`lcov`](http://ltp.sourceforge.net/coverage/lcov.php) (note: it should show the code coverage is below 100%)
- [`CodeCov`](https://codecov.io/) (code coverage is measured by CodeCov).
- Source: multiple files

## Prerequisites

To build the project you need to install `CMake`. ([Install instructions](https://cmake.org/install/))
To display a code coverage report in the console, install `lcov`. ([`Download lcov`](http://ltp.sourceforge.net/coverage/lcov.php), [`Instructions`](http://ltp.sourceforge.net/coverage/lcov/readme.php))

## Guide

1. Compile with code coverage instrumentation enabled [(GCC)](https://gcc.gnu.org/onlinedocs/gcc/Instrumentation-Options.html).
2. Execute the tests to generate the coverage data.
3. (Optionally) generate and customize reports with `lcov`.
4. Upload to CodeCov using the bash uploader.

## Example details

This repo can serve as the starting point for a new project. The following is worth noticing:

1. Use of a build script instead of putting the commands into `.travis.yml`

- Allows local testing
- Allows usage of `set -e` to error out with meaningfull messages on any command failure

2. Separate testing source tree

- Allows to easily enable/disable testing
- Allows usage in parent projects (you don't want to build the tests if you are consumed)
- You may want to exclude coverage of test files which is easier when they are in a separate folder.
  Remember to use **full paths** for patterns (like `'*/tests/*'`)

3. Use of travis cache to cache manually build 3rd-party dependencies (like boost)

- Speeds up build
- More can be added (e.g. `ccache`)
- Those need to be excluded from coverage info too

[1]: https://codecov.io/
[travis-badge]: https://travis-ci.com/alphaolomi/cpp11-cmake.svg?branch=master
[travis-link]: https://travis-ci.com/alphaolomi/cpp11-cmake/
[travis-image]: https://github.com/alphaolomi/cpp11-cmake/blob/master/img/TravisCI.png
[license-badge]: https://img.shields.io/badge/license-MIT-007EC7.svg
[codecov-badge]: https://codecov.io/gh/alphaolomi/cpp11-cmake/branch/master/graph/badge.svg
[codecov-link]: https://codecov.io/gh/alphaolomi/cpp11-cmake/
