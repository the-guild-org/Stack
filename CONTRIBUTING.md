# Contributing to The Guild Projects

We, The Guild, would love to have contributions from each and every one of you in the community be it big or small and you are the ones who motivate us to do better than what we do today.

This document will discuss the workflow, processes and conventions we follow at The Guild so that you can quickly get onboard as a contributor.

## Our Philosophy

The Guild at its core is a group of open source developers formed to bring about a way for sustainable open source development solving real issues for real people through the [services we provide](https://the-guild.dev/services). You can know more about us [here](https://the-guild.dev/about-us). Another guideline we follow is Individuality and responsibility. This is the reason that all the projects as part of The Guild are hosted under a person's name and not an organization.

### Code Of Conduct

Please help us keep all our projects open and inclusive. Kindly follow our [Code of Conduct](./CODE_OF_CONDUCT.md) derived from [Contributor Covenant](https://www.contributor-covenant.org/) to keep the ecosystem healthy and friendly for all.

## A Typical Contributor Workflow

A typical open source contributor workflow looks like this:

- Start with any of our open source projects as an end user, following the instructions as provided in the relevant docs
- You get into trouble with the existing implementation or have an idea for a possible enhancement.
- Start searching the web (Google, Github, Stackoverflow, Docs, etc.) to see if you can find similar issues or solutions online
- If you don't find the solution you are looking for already in the community, file an issue in Github detailing the use case, details in the form of a user story for further discussions. But if your problem has already been reported by someone else and is unsolved, make sure that you upvote the issue so that it comes to our attention.
- Once the issue is filed, we will triage it and have discussions around it suggesting the possible next steps or action items labelling the issue appropriately
- If you are interested in working on the issue, ask the maintainers to assign you to the issue
- Start working on all the action items one at a time following a typical Git workflow.
  - Fork the repo
  - Clone it
  - Work on the action items by making all the changes as needed
  - Commits the changes periodically with appropriate commit messages - We highly recommend starting with a failing test and solving it before doing anything else since that will surface most of the cases it may go wrong. Also, we would recommend keeping the PRs as small as possible just focusing on the main issue which can be easy to review and action upon.
- Once you are done, send a draft PR to the original repository after making sure that all your changes are covered by appropriate tests as discussed
- Update the docs/README with all the changes as necessary keeping SEO in mind. The README should have the relevant terms the users would use typically in a Google search so that it is easily discoverable.
- Fix any code sanity issues like linting, indentation, structure, duplication and so on.
- Update the config files to reflect new versions of the packages to facilitate the build tool for releasing new versions once the PR is merged
- Remove the draft label and request the relevant maintainers for reviews
- All changes are made as per the feedback from the code reviews
- Once all changes have been made, a final review is done, the code is merged and released to the alpha channel for testing
- A final level of testing is done using the alpha version of the packages as released. If there are issues, new PRs are made to fix the issue (same process applies).
- There is a periodic or manual release of the packages for users to consume with appropriate changelog generated automatically, semver appropriately updated


## The Tooling

All projects maintained by The Guild makes use of these tooling to take care of the most important parts of the workflow.

#### Bob, The Bundler

We make use of [Bob](https://github.com/kamilkisiela/bob) which is a bundler allowing you to package and publish scoped packages under an organization scope. Bob makes use of [Rollup](https://rollupjs.org) underneath to do its build. You can find the source for the same [here](https://github.com/kamilkisiela/bob/blob/master/src/commands/build.ts). It makes use of a config file `bob.config.js` and you can see an example of the same being used [here](https://github.com/ardatan/graphql-tools/blob/master/bob.config.js)

#### Jest, The Testing Framework

We make use of [Jest](https://jestjs.io/) as the testing framework of choice. You can find `jest.config.js` in the root of every repository and you can find the test scripts within every package of the monorepo being used.

#### YARN, The Package Manager

We make use of [Yarn](https://yarnpkg.com/) and we recommend that contributors use the same too to avoid any inconsistencies

#### Github Actions, CI/CD Workflows

We make use of [Github Actions](https://github.com/features/actions) for all our CI/CD pipelines. You might want to check the `.github` folder within the root of every repository if you would like to dig into the pipeline for some reason.

#### Docusaurus, Website

We make use of [Docusaurus V2](https://v2.docusaurus.io/) for hosting all our project websites and docs which is backed by Jamstack, React and MDX.

#### Github Pages, Project website & Documentation

We make use of [Github Pages](https://pages.github.com/) for hosting the documentation we have created using Docusaurus. This is deployed automatically using the [Page Deploy Action](https://github.com/JamesIves/github-pages-deploy-action) as you make changes to the website

#### Changesets, Release, Changelogs and Versioning

We make use of [Changesets Release Action](https://github.com/changesets/action) to build and publish packages after bumping up the versions and generating the Changelogs as relevant to the commits.

#### Renovate, Dependency Management

We make use of [Renovate](https://github.com/renovatebot/renovate) to keep all our dependencies updated with the latest compatible upstream versions with automerge enabled for minor versions.

#### ESLint, Linting

We make use of [ESLint](https://eslint.org/) for maintaining sanity across all our projects with appropriate linting rules setup. You can find the rules in the `.eslintrc.json` file in the root of every repository.

#### Prettier, Formatting

We make use of [Prettier](https://prettier.io/) for maintaining all the formatting we need in our codebase. You can find the config setup in the `.prettierrc` file in the root of every repository

## Ways you can contribute

As we have mentioned [here](https://the-guild.dev/about-us), these are the different ways in which you can contribute for The Guild and join our community as a whole

- Spread the word about us - Tell people about our libraries and our services, create guides and tutorials
- Answer and help others on [Github Issues](https://github.com/the-guild-org), [Discord](), Stack Overflow, Twitter, Reddit
Contribute to our docs and also to graphql.org
Create failing tests and reproducible projects
Improve the WhatsApp clone tutorial
Schedule a free meeting for architectural review - we love to learn from you and hopefully we can give valuable advice back
Hire us to work with you - we’ll be that extra nice member on your team
Get a training with us
Join us! - Are you maintaining a popular open source library and thinking of how to spend more time doing just that?
Just contact us directly and tell us your story

## Some helpful links

- [The Guild Blog](https://the-guild.dev/blog)
- [The Guild Stack](https://the-guild.dev/open-source)
- [The GraphQL Ecosystem](https://graphql.org/code/)
- [The GraphQL Spec](http://spec.graphql.org/)