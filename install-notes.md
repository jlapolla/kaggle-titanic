# Linux setup guide

## Not running Linux?

Most of us use Windows or OS X, but many tech tutorials are written for
Linux. To follow along with these tutorials, you can run Linux on a
virtual machine. I recommend using VirtualBox to create a virtual
machine, and then install the latest LTS release of Lubuntu on the
virtual machine.

# Installing dependencies (smoothly)

Running `pip install -r requirements.txt` did not go smoothly. It needs
various tools installed on the system to build all the packages. Many of
the packages listed in `requirements.txt` are also available through
`apt-get`. I hope that by installing them through `apt-get` first, it
will also install the tools I need for building the packages that `pip`
installs. Basically, it's a way to quickly install all build
dependencies.

Here are all the `apt` packages I found:

- python-numpy
- python-scipy
- python-pandas
- python-jinja2
- python-markupsafe
- python-backports.ssl-match-hostname
- ipython
- python-matplotlib
- python-nose
- python-openpyxl
- python-patsy
- python-pyparsing
- python-dateutil
- python-scikits-learn
- python-six
- python-tornado
- python-statsmodels

For each package, run `sudo apt-get install <package_name>
[<package_name> [...]]`.

I also needed to install the following additional packages:

- libfreetype6-dev

Probably need to install `libncurses5-dev` as well so `gnureadline`
builds.

Before you run `pip install -r requirements.txt` remove the last line
from `requirements.txt` (it should say "statsmodels==0.5.0"). Why? See
http://stackoverflow.com/a/11015904.
