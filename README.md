# Zephyr multi-application PoC

These recipes build the OpenAMP example of Zephyr that consists of two Zephyr
applications that run on different cores of the NXP LPC54110 SOC. The sample
has been extracted from the the Zephyr repository, refactored and uploaded into
a separate
[repository](https://github.com/jkloetzke/zephyr-lpcxpresso54114-openamp).

# Prerequisites

* A x86_64 system with the Zephyr development tools installed
* Bleeding edge Bob Build Tool (https://github.com/BobBuildTool/bob)

# How to build

Clone the recipes and build them with Bob:

    $ git clone https://github.com/jkloetzke/zephyr-example-recipes.git \
	    --recurse-submodules
    $ cd zephyr-example-recipes
    $ bob dev demo::zephyr -j

This will download the toolchain and compile the Zephyr applications. The final
image can be found in:

    dev/dist/demo/zephyr/1/workspace/

# Hacking on the sources

The sample sources were cloned to
`dev/src/demo/zephyr/1/workspace/zephyr-lpcxpresso54114-openamp/`. You can find
the Zephyr sources and some required modules next to this directory. Change any
of them as you like and just run

    $ bob dev demo::zephyr -j -b

to incrementally build your changes. See the
[`bob dev` manpage](https://bob-build-tool.readthedocs.io/en/latest/manpages/bob-dev.html)
for more details about the options.
