# DOTNET CORE CI PIPELINE EXAMPLE: 
Goal to have dotnet core c# example pipelines for major git source control dev ops including github, azure devops, gitlab, bitbucket, and etc. Should auto run only on a new pull request, show test results in native ui per website, code coverage, and some additional manual steps running code quality analysis. Badge support native is also nice or from https://shields.io/category/build.
Originally off of [gitlab-ci-example-dotnetcore](https://gitlab.com/tobiaskoch/gitlab-ci-example-dotnetcore).  

## Contribution

* Please do a pull request to the proper source control pipeline that you are trying to update.

## TOC
* GitHub Actions
* Bitbucket
* Azure DevOps
* Gitlab pipelines

### [ ] [GitHub Actions](https://github.com/lastlink/dotnet-ci-pipelines) [![Actions Status](https://github.com/lastlink/dotnet-ci-pipelines/workflows/.net%20core/badge.svg)](https://github.com/lastlink/dotnet-ci-pipelines/actions)

* [limits](https://help.github.com/en/github/setting-up-and-managing-billing-and-payments-on-github/about-billing-for-github-actions) 2,000 (per month) to 20 concurrent jobs support windows, ubuntu, mac
    * doesn't currently support retry and max timeout although will cancel when limit reached.
* [ ] Badges - workflow
* [x] api docs - docfx html only
* [!] Tests - no display just logs and work flow
* [ ] CodeClimate issues with non npm and docker in docker
* [x] resharper cli - no manual triggers support
* [x] security dependency scan - snyk
* [x] artifacts 

### [ ] [Bitbucket](https://bitbucket.org/lastlink/dotnet-ci-pipelines/src)
* [limits](https://confluence.atlassian.com/bitbucket/limitations-of-bitbucket-pipelines-827106051.html) 50 minutes per month, support docker images
* [ ] Badges
* [x] api docs - docfx html only
* [x]  Tests - working display
    * [x] junit works fine
    * [x] print out code coverage in log, not natively supported
* [!] CodeClimate - docker in docker throwing an error
    * `docker: Error response from daemon: authorization denied by plugin pipelines: -v only supports $BITBUCKET_CLONE_DIR and its subdirectories.`
* [x] resharper cli
* artifacts only last 12 hrs are downloaded in the `.tar.gz` format, could not figure out the curl method

### [ ] [Azure DevOps](https://dev.azure.com/funktechno/dotnet%20ci%20pipelines) [![Build Status](https://dev.azure.com/funktechno/dotnet%20ci%20pipelines/_apis/build/status/dotnet%20ci%20pipelines?branchName=master)](https://dev.azure.com/funktechno/dotnet%20ci%20pipelines/_build/latest?definitionId=1&branchName=master)
* [limits](https://azure.microsoft.com/en-us/services/devops/pipelines/) 1,800 minutes per month on private projects
* [ ] Badges?
  * [x] build
* [x] api docs - docfx html only (pdf works locally, maybe self hosted runner)
* [x] Tests - working display
* [x] CodeClimate 3m
* [x] resharper cli
* [x] artifacts

### [ ] [Gitlab](https://gitlab.com/lastlink/dotnet-ci-pipelines) [![pipeline status](https://gitlab.com/lastlink/dotnet-ci-pipelines/badges/master/pipeline.svg)](https://gitlab.com/lastlink/dotnet-ci-pipelines/commits/master)  [![coverage status](https://gitlab.com/lastlink/dotnet-ci-pipelines/badges/master/coverage.svg)](https://gitlab.com/lastlink/dotnet-ci-pipelines/commits/master)
* [limits](https://about.gitlab.com/pricing/) 2,000 minutes per month per group or user
* [ ] Badges
    * [x] pipeline
    * [ ] coverage
        * [x] build in
        * [ ] coverlet
            * [] badge_branchcoverage [![badge_branchcoverage](https://lastlink.gitlab.io/dotnet-ci-pipelines/badge_branchcoverage.svg)](https://lastlink.gitlab.io/dotnet-ci-pipelines/badge_branchcoverage.svg)
            * [] badge_combined [![badge_branchcoverage](https://lastlink.gitlab.io/dotnet-ci-pipelines/badge_combined.svg)](https://lastlink.gitlab.io/dotnet-ci-pipelines/badge_combined.svg)
            * [] badge_linecoverage [![badge_branchcoverage](https://lastlink.gitlab.io/dotnet-ci-pipelines/badge_linecoverage.svg)](https://lastlink.gitlab.io/dotnet-ci-pipelines/badge_linecoverage.svg)
    * [ ] build per job?
* [x] api docs - docfx
* [x] Tests - Junit
* [x] Coverage - coverlet
* [x] Code Quality
    * [x] resharper clis
        * [x] inspectcode 1min
        * [x] dupfinder 1min
    * [x] CodeClimate (complexity & duplication) 10min+ 
* [x] artifacts
