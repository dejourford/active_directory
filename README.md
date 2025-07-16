# Active Directory Lab

<img src="images/diagram.png" alt="infrastructure diagram" width=600/>

## Objective

The purpose of this lab is to use VirtualBox to simulate a corporate environment where there are hundreds of users on an internal network.The Domain Controller will have a NAT adapter, enabling internet access, which will also be used by the machines that
are joined to the domain. Windows Server, Active directory and Remote Access will be installed on the Domain Controller.DHCP will be
used to give each machine joined to the domain a unique IP Address. A client machine will also be set up to test logins and domain connectivity. The client machine will have Windows 10 ISO installed. A PowerShell script will be run to create 1000 unique users so they won't have to be created manually, which would take too much time.

## Project Files

| File Name        | Description                        |
|------------------|------------------------------------|
| Images           | Folder for image files             |
| create_users.ps1 | Script to create users             |
| names.txt        | File containing random names       |


## What I Did

Create a new Domain Controller with two adapters, NAT and Internal Network, and Windows Server ISO installed.

<img src="images/domain_controller.png" alt="domain controller screenshot" width=600/><br />

Install Windows Server ISO on the Domain Controller

<img src="images/install_windows_server.png" alt="windows server installation" width=600/> <br />

Install Active Directory

<img src="images/install_active_directory.png" alt="active directory installation" width=600/><br />

Create Domain named `cyberjour`

<img src="images/create_domain.png" alt="domain creation" width=600/> <br />

Create Admin User

<img src="images/create_admin_user.png" alt="admin user creation" width=600/><br />

Add created admin user to domain admins

<img src="images/add_user_to_domain_admins.png" alt="add user to domain admins" width=600/><br />

Install Remote Access

<img src="images/install_remote_access.png" alt="install remote access" width=600/><br />

Configure Remote Access

<img src="images/configure_remote_access.png" alt="configure remote access" width=600/><br />

Install DHCP Server

<img src="images/install_dhcp_server.png" alt="install dhcp server" width=600/><br />

Setup and authorize DHCP

<img src="images/setup_and_authorize_dhcp.png" alt="dhcp setup" width=600/><br />

Run PowerShell script in PowerShell ISE to create 1000 users in Active Directory

<img src="images/run_script.png" alt="run script" width=600/><br />
