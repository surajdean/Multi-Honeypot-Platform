# Multi-Honeypot-Platform

In this guide, fill in later

## Tools Used

- Azure cloud
- PuTTy
- VirtualBox
- T-Pot

## Environments Used

- <b>Windows 10 VM</b>

## Part 1: Setup Lab Resources

### Step 1: Create a Free Azure Account

If you don't already have an Azure account, you can sign up for free at [this website](https://azure.microsoft.com/en-us/free/) and create an Azure free account.

Follow the steps to create an account, providing the necessary information and verifying your identity.

Once your account is created, you will have access to a range of Azure services, including virtual machines for hosting your honeypot.

Step 2: Install a Remote Connection Program

To access your virtual machine, you'll need a remote connection program like PuTTY.
PuTTY is a free, open-source SSH and telnet client for Windows.
You can download PuTTY from the official website: https://www.putty.org/.
Follow the instructions to download and install PuTTY on your computer.
Once installed, you'll be ready to connect to your Azure virtual machine securely.
Now that you have a free Azure account and a remote connection program installed, you're ready to proceed with creating your honeypot in the cloud using Azure. Let's move on to the next steps!

Step 1: Sign in to Azure Portal

Navigate to portal.azure.com and sign in with your Azure account credentials.
Step 2: Create a Virtual Machine

Once signed in, select "Virtual machines" from the dashboard.
Click on "Add" to create a new virtual machine.
Choose "Azure Virtual Machine" and click on "Create".
Create a new resource group or select an existing one. Name it appropriately.
Choose a recognizable name for your virtual machine, such as "Honeypot".
Select a region that is close to you, considering both proximity and cost implications.
Choose the Debian operating system and leave the architecture as default.
Optionally, enable the Azure spot discount to reduce the cost, but be aware of potential interruptions.
Select an appropriate size for your VM, considering the recommended minimum of 8GB RAM. We suggest choosing 16GB for better performance.
Configure authentication settings by selecting a unique username and password. Save this information for future use.
Ensure SSH is selected in the inbound port section for connecting to your virtual machine later.
Step 3: Configure Disk and Networking

Create and attach a new disk with a minimum size of 128GB.
Proceed with default settings for virtual network, subnet, and public IP address creation.
Step 4: Configure Management

Optionally, enable auto shutdown to save costs by stopping the VM daily.
Decide on the duration you want to keep the VM running, considering associated charges for a stopped VM with a public IP address.
Be mindful of your Azure credit and consider deleting resources when not in use to avoid unexpected charges.
Step 5: Review and Create

Review the configuration settings and ensure everything is set up according to your preferences.
Once validated, click on "Create" to initiate the virtual machine creation process.
Step 6: Download Private Key

After the creation process completes, download the private key for authentication purposes.
Save the private key in a secure location as it will be used to connect to your VM in the next steps.



