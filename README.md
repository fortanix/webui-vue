# webui-vue

webui-vue is a web-based user interface for the OpenBMC firmware stack built on
[Vue.js](https://vuejs.org/).

## How to make PRs to this repo for Fortanix specific changes?
- Checkout and pull  the latest ```series3-openbmc``` branch (all the PRs should be merged to this branch)
- Create a dev branch from ```series3-openbmc```
- Once you are done making changes, you should test the changes (at least the build). The way to do this is to push the changes to remote and then take the commit
  hash and the name of the dev branch and update it in ```asrock-openbmc/meta-phosphor/recipes-phosphor/webui/webui-vue_git.bb``` file.
  The fields are ```SRC_URI``` (change the ```branch``` field to dev branch name) and ```SRCREV``` to the dev branch commit. 
  (repo link - https://bitbucket.org/fortanix/asrock-openbmc/src/main/). Once you have updated the dev branch name and commit hash, you can build openbmc by
  following the instructions https://bitbucket.org/fortanix/asrock-openbmc/src/main/README.md . 
- Once the build suceeds, raise a PR to ```series3-openbmc``` branch and wait for CI to pass. 
- Once the PR is merged, please raise a PR to update the ```SRCREV``` in ```asrock-openbmc/meta-phosphor/recipes-phosphor/webui/webui-vue_git.bb``` with the
  latest commit hash of ```series3-openbmc``` branch of this repo (```webui-vue```). Please  make sure that the ```branch``` field in ```SRC_URI```
  is kept to ```series3-openbmc```.
  

## Hold on... What happened to phosphor-webui?

[phosphor-webui](https://github.com/openbmc/phosphor-webui) was built on
AngularJS and [AngularJS goes End of Life](https://www.convective.com/angularjs-end-of-life/)
June 30, 2021, this repository is its replacement.

## When will this new Vue.js application reach feature parity with phosphor-webui?

Several, mostly minor, features remain for feature parity. See [GitHub Issues label:phosphor-webui-feature-parity](
https://github.com/openbmc/webui-vue/issues?q=is%3Aissue+is%3Aopen+label%3Aphosphor-webui-feature-parity)
for the complete list.

## Why will this application be better?

As mentioned, this application is built using Vue.js, a modern open-source
Model-View-ViewModel JavaScript framework supported by an active community and
strong documentation. It has been architected to allow organizations to easily
update the theme to support their brand. This rewrite takes advantage of
front-end development best practices and does not suffer from some of the
anti-patterns that exist in phosphor-webui today.

## Should I switch to webui-vue from phosphor-webui?

That is up to you. Several companies have switched.
- [Commit moving several systems to webui-vue](https://github.com/openbmc/openbmc/commit/4a3fa4d6d865b46ba54f2652c82f58a406455ebc)
- [Discussion about webui-vue being the standard](https://lists.ozlabs.org/pipermail/openbmc/2020-September/023160.html)

webui-vue although still missing a few features that were in
phosphor-webui, as mentioned above, has the following additional features:
- Ability to easily theme to meet brand guidelines
- Accessibility
- Full Redfish
- Improved user experience based on user feedback
- Language translation-ready
- Modern front-end framework with an active community and future development
roadmap

## How can I get involved?
- Visit the [CONTRIBUTING.md](CONTRIBUTING.md) for more on how to contribute code
- Review some code in [Gerrit](https://gerrit.openbmc-project.xyz/q/project:openbmc%252Fwebui-vue+status:open)
- Join us in the [GUI design workgroup meeting](https://github.com/openbmc/openbmc/wiki/GUI-Design-work-group).


## Documentation
The documentation for coding standards and components is located in the `docs` directory. It is created using the [VuePress](https://vuepress.vuejs.org/) static site generator. Information about how to write documentation can be found on the [VuePress website](https://vuepress.vuejs.org/).
