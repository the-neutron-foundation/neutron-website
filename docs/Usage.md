Getting Started
===============
---

Dependencies
============

Before installing/building/running neutron, you should first install the
dependencies. you can do this via `pip3` or any other
package manager. The dependencies required are:

-   [Numpy](https://www.numpy.org/)
-   [SLY](https://github.com/dabeaz/sly)

Usage
=====

To use, either use the precompiled binaries (find them
[here](https://github.com/the-neutron-foundation/neutron/releases)),
build them yourself, or directly run the python 3 code using
[CPython](https://www.python.org/downloads/) (slow) or
[PyPy](https://pypy.org/) (very fast). It is recommended to use
[PyPy](https://pypy.org/), for its speed. If you choose to build it
yourself, you should have [Numpy](https://www.numpy.org/) installed.
Neutron can also be compiled using a python 3 compiler called
[Nuitka](https://nuitka.net/pages/overview.html). **It is recommended to
use pypy for its speed**.

### Running a file

If you plan to just run the normal source code (recommended), just pass
neutron as the package and the normal arguments after. Make sure you are
in the main directory, and not in the `neutron-repo/neutron`
path. Example:
<!-- tabs:start -->
#### ** Windows **
```bash
pypy neutron path/to/neutron/file.ntn  # Faster than python3

# OR

python neutron path/to/neutron/file.ntn  # Using default python implementation (slower)
```

To use neutron, pass the filename as the first argument to the neutron
binary if you built it from source. If you are using the binary:

``` bash
neutron.exe path/to/neutron/file.ntn
```

#### ** Linux **
```bash
pypy neutron path/to/neutron/file.ntn  # Faster than python3

# OR

python3 neutron path/to/neutron/file.ntn  # Using default python implementation (slower)
```

To use neutron, pass the filename as the first argument to the neutron
binary if you built it from source. If you are using the binary:

``` bash
./neutron.bin path/to/neutron/file.ntn
```

#### ** MacOS **
```bash
pypy neutron path/to/neutron/file.ntn  # Faster than python3

# OR

python3 neutron path/to/neutron/file.ntn  # Using default python implementation (slower)
```

To use neutron, pass the filename as the first argument to the neutron
binary if you built it from source. If you are using the binary:

``` bash
./neutron.bin path/to/neutron/file.ntn
```
<!-- tabs:end -->

### Optional Flags

#### Verbose

Option: `--verbose` or `-v`

Info: make neutron print out the parse tree and the tokens and general
debug info.

Example: `neutron file.ntn -v`

Compiling From Source
=====================

To compile from source, get
[Nuitka](https://nuitka.net/pages/overview.html). After that, go to the
source folder (the master folder) there should be a `neutron` folder in
the master folder, and run the Nuitka build commands.

<!-- tabs:start -->
#### ** Windows **
Here are the commands (run in order):

```bash
$ pip install numpy  # install numpy

$ pip install sly  # install sly

$ pip install nuitka  # install nuitka

$ git clone https://github.com/the-neutron-foundation/neutron  # get repo

$ cd neutron

$ python -m nuitka --follow-imports --include-plugin-directory=./neutron --show-progress --show-scons neutron # compile neutron using python -m flag
```

#### ** Linux **
Here are the commands (run in order):

```bash
$ pip3 install numpy  # install numpy

$ pip3 install sly  # install sly

$ pip3 install nuitka  # install nuitka

$ git clone https://github.com/the-neutron-foundation/neutron  # get repo

$ cd neutron

$ python3 -m nuitka --follow-imports --include-plugin-directory=./neutron --show-progress --show-scons neutron # compile neutron using python -m flag
```

#### ** MacOS **
Here are the commands (run in order):

```bash
$ pip3 install numpy  # install numpy

$ pip3 install sly  # install sly

$ pip3 install nuitka  # install nuitka

$ git clone https://github.com/the-neutron-foundation/neutron  # get repo

$ cd neutron

$ python3 -m nuitka --follow-imports --include-plugin-directory=./neutron --show-progress --show-scons neutron # compile neutron using python -m flag
```

<!-- tabs:end -->

After compiling, you should see a `neutron.exe` file and a `neutron.bin`
file. These are your binaries. To use the .bin binaries on Unix systems
just run `./neutron.bin`. On windows, the `.exe` file can just be run as
`neutron` in the command prompt.
