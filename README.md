# Multi-Honeypot-Platform

In this guide, fill in later

## Tools Used

- Azure cloud
- PuTTy
- VirtualBox
- T-Pot

## Environments Used

- Windows 10 VM

## Part 1: Setup Lab Resources

### Step 1: Create a Free Azure Account

If you don't already have an Azure account, you can sign up for free at [this website](https://azure.microsoft.com/en-us/free/) to create it

Follow the steps to create an account, provide the necessary information, and verify your identity.

Once your account is created, you will have access to a range of Azure services, including virtual machines for hosting your honeypot.

### Step 2: Install a Remote Connection Program

To access your virtual machine, you'll need a remote connection program like PuTTY.

PuTTY is a free, open-source SSH and telnet client for Windows.

You can download PuTTY from the official website: [https://www.putty.org/](https://putty.org/).

Follow the instructions to download and install PuTTY on your computer.

Once installed, you'll be ready to connect to your Azure virtual machine securely.

Now that you have a free Azure account and a remote connection program installed, you're ready to proceed with creating your honeypot in the cloud using Azure. Let's move on to the next steps!

## Part 2: Creating VM in Azure for the HoneyPot

### Step 1: Sign in to Azure Portal

Navigate to portal.azure.com and sign in with your Azure account credentials.

### Step 2: Creating a Virtual Machine

*Once signed in, select "Virtual machines" from the dashboard*

*Click on "Add" to create a new virtual machine*

*Click on "Azure Virtual Machine"*

*Create a new resource group. Name it appropriately.*

**Choose a recognizable name for your virtual machine**

*Select a region that is close to you, considering both proximity and cost implications.*

*Choose the Debian operating system and leave the architecture as default.*

*Optionally, enable the Azure spot discount to reduce the cost, but be aware of potential interruptions.*

*Select an appropriate size for your VM, considering the recommended minimum of 8GB RAM. We suggest choosing 16GB for better performance.*


*Configure authentication settings by selecting a unique username and password. Save this information for future use.*


*Ensure SSH is selected in the inbound port section for connecting to your virtual machine later.*

*Click on Next*

### Step 3: Configure Disk and Networking

*Create and attach a new disk with a minimum size of 128GB.*

*Proceed with default settings for virtual network, subnet, and public IP address creation.*

### Step 4: Configure Management

*Optionally, enable auto shutdown to save costs by stopping the VM daily.*
 
*Decide on the duration you want to keep the VM running, considering associated charges for a stopped VM with a public IP address.*

*Be mindful of your Azure credit and consider deleting resources when not in use to avoid unexpected charges.*


### Step 5: Review and Create

*Review the configuration settings and ensure everything is set up according to your preferences.*

*Once validated, click on "Create" to initiate the virtual machine creation process.*

### Step 6: Download Private Key

*After the creation process completes, download the private key for authentication purposes.*

*Save the private key in a secure location as it will be used to connect to your VM in the next steps.*

## Installing and Configuring the HoneyPot in the Cloud

### Step 1: Open Ports in Azure Portal

*In the Azure Portal, navigate to the resource you created earlier.*

*Go to the networking section.*

*Add an inbound rule to open ports for incoming and outgoing connections.*

*Specify the range of ports from 0 to 65,535.*

*Set the source destination to any, service to custom, and action to allow.*

*Click "Add" to create the new security rule.*

*Verify that the rule was successfully added.*

### Step 2: Connect to Your VM using PuTTY

*Locate the folder where you installed PuTTY and launch the application.*

*Obtain the IP address of your virtual machine from the overview section in Azure Portal.*

*Enter the IP address in PuTTY and click "Open".*

*Accept any security prompts and provide the username and password you set up for your Azure VM.*

*Upon successful authentication, you will be connected to your VM via SSH.*

### Step 3: Update and Upgrade System Packages

*In the terminal, run the command sudo apt update to update the package list.*

*Next, run the command sudo apt upgrade -y to upgrade the packages on your system.*

### Step 4: Install Git

*Git by running the command sudo apt install git.*

*Confirm the installation when prompted.*

### Step 5: Download T-Pot Repository

*Visit the GitHub repository containing the T-Pot installation files.*

*Copy the Git command provided in the repository

*Return to the terminal and execute the copied Git command to download the repository.*

### Step 6: Install T-Pot

*Navigate to the downloaded repository folder in the terminal.*
    
*Run the installation command sudo ./install.sh --type=user.*
    
*Follow the installation prompts, including choosing the standard version and providing a username and password for T-Pot console access.*
    
*Once the installation completes, you're ready to explore and configure your T-Pot honeypot.*
    
By following these steps, you've successfully configured your Azure virtual machine and installed T-Pot, ready to use it as a honeypot for cybersecurity purposes. Enjoy exploring the capabilities of your new honeypot!

## Using the HoneyPot Web Interface to Track Cyber Threats

### Step 1: Accessing the Pod Web Interface

*After deploying the pod on Microsoft Azure Cloud platform, access the pod's web interface using your VM's IP address.*

*Open a new web browser tab and enter https://<your_VM_IP_address>:64297.*

*Ignore any warnings about potential security risks and proceed to the website.*
    
*You'll be prompted to enter the credentials set up during the installation process.*

*Enter the username and password to sign in and access the pod interface.*

### Step 2: Exploring the Pod Interface

*Once logged in, you'll be presented with the pod interface.*

Here's an overview of the main sections:

Attack Map: Displays a live attack map showing the geographic location of attackers and types of attacks on your honeypot.
Cockpit: The main dashboard providing a real-time view of honeypot activity, including attack statistics and top attackers.
Cyber Chef: A web-based tool for analyzing and decoding data captured by the honeypot.
Elastic View: Allows visualization of collected data, enabling searching for specific events and viewing results in various visual formats.
Nibbana: Helps visualize collected data by creating custom dashboards and reports based on the honeypot's data.
Spider Foot: A reconnaissance tool for gathering information about potential attackers from publicly available sources, such as IP addresses, domains, and email addresses.

### Step 3: Further Exploration

*Take some time to explore each section of the pod interface.*

*Familiarize yourself with the tools and features available, such as monitoring attack activity, analyzing captured data, and visualizing collected information.*

*Experiment with different functionalities to gain insights into the activity on your honeypot and potential threats.*

By following these steps, you'll be able to access and explore the pod interface deployed on Microsoft Azure Cloud platform, gaining valuable insights into the security landscape and potential threats facing your environment. Enjoy exploring the capabilities of your T-Pot honeypot!

## How to Discover Cyber Threats with HoneyPots in Real-Time

### Step 1: Exploring the Attack Map

*Open the Attack Map section of the pod interface.*

*The map displays live attacks showing geographic locations and types of attacks.*

*Each country's attacks are represented by dots of different colors.*

*Below the map, columns provide additional information about attacking countries and IP addresses.*

*Clicking on the dots provides more detailed information about the attacks, such as the type of service being attacked.*

*Different colors represent different types of services targeted in attacks.*

### Step 2: Analyzing with Elastic View

*Navigate to the Elastic View section of the pod interface.*

*Connect to the cluster to view server utilization, including disk and RAM usage.*

*View raw logs collected by Logstash in the background.*

*Utilize the query string to search for specific information within the logs.*

*Explore different log entries to understand attack attempts and other activities.*

### Step 3: Visualizing Data with Kibana

*Access Kibana, part of the Elastic Stack, to visualize collected data.*

*Select dashboards to view comprehensive data for specific services, such as Nginx.*

*Use the Teapot dashboard to view aggregated data from all installed honeypots.*

*Customize the time range to analyze data over specific periods.*

*View attack statistics by country and targeted honeypots.*

*Explore different attack types and their frequency.*

### Step 4: Using Spider Foot for Reconnaissance

*Navigate to the Spider Foot section of the pod interface.*

*Run a new scan by providing a target IP address.*

*Choose the scan settings and initiate the scan.*

*Review correlations to identify any potential malicious activity associated with the target IP.*

*Browse the results to access detailed information, including IP domains, email addresses, and phone numbers.*

*Utilize the graphical settings to visualize the gathered information.*
