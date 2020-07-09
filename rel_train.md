# Release Train for SONiC Community                                                  
  
                  
## About this Manual
This document provides general information about the various stages involved in the SONiC Releases.

# SONiC Release Overview 

Community has been making three SONiC releases per year until year 2018. From 2019, two releases are made in a year, once by mid of year and other by end of the year.

## Past SONiC Releases 
1. 201709 - https://github.com/Azure/sonic-buildimage/tree/201709
2. 201712 - https://github.com/Azure/sonic-buildimage/tree/201712
3. 201803 - https://github.com/Azure/sonic-buildimage/tree/201803
4. 201807 - https://github.com/Azure/sonic-buildimage/tree/201807
5. 201811 - https://github.com/Azure/sonic-buildimage/tree/201811
6. 201904 - https://github.com/Azure/sonic-buildimage/tree/201904
7. 201911 - https://github.com/Azure/sonic-buildimage/tree/201911
8. 202006 - https://github.com/Azure/sonic-buildimage/tree/202006

The next release is planned for 202012

# Release Process for Feature Development

SONiC release follows the standard development cycle that includes Planning, Design, Coding, Testing and Release as given below.  

![](https://github.com/pyuvarajan/Test-local/blob/master/release_train_png.png)

## Planning 
This phase includes the following activities.
1. Members/Partners should plan the feature/enhancement for a particular release train and inform the community to add it to the roadmap within a month after previous release. For example, commitment for feature development for 202012 release should happen latest by July2020. 
2. Feature owner should provide the development plan to community with tentative dates for HLD review and Code review.
3. Request the community/partners for reviewer(s) and finalize the reviewer(s).

## Design
This phase includes the following activities. 
1. Feature owner should do the design for the feature by analyzing the various possible design alternatives and prepare the design documet in markdown format.
2. Design document should explain how the feature fits into SONiC architecture and explain the design in detail. It should include command line interfaces planned, configuration database & schema details, required SAI changes, sequence daigram explaining the code flow between various modules(feature module, swss, syncd, various DBs, SAI, Kernel, management modules like CLI, swss/orchagent), containerization, dockers plan, warmboot details, build changes if required, and the unit test cases.
3. Raise Pull Request(PR) in the Azure/SONiC repository in the appropriate folder inside [doc folder](https://github.com/Azure/SONiC/tree/master/doc).
4. Inform the community about the PR and schedule the review meeting. 
5. Present the design during the review meeting. If there are multiple open questions at the end of meeting, schedule offline discussion with the reviewers and address them.
6. Address the review comments and ensure that the HLD is merged. 

All of the above design activities should be completed before fourth month of a release. Example : For 202012 release, design PR should be merged latest by Oct2020.

``` 
Example Feature : Dynamic Port Breakout - developed for 202006 release

a) Design doucment PR - https://github.com/Azure/SONiC/pull/450 
b) Design review meeting - https://groups.google.com/forum/#!msg/sonicproject/jznL7kDtfUM/RiQnZ-BsAwAJ 
c) Design review completion and minutes - https://groups.google.com/d/msg/sonicproject/kST4pB3k-Hw/c-cL03PhAwAJ 
d) Merged design document - https://github.com/Azure/SONiC/blob/master/doc/dynamic-port-breakout/sonic-dynamic-port-breakout-HLD.md

```

## Coding & Testing 
The next phase is Coding the feature. Code the feature and raise a PR for the code. All the PR pertaining to the feature should be listed and informed to the community. Plan for a code review with community, and address the review comments if any. Once the review comments are addressed, ensure that PR is merged. Testing for the code should go in parallel along with the Test report. Code PR should be raised latest by 5th month of the release.  

For example : For 202012 release, code PR should have been raised latest by Nov2020.

Periodic updates has to be given to the [Release Progress Tracking](https://github.com/Azure/SONiC/wiki/Release-Progress-Tracking-202006) sheet. All PR’s related to feature should be label/Tag in the PR in order to track the same. Code PR review and merging should be completed by last month of the release. 

For example : For 202012 release, PR should have been merged by Dec2020. 


## Release
A branch(need link) will be pulled out on the last day of the release. Image stabilization shall happen for 1 or 2 months after branching. Any feature that is not completed before the branching shall catch the next train.

For example : For 202012 release, branch will be pulled out on 31st Dec 2020. 
