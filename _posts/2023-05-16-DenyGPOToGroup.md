---
title: How to Deny GPO to a group
date: 2023-05-16 08:00:00 +0200
categories: [Active Directory, Group Policy]
tags: [security]     # TAG names should always be lowercase
img_path: /assets/img/posts/2023-05-23-ApplyGPOToGroup
#pin: true
#toc: false
#comments: false
#math: true
#mermaid: true
---
## Introduction

Group Policy Objects (GPOs) are a powerful tool for managing and configuring Windows environments. However, there may be times when you want to prevent a GPO from being applied to a specific group of users or computers within your Active Directory (AD) environment. In this post, we'll show you how to deny GPO application for an AD group.

## How to

1. Open the Group Policy Management Console (GPMC) by going to Start > Administrative Tools > Group Policy Management.

2. In the left pane of the GPMC, expand the Forest and Domain nodes until you see the Group Policy Objects node. Right-click on the GPO that you want to prevent from being applied to the AD group and select "Edit".

3. In the Group Policy Management Editor window that opens, navigate to the Delegation tab.

4. Click on the "Advanced" button in the bottom-right corner of the window.

5. In the Advanced Security Settings window that opens, click on the "Add" button.

6. In the "Select User, Computer, or Group" window that opens, enter the name of the AD group that you want to prevent from having the GPO applied and click "OK".

7. Back in the Advanced Security Settings window, select the newly added group in the "Group or user names" list and then scroll down in the "Permissions for [group name]" box until you see the "Apply group policy" permission.

8. Check the "Deny" box next to the "Apply group policy" permission and then click "OK" to save your changes.

## Notes

Nested group works fine and you can use this method for users and computers

## Conclusion

That's it! The GPO will now be denied for members of the specified AD group. Keep in mind that denying a GPO can have unintended consequences, so be sure to test your changes thoroughly before implementing them in a production environment.
