---
layout: default
title: "Pull Request Guides"
permalink: /pr-guides/
---

# Pull Request Guides [DRAFT]  <!-- omit in toc -->

The Daughtridge Sales code review process is based heavily on the Google Engineering Practices Documentation.  Developers should be familiar with it as most items will not be duplicated in this document.

[https://google.github.io/eng-practices/](https://google.github.io/eng-practices/)

Notes below are to summarize important points or to describe Daughtridge Sales flows in more detail.

- [Shorthand](#shorthand)
- [Developer Responsibilities](#developer-responsibilities)
  - [Communication](#communication)
  - [Small Pull Requests](#small-pull-requests)
  - [You are your own QA (Quality Assurance)](#you-are-your-own-qa-quality-assurance)
  - [CHANGELOG](#changelog)
    - [Start with `For Release`](#start-with-for-release)
  - [Merging](#merging)
- [Reviewer Responsibilities](#reviewer-responsibilities)
  - [Get to the review as soon as possible](#get-to-the-review-as-soon-as-possible)
  - [Be thorough, but don't be a jerk](#be-thorough-but-dont-be-a-jerk)
    - [Review types](#review-types)

# Shorthand

- **LGTM:** Looks good to me
    - This is an approval
    - Any review that comes through as an a approval with `LGTM` , but minor changes requested, can be assumed that the reviewer is good with the developer merging the PR after the changes without an additional approval needed

- **Nit / NIT:** Nitpicking, Not very important/critical but preferred
    - This is to highlight non critical issues that do not prevent merge
    - These items should be cleaned up if possible before merging as research shows that they are not typically revisited and ultimately lead to a messier code base

# Developer Responsibilities

## Communication

Reviewers will try to get to your PR as soon as possible. However, we all try to plan our days efficiently and most of us are developing as well.

- Release a `Draft` PR as soon as you can, even if there aren't really any changes in your code yet.
    - This gives reviewers a heads up of what is in the pipe
- Let the reviewer(s) know the estimated timeline of when your PR will be ready.
    - If you are working late in the day on a PR and then ask for a review do not expect your code to be reviewed before you start your day without a conversation with the reviewer.
    - If it is an emergency patch you should already be in conversations with a reviewer so that the patch is released as smoothly as possible

## Small Pull Requests

The size of a PR is relative, however reviews happen more accurately and faster when there is less to go through. This means closing issues faster and and an ever improving improving code base.

For more information on Small PR's see  [https://google.github.io/eng-practices/review/developer/small-cls.html](https://google.github.io/eng-practices/review/developer/small-cls.html)

Be aware that a reviewer can request that you break your PR down into smaller ones.

## You are your own QA (Quality Assurance)

Daughtridge Sales does not have a QA team. 

As a member of the dev team it is your responsibility to add quality code that matches the scope, and to test your code for applicable workflows, user types and browsers.

## CHANGELOG
*See [CHANGELOG Practices](./changelog-practices) for more information*

### Start with `For Release`

- Start with all changes listed under this heading at the top of the CHANGELOG
- Give a short description followed by the issue number hyperlinked to the issue

    ## For Release
    - Fix this thing that was a bug.[#123](https://github.com/dascosales/dev-team/issues/123)

If the change is determined to be independent of other development or critical it will be pushed to release as a patch release, else it will be held for the next scheduled minor release. 

A developer should recommend the path that seems most efficient for clearing issues and releasing improvements faster. A reviewer may agree or disagree.

If the change is determined to be released as soon as possible then the CHANGELOG should by updated to the version along with the `package.json` and the `store.ts/js` file

    ## [2.2.3]
    - Fix this thing that was a bug. [#123](https://gihub.com/dascosales/dev-team/issues/123)

## Merging

Once reviewed and approved, the default is that it is the developer's responsibility to merge their code to the code base to the correct branch.

If there are merge conflicts, these need to be resolved and typically do not require an additional review unless there are questions or concerns.

# Reviewer Responsibilities

## Get to the review as soon as possible

## Be thorough, but don't be a jerk
This comes back to communication.
- Ask for clarification or reasoning if intent is not clear
  - This may lead to:
    - A rewrite of the code
    - Inline comments
    - Reconsidering approach
- Provide reason for change requested and example if possible

### Review types
- Comment
- Approve
  - Use `LGTM` and provide needed context
  - `LGTM` + `Merge after`
    - Does not require an additional approval
- Request changes
  - Be explicit or be in conversation