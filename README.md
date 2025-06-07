# Nessus Agent Scan Project Implementation on Linux

![Linux-Logo-1996-present-700x394](https://github.com/user-attachments/assets/c849f4c6-be62-441b-92fd-f0b92d33c994)

In this project, we demonstrate the deployment of a Nessus Agent on an **Ubuntu Linux 22.04 VM** in **Azure**, and the configuration of an authenticated vulnerability scan using Tenable’s cloud platform.

_**Inception State:**_ No Nessus Agent installed or configured, no scan group created.

_**Completion State:**_ Nessus Agent fully installed, agent group created, scan run, vulnerabilities identified, and initial assessment conducted.

---

# Technology Utilized ✅
- **Tenable** (Nessus Agent, Tenable.io Cloud platform)
- **Azure Virtual Machines** (Ubuntu 22.04)
- **Bash** (Agent installation and configuration)
- **Tenable Agent Groups** (for grouping scan targets)

---
![graphic_nessus_agent_technical_paper1](https://github.com/user-attachments/assets/a4a1d091-9d7c-4d81-a9d8-38c751933405)

## 1. VM and Nessus Agent Setup✅

**We start by provisioning an Ubuntu Linux 22.04 virtual machine on Azure:**

![1- Created Vm](https://github.com/user-attachments/assets/cbdba0f0-bd69-42f4-92b4-40ff82dd3430)

---

## 2. Nessus Agent Group Creation✅

**In Tenable, I created a new Agent Group called `LABUSER-AgentGroupLinux` to logically organize the agent(s):**

![2- Creating a Nessus Agent Group](https://github.com/user-attachments/assets/b10d81eb-e26a-4aac-827f-cbb3d937b7be)

![3- Adding Group Name](https://github.com/user-attachments/assets/127baea3-9d5b-49b5-8123-963dd81f3632)

---

## 3. Nessus Agent Scan Creation✅

**In Tenable, I created a Basic Agent Scan including the newly created `LABUSER-AgentGroupLinux`:** ✅

![4- Creating an Agent Scan](https://github.com/user-attachments/assets/9e9ea15d-729b-44da-a94c-29d0d95ec9ad)

**Selecting the “Basic Agent Scan” template:** ✅

![5- Choosing Basic Agent Scan](https://github.com/user-attachments/assets/5a1a00e8-dfe7-49c3-a61c-41a1a861da91)

**Editing the scan to include the agent group:** ✅

![6- Editing Scan](https://github.com/user-attachments/assets/dd59d351-6bda-41e9-898c-f2631785b126)

**Setting the scan type to “Triggered Scan” and specifying a filename trigger (`dishsoap.lol`):** ✅

![7- Setting Scan Type to Triggered Scan - Filename - and creating a trigger dishsoap lol file](https://github.com/user-attachments/assets/d96e6dba-ffae-4a33-891a-5ed9d3adf880)

---

## 4. Install Nessus Agent in Linux VM ✅

**Logged into the Linux VM as root:** ✅

![8- Logging Inside Linux Ubuntu VM from Terminal](https://github.com/user-attachments/assets/dedf6113-479b-4455-adbd-aed5e302ae49)

**Downloaded and installed the Nessus Agent using the command from Tenable:** ✅

![9- Getting Command form Tenable to run in terminal to install Nessus Agent inside the Linux VM](https://github.com/user-attachments/assets/b961a003-dd6f-44a9-af01-e9b26da2c93b)

![10- Including my group name in the command](https://github.com/user-attachments/assets/27b3dd6b-c661-4461-b5a6-0ae3cf29e495)

**Running as root and running the command to install the Nessus Agent:** ✅

![11- Running as root - running code to install the Nessus Agent](https://github.com/user-attachments/assets/64a79808-55aa-4c62-a60e-36edba271653)

**Installation process and completion:** ✅

![12- Process of installation](https://github.com/user-attachments/assets/107a2132-59dd-4a44-860d-25e34f93ee11)

![13- Process of Installation](https://github.com/user-attachments/assets/587afe37-1f05-4ca0-a230-17023c485c8f)

![14- Installation Completed](https://github.com/user-attachments/assets/baaf778f-41b0-4a76-8dc5-e4d87e355f1b)

---

## 5. Create the Trigger File in Linux✅ 
**Navigated to the triggers directory and created the `dishsoap.lol` file:**

**Command: touch /opt/nessus_agent/var/nessus/triggers/dishsoap.lol**

![15- Creating dishsoap lol inside the triggers folder](https://github.com/user-attachments/assets/7bc79dc0-1da4-469d-88dd-eb3a4c823469)

**Checking file details:** ✅

**Command: ls -lasht** ✅

![16- checking the size of the file](https://github.com/user-attachments/assets/961175e0-f96d-44e9-b4de-e44c8c786558)

## 6. Confirm Nessus Agent Status✅

**Verified that the Nessus Agent was running properly:**

**command: sudo systemctl status nessusagent.service**

![17- Ran this command to make sure the agent was running](https://github.com/user-attachments/assets/8efe77c3-6f79-4438-b4f4-59d23b151c32)

## 7. Triggered Scan Results✅

**After about 10 minutes, the file dishsoap.lol was automatically detected, the scan triggered, and the file deleted:** ✅

![18- After 10 minutes the file was deleted from the folders making the agent successful](https://github.com/user-attachments/assets/79e5df4f-3b3c-4b39-934c-05c8a5eb6435)

**In Tenable, the scan was triggered and is now showing as “Triggered” and “Enabled”:** ✅

![19- Tenable showing the scan was triggered](https://github.com/user-attachments/assets/8e463c45-20d0-4ef1-afb9-a8ba70536715)

**Project Summary**

**This project demonstrates the deployment and configuration of the Tenable Nessus Agent on an Ubuntu Linux 22.04 VM in Azure, using Tenable’s cloud-based scanning platform. It showcases:**

-**✅ VM creation**
-**✅ Nessus Agent Group creation**
-**✅ Nessus Agent installation and linking**
-**✅ Triggered scan configuration**
-**✅ Verification of file-based triggers and scan results**

![linux-pictures-h2knvdg022gb66t9](https://github.com/user-attachments/assets/ac5c9be3-de50-4c1d-8cc5-99ee8eec80c8)

