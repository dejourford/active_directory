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

Create Admin User and add to domain admins

<img src="images/create_admin_user.png" alt="admin user creation" width=600/><br />

<img src="images/add_user_to_domain_admins.png" alt="add user to domain admins" width=600/><br />

Install and configure Remote Access

<img src="images/install_remote_access.png" alt="install remote access" width=600/><br />

<img src="images/configure_remote_access.png" alt="configure remote access" width=600/><br />

Install, setup, and authorize DHCP Server

<img src="images/install_dhcp_server.png" alt="install dhcp server" width=600/><br />

<img src="images/setup_and_authorize_dhcp.png" alt="dhcp setup" width=600/><br />

Run PowerShell script in PowerShell ISE to create 1000 users in Active Directory

<img src="images/run_script.png" alt="run script" width=600/><br />

Verify users were successfully created by checking Active Directory

<img src="images/verify_users_created.png" alt="users in active directory" width=600/><br />

Create client machine and install windows

<img src="images/create_client_machine.png" alt="create client machine" width=600/><br />

<img src="images/install_windows.png" alt="install windows" width=600/><br />

Upon login, check for internet access by pinging google.com

<img src="images/ping.png" alt="ping" width=600/><br />

Check host name, join domain, and check DHCP for address lease

<img src="images/check_host_name.png" alt="join domain" width=600/><br />

<img src="images/join_domain.png" alt="join domain" width=600/><br />

<img src="images/dhcp_lease_check.png" alt="check address lease" width=600/><br />

Since now domain joined, check if other created users can login

<img src="images/check_sign_in.png" alt="check user sign on" width=600 /><br />

<img src="images/check_sign_in2.png" alt="check user sign on" width=600/><br />

## Discussion

I installed Windows Server ISO, Active Directory, and DHCP on the Domain Controller. I then created a domain named `cyberjour`, created an Admin User, and added the user to the Admin Domain. Remote Access was also installed for future plans. DHCP was setup to use IP ranges of 192.xxx.100-200. I executed the PowerShell script that references a text file contaning users by first name and last name to mass create 1000 users instead of doing it manually.


The script works as follows:

1. The text file containing users by first and last name is assigned as an array to a variable

2. A for-loop is executed for each name in the array

3. The name is split on the empty string and the value in the first position is assigned to the first name variable the value in the first position (ex. De'Jour Ford --> De'Jour)

4. The name is split on the empty string and the value in the second position is assigned to the last name variable (ex. De'Jour Ford --> Ford) 

5. The username is the result of the first character of the first name + last name then tranformed to lower case (ex. dford)

6. There's a write statement, "Creating User $($usernmae)" to help with debugging if there are issues

7. Finally, a user is created using commands in PowerShell and the variables

8. The process is repeated until each name in the loop is addressed


I then created the client machine and installed the Windows 10 ISO, logged in, and checked for internet connection by pinging google.com. I checked the host name to ensure the client machine wasn't a part of a domain, then added the client to the `cyberjour` domain and checked DHCP for the address lease. With a successful domain join, I tested a differnent user login from Active Directory to confirm everything was working properly.

## Planned Improvements

`Create a seperate Windows Server for DHCP to simulate real-world production environments`
    
    1. DC - Domain Controller
    
    2. SRV-DHCP - DCHP Server
    
    3. CLIENT1 - Client Machine
    
    4. CLIENT2 - Client Machine
    
    5. KaliLinux - Attacker Machine

`Create an internal machine hosting a vulnerable web app`

`Install outdated or vulnerable software and use **Nessus** to do a vulnerability scan`
