## General Guidelines
_**No local accounts will be provisioned on the MuleSoft platform**._ 

Access to the Mondelez MuleSoft Platform is controlled/governed by existing MDLZ Identity and Access Management processes.  This means that all MuleSoft users (admins, developers, analysts, etc) must:
* **Have a valid MDLZ user account**.  For employees, this account is generated automatically when you are hired.  For Contractors, user accounts are requested and managed through [Access Center](https://accesscenter.mdlz.com/home.jsf).
* **Use the MDLZ Enterprise SSO solution** (PingFederate) to authenticate to the application.   The link to the SSO Logon Page is [https://anypoint.mulesoft.com/login/domain/mdlz](https://anypoint.mulesoft.com/login/domain/mdlz)

![image](https://user-images.githubusercontent.com/19505714/194117610-5bf05338-af65-4277-b958-c77bc984a55e.png)
* **Use Ping MFA** for multi-factor authentication.   [Click here for details on Ping MFA](https://mdlz.service-now.com/technology?id=itsm_kb_article_view&sys_kb_id=3e900d121b065514009fa60fe54bcb10)


## Requesting Access
Access to MuleSoft can be requested through [Access Center](https://accesscenter.mdlz.com/). The request process is very straightforward and can be started by anyone in the organization with a valid Mondelez User Account.

At a high level, here's the process:
* Go to [Access Center](https://accesscenter.mdlz.com/)
* From the menu, select "Self Service Group Management" > "Active Directory (AD) Group Management."
* Choose "Add/Remove Members"
* Search for groups that start with "MDZ MuleSoft".  You'll probably want the "Developer" group and Submit.
* Once that request is approved (by the Entitlement Role Owner), Sailpoint will add the user to the AD Group and the user will now be able to access MuleSoft using the SSO custom-domain logon page.


## Additional Information
More detailed information is available for you once you have been added to this GitHub Organization.  You can view the (private version of this documentation here)[https://github.com/mondelez-mulesoft-eng/platform-project-tasks/wiki/MuleSoft-Identity-Management].



