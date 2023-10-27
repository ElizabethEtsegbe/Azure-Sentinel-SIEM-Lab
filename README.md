# Azure Sentinel (SIEM) Lab with Live Attack Observations

In this Azure Sentinel (SIEM) Lab, I set up Azure Sentinel, connecting it to a live virtual machine acting as a honey pot, and observing live attacks, specifically RDP Brute Force attempts, from around the world. In this lab, I also use a custom PowerShell script to retrieve attackers' Geolocation information and plot it on the Azure Sentinel Map.

## Table of Contents
1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Lab Setup](#lab-setup)
   - [Creating a Honey Pot VM](#creating-a-honey-pot-vm)
   - [Setting Up Azure Sentinel](#setting-up-azure-sentinel)
   - [Connecting Azure Sentinel and Honey Pot](#connecting-azure-sentinel-and-honey-pot)
4. [Observing Live Attacks](#observing-live-attacks)
   - [Monitoring RDP Brute Force Attempts](#monitoring-rdp-brute-force-attempts)
5. [Geolocation Information Retrieval](#geolocation-information-retrieval)
   - [Developing a Custom PowerShell Script](#developing-a-custom-powershell-script)
   - [Automating Geolocation Lookup](#automating-geolocation-lookup)
6. [Plotting on Azure Sentinel Map](#plotting-on-azure-sentinel-map)
   - [Integrating Geolocation Data](#integrating-geolocation-data)
   - [Visualizing on the Azure Sentinel Map](#visualizing-on-the-azure-sentinel-map)
7. [Contributing](#contributing)
8. [License](#license)

## Introduction

Azure Sentinel is a cloud-native security information and event management (SIEM) solution that provides intelligent security analytics for your entire enterprise. In this lab, we will not only set up Azure Sentinel but also dive deep into live threat monitoring and geolocation mapping, which are valuable skills for any cybersecurity professional.

## Prerequisites

- An active Azure subscription with the necessary permissions.
- Basic knowledge of Azure services, virtual machines, and PowerShell scripting.
- Access to a separate, isolated Azure environment for hosting your honey pot VM.

## Lab Setup

### Creating a Honey Pot VM

1. **Deploy a Virtual Machine:**
   - Create a new VM in Azure specifically for use as a honey pot.
   - Configure this VM to be isolated from your production environment.
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/4614b490-3d48-4599-b9a0-dded7051b0ad" width="400" alt="Screenshot">
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/d160ec5f-8f09-4bd1-b548-fb6a206c7157" width="400">



### Setting Up Azure Sentinel

1. **Create an Azure Sentinel Workspace:**
   - Establish an Azure Sentinel workspace within your Azure subscription.
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/d3699402-ff1f-4be9-b30f-04cd88d61d02" width="400">
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/d03abce7-dbd2-45ce-a6b8-e2d83331300e" width="400">

2. **Configure Data Connectors:**
   - Configure the necessary data connectors in Azure Sentinel to collect security data from various sources.
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/f636cfd3-b947-4b05-9ad3-7ebe0948357e" width="400">

### Connecting Azure Sentinel and Honey Pot

1. **Configure Honey Pot VM Logs:**
   - Adjust the logging settings on your honey pot VM to capture security-related logs.
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/360b0d57-23c7-4464-bd10-a5f364b01e63" width="400">
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/2255228b-5eff-470b-b8ac-3a9b3fe1a996" width="400">

2. **Forward Logs to Azure Sentinel:**
   - Configure the honey pot VM to send these logs to your Azure Sentinel workspace for analysis.
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/ab1e0bed-f2a7-4cca-9f7d-e39eae8e7111" width="400">


## Observing Live Attacks

### Monitoring RDP Brute Force Attempts

1. **Set Up Alert Rules:**
   - Create alert rules in Azure Sentinel that trigger on specific RDP Brute Force patterns.
   
2. **View Live Attacks:**
   - Monitor the live RDP Brute Force attacks on your honey pot VM through Azure Sentinel's real-time dashboards.

## Geolocation Information Retrieval

### Developing a Custom PowerShell Script

1. **Script Creation:**
   - Develop a custom PowerShell script that takes the attackers' IP addresses, retrieves their geolocation information, and stores it in a suitable format.
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/e4135e56-183d-40b3-86ff-b0fbc6b8506b" width="400">

2. **Test the Script:**
   - Test the script on sample IP addresses to ensure accurate geolocation data retrieval.
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/d3444206-fcc3-42a5-9cf6-c93af13fe190" width="400">

### Automating Geolocation Lookup

1. **Script Scheduling:**
   - Set up a scheduled task on your honey pot VM to run the PowerShell script at regular intervals.

2. **Collecting Geolocation Data:**
   - Collect geolocation data for ongoing attacks, enriching your threat intelligence.

## Plotting on Azure Sentinel Map

### Integrating Geolocation Data

1. **Data Ingestion:**
   - Ingest the geolocation data into Azure Sentinel for analysis.

2. **Create Custom Log Queries:**
   - Write custom log queries in Azure Sentinel to extract geolocation information.
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/b99cab22-a350-4eaa-bc51-79848ae95231" width="400">
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/93bc01e1-5df5-4989-8663-08d25a9bc6f5" width="400">

### Visualizing on the Azure Sentinel Map

1. **Map Visualization:**
   - Use the Azure Sentinel Map to visualize the geographical locations of attackers based on the retrieved geolocation data.
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/47991b33-bd26-48c4-a409-cc015a383f12" width="400">
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/d97f29ce-9014-4339-8e8e-8982967256f5" width="400">

2. **Customize Dashboard:**
   - Customize your Azure Sentinel dashboard to include the map visualization for real-time insights.
<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/0fcad663-599f-4916-8d1b-19f21101a048" width="400">

After 1 hour

<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/3ebdab7f-5a85-4960-a926-5e0a24d3c485" width="400"> 

After 6 Hours

<img src="https://github.com/ElizabethEtsegbe/Azure-Sentinel-SIEM-Lab/assets/148573965/8915ca72-1a9e-4b19-b1d0-5b322b328643" width="400">

After 12 hours 


This comprehensive lab offers a deep dive into Azure Sentinel, threat monitoring, and geolocation mapping
