---
title: Active Directory best Practices
date: 2023-05-09 08:00:00 +0200
categories: [Active Directory, Domain Controller]
tags: [best praticices]     # TAG names should always be lowercase
img_path: /assets/img/posts
#pin: true
#toc: false
#comments: false
#math: true
mermaid: true
---

## Introduction
In this document i will centralized all best praticices to setup an configure an Active Directory domain.
This list might be not complete but it is a good start.

## Items
* Enable reverse lookup
* Configure DNS redirector to at least 2 public DNS
* Local DNS configuration for DC have to use 127.0.0.1 at the bottom of the DNS server list
* Create the KDS root key to enable the use of gMSA
* Dispatch FSMO roles on different servers
* The database folder and the sysvol folder should be on dedicated disk
* Define naming convention for users, devices, groups
* Users, Endpoints and Servers should not be in the same OU
* Have one GC per AD site (Do not set GC on RODC)
* Keep in mind that your OU should reflect something real in your organization
Aim something like that :
   
<div class="mermaid">
graph TD;
    A[Domain root]-->B[Bastien-W];
    B[Bastien-W]-->C[Paris];
    C[Paris]-->D[Devices]-->E[Endpoints];
    D[Devices]-->F[Servers];
    C[Paris]-->G[Users];
    C[Paris]-->H[Groups];
    B[Bastien-W]-->I[London]-->J[...];
</div>