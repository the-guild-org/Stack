# Contributing to The Guild Projects

We, The Guild, would love to have contributions from each and every one of you in the community be it big or small and you are the ones who motivate us to do better than what we do today. In fact, The Guild itself is a group of people who started as individual contributors that just decided to work together

This document will discuss the workflow, processes and conventions we follow at The Guild so that you can quickly get onboard as a contributor. You can also contribute to the doc itself! ;) 

## Our Philosophy

The Guild at its core is a group of open source developers formed to bring about a way for sustainable open source development solving real issues for real people through the [services we provide](https://the-guild.dev/services). You can know more about us [here](https://the-guild.dev/about-us). Another guideline we follow is Individuality and responsibility. This is the reason that all the projects as part of The Guild are hosted under a person's name and not an organization ([a list of all of the projects we actively maintain](https://the-guild.dev/open-source)).

### Code Of Conduct

Please help us keep all our projects open and inclusive. Kindly follow our [Code of Conduct](./CODE_OF_CONDUCT.md) derived from [Contributor Covenant](https://www.contributor-covenant.org/) to keep the ecosystem healthy and friendly for all.

## A Typical Contributor Workflow

A typical open source contributor workflow looks like this:

1. Start with any of [our open source projects](https://the-guild.dev/open-source) as an end user, following the instructions as provided in the relevant docs
2. You get into trouble with the existing implementation or have an idea for a possible enhancement.
3. When you face an issue, make sure that you update to the latest version of the library. The issue might have been already fixed.
4. Start searching the web (Google, Github, Stackoverflow, Docs, etc.) to see if you can find similar issues or solutions online
5. In case you've found a solution, try to remember the breadcrumbs that lead you to the solution and see if you can improve and make that path shorter and easier for others that would look for the same thing. That can include improving the docs, upvoting answers on Stack Overflow, commenting on a blog post or forum, etc)
6. If you would like to contribute to the docs of a respective project, all you need to do is edit the markdown files in `website/docs` folder within the respective repository or use `Edit this page` link at the bottom of every page which will bring you to the online Github editor directly.
7. If you don't find the solution you are looking for already in the community, file an issue in Github detailing the use case, details in the form of a user story for further discussions. But if your problem has already been reported by someone else and is unsolved, make sure that you upvote the issue so that it comes to our attention. If your solution is a potential new feature, do add information on how an end user might benefit from the feature and what problem you aim to address followed by the approach you are going to take. This can help in having productive discussions around the same and finalize on the agenda for the PR.
8. The best way to make progress on an issue fast, is to help us and follow the next steps. Each step you could advance the issue in, would shorten the time for us to solve those significantly
9.  Creating a reproduction can really help us in identifying the issues you face in our environment so that we work on solving them. You can create a minimal reproduction by following these steps:
    - Create a sample repo on Github
    - Demonstrate the problem, and only the problem. Remove unnecessary dependencies, code, packages and so on which are not related to the issue.
    - Install all your dependencies related to the problem in `package.json` file if it doesn't exist. We should be able to clone it and run it on our end and be able to reproduce the problem.
    - Kindly provide instructions if any in the repository along with expected and actual behavior and a link back to the issue and any instructions/steps to running the repro locally. 
10. The next step after a reproduction is adding failing tests inside the library and this can [really add confidence](https://kentcdodds.com/blog/make-your-test-fail) on the codebase. Follow the instructions on how to clone the repo, run tests locally, find a new case that covers your scenario, make sure it fails and submit it as a pull request.
11. Start working on all the action items one at a time following a typical Git workflow.
     - [Fork the repo](https://docs.github.com/en/github/getting-started-with-github/fork-a-repo)
     - [Clone it](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository)
     - Work on the action items by making all the changes as needed
     - [Commits the changes periodically](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/committing-and-reviewing-changes-to-your-project) with appropriate commit messages - We highly recommend starting with a failing test and solving it before doing anything else since that will surface most of the cases it may go wrong. Also, we would recommend keeping the PRs as small as possible just focusing on the main issue which can be easy to review and action upon.
12. Once you are done, send a [draft PR](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests#draft-pull-requests) to the original repository after making sure that all your changes are covered by appropriate tests as discussed
13. Update the docs/README with all the changes as necessary keeping [SEO](https://searchengineland.com/guide/what-is-seo) in mind. The README should have the relevant terms the users would use typically in a Google search so that it is easily discoverable.
14. Fix any code sanity issues like linting, indentation, structure, duplication and so on.
15. Update the config files to reflect new versions of the packages to facilitate the build tool for releasing new versions once the PR is merged
16. Remove the draft label and request the relevant maintainers for reviews
17. All changes are made as per the feedback from the code reviews
18. Once all changes have been made, a final review is done, the code is merged and released to the alpha channel for testing
19. A final level of testing is done using the alpha version of the packages as released. If there are issues, new PRs are made to fix the issue (same process applies).
20. There is a periodic or manual release of the packages for users to consume with appropriate changelog generated automatically, semver appropriately updated


## The Tooling

All projects maintained by The Guild makes use of these tooling to take care of the most important parts of the workflow. We highly recommend you use these tools with your projects as well or that if you know better ones, let us know!

#### Bob The Bundler

We make use of [Bob The Bundler](https://github.com/kamilkisiela/bob) which is a bundler allowing you to package and publish scoped packages under an organization scope. Bob The Bundler makes use of [Rollup](https://rollupjs.org) underneath to do its build. You can find the source for the same [here](https://github.com/kamilkisiela/bob/blob/master/src/commands/build.ts). It makes use of a config file `bob.config.js` and you can see an example of the same being used [here](https://github.com/ardatan/graphql-tools/blob/master/bob.config.js)

In addition to what rollup does, Bob The Bundler also takes care of common and important tasks like validating `package.json` files, glob through a YARN workspace so that all files can be packaged together as scoped packages, generate multiple types of the same package (cjs, esm) and finally also validate whether the build is successful by running some test scripts.

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

We make use of [Renovate](https://github.com/renovatebot/renovate) to keep all our dependencies updated with the latest compatible upstream versions with automerge enabled for minor versions. We highly recommend for people to use it on their projects as well to make sure that you are always updated and patched from possible vulnerabilities.

#### ESLint, Linting

We make use of [ESLint](https://eslint.org/) for maintaining sanity across all our projects with appropriate linting rules setup. You can find the rules in the `.eslintrc.json` file in the root of every repository.

#### Prettier, Formatting

We make use of [Prettier](https://prettier.io/) for maintaining all the formatting we need in our codebase. You can find the config setup in the `.prettierrc` file in the root of every repository. We use tools behind the scenes to automatically run it before commits even in case you forget to do it yourself.

## Ways you can contribute other than writing code

As we have mentioned [here](https://the-guild.dev/about-us), these are the different ways in which you can contribute for The Guild and join our community as a whole

- Spread the word [about us](https://the-guild.dev/about-us) - Tell people about our libraries and our services, create guides, blog posts and tutorials
- Keep all your dependencies up to date with the latest versions. It would help you and also help us with good feedback
- Answer and help others on [Github Issues](https://github.com/the-guild-org), [Discord](https://discordapp.com/invite/xud7bH9), Stack Overflow, Twitter, [Reddit](https://www.reddit.com/r/graphql/)
- Contribute to our docs and also to [graphql.org](https://graphql.org/)
- Create [failing tests](https://kentcdodds.com/blog/make-your-test-fail) and reproducible projects
- Improve the [WhatsApp clone tutorial](https://github.com/Urigo/WhatsApp-Clone-Tutorial)
- Schedule a [free meeting](https://the-guild.dev/contact) for architectural review - we love to learn from you and hopefully we can give valuable advice back
- [Hire us](https://the-guild.dev/contact) to work with you - we’ll be that extra nice member on your team
- Get a training with us
- [Join us](https://github.com/orgs/the-guild-org/people)! - Are you maintaining a popular open source library and thinking of how to spend more time doing just that?
- Just [contact us](https://the-guild.dev/contact) directly and tell us your story

## Some helpful links

- [The Guild Blog](https://the-guild.dev/blog)
- [The Guild Stack](https://the-guild.dev/open-source)
- [The GraphQL Ecosystem](https://graphql.org/code/)
- [The GraphQL Spec](http://spec.graphql.org/)