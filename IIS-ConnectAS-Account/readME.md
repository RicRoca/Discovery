# Discover ConnectAs Account

## What is ConnectAs

ConnectAs credentials allow Websites, Virtual Directories, and Applications in IIS to use alternatives credentials to connect to drives, and folders.

| Environment | Version |
| ------ | ------ |
| Secret Server | 10.0+ |
| Operating System | Any Supported |
| PowerShell | Windows Management Framework 3+ |

## Prerequisites

- Powershell remoting enabled on these machines
- WebAdministration PowerShell Module installed on the remote machines

## Installation

1. Apply Discover ConnectAs script:
    - **ADMIN** > **Scripts**
2. Configure Scan Template:
    - **ADMIN** > **Discovery** > **Extensible Discovery** > **Configure Scan Templates** >
    - **Dependencies** > **Create New Scan Template**

    ![Scan Template Designer](imgs/scanner-1.PNG)

3. Configure Discovery Scanner:
    - **ADMIN** > **Discovery** > **Extensible Discovery** > **Configure Discovery Scanners** >
    - **Dependencies** > **Create New Scanner**
    - **Input Template**: Windows Computer
    - **Output Template**: Select scan template from step 2
    - **Script**: Select  script from step 1
    - **Arguments**:$target

    ![Create New Scanner](imgs/scanner-2.PNG)

4. Adding the Scanner
    - **ADMIN** > **Discovery** > **Edit Discovery Sources** and select your source
    - Click on **Scanner Settings** Tab
    - Scroll down to **Find Dependencies** > **Add New Dependency Scanner**
    - Select **ConnectAs** from the scanner list

    ![Add Scanner](imgs/scanner-3.PNG)

5. Run Discovery, PROFIT!
    - The new scanner will find the Dependencies
    - You will not be able to import without a [Dependency a dependency changer](https://github.com/thycotic/PasswordChangers/tree/master/Dependencies/ConnectAS "ConnectAS Changer")
