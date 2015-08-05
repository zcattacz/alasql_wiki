#!/bin/sh

: '
# How to release a new version of AlaSQL

AlaSQL uses [git flow](http://danielkummer.github.io/git-flow-cheatsheet/) to manage development and [Semantic Versioning](http://semver.org) to manage versioning. 

**In practice the result is that the master branch us never updated without updating the version number.**
That includes changes like minor corrections to documentation files such as README.md. 



The formatting is a bit fun so it can work both as a markdown document and also as a sh script - so if you feel you trust this source you can run

```bash
curl https://raw.githubusercontent.com/wiki/agershun/alasql/how-to-release.md | sh
```

    
Version Bumping This actually comes baked into npm (it is a package manager after all). Simply run npm version patch to increment the patch number (e.g. 1.1.1 -> 1.1.2), npm version minor to increment the minor version number (e.g. 1.1.1 -> 1.2.0) or npm version major (e.g. 1.1.1 -> 2.0.0). It'll commit and tag up your package for you, all that is left is to git push and npm publish. This can be fully customised too. For example, if you don't want it running git tag, simply run it with the --git-tag-version=false flag (or set it to permanently not with npm config set git-tag-version false). Want to configure the commit message? Simply run it with the -m flag, e.g. npm version patch -m "Bumped to %s"


'

go(){


##The following is a checklist for the team to remember the steps. Please update where you see a better way...


#### # Get latest version of master and develop 
run "Make sure you have the last version of both master and develop" "git checkout develop && git pull && git checkout master && git pull"


#### # Run gulp, change a line in any js file in src and wait until uglyfy is done - close it. 
###### To do: automate npm build script - or/and make better gulp file_ 
todo "Run gulp, change a line in any js file in src and wait until uglyfy is done - close it"



#### # Verify that `npm test` does not give any errors
echo "For the checklist to continue npm test must be OK" && hitkey
npm test || exit 1
hr


#### # Copy al content from https://github.com/agershun/alasql/wiki/readme into README.md
run "Update README" "curl https://raw.githubusercontent.com/wiki/agershun/alasql/readme.md -o README.md"




#### # Update CHANGELOG.md with some words to what has changed. Select a city name the flavor of the day as part of the title. You can see [the commits](https://github.com/agershun/alasql/commits/develop) and [the roadmap](https://trello.com/b/qxz65pVi/alasql-roadmap) for inspiration to what to write


run "Update CHANGELOG.md with some words to what has changed. ${CR}Select a city name (flavor of the day) as part of the title. ${CR}Edit CHANGELOG.md and open url for roadmap + commits" "vim CHANGELOG.md && open https://github.com/agershun/alasql/commits/develop && https://trello.com/b/qxz65pVi/alasql-roadmap"



#### # Pick the correct version number: Given a version number MAJOR.MINOR.PATCH, increment the: **MAJOR** version when you make incompatible API changes, **MINOR** version when you add functionality in a backwards-compatible manner. **PATCH** version when you make backwards-compatible bug fixes.

flee "Rest of this checklist not implemented in shell script... (sorry)"

#### # #  identify new version
thisVersion=`npm view .. version`

info "Version is now: $thisVersion"


#### # Create and switch to a new release branch `git flow release start x.y.z` (in source tree click "git flow" at the top right). Name it exactly as the new version number (for example "###2.0"). 
todo "Create and switch to a new release branch"


#### # Change version number in `src/05start.js`, `src/10alasql.js` 
todo "Change version number in src/05start.js, src/10alasql.js"


#### # Change version number in package.json 
todo "Change version number in package.json"


#### # Change version number in bower.json
todo "Change version number in bower.json"


#### # Change version number for Meteor `meteor/10alasql.js`
todo "Change version number for Meteor meteor/10alasql.js"




#### # Run gulp, change a line in any js file in src and wait until uglyfy is done - close it. 
###### To do: automate npm build script - or/and make better gulp file_ 
todo "Run gulp, change a line in any js file in src and wait until uglyfy is done - close it"

#### # Verify that `npm test` does not give any errors
echo "For the checklist to continue npm test must be OK" && hitkey
npm test || exit 1
hr


#### # Finish release `git flow release finish x.y.z` (for source tree just clicking "git-flow" at the top right corner)
todo "Finish release"


#### # Push develop to github `git checkout develop && git push`
todo "Push develop to github" "git checkout develop && git push"


#### # Push master and tags to github `git checkout master && git push && git push --tags`
todo "Push master and tags to github" "git checkout master && git push && git push --tags"


#### # [Create a new github release](https://github.com/agershun/alasql/releases/new) Same description as CHANGELOG.md and with release title as `"CITYNAME" (LAST_RELEASE - TODAY)` for example `"Athens" (02.06.2015 - 13.07.2015)` You should be able to find it in the dropdown in "Tag version" - and select **master** as branch.
run "Create a new github release" "open https://github.com/agershun/alasql/releases/new"





#### # push package to npm `npm publish` 
run "push package to npm" "npm publish"


#### # push package to athmospherejs (Meteor) `cd meteor && meteor publish && cd ..` 
run "push package to athmospherejs (Meteor)" "cd meteor && meteor publish && cd .."






}


# Functions to make it all easy
: '
```
'

pause() {
 OLDCONFIG=`stty -g`
 stty -icanon -echo min 1 time 0
 dd count=1 2>/dev/null
 stty $OLDCONFIG
}
todo(){
  echo "$(echo "\033[0;101mManual action:\033[0m \033[0;32m$1\033[0m ")" 
  if [ -n "$2" ]; then
    echo "This might help you: \033[1;36m$2\033[0m"
  fi
  info "Hit a key when its done..." 
  pause
  hr
}
CR=`echo '\n.'` ###### Get a carriage return into `CR`
CR=${CR%.}
hr () {
#echo ""
clear
echo "‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗‗"
echo ""
}
run () { ###### Aks if user wants to do something
    while true; do
        read -p "$(echo "\033[0;32m$1\033[0m")${CR}Would you like to execute: $CR$(echo "\033[1;30m$2\033[0m")$CR(Yes) " yn
        case ${yn:-Y} in
            [Yy]* ) { eval $2 || { flee "Please solve the problem manually and restart this checklist"; } ; } && hr && return;;
            [Nn]* ) echo "$(echo "\033[0;101mThis step was skipped - Please fix manually...\033[0m")" && hitkey && hr && return;;
            [Qq]* ) echo "Are you a quitter?" && exit;;
            * ) echo "${CR}Please answer $(echo "\033[0;32mY\033[0mes or \033[0;31mN\033[0mo")";;
        esac
    done
}
info () {
    echo "\033[1;30m$1\033[0m"
}
hitkey () { 
     info "Hit a key to continue..." && pause 
} 
alert(){
echo "\033[0;101m$1\033[0m"
}
flee(){
echo
alert "$1"
echo
exit 1
}
check(){
clear  && echo
echo "How to release a new version of AlaSQL" && hr

#### # Check git is installed
git version > /dev/null 2>&1 || flee "Please install git before continuing"  


#### # Check git-flow is installed
git flow version > /dev/null 2>&1 || flee "Please install git-flow before continuing" 

go
}

check

echo "All Done"

exit

: '
```
' 