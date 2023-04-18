---
title: TITLE
date: 2023-04-17 09:00:00 +0200
categories: [Microsoft 365, Microsoft Intune]
tags: [enrollment] # TAG names should always be lowercase
img_path: /assets/img/posts
#pin: true
#toc: false
#comments: false
#math: true
#mermaid: true
---
{% capture check %}<i class="fa-solid fa-check" style="color: #00ff00;"></i>{% endcapture %}
{% capture mark %}<i class="fa-solid fa-xmark" style="color: #ff0000;"></i>{% endcapture %}

## Introduction
This post is to give a quick overview of the enrollment methods available for each OS

## Windows

For existing Windows Device if you want to be hybrid most of the time you are going to use the GPO enrollment and User Enrollment if you want to be Azure AD Join Only (with Company portal or by windows Settings)

For New devices the recommanded way is to use Windows Autopilot

## iOS

In most cases Automated Device Enrollment will be used for new devices and User Enrollment for existing one, MAM is a good option too.

| Feature | Automated Device Enrollment | Apple Configurator | User Enrollment |
|:-:|:-:|:-:|:-:|
| BYOD | {{mark}} |{{mark}} |{{check}} | 
| Corporate Device |  {{check}} | {{check}} |{{mark}} | 
| New Device |  {{check}} | {{check}} |{{check}} | 
| Existing Device |  {{mark}} | {{check}} |{{check}} | 
| Device associated to a user |  {{check}} | {{check}} |{{check}} | 
| Device not associated to a user |  {{check}} | {{check}} |{{mark}} | 
| DEM Account | {{mark}} |{{mark}} |{{check}} | 
| Is Supervised |  {{check}} | {{check}} |{{mark}} | 
| Cannot use ABM or ASM | {{mark}} | {{check}} |{{check}} | 

## MacOS

## Android

In most cases for new device you will use Fully Managed or Dedicated Device depending on whenever you need users afinity or not.
For existing device i recommand using MAM policies.

I'm not going to cover Android AOSP which is rarely used.

And Corporate Owned with work profile is deprecated since Android 11 so i'm not going to cover this.

| Feature | Automated Device Enrollment | Apple Configurator | User Enrollment |
|:-:|:-:|:-:|:-:|
