# Prepare Setup

## Introduction
This lab will show you how to download the Oracle Resource Manager (ORM) stack zip file and how to setup a Resource Manager Stack that will generate a compute instance and a Virtual Cloud Network (VCN).

*Estimated Lab Time:* 15 minutes

### Objectives
* Download ORM stack need to create Compute Instance(Virtual Machine) for this workshop.
* Create Compute + Networking Resource Manager Stack
* Connect to compute instance


### Prerequisites
This lab assumes you have:
* An Oracle Free Tier or Paid Cloud account
* Have sufficient quota for in your tenancy to create VM and VCN.

## Task 1: Download Oracle Resource Manager (ORM) stack zip file
1.  Click on the link below to download the Resource Manager zip file you need to build your environment: [wktui-mkplc-freetier.zip](https://objectstorage.us-ashburn-1.oraclecloud.com/p/sDX34HYvxdv1GjdCplfdYt-HSj9NBe4rjsXgltW0Ax5VPGmhSlGBpqm3wVVvhFxR/n/oraclepartnersas/b/omlvm-mkplc-freetier/o/omlvm-mkplc-freetier.zip)

2.  Save in your downloads folder.

## Task 2: Setup Compute and Networking

Proceed to deploy your workshop environment using Oracle Resource Manager (ORM) stack.

1. Identify the ORM stack zip file downloaded in Task 1.

2. Login to Oracle Cloud.

3. Open up the hamburger menu in the left hand corner.  Click **Developer Services**, choose **Resource Manager > Stacks**. Choose the compartment in which you would like to install. Click **Create Stack**.

4. Select **My Configuration**, choose the **.ZIP FILE** button, click the **Browse** link and select the zip file that you downloaded or drag-n-drop for the file explorer.

5. Click **Next**.

6. Enter or select the following:
    **Instance Count:** Accept the default, **1**.
    **Select Availability Domain:** Select an availability domain from the dropdown list.
    **Need Remote Access via SSH?** Keep Unchecked for Remote Desktop only Access - The Default
    **Use Flexible Instance Shape with Adjustable OCPU Count?:** Keep the default as checked (unless you plan on using a fixed shape)
    **Instance Shape:** Keep the default (*VM.Standard.E4.Flex*).
    **Select OCPUs Count per Instance:** Accept the default shown(**1**).
    **Use Existing VCN?:** Accept the default by leaving this unchecked. This will create a **new VCN**.

7. Click **Next**.

8. check the box for  **Run Apply** and click **Create**.

9. Your stack has is now created and the *Apply* action triggered is running to deploy your environment!  

## Task 3: Access the Graphical Remote Desktop

For ease of execution of this workshop, your VM instance has been pre-configured with a remote graphical desktop accessible using any modern browser on your laptop or workstation. Proceed as detailed below to login.

1. Navigate to **Stack Details**, **Application Information** tab, and click on the remote desktop URL.

  This should take you directly to your remote desktop in a single click.

You may now [proceed to the next lab](#next).

## Acknowledgements

* **Author** - Rene Fontcha, Master Principal Solutions Architect, NA Technology
* **Contributors** - Meghana Banka, Rene Fontcha, Narayanan Ramakrishnan
* **Last Updated By/Date** - Rene Fontcha, LiveLabs Platform Lead, NA Technology, January 2021
