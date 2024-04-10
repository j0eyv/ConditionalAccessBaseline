# Conditional Access Baseline

This conditional access baseline is based on the Microsoft Conditional Access Baseline by Claus Jespersen. This one is slightly minimized and less dificult to understand but still protects almost everything you could wish for. Use this baseline to start off with and expend where needed.

## Resources
➡ Microsoft Learn: https://learn.microsoft.com/en-us/azure/architecture/guide/security/conditional-access-framework

➡ Framework documentation by Claus Jespersen: https://github.com/microsoft/ConditionalAccessforZeroTrustResources/blob/main/ConditionalAccessGovernanceAndPrinciplesforZeroTrust%20October%202023.pdf

➡ Framework resources: https://github.com/microsoft/ConditionalAccessforZeroTrustResources



## Table of Contents
- [Conditional access](#section-1)

  - [Conditional access policies](#section-2)

    - [CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA](#section-3)

    - [CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist](#section-4)

    - [CA002-Global-IdentityProtection-AnyApp-AnyPlatform-Block-LegacyAuthentication](#section-5)

    - [CA003-Global-BaseProtection-RegisterOrJoin-AnyPlatform-MFA](#section-6)

    - [CA004-Global-IdentityProtection-AnyApp-AnyPlatform-AuthenticationFlows](#section-7)

    - [CA005-Global-DataProtection-Office365-AnyPlatform-Unmanaged-AppEnforcedRestrictions-BlockDownload](#section-8)

    - [CA100-Admins-IdentityProtection-AdminPortals-AnyPlatform-MFA](#section-9)

    - [CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA](#section-10)

    - [CA102-Admins-IdentityProtection-AllApps-AnyPlatform-SigninFrequency](#section-11)

    - [CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA](#section-12)

    - [CA201-Internals-IdentityProtection-AnyApp-AnyPlatform-BLOCK-HighRisk](#section-13)

    - [CA202-Internals-IdentityProtection-AllApps-WindowsMacOS-SigninFrequency-UnmanagedDevices](#section-14)

    - [CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA](#section-15)

    - [CA204-Internals-AttackSurfaceReduction-AllApps-AnyPlatform-BlockUnknownPlatforms](#section-16)

    - [CA205-Internals-IdentityProtection-AllApps-AnyPlatform-CombinedRegistration](#section-17)

    - [CA206-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ](#section-18)

    - [CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA](#section-19)

    - [CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess](#section-20)

    - [CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency](#section-21)

  - [Named Locations](#section-22)

    - [ALLOWED COUNTRIES](#section-23)


<h1 id="section-1">Conditional access</h1>
<h2 id="section-2">Conditional access policies</h2>
<h3 id="section-3">CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 09:47:07</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Wednesday, 27 March 2024 14:41:39</td>
</tr>
</table>

###### Table 1. Basics - CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All users</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Directory roles</td>
<td class='property-column2'>Directory Synchronization Accounts</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'><details class='description'><summary data-open='Minimize' data-close='CA101-Admins-IdentityProtection-AnyApp-A...expand'></summary>CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA - Exclude<br />CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA - Exclude<br />CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA - Exclude<br />CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA - Exclude<br />CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA - Exclude<br />CA-BreakGlassAccounts - Exclude</details></td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>Require multifactor authentication</td>
<td class='property-column2'>Enabled</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require one of the selected controls</td>
</tr>
</table>

###### Table 2. Settings - CA000-Global-IdentityProtection-AnyApp-AnyPlatform-MFA


<h3 id="section-4">CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 08:02:06</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Tuesday, 2 January 2024 10:38:04</td>
</tr>
</table>

###### Table 3. Basics - CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All users</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist - Exclude<br />CA-BreakGlassAccounts - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Conditions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Locations</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Any location</td>
</tr>
<tr class=''>
<td class='property-column1'>Exclude</td>
<td class='property-column2'>ALLOWED COUNTRIES</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Block access</td>
</tr>
</table>

###### Table 4. Settings - CA001-Global-AttackSurfaceReduction-AnyApp-AnyPlatform-BLOCK-CountryWhitelist


<h3 id="section-5">CA002-Global-IdentityProtection-AnyApp-AnyPlatform-Block-LegacyAuthentication</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA002-Global-IdentityProtection-AnyApp-AnyPlatform-Block-LegacyAuthentication</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 07:08:14</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Tuesday, 2 January 2024 10:38:10</td>
</tr>
</table>

###### Table 5. Basics - CA002-Global-IdentityProtection-AnyApp-AnyPlatform-Block-LegacyAuthentication


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All users</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA002-Global-IdentityProtection-AnyApp-AnyPlatform-Block-LegacyAuthentication - Exclude<br />CA-BreakGlassAccounts - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Conditions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Client apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Exchange ActiveSync<br />Other clients</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Block access</td>
</tr>
</table>

###### Table 6. Settings - CA002-Global-IdentityProtection-AnyApp-AnyPlatform-Block-LegacyAuthentication


<h3 id="section-6">CA003-Global-BaseProtection-RegisterOrJoin-AnyPlatform-MFA</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA003-Global-BaseProtection-RegisterOrJoin-AnyPlatform-MFA</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Wednesday, 3 January 2024 07:52:15</td>
</tr>
</table>

###### Table 7. Basics - CA003-Global-BaseProtection-RegisterOrJoin-AnyPlatform-MFA


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All users</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA003-Global-BaseProtection-RegisterOrJoin-AnyPlatform-MFA - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>User actions</td>
</tr>
<tr class=''>
<td class='property-column1'>Select the action this policy will apply to</td>
<td class='property-column2'>Register or join devices</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>Require multifactor authentication</td>
<td class='property-column2'>Enabled</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require one of the selected controls</td>
</tr>
</table>

###### Table 8. Settings - CA003-Global-BaseProtection-RegisterOrJoin-AnyPlatform-MFA


<h3 id="section-7">CA004-Global-IdentityProtection-AnyApp-AnyPlatform-AuthenticationFlows</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA004-Global-IdentityProtection-AnyApp-AnyPlatform-AuthenticationFlows</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Wednesday, 27 March 2024 14:28:00</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Monday, 8 April 2024 12:38:51</td>
</tr>
</table>

###### Table 9. Basics - CA004-Global-IdentityProtection-AnyApp-AnyPlatform-AuthenticationFlows


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All users</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA004-Global-IdentityProtection-AnyApp-AnyPlatform-AuthenticationFlows - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Block access</td>
</tr>
</table>

###### Table 10. Settings - CA004-Global-IdentityProtection-AnyApp-AnyPlatform-AuthenticationFlows


<h3 id="section-8">CA005-Global-DataProtection-Office365-AnyPlatform-Unmanaged-AppEnforcedRestrictions-BlockDownload</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA005-Global-DataProtection-Office365-AnyPlatform-Unmanaged-AppEnforcedRestrictions-BlockDownload</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Wednesday, 27 March 2024 14:40:41</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Monday, 8 April 2024 12:38:39</td>
</tr>
</table>

###### Table 11. Basics - CA005-Global-DataProtection-Office365-AnyPlatform-Unmanaged-AppEnforcedRestrictions-BlockDownload


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All users</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA005-Global-DataProtection-Office365-AnyPlatform-Unmanaged-AppEnforcedRestrictions-BlockDownload - Exclude<br />CA-BreakGlassAccounts - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Office 365 Exchange Online<br />Office 365 SharePoint Online</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Conditions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Client apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Browser</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Filter for devices</td>
</tr>
<tr class=''>
<td class='property-column1'>Exclude filtered devices from policy</td>
<td class='property-column2'>device.isCompliant -eq True</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require all the selected controls</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Session</td>
</tr>
<tr class=''>
<td class='property-column1'>Use app enforced restrictions</td>
<td class='property-column2'>Enabled</td>
</tr>
</table>

###### Table 12. Settings - CA005-Global-DataProtection-Office365-AnyPlatform-Unmanaged-AppEnforcedRestrictions-BlockDownload


<h3 id="section-9">CA100-Admins-IdentityProtection-AdminPortals-AnyPlatform-MFA</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA100-Admins-IdentityProtection-AdminPortals-AnyPlatform-MFA</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Friday, 22 December 2023 10:12:23</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Wednesday, 3 January 2024 09:43:35</td>
</tr>
</table>

###### Table 13. Basics - CA100-Admins-IdentityProtection-AdminPortals-AnyPlatform-MFA


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr class=''>
<td class='property-column1'>Directory roles</td>
<td class='property-column2'><details class='description'><summary data-open='Minimize' data-close='Global Administrator...expand'></summary>Global Administrator<br />Security Administrator<br />SharePoint Administrator<br />Exchange Administrator<br />Conditional Access Administrator<br />Helpdesk Administrator<br />Billing Administrator<br />User Administrator<br />Authentication Administrator<br />Application Administrator<br />Cloud Application Administrator<br />Password Administrator<br />Privileged Authentication Administrator<br />Privileged Role Administrator</details></td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA100-Admins-IdentityProtection-AdminPortals-AnyPlatform-MFA - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>MicrosoftAdminPortals</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>Authentication strength</td>
<td class='property-column2'></td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require one of the selected controls</td>
</tr>
</table>

###### Table 14. Settings - CA100-Admins-IdentityProtection-AdminPortals-AnyPlatform-MFA


<h3 id="section-10">CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Monday, 31 January 2022 16:44:43</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Tuesday, 2 January 2024 10:38:19</td>
</tr>
</table>

###### Table 15. Basics - CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr class=''>
<td class='property-column1'>Directory roles</td>
<td class='property-column2'><details class='description'><summary data-open='Minimize' data-close='Exchange Administrator...expand'></summary>Exchange Administrator<br />Security Administrator<br />Conditional Access Administrator<br />SharePoint Administrator<br />Helpdesk Administrator<br />Billing Administrator<br />User Administrator<br />Authentication Administrator<br />Global Administrator<br />Global Reader<br />Intune Administrator</details></td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Conditions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Locations</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Any location</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Client apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Exchange ActiveSync<br />Browser<br />Mobile apps and desktop clients<br />Other clients</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>Require multifactor authentication</td>
<td class='property-column2'>Enabled</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require one of the selected controls</td>
</tr>
</table>

###### Table 16. Settings - CA101-Admins-IdentityProtection-AnyApp-AnyPlatform-MFA


<h3 id="section-11">CA102-Admins-IdentityProtection-AllApps-AnyPlatform-SigninFrequency</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA102-Admins-IdentityProtection-AllApps-AnyPlatform-SigninFrequency</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 10:02:19</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Tuesday, 2 January 2024 10:38:23</td>
</tr>
</table>

###### Table 17. Basics - CA102-Admins-IdentityProtection-AllApps-AnyPlatform-SigninFrequency


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr class=''>
<td class='property-column1'>Directory roles</td>
<td class='property-column2'><details class='description'><summary data-open='Minimize' data-close='Authentication Administrator...expand'></summary>Authentication Administrator<br />Billing Administrator<br />Conditional Access Administrator<br />Exchange Administrator<br />Global Administrator<br />Global Reader<br />Helpdesk Administrator<br />Intune Administrator<br />Security Administrator<br />User Administrator<br />SharePoint Administrator</details></td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA102-Admins-IdentityProtection-AllApps-AnyPlatform-SigninFrequency - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require all the selected controls</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Session</td>
</tr>
<tr class=''>
<td class='property-column1'>Sign-in frequency</td>
<td class='property-column2'>12 hours</td>
</tr>
</table>

###### Table 18. Settings - CA102-Admins-IdentityProtection-AllApps-AnyPlatform-SigninFrequency


<h3 id="section-12">CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Monday, 31 January 2022 16:44:44</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Tuesday, 2 January 2024 14:10:23</td>
</tr>
</table>

###### Table 19. Basics - CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>APP_Microsoft365_E5_Dev</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA - Exclude<br />CA-BreakGlassAccounts - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Conditions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Locations</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Any location</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Client apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Browser<br />Mobile apps and desktop clients</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>Require multifactor authentication</td>
<td class='property-column2'>Enabled</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require one of the selected controls</td>
</tr>
</table>

###### Table 20. Settings - CA200-Internals-IdentityProtection-AnyApp-AnyPlatform-MFA


<h3 id="section-13">CA201-Internals-IdentityProtection-AnyApp-AnyPlatform-BLOCK-HighRisk</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA201-Internals-IdentityProtection-AnyApp-AnyPlatform-BLOCK-HighRisk</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 07:45:42</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Wednesday, 24 January 2024 08:53:55</td>
</tr>
</table>

###### Table 21. Basics - CA201-Internals-IdentityProtection-AnyApp-AnyPlatform-BLOCK-HighRisk


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>APP_Microsoft365_E5_Dev</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA201-Internals-IdentityProtection-AnyApp-AnyPlatform-BLOCK-HighRisk - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Conditions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>User risk</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>High</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Sign-in risk</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>High</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Block access</td>
</tr>
</table>

###### Table 22. Settings - CA201-Internals-IdentityProtection-AnyApp-AnyPlatform-BLOCK-HighRisk


<h3 id="section-14">CA202-Internals-IdentityProtection-AllApps-WindowsMacOS-SigninFrequency-UnmanagedDevices</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA202-Internals-IdentityProtection-AllApps-WindowsMacOS-SigninFrequency-UnmanagedDevices</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 10:06:50</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Wednesday, 3 January 2024 09:54:21</td>
</tr>
</table>

###### Table 23. Basics - CA202-Internals-IdentityProtection-AllApps-WindowsMacOS-SigninFrequency-UnmanagedDevices


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>APP_Microsoft365_E5_Dev</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA202-Internals-IdentityProtection-AllApps-WindowsMacOS-SigninFrequency-UnmanagedDevices - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Conditions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Device platform</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Windows<br />macOS</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Filter for devices</td>
</tr>
<tr class=''>
<td class='property-column1'>Exclude filtered devices from policy</td>
<td class='property-column2'>device.deviceOwnership -eq "Company" -or device.isCompliant -eq True</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require all the selected controls</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Session</td>
</tr>
<tr class=''>
<td class='property-column1'>Sign-in frequency</td>
<td class='property-column2'>12 hours</td>
</tr>
</table>

###### Table 24. Settings - CA202-Internals-IdentityProtection-AllApps-WindowsMacOS-SigninFrequency-UnmanagedDevices


<h3 id="section-15">CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 09:30:47</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Tuesday, 2 January 2024 10:39:07</td>
</tr>
</table>

###### Table 25. Basics - CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>APP_Microsoft365_E5_Dev</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Microsoft Intune Enrollment</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>Require multifactor authentication</td>
<td class='property-column2'>Enabled</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require one of the selected controls</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Session</td>
</tr>
<tr class=''>
<td class='property-column1'>Sign-in frequency</td>
<td class='property-column2'>Every time</td>
</tr>
</table>

###### Table 26. Settings - CA203-Internals-AppProtection-MicrosoftIntuneEnrollment-AnyPlatform-MFA


<h3 id="section-16">CA204-Internals-AttackSurfaceReduction-AllApps-AnyPlatform-BlockUnknownPlatforms</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA204-Internals-AttackSurfaceReduction-AllApps-AnyPlatform-BlockUnknownPlatforms</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 09:32:55</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Tuesday, 2 January 2024 10:39:24</td>
</tr>
</table>

###### Table 27. Basics - CA204-Internals-AttackSurfaceReduction-AllApps-AnyPlatform-BlockUnknownPlatforms


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>APP_Microsoft365_E5_Dev</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA204-Internals-AttackSurfaceReduction-AllApps-AnyPlatform-BlockUnknownPlatforms - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Conditions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Device platform</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Any device</td>
</tr>
<tr class=''>
<td class='property-column1'>Exclude</td>
<td class='property-column2'>Android<br />iOS<br />Windows<br />macOS</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Block access</td>
</tr>
</table>

###### Table 28. Settings - CA204-Internals-AttackSurfaceReduction-AllApps-AnyPlatform-BlockUnknownPlatforms


<h3 id="section-17">CA205-Internals-IdentityProtection-AllApps-AnyPlatform-CombinedRegistration</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA205-Internals-IdentityProtection-AllApps-AnyPlatform-CombinedRegistration</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Wednesday, 3 January 2024 08:08:24</td>
</tr>
</table>

###### Table 29. Basics - CA205-Internals-IdentityProtection-AllApps-AnyPlatform-CombinedRegistration


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>APP_Microsoft365_E5_Dev</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA205-Internals-IdentityProtection-AllApps-AnyPlatform-CombinedRegistration - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>None</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>Require device to be marked as compliant</td>
<td class='property-column2'>Enabled</td>
</tr>
<tr class=''>
<td class='property-column1'>Require Microsoft Entra hybrid joined device</td>
<td class='property-column2'>Enabled</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require one of the selected controls</td>
</tr>
</table>

###### Table 30. Settings - CA205-Internals-IdentityProtection-AllApps-AnyPlatform-CombinedRegistration


<h3 id="section-18">CA206-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA206-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 07:27:49</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Wednesday, 3 January 2024 09:52:28</td>
</tr>
</table>

###### Table 31. Basics - CA206-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>APP_Microsoft365_E5_Dev</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA206-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ - Exclude<br />CA-BreakGlassAccounts - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Exclude</td>
<td class='property-column2'>Microsoft Intune Enrollment</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Conditions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Device platform</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Windows</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>Require device to be marked as compliant</td>
<td class='property-column2'>Enabled</td>
</tr>
<tr class=''>
<td class='property-column1'>Require Microsoft Entra hybrid joined device</td>
<td class='property-column2'>Enabled</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require one of the selected controls</td>
</tr>
</table>

###### Table 32. Settings - CA206-Internals-BaseProtection-AnyApp-Windows-CompliantorAADHJ


<h3 id="section-19">CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 07:23:41</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Tuesday, 2 January 2024 10:52:19</td>
</tr>
</table>

###### Table 33. Basics - CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA-BreakGlassAccounts - Exclude<br />CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>Require multifactor authentication</td>
<td class='property-column2'>Enabled</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require one of the selected controls</td>
</tr>
</table>

###### Table 34. Settings - CA400-GuestUsers-IdentityProtection-AnyApp-AnyPlatform-MFA


<h3 id="section-20">CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 09:37:47</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Wednesday, 27 March 2024 15:06:48</td>
</tr>
</table>

###### Table 35. Basics - CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess - Exclude<br />CA-BreakGlassAccounts - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Exclude</td>
<td class='property-column2'>My Apps<br />Office365</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Block access</td>
</tr>
</table>

###### Table 36. Settings - CA401-GuestUsers-AttackSurfaceReduction-AllApps-AnyPlatform-BlockNonGuestAppAccess


<h3 id="section-21">CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency</td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Conditional Access</td>
</tr>
<tr class=''>
<td class='property-column1'>Enable policy</td>
<td class='property-column2'>On</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Tuesday, 2 January 2024 09:55:02</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Tuesday, 2 January 2024 10:39:39</td>
</tr>
</table>

###### Table 37. Basics - CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Include</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>Select users and groups</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Exclude</td>
</tr>
<tr class=''>
<td class='property-column1'>Users and groups</td>
<td class='property-column2'>CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency - Exclude<br />CA-BreakGlassAccounts - Exclude</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Cloud apps or actions</td>
</tr>
<tr>
<td colspan="2" class='category-level2'>Cloud apps</td>
</tr>
<tr class=''>
<td class='property-column1'>Include</td>
<td class='property-column2'>All cloud apps</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Grant</td>
</tr>
<tr class=''>
<td class='property-column1'>Control access enforcement to block or grant access.</td>
<td class='property-column2'>Grant access</td>
</tr>
<tr class=''>
<td class='property-column1'>For multiple controls</td>
<td class='property-column2'>Require all the selected controls</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Session</td>
</tr>
<tr class=''>
<td class='property-column1'>Sign-in frequency</td>
<td class='property-column2'>12 hours</td>
</tr>
</table>

###### Table 38. Settings - CA402-GuestUsers-IdentityProtection-AllApps-AnyPlatform-SigninFrequency


<h2 id="section-22">Named Locations</h2>
<h3 id="section-23">ALLOWED COUNTRIES</h3>

<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr>
<td colspan="2" class='category-level1'>Basics</td>
</tr>
<tr class=''>
<td class='property-column1'>Name</td>
<td class='property-column2'>ALLOWED COUNTRIES</td>
</tr>
<tr class=''>
<td class='property-column1'>Description</td>
<td class='property-column2'></td>
</tr>
<tr class=''>
<td class='property-column1'>Profile type</td>
<td class='property-column2'>Named locations</td>
</tr>
<tr class=''>
<td class='property-column1'>Created</td>
<td class='property-column2'>Wednesday, 7 September 2022 13:48:18</td>
</tr>
<tr class=''>
<td class='property-column1'>Last modified</td>
<td class='property-column2'>Friday, 3 February 2023 08:18:30</td>
</tr>
</table>

###### Table 39. Basics - ALLOWED COUNTRIES


<table class='table-settings'>
<tr class='table-header1'>
<td>Name</td>
<td>Value</td>
</tr>
<tr class=''>
<td class='property-column1'>Country lookup method</td>
<td class='property-column2'>Determine location by IP address (IPv4 and IPv6)</td>
</tr>
<tr class=''>
<td class='property-column1'>Include unknown countries/regions</td>
<td class='property-column2'>Disabled</td>
</tr>
<tr class=''>
<td class='property-column1'>Countries</td>
<td class='property-column2'><br /><br /></td>
</tr>
</table>

###### Table 40. Settings - ALLOWED COUNTRIES



