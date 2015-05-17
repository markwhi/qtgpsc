# Installing From Sources #

**Important:** _If you are upgrading to a new build of qtGpsc, you should uninstall the old one first. Follow the [uninstallation](#Uninstalling.md) instructions at the end of this document before continuing._

To build, make sure you have the prerequisites.

  * Linux kernel >= 2.6
  * CMake >= 2.6
  * GCC and make
  * Qt >= 4.5 development files and headers
  * libgps >= 2.96

openSUSE 11.3 or later users can run this to get the required packages:
> `zypper install cmake libqt4-devel libgps20`

**Important:** _At the time of this writing the latest published gpsd version
is 2.95 (published on 2010-07-13) which is **not** compatible
with this software, as we require libgps API version 5.0 or
greater. This means you will have to build [gpsd](http://gpsd.berlios.de/) from source in order to run this program, until the next version of gpsd comes out._

Once you have the required libraries, you can build and install with:
> `cd <qtgpsc_dir>`

> `./install.sh`

If your gpsd libraries are in a non-standard path, you can use:
> `cd <qtgpsc_dir>`

> `./install.sh -DCMAKE_INCLUDE_PATH=/path/to/gpsd/include -DCMAKE_LIBRARY_PATH=/path/to/gpsd/lib`

The script will escalate your privileges to root (using "sudo") to complete the
installation. If that makes you nervous, you can do each step manually. Just
take a look at what "install.sh" does and do the same thing at the console.

# Installing qtGpsc From Packages #

Binary installation packages for certain Linux distributions are available
via the openSUSE Build Service (http://build.opensuse.org/). These can be installed
through your distro's native package manager. You can also add our
repositories to be notified about future upgrades. Visit
http://navlost.eu/devel/qtgpsc for details.

Note that these packages are not "official" packages maintained by the distro
developers. If your distro provides its own packages, you should use those
instead unless you want the absolute latest code.

You can also build the distro packages yourself if you have an account at the
openSUSE Build Service (OBS). To do this, first run the "./obs-staging.sh"
script from the top-level project directory. This will prepare a tarball of
the source code and also generate the meta-package files, all of which are
placed in a subdirectory called "staging". Simply upload the contents of
this directory to OBS or use the command line "osc" tool to build packages
locally. Instructions for OBS are available at http://build.opensuse.org.

# Uninstalling qtGpsc #

To remove qtGpsc or before upgrading, follow these steps:

  1. If you installed directly from sources, run these commands as root:
> > `cd <qtgpsc_dir>/build; make uninstall`
  1. If you installed from a package, remove it via your package manager.