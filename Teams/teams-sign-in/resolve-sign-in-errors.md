---
title: Resolve sign-in errors in Teams
description: Provides troubleshooting steps if you encounter errors when trying to sign in to Microsoft Teams. 
author: v-charloz
ms.author: v-chazhang
manager: dcscontentpm
audience: ITPro 
ms.topic: troubleshooting 
ms.service: msteams
localization_priority: Normal
ms.custom: 
- CI 156289
- CSSTroubleshoot
ms.reviewer: billkau; meerak
appliesto:
- Microsoft Teams
search.appverid: 
- MET150
---
# Resolve sign-in errors in Teams

**Note:** This article is intended for tenant administrators.

If your users encounter errors when they try to sign in to Microsoft Teams, use the following steps to troubleshoot the problem:

1. Run the Teams Sign-in diagnostic:

    1. Select the following button to populate the diagnostic in the Microsoft 365 admin center:
        >[!div class="nextstepaction"]
        >[Diag: Teams Sign-in](https://aka.ms/TeamsSignInDiag)
    1. In the **User Name or Email Address field**, enter the email address of the user who's experiencing the Teams sign-in issue.

1. If the diagnostic detects an issue that affects the instance of Teams on the tenant, follow the provided solution to fix the issue. If the diagnostic doesn't detect an issue, check whether the user's [Teams client is running the latest update](https://support.microsoft.com/en-us/office/update-microsoft-teams-535a8e4b-45f0-4f6c-8b3d-91bca7a51db1). Select the **Settings and more** menu next to the user's profile picture at the top right of the Teams window, and then select **Check for updates**.

    The desktop app is configured to update automatically. However, if you find that the app is missing the latest update, follow the instructions to install it, and try again to sign in. If you still see an error when you try to sign in to Teams, go to step 3.

1. If you use a federated sign-in provider such as Active Directory Federation Services (AD FS), verify the AD FS sign-in configuration by using the  [Office 365 Single Sign-on Test](https://testconnectivity.microsoft.com/tests/SingleSignOn/input) in the Microsoft Remote Connectivity Analyzer.

1. Check the error code on the Teams sign-in screen. If the code is listed here, follow the provided guidance to fix the error. If the code isn't listed here, see [Why am I having trouble signing in to Microsoft Teams?](https://support.microsoft.com/en-us/topic/a02f683b-61a3-4008-9447-ee60c5593b0f)

    - **0xCAA82EE7** or **0xCAA82EE2**  
        Make sure that the user has Internet access. Then, use the [Network assessment tool](https://www.microsoft.com/en-us/download/details.aspx?id=53885) to verify that the network and network elements between the user location and the Microsoft network are configured correctly. This is necessary to enable communication to the IP addresses and ports that are required for Teams calls.

        For information about endpoints that users should be able to reach if they're using Teams in Office 365 plans, government environments, or other clouds, see [Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges).

    - **0xCAA20004**  
        This error occurs if an issue affects conditional access. For more information, see [Conditional Access policies for Teams](/microsoftteams/security-compliance-overview#how-conditional-access-policies-work-for-teams).

    - **0xCAA70004** or **0xCAA70007**, or if the sign-in issue also occurs in other Office applications: See [Connection issues in sign-in after update to Office 2016 build 16.0.7967](/Microsoft365/admin/authentication/connection-issue-when-sign-in-office-2016).

1. If the sign-in error occurs only in the Teams web client, see [Microsoft Teams is stuck in a login loop](sign-in-loop.md) for resolutions that are specific to the user's preferred browser.

1. If the error persists, reinstall Teams as follows:

    1. [Uninstall Teams](https://support.microsoft.com/en-us/windows/uninstall-or-remove-apps-and-programs-in-windows-10-4b55f974-2cc6-2d2b-d092-5905080eaf98).
    1. Browse to the *%appdata%\Microsoft* folder on the user's computer, and delete the *Teams* folder.
    1. Download and install [Teams](https://www.microsoft.com/en-us/microsoft-teams/group-chat-software). If possible, reinstall Teams as an administrator. To do this, right-click the Teams installer file, and select  **Run as administrator**.

If none of these steps help to resolve the Teams sign-in issue, create a support request. For the request, [collect debug logs](/microsoftteams/log-files), and provide the error code that's displayed on the Teams sign-in screen.