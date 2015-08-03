# How to release a new version of AlaSQL

AlaSQL uses [git flow](http://danielkummer.github.io/git-flow-cheatsheet/) to manage development and [Semantic Versioning](http://semver.org) to manage versioning. 

**In practice the result is that the master branch us never updated without updating the version number.**
That includes changes like minor corrections to documentation files such as README.md. 

The following is a checklist for the team to remember the steps. Please update where you see a better way...


0. Make sure you have the last version of both master and develop `git checkout develop && git pull && git checkout master && git pull`
    
0. Pick the correct version number: Given a version number MAJOR.MINOR.PATCH, increment the: **MAJOR** version when you make incompatible API changes, **MINOR** version when you add functionality in a backwards-compatible manner. **PATCH** version when you make backwards-compatible bug fixes.

0. Create and switch to a new release branch `git flow release start x.y.z` (in source tree click "git flow" at the top right). Name it exactly as the new version number (for example "0.2.0"). 

0. Copy al content from https://github.com/agershun/alasql/wiki/readme into README.md
0. Update CHANGELOG.md with some words to what has changed. Select a city name the flavor of the day as part of the title. You can see [the commits](https://github.com/agershun/alasql/commits/) and [the roadmap](https://trello.com/b/qxz65pVi/alasql-roadmap) for inspiration to what to write

0. [Create a **draft**](https://github.com/agershun/alasql/releases/new) of the release on github. Same description as CHANGELOG.md and with release title as `"CITYNAME" (LAST_RELEASE - TODAY)` for example `"Athens" (02.06.2015 - 13.07.2015)` 

0. Change version number in `src/05start.js`, `src/10alasql.js` 

0. Change version number in package.json 

0. Change version number in bower.json _Todo: describe how_

0. Change version number for Meteor `meteor/10alasql.js`

0. Run gulp``, change a line in any js file in src and wait until uglyfy is done - close it. _Todo: automate npm build script - or/and make better gulp file_ 

0. Verify that `npm test` does not give any erros

0. _Todo: describe how to locally test node_module works_

0. push package to npm `npm publish` 

0. push package to athmospherejs (Meteor) `cd meteor && meteor publish && cd ..` 

0. Finish release `git flow release finish x.y.z` (for source tree just clicking "git-flow" at the top right corner)

0. Push develop to github `git checkout develop && git push`

0. Push master and tags to github `git checkout master && git push && git push --tags`

0. [Finish your draft](https://github.com/agershun/alasql/releases/) of the release on github. You should be able to find it in the dropdown in "Tag version" - and select **master** as branch.

----

Todo: 

* implement https://www.npmjs.com/package/npm-check as part of the release check

* idea: implement this list as a script in npm so one can `npm release-steps`. Each step must be optional. Will be an issue to keep script and this wiki updated.





----

#!/bin/sh

:'
# Steps for making new release 

This contains a list of all the steps to make a new releasing of AlaSQL. The Idea came from how you install (this is not an install - its only for the members of the team behind the library).

The formatting is a bit fun so it can work both as a markdown document but also as a sh script - so if you feel you trust this source you can

```sh
curl https://raw.githubusercontent.com/wiki/agershun/alasql/release.md | sh
```


    curl https://raw.githubusercontent.com/wiki/agershun/alasql/readme.md -o readme.md
'

###### Functions to wait for keypress
Pause()
{
 OLDCONFIG=`stty -g`
 stty -icanon -echo min 1 time 0
 dd count=1 2>/dev/null
 stty $OLDCONFIG
}

###### Get a carriage return into `CR`
CR=`echo $'\n.'`
CR=${CR%.}

###### Aks if user wants to do something
todo () {
    while true; do
        read -p "Would you like to $1 by executing: $CR$2$CR(Yes)$CR" yn
        case ${yn:-Y} in
            [Yy]* ) $2 && return;;
            [Nn]* ) ECHO "OK - just make sure to do it your self (!). Hit a key to continue..." && Pause && return;;
            * ) echo "Please answer yes or no.";;
        esac
    done
}

##### Stub to check if git and git-flow is installed.
if ! foobar_loc="$(type -p "$foobar_command_name")" || [ -z "$foobar_loc" ]; then
  # install foobar here
fi

# Steps for making new release

## Make sure you are awesome
todo "**make new branch**" "echo I love you";

echo "All Done"


