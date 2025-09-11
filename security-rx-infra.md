# _Lab:_ Security RX for Infrastructure

**Objective:** After completing this lab, you will be able to navigate the Security Remediation Explorer to discover infrastructure vulnerabilities and determine what must be done to remediate them.

For this lab, you will assume the role of an infrastructure engineer who manages the 10.0.0.0/8 and 192.168.0.0/16 internal networks.

## Step 1
Log into the New Relic demo account and select _Security RX_ from the _All Capabilities_ menu.

## Step 2
You’ve received communication from your Security team that there has been increasing activity involving CVE-2024-4671. They’ve asked you to confirm that you have remediated all instances of this vulnerability in your environment. 

From the _All Vulnerabilities_ page, see if there are entities in either of your networks that are subject to this vulnerability. _Hint:_ In the search field, try “192-168” or ”10-0”.

## Step 3
Are there any critical vulnerabilities in either of your networks? If so, select a vulnerability to discover: 

- Which network? 
- What entities is affected? 
- What is the recommended remediation?

## Step 4
Select the affected entity (host): 

- What is the OS distribution?
- How many critical vulnerabilities affecting this host could be remediated by upgrading the distribution?

## Step 5
The following day, you see a bulletin that the `containerd` package shipped with some Amazon Linux 2 instances has a critical vulnerability. Naturally, you want to determine whether you are affected by this vulnerability. 

Return to the Remediation Explorer and select _Packages_. Try searching for both the package in question and the entities that you manage. _Hint:_ You can search by tags or any other searchable attribute. Last time we searched for part of the entity name.

If you found a critical vulnerability, what is the suggested remediation?

## Step 6
Is the **Demo Engineering** team affected by this vulnerability?

## Additional resources
[Documentation: Manage vulnerabilities in your infrastructure](https://docs.newrelic.com/docs/vulnerability-management/infra-workflow/)