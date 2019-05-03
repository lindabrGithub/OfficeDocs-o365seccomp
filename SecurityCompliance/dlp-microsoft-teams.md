---
title: "Data loss prevention and Microsoft Teams"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/03/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: 
- M365-security-compliance
search.appverid: 
- MET150
description: "You can now apply DLP policies to Microsoft Teams chats and channels. Read this article to learn more about how it works."
---

# Data loss prevention and Microsoft Teams

> [!NOTE]
> Data loss prevention capabilities were recently added to Microsoft Teams in Office 365 E5 and Office 365 Advanced Compliance. To learn more about feature availability, see [Office365 Service Descriptions: Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## Overview of DLP for Microsoft Teams

Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams. If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session. Here are some examples of how this protection works:

- **Example 1: Protecting sensitive information in messages**. Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users). If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted. This happens automatically, and within seconds, according to how your DLP policy is configured.

- **Example 2: Protecting sensitive information in documents**. Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information. If you have a DLP policy defined to prevent this, the document won't open for those users. Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.

## Policy tips help educate users

Similar to how DLP works in [Exchange, Outlook, and Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint and OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy. Here's an example of a policy tip:

![Blocked message notification in Teams](media/dlp-teams-blockedmessage-notification.png)

In this case, the sender attempted to share a social security number in a Microsoft Teams channel. The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue. Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.

![Options to resolve blocked message](media/dlp-teams-blockedmessage-possibleactions.png)

In your organization, you can choose whether to allow users to override a DLP policy, or not. And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization. 

Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:

![Message blocked](media/dlp-teams-blockedmessage-notification-to-user.png)

The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.

### To customize policy tips

To perform this task, you must be assigned a role that has permissions to edit DLP policies. To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).

1. Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.

2. Choose **Data loss prevention** > **Policy**. 

3. Select a policy, and next to **Policy settings**, choose **Edit**.

4. Either create a new rule, or edit an existing rule for the policy.<br/>![Editing a rule for a policy](media/dlp-teams-editrule.png)<br/>

5. On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.<br/>![Customize user notifications and policy tips](media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**. 

7. On the **Policy settings** tab, choose **Save**.

Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.
 
## Add Microsoft Teams as a location to existing DLP policies

To perform this task, you must be assigned a role that has permissions to edit DLP policies. To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).

1. Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.

2. Choose **Data loss prevention** > **Policy**. 

3. Select a policy, and look at the values under **Locations**. If you see **Teams chat and channel messages**, you're all set. If you don't, click **Edit**.<br/>![Locations for existing policy](media/dlp-teams-editexistingpolicy.png)<br/>

4. In the **Status** column, turn the policy on for **Teams chat and channel messages**.<br/>![DLP for Teams chats and channels](media/dlp-teams-addteamschatschannels.png)<br/>

5. Keep the default settings of all accounts, or specify which accounts to include or exclude.

6. Click **Save**.

Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.

## Define a new DLP policy for Microsoft Teams

To perform this task, you must be assigned a role that has permissions to edit DLP policies. To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).

1. Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.

2. Choose **Data loss prevention** > **Policy** > **+ Create a policy**. 

3. Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.<br/>In our example, we chose the U.S. Personally Identifiable Information Data template.<br/>![Privacy template for DLP policy](media/dlp-teams-createnewpolicy-template.png)<br/>

4. On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**. 

5. On the **Choose locations** tab, keep the default setting of all locations, or select **Let me choose specific locations**, and then choose **Next**.<br/>If you opted to choose specific locations, select the locations for your DLP policy, and then choose **Next**.<br/>![DLP policy locations](media/dlp-teams-selectlocationsnewpolicy.png)<br/>
    > [!NOTE]
    > If you want to make sure documents that contain sensitive information are not shared inappropriately, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.
<br/>

6. On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**. If you choose advanced settings, you can create or edit rules for your policy. (To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)

7.  On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings. (Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)<br/>![DLP policy settings with tips and notifications](media/dlp-teams-policysettings-tipsemails.png)<br/>When you're finished reviewing or editing settings, choose **Next**.

8. On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.<br/>![Specify whether to turn the policy on](media/dlp-teams-policysettings-turnonnow.png)<br/>

9. On the **Review your settings** tab, review the settings for your new policy. Choose **Edit** to make changes. When you're finished, choose **Create**. 

Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.

## Related articles

[Create, test, and tune a DLP policy](create-test-tune-dlp-policy.md)

[Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md)