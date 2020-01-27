---
layout: default
title: "CHANGELOG Practices"
permalink: /changelog-practices/
---

# CHANGELOG Practices  <!-- omit in toc -->
- [Version Semantics for Daughtridge Sales](#version-semantics-for-daughtridge-sales)
  - [1.X.X Major Release](#1xx-major-release)
  - [X.1.X Minor Release](#x1x-minor-release)
  - [X.X.1 Patch Release](#xx1-patch-release)
- [CHANGELOG.md](#changelogmd)
  - [Updating CHANGELOG.md and Formatting scenarios when merging PR's](#updating-changelogmd-and-formatting-scenarios-when-merging-prs)
    - [For a PR merge working towards a release](#for-a-pr-merge-working-towards-a-release)
    - [For a release merging to production](#for-a-release-merging-to-production)

# Version Semantics for Daughtridge Sales

## 1.X.X Major Release 
Major releases increment the first digit by 1 and are the least used. It is only changed if the new features break backward compatibility, current features, or if it is something like a major UI/UX change that is application-wide.

## X.1.X Minor Release 
Minor releases increment the middle digit by 1 if the new features don't break any existing features and are compatible with the app in its current state.

These are often reserved for epics and longer-term projects that are based on planned release versions and should not be pushed to production until release date

Typically these are PR's branched off of `develop` or a specific `release_branch`.

 
## X.X.1 Patch Release
Patch releases increment the last digit by 1. These are releases that introduce non-breaking changes and can originate from
- Epics or Issue in an Epic that can be released when completed
- A bug 
- Patch fix

Typically these are PR's branched off of `master`.

# CHANGELOG.md
This file tracks the high-level changes of versions. It is not meant to replace version/PR/Release info from Github, nor is it supposed to be highly technical.

There are two primary user stories for the Changelog
1. A non-developer user who wants to see what features were added/removed and when this occurred.
2. A developer who wants a quick overview of when features were added/removed to be able to quickly locate the needed PR or source code in the correct repo.

Having CHANGELOG.md accessible and readable for both users creates time efficiencies.

Changelog comments should be in the **present tense**.
- Add vs Adds, Added or Adding
- Create vs Creates, Created or Creating
- Update, Fix, etc

A properly formed Git commit subject line should always be able to complete the following sentence:

If applied, this commit will ***`your subject line here`***

For example:

```
If applied, this commit will refactor subsystem X for readability
If applied, this commit will update getting started documentation
If applied, this commit will remove deprecated methods
If applied, this commit will release version 1.0.0
If applied, this commit will merge pull request #123 from user/branch
```

Notice how this doesn’t work for the other non-imperative forms:

```
If applied, this commit will fixed bug with Y
If applied, this commit will changing behavior of X
If applied, this commit will more fixes for broken stuff
If applied, this commit will sweet new API methods
```

## Updating CHANGELOG.md and Formatting scenarios when merging PR's

- If a merge is for a planned release is approved
  - Developer places all changelog notes under `## For Release` during development
  - Reviewer/Merger resolves any `CHANGELOG.md` merge conflicts for this section only
- If a merge is for a patch is approved
  - Developer places all changelog notes under `## For Release` during development
  - Reviewer/Merger updates 
    - Patch Release versions in `CHANGELOG.md` using the header format 
      - `## [2.4.16] 2019-09-25`
    - `version` prop in `store.state` to Patch Release version
    - `version` prop in `package.json`
    - Merges to production 

### For a PR merge working towards a release
```
## For Release
- Lorem ipsum [#123](https://github.com/dascosales/dev-team#123)
- Lorem ipsum [#105](https://github.com/dascosales/dev-team#105)
- Lorem ipsum [#144](https://github.com/dascosales/dev-team#144)
```

### For a release merging to production
```
## [2.4.16] 2019-09-25
- Lorem ipsum [#123](https://github.com/dascosales/dev-team#123)
- Lorem ipsum [#105](https://github.com/dascosales/dev-team#105)
- Lorem ipsum [#144](https://github.com/dascosales/dev-team#144)
```