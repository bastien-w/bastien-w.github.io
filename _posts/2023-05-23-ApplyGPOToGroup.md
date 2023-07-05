---
title: How to Apply a GPO to a group
date: 2023-05-23 08:00:00 +0200
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

Group Policy Objects (GPOs) are a powerful tool for managing and configuring Windows environments. However, there may be times when you want to apply a GPO only to a specific group of users or computers within your Active Directory (AD) environment. In this post, we'll show you how to apply a GPO only to a specified AD group.

## How to

1. Open the Group Policy Management Console (GPMC) by going to Start > Administrative Tools > Group Policy Management.

2. In the left pane of the GPMC, expand the Forest and Domain nodes until you see the Group Policy Objects node. Right-click on the GPO that you want to apply only to the specified AD group and select "Edit".

3. In the Group Policy Management Editor window that opens, navigate to the Scope tab.

4. In the "Security Filtering" section of the Scope tab, click on the "Add" button.

5. In the "Select User, Computer, or Group" window that opens, enter the name of the AD group that you want to apply the GPO to and click "OK".

6. In the Advanced Security Settings window, select "Authenticated Users" list and then scroll down in the "Permissions for Authenticated Users" box until you see the "Apply group policy" permission.

7. Uncheck the "Apply" box next to the "Apply group policy" permission and then click "OK" to save your changes.

## Notes

Nested group works fine and you can use this method for users and computers

## Conclusion

That's it! The GPO will now be applied only to members of the specified AD group. Keep in mind that applying a GPO only to a specific group can have unintended consequences, so be sure to test your changes thoroughly before implementing them in a production environment.
