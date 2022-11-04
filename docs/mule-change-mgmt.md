## MuleSoft Change Management Guidelines
*Disclaimer* - This document assumes that you are familiar with ServiceNow. It is *NOT* intended to be a comprehensive overview on the topic of the ServiceNow Change Management process. For more detailed information about the ServiceNow Change Process, please check out the [training material provided by the ServiceNow Team](https://collaboration.mdlz.com/:p:/r/sites/technologycentertraining/Shared%20Documents/Change%20Management/Change%20Management%20Training%20Materials/Change%20Management%20Training%20Deck%20V2.pptx?d=wd28936ac67e744b096f11bb80352f17c&csf=1&web=1)  as a starting point. 

## General Change Management Principles for EVERYONE
The below graphics have been shamelessly plagurized from the above-mentioned training documentation.  It provides a good over-arching set of guidelines for how Change Management should work.

![guidelines 1](https://user-images.githubusercontent.com/19505714/199533046-059e5d3d-f767-44cf-bfee-e5e8c8b8caf9.png)

[TL;DR](https://www.howtogeek.com/435266/what-does-tldr-mean-and-how-do-you-use-it/) - if you want to deploy a production change in MuleSoft, you need a ServiceNow change record!  As with any enterprise, we can't just blindly change APIs and their source code whenever we feel like it.  At Mondelez, [ServiceNow](https://mdlz.service-now.com) is the system of record for all IT related changes.  

Some additional helpful rules:

![change guidelines](https://user-images.githubusercontent.com/19505714/199530792-6e5aac53-fa4e-4327-8e3e-18e6edb2f084.png)

### So How Does this Apply To MuleSoft?
Great Question.  Here's a quick summary of what you need to know:

 * Source code for MuleSoft APIs are managed in GitHub Repositories.  Each API has it's own repository.  The "main" branch of the repository represents the code that should be deployed in production.
 * Every PRODUCTION Github Pull Request (PRs to main) should be traceable back to an APPROVED ServiceNow Change Requests. An approved change record is required for every production API deployment.  No Approved Change Record?  No Deployment!  No Exceptions.  Note: Change Requests are NOT required to merge code to other branches within GitHub (features, develop, test, release).
 * Developers create Pull Requests to signal their code is ready to go to production.  When a developer submits the Pull Request, an administrative review is triggered within GitHub.  Generally speaking, change requests should be created in ServiceNow at the time you are starting to plan your release to production.  Note that CAB meets on a periodic basic to review changes.  Please take the CAB schedule into account to ensure reviews are done ahead of time.
 * Deployments (eg. Production Changes) are controlled by administrators in GitHub; they are tightly controlled and automated.  Pull Request should NOT be approved without a corresponding approved Change Record.  When a Pull Request is approved in GitHub, the source code will be merged to the main branch and the API is automatically deployed to the production environment using GitHub Actions.   
 * In order to record "which API is changing", each MuleSoft API should exist in the ServiceNow CMDB as a valid CI.  The class of the CI and data contained is still to be aligned to be aligned with the Configuration Management Team.

