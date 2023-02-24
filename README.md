# Hosting-and-Accessing-a-Linux-VM-on-Digital-Ocean
A rundown on creating a Linux Virtual Machine using Digital Ocean’s Cloud services.

# Registering and Configuring a VM Instance
## Step 0: Prerequisites
Create an account on Digital Ocean and configure your payment plans. A valid credit card will be needed to check the payment.

## Step 1: Spin Up a Droplet
The first step would be to create a droplet from the Home-screen Dashboard. There are multiple options available, but we will be selecting “Spin up a droplet”

![image](https://user-images.githubusercontent.com/68028786/221156571-23983dc7-4b08-4829-9260-059a14e8ab36.png)


## Step 2: Select a Datacenter
Choose a datacenter that will host the server. There are multiple options for this, but the best one will be the one closest to our targeted audience as well as our own location

Bangalore was chosen in my case.

![image](https://user-images.githubusercontent.com/68028786/221156771-d568ed34-41a6-4690-b572-350c4f721d6c.png)

## Step 3: Select an Image
The next step is to choose an image or operating system that will be used for our droplet. There is a variety of options to choose from; we will choose Ubuntu, a popular Linux flavor.

![image](https://user-images.githubusercontent.com/68028786/221156789-a54a1433-3733-4bc7-a761-a23b34cf1e12.png)

## Step 4: Choose Size
Digital Ocean is one of the top cloud services platform and hence provides lots of different sizes and versions. Some may be CPU-optimized, Memory-Optimized or Storage-Optimized depending on the users requirements

We will choose the most basic version to test out the functionalities.

![image](https://user-images.githubusercontent.com/68028786/221156856-484a8f04-2f88-4f41-b9ee-101f9b2cd247.png)


## Step 5: Choose a Plan
There are many different CPU options as well as disk options. Digital Ocean charges different rates according to the size of the disks, number of CPUS and Storage Size.

For this project, a regular CPU with the most basic functionalities is sufficient

![image](https://user-images.githubusercontent.com/68028786/221156927-d192bd68-368c-4828-bb1c-722c7397966d.png)

## Step 6: Configure an Authentication Method
Digital Ocean has several authentication methods for the root program. We will be using an SSH key to generate a private and public key for a more secure droplet.

![image](https://user-images.githubusercontent.com/68028786/221157002-e82c011d-711f-41ca-bd66-e8d8e6540ac8.png)

## Step 7: Generate SSH Keys
For this step, we will be using a 3rd party software “PuTTY” for generation of keys. It can be downloaded from https://www.putty.org/.

### 1. Generate a Public Key.

![image](https://user-images.githubusercontent.com/68028786/221157162-901fac89-74a8-4748-aed1-fd40c351c9af.png)

### 2. Choose a passphrase to create a Private Key
### 3. Save the private key as a .pkk file.

![image](https://user-images.githubusercontent.com/68028786/221157223-5e126dce-c88b-4cf0-9403-bd2eaaca028f.png)

### 4. Add SSH Key to Digital Ocean

![image](https://user-images.githubusercontent.com/68028786/221157288-bb9c2c8b-efce-4d38-b3a5-9fe5bd9fd9b7.png)

## Step 8: Finalize the Virtual Machine
Re-check all steps and give the Droplet a Unique name. Press Create Droplet to finalize the Virtual Machine.

![image](https://user-images.githubusercontent.com/68028786/221157360-e052fab2-186c-49ff-8311-02d5694b635e.png)

That’s all for setting up the droplet. We can easily view and manage the droplet now.


# Accessing and Configuring the Droplet
The next step is to configure the droplet and accessing it with the SSH key, configuring the Firewall and Accessing the Droplet with RDP.


## Step 1: Set PuTTY Configuration
PuTTY Configuration is an application used as SSH and Telnet Client for Windows. It is used to access a remote server from a local desktop.

### 1. Retrieve Host IP Address of our droplet.

![image](https://user-images.githubusercontent.com/68028786/221157731-a114aa64-c500-4612-b49d-04ab75e9c525.png)


### 2. Locate SSH Private key for Credentials

![image](https://user-images.githubusercontent.com/68028786/221157769-7334267c-5b3f-48cf-9d73-5f63c2559545.png)


### 3. Set login with Root User

![image](https://user-images.githubusercontent.com/68028786/221157789-921d9a87-d75f-46b9-898c-a18cb7306c07.png)


### 4. Save the Session Details

![image](https://user-images.githubusercontent.com/68028786/221157804-1c068572-0379-4f7b-92fe-641ab334276f.png)


### 5. Dial and Connect to Server
### 6. Enter Passphrase

![image](https://user-images.githubusercontent.com/68028786/221157818-43c88abb-46f5-4632-bed2-264bae3728f7.png)


## Step 2: Configure Firewall
The next step is to secure our VM by creating a firewall for it.

### 1. We will open TCP Port 3389 for RDP.
### 2. We will open HTTP Port for HTTP Server.
### 3. We will Open TCP Port 443 for Apache Server.

![image](https://user-images.githubusercontent.com/68028786/221157917-f330e66f-f79d-4fac-90cd-b589344c46a0.png)

## Step 3: Installing RDP and Accessing VM
### 1. Access VM using Telnet and Login
### 2. Update Ubuntu `sudo apt update`
### 3. Install xfce and xfce-goodies `sudo apt install xfce4 xfce4-goodies -y`
### 4. Install xrdp `sudo apt install xrdp -y` Start xrdp `sudo systemctl start xrdp`
### 5. Create Username/Password
### 6. Open Remote Desktop Connection
#### - Dial in the IP and Username

![image](https://user-images.githubusercontent.com/68028786/221158261-01c68f19-d31d-4bee-954d-df3ef6507c1c.png)

#### - Connect
#### - Login as new User

![image](https://user-images.githubusercontent.com/68028786/221158286-92fb3e07-bce2-423f-81b2-284d01214eb6.png)

#### - Access Remote Ubuntu Desktop of VM

![image](https://user-images.githubusercontent.com/68028786/221158315-5c26fa5b-0d71-4f26-9dc1-abca97d4ddb0.png)

## Step 4: Hosting File Using HTTP Server
We will be using Apache to create an HTTP server on our droplet. The HTTP server will be accessible to anyone.

### 1. Install Apache on VM `sudo apt install apache2`
### 2. Access IP from any device

![image](https://user-images.githubusercontent.com/68028786/221158637-9ab5996b-fdf0-4b66-8428-e27696faaf10.png)


# Conclusion

In this blog, theres a list of things we did:
- Created a Ubuntu Droplet
- Configured SSH Keys
- Configured Firewall
- Used PuTTY to remotely access server CLI
- Used RDP to access Server with Interface
- Hosted an Apache server on the Droplet.

This shows us how simple it is to get started with using cloud services and creating a basic Virtual Machine. Hopefuly you enjoyed this tutorial and found it helpful.






