---
title: Active Directory best Practices
date: 2023-04-17 08:00:00 +0200
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
This list is not complet and will be updated

## Items
1. Enable reverse lookup for all IP ranges
2. Configure DNS redirector to at least 2 public DNS
3. Local DNS configuration for DC have to use 127.0.0.1 at the bottom of the DNS server list
4. Create the KDS root key to enable the use of gMSA
5. Dispatch FSMO roles on different servers
6. The database folder and the sysvol folder should be on dedicated disk
7. Define naming convention for users, devices, groups
8. Users, Endpoints and Servers should not be in the same OU
   1. Keep in mind that your OU should reflect something real in you organization
   2. Aim something like that :
```mermaid
graph TD;
    A[Domain root]-->B[Bastien-W];
    B[Bastien-W]-->C[Paris];
    C[Paris]-->D[Devices];
    D[Devices]-->E[Endpoints];
    D[Devices]-->F[Servers];
    C[Paris]-->G[Users];
    C[Paris]-->H[Groups];
    B[Bastien-W]-->I[Londre]-->J[...];
```

