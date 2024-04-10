# Conditional access Baselne

This conditional access baseline is based on the Microsoft Conditional Access Baseline by Claus Jespersen. This one is slightly minimized and less dificult to understand but still protects almost everything you could wish for. Use this baseline to start off with and expend or modify where needed.

> [!NOTE]
> There's no need to create policies, groups or named locations yourself. This can be done automated using Mick-K his [Intune Management tool](https://github.com/Micke-K/IntuneManagement). This is described in [Importing the baseline](#importing-the-baseline).


# Table of Contents
- [Conditional access Baselne](#conditional-access-baselne)
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
    - [CA205-Internals-IdentityProtection-AllApps-AnyPlatform-CombinedRegistration](#ca205-internals-identityprotection-allapps-anyplatform-combinedregistration)
    - [CA206-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ](#ca206-internals-baseprotection-anyapp-windows-compliantoraadhj)
    - [CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA](#ca400-guestusers-identityprotection-anyapp-anyplatform-mfa)
    - [CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess](#ca401-guestusers-attacksurfacereduction-allapps-anyplatform-blocknonguestappaccess)
    - [CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency](#ca402-guestusers-identityprotection-allapps-anyplatform-signinfrequency)
  - [Named locations](#named-locations)
  - [Importing the baseline](#importing-the-baseline)


## Resources
➡ Microsoft Learn: https://learn.microsoft.com/en-us/azure/architecture/guide/security/conditional-access-framework

➡ Framework documentation by Claus Jespersen: https://github.com/microsoft/ConditionalAccessforZeroTrustResources/blob/main/ConditionalAccessGovernanceAndPrinciplesforZeroTrust%20October%202023.pdf

➡ Framework resources: https://github.com/microsoft/ConditionalAccessforZeroTrustResources


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

### CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist

This policy blocks all countries, to all cloud apps, from every platform except for the countries configured in the named location **ALLOWED COUNTRIES**. This named location is excluded in this policy.

### CA002-Global-IdentityProtection-AnyApp-AnyPlatform-Block-LegacyAuthentication

This policy blocks legacy authentication for all users, to all cloud apps, from any platform.

### CA003-Global-BaseProtection-RegisterOrJoin-AnyPlatform-MFA

This policy requires MFA for all users, to register or join a device to your tenant/environment. Make sure to disable *Require Multifactor Authentication to register or join devices with Microsoft Entra*. This can be found under https://portal.azure.com -> Entra ID -> Devices -> Device settings.

![Image1](Images\image1.png)

### CA004-Global-IdentityProtection-AnyApp-AnyPlatform-AuthenticationFlows

This policy prevents all users from transfering authentication flows from PC to mobile for example. This feature is currently in preview.

### CA005-Global-DataProtection-Office365-AnyPlatform-Unmanaged-AppEnforcedRestrictions-BlockDownload

This policy prevents all users from downloading, printing or syncing Office 365 data from an unmanaged device. It requires App Enforce Restrictions.

### CA100-Admins-IdentityProtection-AdminPortals-AnyPlatform-MFA

This policy requires MFA for certain admin roles when they access the Admin Portals.

### CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA

This policy requires MFA for certain admin roles when they access the any cloud app. 

### CA102-Admins-IdentityProtection-AllApps-AnyPlatform-SigninFrequency

This policy sets a Sign-in frequency for certain admin roles to a maximum of 12 hours. Admins need to re-authenticate of logon after 12 hours.

### CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA

This policy requires MFA for all internal identities, for all cloud applications, from any platform.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it.

### CA201-Internals-IdentityProtection-AnyApp-AnyPlatform-BLOCK-HighRisk

This policy blocks all internal users which have a **high risk** (sign-in and user risk) status, to all cloud apps, from all platforms.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it.

### CA202-Internals-IdentityProtection-AllApps-WindowsMacOS-SigninFrequency-UnmanagedDevices

This policy sets a Sign-in frequency to a maximum of 12 hours for internals, to all cloud apps, using unmanaged Windows or MacOS devices.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it.

### CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA

This policy requires MFA for internals when enrolling their devices in Intune.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it.

### CA204-Internals-AttackSurfaceReduction-AllApps-AnyPlatform-BlockUnknownPlatforms

This policy blocks unknown/unsupported device platforms for internals.

> [!NOTE]
> Currently only Windows, MacOS, Android and iOS are supported. If (for example) Linux or Windows Phone is allowed you need to modify the policy.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it.

### CA205-Internals-IdentityProtection-AllApps-AnyPlatform-CombinedRegistration

This policy requires secrity information registration for internals only from a managed or compliant device.

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it.

### CA206-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ

> [!IMPORTANT]
> Verify the included group(s) and/or add your custom groups which have all internals in it.

### CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA
### CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess
### CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency


## Named locations



## Importing the baseline