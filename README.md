# Conditional access Baseline

This conditional access baseline is based on the Microsoft Conditional Access Baseline by Claus Jespersen. This one is slightly minimized and less difficult to understand but still protects almost everything you could wish for. Use this baseline to start off with and expend or modify where needed.

> [!TIP]
> There's no need to create policies, groups or named locations yourself. This can be done automated using Mick-K his [Intune Management tool](https://github.com/Micke-K/IntuneManagement). This is described in [Importing the baseline](#importing-the-baseline).


> [!IMPORTANT]
> Do not forget to add your break the glass/emergency access accounts to the exclusion group. When using this baseline that would be **CA-BreakGlassAccounts - Exclude**.

# Table of Contents
- [Conditional access Baseline](#conditional-access-baseline)
- [Table of Contents](#table-of-contents)
  - [Resources](#resources)
  - [Version history](#version-history)
  - [Changelog](#changelog)
  - [Persona's](#personas)
      - [Global](#global)
      - [Admins](#admins)
      - [Internals](#internals)
      - [Guests](#guests)
  - [Conditional access policies](#conditional-access-policies)
    - [CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA](#ca000-global-identityprotection-anyapp-anyplatform-mfa)
    - [CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist](#ca001-global-attacksurfacereduction-anyapp-anyplatform-block-countrywhitelist)
    - [CA002-Global-IdentityProtection-AnyApp-AnyPlatform-Block-LegacyAuthentication](#ca002-global-identityprotection-anyapp-anyplatform-block-legacyauthentication)
    - [CA003-Global-BaseProtection-RegisterOrJoin-AnyPlatform-MFA](#ca003-global-baseprotection-registerorjoin-anyplatform-mfa)
    - [CA004-Global-IdentityProtection-AnyApp-AnyPlatform-AuthenticationFlows](#ca004-global-identityprotection-anyapp-anyplatform-authenticationflows)
    - [CA005-Global-DataProtection-Office365-AnyPlatform-Unmanaged-AppEnforcedRestrictions-BlockDownload](#ca005-global-dataprotection-office365-anyplatform-unmanaged-appenforcedrestrictions-blockdownload)
    - [CA100-Admins-IdentityProtection-AdminPortals-AnyPlatform-MFA](#ca100-admins-identityprotection-adminportals-anyplatform-mfa)
    - [CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA](#ca101-admins-identityprotection-anyapp-anyplatform-mfa)
    - [CA102-Admins-IdentityProtection-AllApps-AnyPlatform-SigninFrequency](#ca102-admins-identityprotection-allapps-anyplatform-signinfrequency)
    - [CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA](#ca200-internals-identityprotection-anyapp-anyplatform-mfa)
    - [CA201-Internals-IdentityProtection-AnyApp-AnyPlatform-BLOCK-HighRisk](#ca201-internals-identityprotection-anyapp-anyplatform-block-highrisk)
    - [CA202-Internals-IdentityProtection-AllApps-WindowsMacOS-SigninFrequency-UnmanagedDevices](#ca202-internals-identityprotection-allapps-windowsmacos-signinfrequency-unmanageddevices)
    - [CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA](#ca203-internals-appprotection-microsoftintuneenrollment-anyplatform-mfa)
    - [CA204-Internals-AttackSurfaceReduction-AllApps-AnyPlatform-BlockUnknownPlatforms](#ca204-internals-attacksurfacereduction-allapps-anyplatform-blockunknownplatforms)
    - [CA205-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ](#ca205-internals-baseprotection-anyapp-windows-compliantoraadhj)
    - [CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA](#ca400-guestusers-identityprotection-anyapp-anyplatform-mfa)
    - [CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess](#ca401-guestusers-attacksurfacereduction-allapps-anyplatform-blocknonguestappaccess)
    - [CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency](#ca402-guestusers-identityprotection-allapps-anyplatform-signinfrequency)
  - [Named locations](#named-locations)
  - [Considerations](#considerations)
  - [Importing the baseline](#importing-the-baseline)
    - [Setup IntuneManagement](#setup-intunemanagement)
    - [Import the configuration](#import-the-configuration)


## Resources
➡ Microsoft Learn: https://learn.microsoft.com/en-us/azure/architecture/guide/security/conditional-access-framework

➡ Framework documentation by Claus Jespersen: https://github.com/microsoft/ConditionalAccessforZeroTrustResources/blob/main/ConditionalAccessGovernanceAndPrinciplesforZeroTrust%20October%202023.pdf

➡ Framework resources: https://github.com/microsoft/ConditionalAccessforZeroTrustResources

➡ idPowerToys for CA documentation: https://idpowertoys.merill.net/


## Version history
| Version nr | Release date |
| -------- | -------- |
| 2024.4.1 | Released 10-04-2024 |
| 2024.x.x | Released xx-xx-2024 |


## Changelog
Changes are documented here once they are made.


## Persona's

#### Global
Global is a persona/placeholder for policies that are general 
in nature or do not only apply to one persona. So it is used 
to define policies that apply to all personas or don't apply to 
one specific persona. The reason for having this persona is to 
be able to have a model where we can protect all relevant 
scenarios. It should be used to hold policies that apply to all 
users or policies that enforce protection on scenarios not 
covered by policies for other personas

#### Admins
We define admins in this context as any non-guest identity 
(cloud or synced) that have any Azure AD or other Microsoft 
365 admin Role (like in MDCA, Exchange, Defender for 
Endpoints or Compliance). As guests who have such roles are 
covered in a separate persona, guests are excluded from this 
persona.

#### Internals
Internals cover all users who have an AD account synced to 
Azure AD who are employees of the company and work in a 
standard end-user role.

#### Guests
Guests holds all users who have an Azure AD guest account 
that has been invited into the customer tenant


## Conditional access policies

### CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA

This policy requires MFA for all cloud apps, from every platform. It captures all authentications in scope not captured by other MFA policies.

![CA000](./Images/CA000.png)

### CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist

This policy blocks all countries, to all cloud apps, from every platform except for the countries configured in the named location **ALLOWED COUNTRIES**. This named location is excluded in this policy.

> [!IMPORTANT]
> Modify the named location with your approved countries. By default only Belgium, Luxembourgh and Netherlands are allowed to have access from.

![CA001](./Images/CA001.png)

### CA002-Global-IdentityProtection-AnyApp-AnyPlatform-Block-LegacyAuthentication

This policy blocks legacy authentication for all users, to all cloud apps, from any platform.

![CA002](./Images/CA002.png)

### CA003-Global-BaseProtection-RegisterOrJoin-AnyPlatform-MFA

This policy requires MFA for all users, to register or join a device to your tenant/environment.

> [!TIP]
> Make sure to disable *Require Multifactor Authentication to register or join devices with Microsoft Entra*. This can be found under https://portal.azure.com -> Entra ID -> Devices -> Device settings.

![CA003](./Images/CA003.png)

### CA004-Global-IdentityProtection-AnyApp-AnyPlatform-AuthenticationFlows

This policy prevents all users from transfering authentication flows from PC to mobile for example. This feature is currently in preview.

![CA004](./Images/CA004.png)

### CA005-Global-DataProtection-Office365-AnyPlatform-Unmanaged-AppEnforcedRestrictions-BlockDownload

This policy prevents all users from downloading, printing or syncing Office 365 data from an unmanaged device. It requires App Enforce Restrictions.

![CA005](./Images/CA005.png)

### CA100-Admins-IdentityProtection-AdminPortals-AnyPlatform-MFA

This policy requires MFA for certain admin roles when they access the Admin Portals.

![CA100](./Images/CA100.png)

### CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA

This policy requires MFA for certain admin roles when they access the any cloud app. 

![CA101](./Images/CA101.png)

### CA102-Admins-IdentityProtection-AllApps-AnyPlatform-SigninFrequency

This policy sets a Sign-in frequency for certain admin roles to a maximum of 12 hours. Admins need to re-authenticate of logon after 12 hours.

![CA102](./Images/CA102.png)

### CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA

This policy requires MFA for all internal identities, for all cloud applications, from any platform.


> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it. APP_Microsoft365_E5_DEV is added as an example.

![CA200](./Images/CA200.png)

### CA201-Internals-IdentityProtection-AnyApp-AnyPlatform-BLOCK-HighRisk

This policy blocks all internal users which have a **high risk** (sign-in and user risk) status, to all cloud apps, from all platforms.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it. APP_Microsoft365_E5_DEV is added as an example.

![CA201](./Images/CA201.png)

### CA202-Internals-IdentityProtection-AllApps-WindowsMacOS-SigninFrequency-UnmanagedDevices

This policy sets a Sign-in frequency to a maximum of 12 hours for internals, to all cloud apps, using unmanaged Windows or MacOS devices.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it. APP_Microsoft365_E5_DEV is added as an example.

![CA202](./Images/CA202.png)

### CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA

This policy requires MFA for internals when enrolling their devices in Intune.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it. APP_Microsoft365_E5_DEV is added as an example.

![CA203](./Images/CA203.png)

### CA204-Internals-AttackSurfaceReduction-AllApps-AnyPlatform-BlockUnknownPlatforms

This policy blocks unknown/unsupported device platforms for internals.

> [!NOTE]
> Currently only Windows, MacOS, Android and iOS are supported. If (for example) Linux or Windows Phone is allowed you need to modify the policy.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it. APP_Microsoft365_E5_DEV is added as an example.

![CA204](./Images/CA204.png)

### CA205-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ

This policy requires internals to make use of a Windows device that is compliant or AADHJ (Azure AD Hybrid Joined / Entra ID Hybrid Joined) while accessing any cloud app.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it. APP_Microsoft365_E5_DEV is added as an example.

![CA205](./Images/CA205.png)

### CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA

This policy requires guest to use MFA, from any platform when accessing any cloud app.

![CA400](./Images/CA400.png)

### CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess

This policy blocks access for guests to all cloud apps (except for those excluded), from any device.

> [!IMPORTANT]
> Make sure to exclude additional cloud apps if any guest needs access to these apps.

![CA401](./Images/CA401.png)

### CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency

This policy sets a Sign-in frequency to a maximum of 12 hours for guests, to all cloud apps, using any device.

![CA402](./Images/CA402.png)

## Named locations

| Name | Location type | Assigned to policy |
| -------- | -------- | -------- |
| ALLOWED COUNTRIES | Countries (IP) | CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist |

## Considerations
1. You might want to remove the "CA - BreakGlassAccounts - Exclude" group from Admin MFA policies (CA101, CA102) if they use MFA and/or only exclude 1 single BreakGlass account.

2. You might want to lower the risk state in CA201 and/or separate User-Risk and Sign-in Risk in 2 single policies.

## Importing the baseline

These PowerShell scripts are using Microsoft Authentication Library (MSAL), Microsoft Graph APIs and Azure Management APIs to manage objects in Intune and Azure. The scripts has a simple WPF UI and it supports operations like Export, Import, Copy, Download, Compare etc.

This makes it easy to backup or clone a complete Intune environment. The scripts can export and import objects including assignments and support import/export between tenants. The scripts will create a migration table during export and use that for importing assignments in other environments. It will create missing groups in the target environment during import. Group information like name, description and type will be imported based on the exported group e.g. dynamic groups are supported. There will be one json file for each group in the export folder.

The script also support dependencies e.g. an App Protection is depending on an App, Policy Sets are depending on Compliance Policies, objects has Scope Tags etc. Dependency support requires exported json files and that the dependency objects are imported in the environment. The script uses the exported json files to get the Id and name's of the exported object and uses that information and updates Id's before import an object from a json file. The Bulk Import form shows the import order of the objects. The objects with the lowest order number will be imported first.

![IntuneManagement1](./Images/IntuneManagement1.png)

> [!TIP]
> The following tool is used: https://github.com/Micke-K/IntuneManagement. Always download the lastest version before importing or exporting data.

### Setup IntuneManagement

Start by downloading the files in GitHub. Extract the Github repo somewhere on your device. For example: *C:\Intune\IntuneManagement*.

![IntuneManagement2](./Images/IntuneManagement2.png)

Unblock all .cmd/.ps1/.psd files with the following PowerShell command.

```
Get-ChildItem -Path "C:\Intune\IntuneManagement\" -File -Recurse | Unblock-File
```

Start the IntuneManagementTool
```
cd C:\Intune\IntuneManagement\
.\Start-IntuneManagement.ps1
```

Start by authenticating to your tenant with the profile icon in the top right.

![IntuneManagement3](./Images/IntuneManagement3.png)

In the modern authentication window that pops up, sign in with an account that has appropriate permissions, if unsure use Global Administrator. After sign-in you will be prompted to accept permissions for Microsoft Intune PowerShell, **DO NOT** tick the box to consent on behalf of your organisation.

![IntuneManagement4](./Images/IntuneManagement4.png)

It's likely the first time you do this you'll still see you don't have access to the settings, you'll know this as the menu on the left-hand side will have all text in red, like so.

![IntuneManagement5](./Images/IntuneManagement5.png)

From here, select the profile icon in the top right corner and then Request Consent again.

![IntuneManagement6](./Images/IntuneManagement6.png)

Go ahead and accept the popup again, this should clear all the red text on the left hand-side. **DO NOT** tick the box to consent on behalf of your organisation.

![IntuneManagement7](./Images/IntuneManagement7.png)

Now we can start importing, exporting, or comparing tenant configurations. 

### Import the configuration

1: Click on **Bulk** -> **Import**

![IntuneManagement8](./Images/IntuneManagement8.png)

2: Select the folder where you stored the conditional access policies.

3: Decide if you want to import all the assignments or assign all policies yourself.

4: Set "Conditional Access State" to **Off** or **Report-only**. Don't forget to enable these later! This should be done after MFA is setup for an Global Admin account and (if required) a Break the Glass account is created.

5: Click **Import**

![IntuneManagement9](./Images/IntuneManagement9.png)

Once the importing is complete, all policies will be available for you to modify and/or enable them.

> [!CAUTION]
> Be careful activating the policies! Make sure you have decent exclusions and/or a break the glass account in place. Enable the policies one by one or start with report-only.

![CA Policies](./Images/image2.png)