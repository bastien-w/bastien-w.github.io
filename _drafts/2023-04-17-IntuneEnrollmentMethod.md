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

If you aim to use Fully managed devices for new device i recommand to use MAM for existing one.

If you aim to use Corporate owned work profile you can use the BYOD enrollment (Personnal with work profile)

My recommandation is based on the user experience because if you aim to use Fully Managed and you do BYOD Enrollment the user will have a really different experience on the two devices. 

I'm not going to cover Android AOSP which is rarely used.

| Feature | Personnal/WorkProfile | Fully Managed | Dedicated | Corporate/Work Profile |
|:-:|:-:|:-:|:-:|
|Need Reset| {{mark}}|{{check}}|{{check}}|{{check}}|
| BYOD | {{check}} |{{mark}}|{{mark}}| {{mark}} |
| Corporate Device |{{mark}}|{{check}}|{{check}}|{{check}}|
| New Device |{{mark}}|{{check}}|{{check}}|{{check}}|
| Existing Device |{{check}} |{{mark}}|{{mark}}|{{mark}}|
| Device associated to a user |{{check}}|{{check}}|{{mark}}|{{check}}| 
| Device not associated to a user |{{mark}}|  {{mark}} | {{check}} |{{mark}} | 
| DEM Account |{{mark}}|{{mark}}|{{check}}|{{mark}}|