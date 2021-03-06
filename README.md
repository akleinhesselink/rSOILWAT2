
| Unix | Windows | Release | License | Coverage | Downloads |
| :---- | :---- | :---- | :---- | :---- | :---- |
[ ![Travis build status][1]][2] | [![Appveyor build status][3]][4] | [ ![github release][5]][6] | [![license][7]][8] | [![coveralls status][9]][10] | [![github downloads][11]][12] |

[1]: https://travis-ci.org/DrylandEcology/rSOILWAT2.svg?branch=master
[2]: https://travis-ci.org/DrylandEcology/rSOILWAT2
[3]: https://ci.appveyor.com/api/projects/status/3bgvcsokr27bo1uh/branch/master?svg=true
[4]: https://ci.appveyor.com/project/DrylandEcologyGit/rSOILWAT2/branch/master
[5]: https://img.shields.io/github/release/DrylandEcology/rSOILWAT2.svg?label=current+release
[6]: https://github.com/DrylandEcology/rSOILWAT2/releases
[7]: https://img.shields.io/github/license/DrylandEcology/rSOILWAT2.svg
[8]: https://www.gnu.org/licenses/gpl.html
[9]: https://coveralls.io/repos/github/DrylandEcology/rSOILWAT2/badge.svg
[10]: https://coveralls.io/github/DrylandEcology/rSOILWAT2
[11]: https://img.shields.io/github/downloads/DrylandEcology/rSOILWAT2/total.svg
[12]: https://github.com/DrylandEcology/rSOILWAT2

<br>

# rSOILWAT2
A R package for SOILWAT2.

## Considerations

We haven't really published the code yet nor prepared it for sharing (though
through our use of github made it openly accessible), it is actively and
gradually being developed by the Lauenroth lab and affiliates, and there is
no manual either - we cannot give you individual support in setting up and
running the model except if we agreed on a collaboration or similar agreement.

Not every part of the code has been extensively tested or is in a stable state.
Similarly, not every combination of model inputs and options has been evaluated
in depth and there is not guarantee for anything to work. The code comes with
no warranty and no guarantees, expressed or implied, as to suitability,
completeness, accuracy, and whatever other claim you would like to make.

There is no graphical user interface, help pages and available documentation
may be out of date, and you will need to write your own tools to analyse
outputs.

Note, the branch 'master' is deployable and is released with version numbers.

Please cite the package if you publish results based on simulations carried
out with our package, see `citation("rSOILWAT2")`, and we would like to hear
about your publication.

Some other references

* Bradford, J. B., D. R. Schlaepfer, and W. K. Lauenroth. 2014. Ecohydrology of
  adjacent sagebrush and lodgepole pine ecosystems: The consequences of climate
  change and disturbance. Ecosystems 17:590-605.
* Palmquist, K.A., Schlaepfer, D.R., Bradford, J.B., and Lauenroth, W.K. 2016.
  Mid-latitude shrub steppe plant communities: climate change consequences for
  soil water resources. Ecology 97:2342–2354.
* Schlaepfer, D. R., W. K. Lauenroth, and J. B. Bradford. 2012. Ecohydrological
  niche of sagebrush ecosystems. Ecohydrology 5:453-466.


References for the original version of "Soilwat"

* Parton, W.J. (1978). Abiotic section of ELM. In: Grassland simulation model
  (ed. Innis, G.S.). Springer New York, NY, pp. 31-53.
* Sala, O.E., Lauenroth, W.K. & Parton, W.J. (1992). Long-term soil-water
  dynamics in the shortgrass steppe. Ecology, 73, 1175-1181.


<br>

### Obtain the source package

There are several options:

- Download the
  [package zip file](https://github.com/DrylandEcology/rSOILWAT2/archive/master.zip)
  via your web browser.

- Use git to clone and get submodules in one line
  ```
  git clone -b master --single-branch --recursive https://github.com/DrylandEcology/rSOILWAT2.git rSOILWAT2
  ```


### Installation

'rSOILWAT2' will compile the c code of
[SOILWAT2](https://github.com/DrylandEcology/SOILWAT2). Your computer must be
set up adequately.
- If you use a Windows OS, then you need the
  [Rtools](http://cran.us.r-project.org/bin/windows/Rtools/)
  installed that match your R version; please find further information for
  instance [here](https://www.biostat.wisc.edu/~kbroman/Rintro/Rwinpack.html).
- If you use a macOS, then you need [Xcode](https://developer.apple.com/xcode/) and
  its [command-line tools](https://developer.apple.com/library/content/technotes/tn2339/_index.html)
  installed; please find further information for instance
  [here](https://railsapps.github.io/xcode-command-line-tools.html).


After you downloaded the source package, run
```
R CMD INSTALL rSOILWAT2
```

Or do all at once from within R:
```{r}
system2(command = "git", args = "clone -b master --single-branch --recursive https://github.com/DrylandEcology/rSOILWAT2.git rSOILWAT2")
tools::Rcmd(args = paste("INSTALL rSOILWAT2"))
```

### Binary package version
If you want a binary version of the 'rSOILWAT2' package (e.g., to distribute to
someone without development tools) for a platform to which you do not have
access, then you may consider using one of the cloud services (no endorsements):
- https://builder.r-hub.io offers different Linux, Windows, and mac OS flavors
  as targets
- http://win-builder.r-project.org/ offers Windows OS as target

Alternatively, you may access the previous binary package version for
Windows OS from our CI appveyor service if the build was successful and an
artifact was generated for the binary package (this would be named
'rSOILWAT2_X.Y.Z.zip' with version number X.Y.Z) at
- https://ci.appveyor.com/project/dschlaep/rSOILWAT2/build/artifacts
If the latest build should have failed, then you may want to check out the
'History' tab for binaries of older versions.
- After you downloaded the binary package, open R, and run
  ```{r}
  install.packages(pkgs = "path/to/downloaded/zipfile.zip", repos = NULL)
  ```


<br>


### For code contributors only

__Follow our guidelines__ as detailed [here](https://github.com/DrylandEcology/workflow_guidelines)

__Tests, documentation, and code__ form a trinity
- Code documentation
  * Read the [section 'Object documentation' in Wickham's book 'R packages'](http://r-pkgs.had.co.nz/man.html)
  * Use [roxygen2](https://cran.r-project.org/web/packages/roxygen2/vignettes/formatting.html)
    to write inline code documentation
  * Update help pages and NAMESPACE with the command `devtools::document()`
  * Ideally, add examples to function documentation and check these examples
    with the command `devtools::run_examples()`
- Code tests
  * Read the [section 'Testing' in Wickham's book 'R packages'](http://r-pkgs.had.co.nz/tests.html)
  * Unit tests
    * Use [testthat](https://github.com/hadley/testthat) to add unit tests to the
      existing framework
    * Run unit tests locally with the command `devtools::test()`
    * These unit tests will also be run on the command-line with `R CMD check .`
      which you can run also with `devtools::check()`
    * The command-line check will be run on the continuous integration frameworks
      'travis' and 'appveyor' when commits are pushed
    * Development/feature branches can only be merged into master if they pass
      all checks
  * Integration tests/checks: run a default example and look at some of the
      output (see also `?sw_exec`), e.g.,
      ```{r}
      path_demo <- system.file("extdata", "example1", package = "rSOILWAT2")
      x <- sw_exec(dir = path_demo, files.in = "files.in", quiet = TRUE)
      str(x)
      ```

__Debugging compiled code__
  * Compile C code in `src/` and `src/SOILWAT2/` in 'debugging' mode.
    This will define 'SWDEBUG' in 'SOILWAT2' source code
    (see [SOILWAT2's README](https://github.com/DrylandEcology/SOILWAT2)):
    * Install package on the command line:
      ```
      MAKEFLAGS="PKG_DEBUG=-DRSWDEBUG" R CMD INSTALL --preclean --clean .
      ```
    * Using R package 'devtools' (e.g., while running R interactively):
      ```{r}
      Sys.setenv(PKG_DEBUG="-DRSWDEBUG")
      devtools::load_all(recompile = TRUE)
      ```
  * For a more formal approach using `gdb`/`lldb`, please see the
    [section 'Debugging-compiled-code' in the 'R-exts' manual](https://cran.r-project.org/doc/manuals/R-exts.html#Debugging-compiled-code)

__How to update the submodule 'SOILWAT2'__ to the latest commit
```
git submodule update --remote #--remote: uses the latest commit; without --remote: uses the previously defined commit
git commit -am "Pulled down latest commit 'COMMIT-FLAG' for submodule SOILWAT2"
git push
```

Change branch of submodule `SOILWAT2`
```
nano .gitmodules # and change branch = <branch> to the desired <branch>

git submodule init
git submodule update --remote #--remote: uses the latest commit; without --remote: uses the previously defined commit
git commit -am "Changed to branch 'branch' commit 'COMMIT-FLAG' for submodule SOILWAT2"
git push
```

Run the script `./data-raw/prepare_testInput_objects.R` from within `rSOILWAT2/`
if the `SOILWAT2` updated included changes to the input files.


### Version numbers

We attempt to follow guidelines of [semantic versioning](http://semver.org/)
with version numbers of `MAJOR.MINOR.PATCH`.
If the version numbers changes, then the following files must be updated
* `DESCRIPTION``: adjust lines 'Version' and 'Date'
* optionally, `R/zzz.R`: adjust package startup message in function `.onAttach`

### How to contribute
You can help us in different ways:

1. Reporting [issues](https://github.com/DrylandEcology/rSOILWAT2/issues)
2. Contributing code and sending a [pull request](https://github.com/DrylandEcology/rSOILWAT2/pulls)

In order to contribute to the code base of this project, you should first
contact the Lauenroth Lab. We retain any decision to accept your
suggestions/contributions or not.


<br>


# Code of conduct
Please note that this project is released with a
[Contributor Code of Conduct](CONDUCT.md). By participating in this project you
agree to abide by its terms.


# License
This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, [version 3 of the License](LICENSE).

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.


<br>

# Funding
Work on this package has been supported by various funds managed by
Dr. Bill Lauenroth (Yale University), Dr. John Bradford (USGS), and
Dr. Daniel Schlaepfer.


<br>

# Notes

__Organization renamed from Burke-Lauenroth-Lab to DrylandEcology on Dec 22, 2017__

All existing information should [automatically be redirected](https://help.github.com/articles/renaming-a-repository/) to the new name.
Contributors are encouraged, however, to update local clones to [point to the new URL](https://help.github.com/articles/changing-a-remote-s-url/), i.e.,
```
git remote set-url origin https://github.com/DrylandEcology/rSOILWAT2.git
```


__Repository renamed from Rsoilwat (Rsoilwat31) to rSOILWAT2 on Feb 23, 2017__

All existing information should [automatically be redirected](https://help.github.com/articles/renaming-a-repository/) to the new name.

Contributors are encouraged, however, to update local clones to [point to the new URL](https://help.github.com/articles/changing-a-remote-s-url/), i.e.,
```
git remote set-url origin https://github.com/DrylandEcology/rSOILWAT2.git
```
If you have installed a previous version as R package, then you may consider
removing the old version with
```{r}
remove.packages("Rsoilwat31")
```

