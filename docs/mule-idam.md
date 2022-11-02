## General Guidelines
_**No local accounts will be provisioned on the MuleSoft platform**._ 

Access to the Mondelez MuleSoft Platform is controlled/governed by existing MDLZ Identity and Access Management processes.  This means that all MuleSoft users (admins, developers, analysts, etc) must:
* **Have a valid MDLZ user account**.  For employees, this account is generated automatically when you are hired.  For Contractors, user accounts are requested and managed through [Access Center](https://accesscenter.mdlz.com/home.jsf).
* **Use the MDLZ Enterprise SSO solution** (PingFederate) to authenticate to the application.   The link to the SSO Logon Page is [https://anypoint.mulesoft.com/login/domain/mdlz](https://anypoint.mulesoft.com/login/domain/mdlz)

![image](https://user-images.githubusercontent.com/19505714/194117610-5bf05338-af65-4277-b958-c77bc984a55e.png)
* **Use Ping MFA** for multi-factor authentication.   [Click here for details on Ping MFA](https://mdlz.service-now.com/technology?id=itsm_kb_article_view&sys_kb_id=3e900d121b065514009fa60fe54bcb10)

## Understanding MuleSoft Custom Roles
At time of initial launch, Mondelez has defined a set of 5 custom roles for the Anypoint platform.  These roles define the set of Anypoint permissions available to each user. 

**Important** The permissions for a given role can vary depending on the MuleSoft ENVIRONMENT -- eg. a user with the Developer role may have MORE permissions in the Development/Test environments than in Production.

Assignment of these roles to users is managed through groups in Active Directory.   There are 5 total AD groups for MuleSoft:
* MDZ MuleSoft Administrator
* MDZ MuleSoft Developer
* MDZ MuleSoft SupportEngineer
* MDZ MuleSoft TestEngineer
* MDZ MuleSoft BusinessAnalyst

These AD groups are mapped to our Anypoint custom roles within each MuleSoft Business Group to allow access to be granted to the user. Below, you can see the general design for identity management.
![image](https://user-images.githubusercontent.com/19505714/194120246-5e2444f5-4778-4dc5-9535-a2fdf03deaf2.png)



## Requesting Access
**COMING SOON - WORK IN PROGRESS**

As shown above, the long term solution is to request access via Sailpoint.  The request process is very straightforward and can be started by anyone in the organization with a valid Mondelez User Account.

* Go to AccessCenter.
* Search for the MuleSoft "Entitlement" (one of the above AD Groups) and submit the request.
* Once that request is approved (by the Entitlement Role Owner), Sailpoint will add the user to the AD Group and the user will now be able to access MuleSoft using the SSO custom-domain logon page.

**SHORT TERM WORKAROUND**

MuleSoft has not yet been "onboarded" to Sailpoint Access Center yet.  Until that time, you should use the [Self-Service Group Management Form in iRequest](https://irequest.mdlz.com/sc/catalog.product.aspx?product_id=zbb.group.management) to add users to new groups.

1. Select "Add/Remove Group Members" 
2. select "Add" or "Remove".
3. Under Groups, search for "MDZ Mule" as an easy way to get a list of the relevant groups. Make sure to **SELECT** the group so that you can see the group name and Group Owner Details.

![image](https://user-images.githubusercontent.com/19505714/194123014-bdd9d257-b517-4ab0-b385-03d1783b01cf.png)

4. Now that you've selected the right group, you can add one or more users to the group.  Look at the screenshot below and use your imagination on how to complete this step.  I believe in you.  You can do it.  :-)   And let's be honest, if you can't figure this out, we probably don't want you developing integrations anyway...

![image](https://user-images.githubusercontent.com/19505714/194123470-223dbd48-5984-42df-a151-1be2e0b3125b.png)



## How Authentication Works

* Once a user has been added to a particular AD group, they should they should be able to log in to Anypoint using SSO at [https://anypoint.mulesoft.com/login/domain/mdlz](https://anypoint.mulesoft.com/login/domain/mdlz)
* PingFederate will validate the users credentials and will also prompt for MFA.
* Ping will issue an SSO token that will include the list of groups where the user is a member.
* MuleSoft group-mapping will evaluate those groups and assign the appropriate custom roles/permissions for the user depending on their selected business group.

![image](https://user-images.githubusercontent.com/19505714/194118136-a38440d7-0165-47de-ab92-093b7a431214.png)




