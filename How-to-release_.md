# How to release a new version of AlaSQL

AlaSQL uses [git flow](http://danielkummer.github.io/git-flow-cheatsheet/) to manage development and [Semantic Versioning](http://semver.org) to manage versioning. 

**In practice the result is that the master branch us never updated without updating the version number.**
That includes changes like minor corrections to documentation files such as README.md. 

The following is a checklist for the team to remember the steps. Please update where you see a better way...

0. Pick the correct version number: Given a version number MAJOR.MINOR.PATCH, increment the: **MAJOR** version when you make incompatible API changes, **MINOR** version when you add functionality in a backwards-compatible manner. **PATCH** version when you make backwards-compatible bug fixes.

0. Create and switch to a new release branch (in source tree click "git flow" at the top right). Name it exactly as the new version number (for example "0.2.0"). 

0. Copy al content from https://github.com/agershun/alasql/wiki/readme into README.md

0. Update CHANGELOG.md with some words to what has changed. Select a city name the flavor of the day as part of the title

0. [Create a **draft**](https://github.com/agershun/alasql/releases/new) of the release on github. Same description as CHANGELOG.md and with release title as `"CITYNAME" (LAST_RELEASE - TODAY)` for example `"Athens" (02.06.2015 - 13.07.2015)` and 

0. Change version number in alasql.version. _Todo: Describe where its located_ 

0. Change version number in comments in alasql.js sourcecode _Todo: Describe where they are located_ 

0. Change version number in package.json

0. Change version number for Meteor _Todo: Describe where its located_ 

0. Run 'gulp', change a line in any js file in src and wait until uglyfy is done - close it. _Todo: automate npm build script - or/and make better gulp file_ 

0. Verify that 'npm test' does not give any erros

0. push package to npm

0. push package to athmospherejs (Meteor)

0. Finish release (for source tree just clicking "git-flow" at the top right corner)

0. Push both master and develop to github

0. [Finish your draft](https://github.com/agershun/alasql/releases/) of the release on github. Write the new version number in "Tag version" and select master as branch.







