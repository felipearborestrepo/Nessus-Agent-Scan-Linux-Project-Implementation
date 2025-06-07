# Nessus Agent Scan Project Implementation on Linux

In this project, we demonstrate the deployment of a Nessus Agent on an **Ubuntu Linux 22.04 VM** in **Azure**, and the configuration of an authenticated vulnerability scan using Tenable’s cloud platform.

_**Inception State:**_ No Nessus Agent installed or configured, no scan group created.

_**Completion State:**_ Nessus Agent fully installed, agent group created, scan run, vulnerabilities identified, and initial assessment conducted.

---

# Technology Utilized
- **Tenable** (Nessus Agent, Tenable.io Cloud platform)
- **Azure Virtual Machines** (Ubuntu 22.04)
- **Bash** (Agent installation and configuration)
- **Tenable Agent Groups** (for grouping scan targets)

---

## 1. VM and Nessus Agent Setup

**We start by provisioning an Ubuntu Linux 22.04 virtual machine on Azure:**

![1- Created VM](./1- Created Vm.png)

---

## 2. Nessus Agent Group Creation

**In Tenable, I created a new Agent Group called `LABUSER-AgentGroupLinux` to logically organize the agent(s):**

![2- Creating a Nessus Agent Group](./2- Creating a Nessus Agent Group.png)

![3- Adding Group Name](./3- Adding Group Name.png)

---

## 3. Nessus Agent Scan Creation

**In Tenable, I created a Basic Agent Scan including the newly created `LABUSER-AgentGroupLinux`:**

![4- Creating an Agent Scan](./4- Creating an Agent Scan.png)

**Selecting the “Basic Agent Scan” template:**

![5- Choosing Basic Agent Scan](./5- Choosing Basic Agent Scan.png)

**Editing the scan to include the agent group:**

![6- Editing Scan](./6- Editing Scan.png)

**Setting the scan type to “Triggered Scan” and specifying a filename trigger (`dishsoap.lol`):**

![7- Setting Scan Type to Triggered Scan - Filename - and creating a trigger dishsoap.lol file](./7- Setting Scan Type to Triggered Scan - Filename - and creating a trigger dishsoap.lol file.png)

---

## 4. Install Nessus Agent in Linux VM

**Logged into the Linux VM as root:**

![8- Logging Inside Linux Ubuntu VM from Terminal](./8- Logging Inside Linux Ubuntu VM from Terminal.png)

**Downloaded and installed the Nessus Agent using the command from Tenable:**

![9- Getting Command from Tenable to run in terminal to install Nessus Agent inside the Linux VM](./9- Getting Command from Tenable to run in terminal to install Nessus Agent inside the Linux VM.png)

![10- Including my group name in the command](./10- Including my group name in the command.png)

**Running as root and running the command to install the Nessus Agent:**

![11- Running as root - running code to install the Nessus Agent](./11- Running as root - running code to install the Nessus Agent.png)

**Installation process:**

![12- Process of installation](./12- Process of installation.png)
![13- Process of Installation](./13- Process of Installation.png)
![14- Installation Completed](./14- Installation Completed.png)

---

## 5. Confirm Nessus Agent Status

**Verified that the Nessus Agent was running properly:**

```bash
sudo systemctl status nessusagent.service
![17- Ran this command to make sure the agent was running](./17- Ran this command to make sure the agent was running.png)

## 6. Create the Trigger File in Linux
Navigated to the triggers directory and created the `dishsoap.lol` file:

```bash
cd /opt/nessus_agent/var/nessus/triggers
touch dishsoap.lol
![15- Creating dishsoap.lol inside the triggers folder](./15- Creating dishsoap.lol inside the triggers folder.png)

Checking file details:

bash
Copy
Edit
ls -lasht
![16- checking the size of the file](./16- checking the size of the file.png)

7. Triggered Scan Results
After about 10 minutes, the file dishsoap.lol was automatically detected, the scan triggered, and the file deleted:

![18- After 10 minutes the file was deleted from the folders making the agent successful](./18- After 10 minutes the file was deleted from the folders making the agent successful.png)

In Tenable, the scan was triggered and is now showing as “Triggered” and “Enabled”:

![19- Tenable showing the scan was triggered](./19- Tenable showing the scan was triggered.png)

Project Summary
This project demonstrates the deployment and configuration of the Tenable Nessus Agent on an Ubuntu Linux 22.04 VM in Azure, using Tenable’s cloud-based scanning platform. It showcases:

✅ VM creation
✅ Nessus Agent Group creation
✅ Nessus Agent installation and linking
✅ Triggered scan configuration
✅ Verification of file-based triggers and scan results
