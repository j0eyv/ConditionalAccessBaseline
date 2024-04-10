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
  - [Conditional access policies](#conditional-access-policies)
    - [CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA](#ca000-global-identityprotection-anyapp-anyplatform-mfa)
    - [CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA](#ca000-global-identityprotection-anyapp-anyplatform-mfa-1)
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


## Conditional access policies

### CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA
### CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA
### CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist
### CA002-Global-IdentityProtection-AnyApp-AnyPlatform-Block-LegacyAuthentication
### CA003-Global-BaseProtection-RegisterOrJoin-AnyPlatform-MFA
### CA004-Global-IdentityProtection-AnyApp-AnyPlatform-AuthenticationFlows
### CA005-Global-DataProtection-Office365-AnyPlatform-Unmanaged-AppEnforcedRestrictions-BlockDownload
### CA100-Admins-IdentityProtection-AdminPortals-AnyPlatform-MFA
### CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA
### CA102-Admins-IdentityProtection-AllApps-AnyPlatform-SigninFrequency
### CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA
### CA201-Internals-IdentityProtection-AnyApp-AnyPlatform-BLOCK-HighRisk
### CA202-Internals-IdentityProtection-AllApps-WindowsMacOS-SigninFrequency-UnmanagedDevices
### CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA
### CA204-Internals-AttackSurfaceReduction-AllApps-AnyPlatform-BlockUnknownPlatforms
### CA205-Internals-IdentityProtection-AllApps-AnyPlatform-CombinedRegistration
### CA206-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ
### CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA
### CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess
### CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency


## Named locations



## Importing the baseline