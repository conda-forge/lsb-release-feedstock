About lsb-release
=================

Home: https://wiki.linuxfoundation.org/lsb/start

Package license: GPL-2.0-only

Feedstock license: [BSD-3-Clause](https://github.com/conda-forge/lsb-release-feedstock/blob/master/LICENSE.txt)

Summary: LSB release detection module for Debian

Development: https://salsa.debian.org/debian/lsb

Intro
-----

This conda package provides the `lsb_release` command for Debian-based Linux
distributions such as Debian and Ubuntu. It provides a simple command-line interface
for accessing metadata about the installed Linux distribution.

Motivation
----------

Installation instructions for many Linux programs rely on the `lsb_release` command
to detect the release number and/or codename of the installed Linux distribution.
For example, as of the time of writing,
[PostgreSQL](https://www.postgresql.org/download/linux/ubuntu/) uses
the `lsb_release -cs` command to detect the proper codename for the apt repository.

The Debian-based
[lsb-release package](https://packages.debian.org/stable/lsb-release)
unfortunately depends on a system-wide installation of `python3`. This conda
package avoids the need for a system-wide installation of `python3` when a conda
environment is already available. The distribution-specific data is comes from
a tiny system package named
[distro-info-data](https://packages.debian.org/stable/distro-info-data),
which can be installed with `apt-get install -y distro-info-data`.

Examples
--------

Bash:
```bash
sudo apt-get install -y distro-info-data
mamba install -y lsb-release
lsb_release -a
```

(Substitute `conda` for `mamba` above in case you use that instead.)

Docker:
```dockerfile
FROM condaforge/mambaforge:4.10.1-0

RUN : \
    && apt-get update \
    && apt-get install -y distro-info-data \
    && rm -rf /var/lib/apt/lists/* \
    && mamba install -y lsb-release \
    && conda clean -afy \
;

RUN lsb_release -a
```


Current build status
====================


<table>
    
  <tr>
    <td>Azure</td>
    <td>
      <details>
        <summary>
          <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=13255&branchName=master">
            <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/lsb-release-feedstock?branchName=master">
          </a>
        </summary>
        <table>
          <thead><tr><th>Variant</th><th>Status</th></tr></thead>
          <tbody><tr>
              <td>linux_64_python3.10.____cpython</td>
              <td>
                <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=13255&branchName=master">
                  <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/lsb-release-feedstock?branchName=master&jobName=linux&configuration=linux_64_python3.10.____cpython" alt="variant">
                </a>
              </td>
            </tr><tr>
              <td>linux_64_python3.7.____73_pypy</td>
              <td>
                <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=13255&branchName=master">
                  <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/lsb-release-feedstock?branchName=master&jobName=linux&configuration=linux_64_python3.7.____73_pypy" alt="variant">
                </a>
              </td>
            </tr><tr>
              <td>linux_64_python3.7.____cpython</td>
              <td>
                <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=13255&branchName=master">
                  <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/lsb-release-feedstock?branchName=master&jobName=linux&configuration=linux_64_python3.7.____cpython" alt="variant">
                </a>
              </td>
            </tr><tr>
              <td>linux_64_python3.8.____cpython</td>
              <td>
                <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=13255&branchName=master">
                  <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/lsb-release-feedstock?branchName=master&jobName=linux&configuration=linux_64_python3.8.____cpython" alt="variant">
                </a>
              </td>
            </tr><tr>
              <td>linux_64_python3.9.____cpython</td>
              <td>
                <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=13255&branchName=master">
                  <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/lsb-release-feedstock?branchName=master&jobName=linux&configuration=linux_64_python3.9.____cpython" alt="variant">
                </a>
              </td>
            </tr>
          </tbody>
        </table>
      </details>
    </td>
  </tr>
</table>

Current release info
====================

| Name | Downloads | Version | Platforms |
| --- | --- | --- | --- |
| [![Conda Recipe](https://img.shields.io/badge/recipe-lsb--release-green.svg)](https://anaconda.org/conda-forge/lsb-release) | [![Conda Downloads](https://img.shields.io/conda/dn/conda-forge/lsb-release.svg)](https://anaconda.org/conda-forge/lsb-release) | [![Conda Version](https://img.shields.io/conda/vn/conda-forge/lsb-release.svg)](https://anaconda.org/conda-forge/lsb-release) | [![Conda Platforms](https://img.shields.io/conda/pn/conda-forge/lsb-release.svg)](https://anaconda.org/conda-forge/lsb-release) |

Installing lsb-release
======================

Installing `lsb-release` from the `conda-forge` channel can be achieved by adding `conda-forge` to your channels with:

```
conda config --add channels conda-forge
conda config --set channel_priority strict
```

Once the `conda-forge` channel has been enabled, `lsb-release` can be installed with:

```
conda install lsb-release
```

It is possible to list all of the versions of `lsb-release` available on your platform with:

```
conda search lsb-release --channel conda-forge
```


About conda-forge
=================

[![Powered by NumFOCUS](https://img.shields.io/badge/powered%20by-NumFOCUS-orange.svg?style=flat&colorA=E1523D&colorB=007D8A)](http://numfocus.org)

conda-forge is a community-led conda channel of installable packages.
In order to provide high-quality builds, the process has been automated into the
conda-forge GitHub organization. The conda-forge organization contains one repository
for each of the installable packages. Such a repository is known as a *feedstock*.

A feedstock is made up of a conda recipe (the instructions on what and how to build
the package) and the necessary configurations for automatic building using freely
available continuous integration services. Thanks to the awesome service provided by
[CircleCI](https://circleci.com/), [AppVeyor](https://www.appveyor.com/)
and [TravisCI](https://travis-ci.com/) it is possible to build and upload installable
packages to the [conda-forge](https://anaconda.org/conda-forge)
[Anaconda-Cloud](https://anaconda.org/) channel for Linux, Windows and OSX respectively.

To manage the continuous integration and simplify feedstock maintenance
[conda-smithy](https://github.com/conda-forge/conda-smithy) has been developed.
Using the ``conda-forge.yml`` within this repository, it is possible to re-render all of
this feedstock's supporting files (e.g. the CI configuration files) with ``conda smithy rerender``.

For more information please check the [conda-forge documentation](https://conda-forge.org/docs/).

Terminology
===========

**feedstock** - the conda recipe (raw material), supporting scripts and CI configuration.

**conda-smithy** - the tool which helps orchestrate the feedstock.
                   Its primary use is in the construction of the CI ``.yml`` files
                   and simplify the management of *many* feedstocks.

**conda-forge** - the place where the feedstock and smithy live and work to
                  produce the finished article (built conda distributions)


Updating lsb-release-feedstock
==============================

If you would like to improve the lsb-release recipe or build a new
package version, please fork this repository and submit a PR. Upon submission,
your changes will be run on the appropriate platforms to give the reviewer an
opportunity to confirm that the changes result in a successful build. Once
merged, the recipe will be re-built and uploaded automatically to the
`conda-forge` channel, whereupon the built conda packages will be available for
everybody to install and use from the `conda-forge` channel.
Note that all branches in the conda-forge/lsb-release-feedstock are
immediately built and any created packages are uploaded, so PRs should be based
on branches in forks and branches in the main repository should only be used to
build distinct package versions.

In order to produce a uniquely identifiable distribution:
 * If the version of a package **is not** being increased, please add or increase
   the [``build/number``](https://docs.conda.io/projects/conda-build/en/latest/resources/define-metadata.html#build-number-and-string).
 * If the version of a package **is** being increased, please remember to return
   the [``build/number``](https://docs.conda.io/projects/conda-build/en/latest/resources/define-metadata.html#build-number-and-string)
   back to 0.

Feedstock Maintainers
=====================

* [@maresb](https://github.com/maresb/)

