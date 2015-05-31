# How to prepare new release?



```
// Change version in README.md
// Change version in package.json
// Change version in .bower.json
// Check CHANGELOG.md
// Change version in src/05start.js
// Change version in src/10alasql.js
// Change version in meteor/10alasql.js

> git add --all
> git commit -m 'Release 0.1.10'
> git flow release start 0.1.10
// resolve all merge conflicts
> git flow release finish 0.1.10
> git checkout develop
> git push --tags
> git checkout develop
> npm publish
cd meteor
> meteor publish

// Move description from CHANGELOG.md to github.com/agershun/alasql
// Create new header for CHANGELOG.md

```