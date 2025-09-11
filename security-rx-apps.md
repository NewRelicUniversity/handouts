# _Lab:_ Security RX for Applications

**Objective:** After completing this lab, you will be able to navigate the Security Remediation Explorer to discover application vulnerabilities and determine what must be done to remediate them.

## Step 1: Log into the training account

In a private browser window, use the following credentials to log into New Relic: 

- URL: [https://one.newrelic.com/](https://one.newrelic.com/)
- Email: demo@newrelicuniversity.com
- The instructor will provide the password

## Step 2
From New Relic’s _All Capabilities_ menu, select _Security RX_. Use the _All Vulnerabilities_ page (the default) to answer these questions: 

- What is the total number of vulnerabilities detected?

- Notice the prioritization of the detected vulnerabilities. Are _Critical_ vulnerabilities always the highest priority? _Hint:_ Click the question mark beside “Reason to prioritize”.

## Step 3
Select the _Overview_ menu under SECURITY RX - APPLICATIONS: 

- What is the total number of application vulnerabilities?

- In the filter bar, click “Team = All” and select “eComm Services”, then click _Apply_. How many vulnerabilities affect the eComm Services team?

## Step 4
Scroll down to the table labeled “High priority vulnerabilities” and select the top item in the table: 

- Which entity or entities are affected by this vulnerability?
- What is the recommended fix?
- Which library is vulnerable? How was it detected (Source)?
- Which CVE contains detailed information about this vulnerability?

## Step 5
Select the _Entities_ menu. Notice that you may filter the list of vulnerable APM entities by selecting _All entities_, _Online_, or _Offline_. If you have many vulnerable applications, it may be beneficial to focus on those that are current online.

Filter the list to online entities and look at the first item in the list. How many vulnerabilities does it have?

## Step 6
Select the first item in the list of online entities. Note that you are taken to the Security RX Overview for that repository, letting you see all information related to it. Now it’s time to schedule patches for the highest-priority vulnerabilies!

## Additional resources
[Documentation: Manage vulnerabilities in your application](https://docs.newrelic.com/docs/vulnerability-management/dev-workflow/)