# Document Name                                                  
Release Train for SONiC Community  
                          
# High Level Design Document                                   
#### Rev 0.1                                                   

# About this Manual
This document provides general information about the process on feature release train, for the SONiC Community.

# Scope                                                                                  
This document describes the scope of a SONiC Community member, and his/her contribution towards the feature release train.

# 1 Overview on SONiC Release Information

## 1.1 SONiC Release Train 
Community has been making three SONiC releases per year until year 2018. From 2019, two releases are made in a year, once by mid of year and other by end of the year.

Various stages of a release include the following.
	
#####  1.1.1 Planning 
#####  1.1.2 Design 
#####  1.1.3 Coding & Testing  
#####  1.1.4 Release  

![](https://github.com/pyuvarajan/Test-local/blob/master/release_train_png.png)

### 1.1.1 Planning 
Plan the feature/enhancement for a particular release train and inform community to add it to the roadmap. Members should inform community about feature set within a month after previous release. Provide an update to community with the plan with specific requests for HLD review dates and probable code review dates. Identify, discuss and finalize reviewer for the feature and get an assigned reviewer for the feature. 

For example : For 202012 release commitment should be given latest by July2020 and HLD and code reviewer should be assigned latest by Aug2020.

### 1.1.2 Design
The next phase after the planning would be a design phase for the feature. Prepare the HLD documet in markdown format, and raise Pull Request(PR) in the azure/SONiC repository in their appropriate feature folder (create a new folder if there isn't a existing one) "[example](https://github.com/Azure/SONiC/tree/master/doc)" and send it to community for review. Once a design is done, request for design review, and get it reviewed in community meeting. Address the review comments if any and ensure that HLD is merged. Design for the feature should be completed before fourth month of a release. 

For example : For 202012 release design PR should be merged latest by Oct2020.

Here are few existing features link mentioned below for our understanding : 

a) [Design PR](https://github.com/Azure/SONiC/pull/450)<br>
b) [Design Review meeting plan](https://groups.google.com/forum/#!msg/sonicproject/jznL7kDtfUM/RiQnZ-BsAwAJ)<br>
c) [Design review completion and minutes](https://groups.google.com/d/msg/sonicproject/kST4pB3k-Hw/c-cL03PhAwAJ)<br>
d) [Merged design document](https://github.com/Azure/SONiC/blob/master/doc/dynamic-port-breakout/sonic-dynamic-port-breakout-HLD.md)

### 1.1.3 Coding & Testing 
The next phase is Coding the feature. Code the the feature and raise a Pull request for code. All the PR pertaining to the feature should be listed and informed to the community. Plan for a code review with community, and address the review comments if any. Once the review comments are addressed, ensure that PR is merged. Testing for the code should go in parallel along with the Test report. Code PR should be raised latest by 5th month of the release.  

For example : For 202012 release, code PR should have been raised latest by Nov2020.

Periodic updates has to be given to the [Release Progress Tracking](https://github.com/Azure/SONiC/wiki/Release-Progress-Tracking-202006) sheet. All PR’s related to feature should be label/Tag in the PR in order to track the same. Code PR review and merging should be completed by last month of the release. 

For example : For 202012 release, PR should have been merged by Dec2020. 


### 1.1.4 Release
A branch(need link) will be pulled out on the last day of the release. For example : For 202012 release, branch will be pulled out on 31st Dec 2020. Image stabilization shall happen for 1 or 2 months after branching
