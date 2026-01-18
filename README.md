# Virtual Machine Creation
To be able to do Linux exercises, we need a Linux machine. Hence, we use public cloud virtual machines from Microsoft Azure cloud to be doable at any time and place. To create a Linux virtual machine, we must follow the following instructions:
1. Login to [portal.azure.com](portal.azure.com) using HAMK student id
2. To receive student credits, request credit from [Azure](https://azure.microsoft.com/en-us/free/students/) to receive $100 in credit by clicking Get Started Free. By clicking on it, we need to log in with our student account and enter a form of our information. This step is necessary not only to receive the credit but also to join the class group (when creating the virtual machine).
   ![V1](Images/V1.png)
Once we've been accepted into your Azure for Students subscription, we can create a new virtual machine for ourselves. We'll go to our portal home page, portal.azure.com, and create a new resource, a virtual machine, with the following settings:
3. By clicking on “Resource groups” and then create, we can connect to the lesson group and assign a name to it. Finally, we click on Review+Create.
   ![V2](Images/V2.png)
   ![V3](Images/V3.png)
At the end, the created Resource groups can be seen as follows.
   ![V4](Images/V4.png)
4. Then, by returning to Home and clicking on Virtual Machine, Create and selecting Virtual Machine, we enter the creation stage.
      ![V5](Images/V5.png)
The settings the Azure VM provisioning wizard displays in the Azure portal are grouped into the following pages:
    - Basics
    -	Disks
    -	Networking
    -	Management
    -	Monitoring
    -	Advanced
    -	Tags
      1) <ins> **Basics** </ins>: The settings on this page configure the target subscription, either an existing or new resource group, and the Azure region where the Azure VM and the resources   on which it depends will reside. From here you also specify:
          -	The Azure VM name.
          -	Availability options.
          -	The OS image.
          -	Administrator account name.
          -	Depending on your choice of the authentication type, either the corresponding password or the secure shell protocol (SSH) key.
            ![V6](Images/V6.jpg)

      2) <ins> **Disks** </ins>: You can use the Disks tab to specify the type and encryption of the disk hosting the Azure VM OS. You can also attach one or more data disks, although this option is available at any point following the deployment. The maximum number of data disks that an Azure VM supports depends on its size.
           ![V7](Images/V7.png)
      3)  <ins> **Networking** </ins>: Every Azure VM uses its network interface to attach to a virtual network's subnet. Therefore, having a virtual network with at least one subnet is a prerequisite when provisioning an Azure VM.
           ![V8](Images/V8.png)



