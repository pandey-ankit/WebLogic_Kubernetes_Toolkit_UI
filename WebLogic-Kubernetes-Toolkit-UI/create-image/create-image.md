# Creation of Images for the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI)
## Introduction



### About Product/Technology



### Objectives

In this lab, you will:

* 

### Prerequisites

## Task 1: Creation of repository inside Oracle Cloud Container Registry Repository

1. In the Console, select the *Hamburger Menu* -> *Developer Services* -> *Container Registry* as shown.
    ![](images/32.png)

2. Select your compartment, where you are allowed to create the repository. Click *Create Repository*.
    ![](images/33.png)

3. Enter *`test-model-your_first_name`* as Repository name and Access as *Public* then click *Create repository*.
    ![](images/34.png)

4. Once your repository is ready, you need to note down the tenancy namespace somewhere.
    ![](images/35.png)


## Task 2: Enter details of Primary Container Image 

1. Click the link for the Oracle Container Registry [https://container-registry.oracle.com/](https://container-registry.oracle.com/) and sign in. For this, you need an Oracle Account.

2. Enter your *Oracle Account Credentials* in the Username and Password fields, and then click *Sign In*.

3. In the Home page of Oracle Container Registry, Search for *weblogic*.

4. Click *weblogic* as shown and select *English* as the language, then click *Continue*.

5. Click *Accept* to accept the license agreement.

6. Click *Image*. Copy the below Image tag for Oracle WebLogic Server image and paste it inside *Image Tag*. This will automatically populate the Image Registry Address.

    ````bash
    <copy>container-registry.oracle.com/middleware/weblogic:12.2.1.3-ol8</copy>
    ````

    ![](images/30.png)


## Task 3: Prepare Auxiliary Image and Push the Auxiliary Image to Oracle Container Image Registry 

1. We are creating an Auxiliary image, which we will push to the Oracle Cloud Container Registry in this Lab. To create the Auxiliary Image Tag, we need the following information:

    * Tenancy Namespace
    * End point for the Region

    You can find out your *Region Name* in top right corner in the Oracle Cloud Console.

2. In Task 1 of this lab, You already noted the tenancy namespace. If not, then for finding the Namespace of the tenancy, select the *Hamburger Menu* -> *Developer Services* -> *Container Registry*, as shown. In the compartment, you will find the Namespace.

3. To find out the endpoint for your Region, select this URL [https://docs.oracle.com/en-us/iaas/Content/Registry/Concepts/registryprerequisites.htm#Availab](https://docs.oracle.com/en-us/iaas/Content/Registry/Concepts/registryprerequisites.htm#Availab). In my case, it is *UK South (London)* as the region name, thus its endpoint is *lhr.ocir.io*. Find out your endpoint for your own *Region Name* and save it in the text editor. We will also need it for the next lab.

4. Now you have both the Tenancy Namespace and Endpoint for your region. Copy the following command and paste it in your text editor. Then replace the `END_POINT_OF_YOUR_REGION` with the endpoint of your region name, `NAMESPACE_OF_YOUR_TENANCY` with your tenancy's namespace and `your_first_name` with your first name in lower case.

    ````bash
    <copy>END_POINT_OF_YOUR_REGION/NAMESPACE_OF_YOUR_TENANCY/test-domain-your_first_name:v1</copy>
    ````

> For example, in my case Auxiliary Image tag is `lhr.ocir.io/tenancynamespace/test-domain-ankit:v1`.

5. In the previous step, you also determined the tenancy namespace.
Enter the  Auxiliary Image Registry Push Username as follows: `NAMESPACE_OF_YOUR_TENANCY`/`YOUR_ORACLE_CLOUD_USERNAME`. <br>
* Replace `NAMESPACE_OF_YOUR_TENANCY` with your tenancy's namespace
* Replace `YOUR_ORACLE_CLOUD_USERNAME` with your Oracle Cloud Account user name and then copy the replaced username from your text editor and paste it in the *Auxiliary Image Registry Push Username*.
* For Password, copy and paste the Authentication Token from your text editor(or wherever you saved it) and paste it in the *Auxiliary Image Registry Push Username*.
    ![](images/31.png)

6. Click *Create Auxiliary Image*.
    ![](images/36.png)

7. As we already prepared the model in Lab 2, so click on *No*.
    ![](images/37.png)

8. Select *Downloads* folder where we want to save *WebLogic Deployer* and click *Select* as shown.
    ![](images/38.png)

9. Once Auxiliary images is successfully created, On *Create Auxiliary Image Complete* window, click *Ok*.
    ![](images/39.png)

10. Click *Push Auxiliary Image* to push the image in repository inside your Oracle Cloud Container Image Registry.
    ![](images/40.png)
11. Once image is successfully pushed, On *Push Image Complete* window, click *Ok*. 
    ![](images/41.png)


## Acknowledgements

* **Author** -  Ankit Pandey
* **Contributors** - Maciej Gruszka, Sid Joshi
* **Last Updated By/Date** - Kamryn Vinson, January 2022