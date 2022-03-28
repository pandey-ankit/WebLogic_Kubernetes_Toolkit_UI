# Creation of Model for the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI)
## Introduction

In this lab, we explore the on-premise WebLogic domain. We navigate through the administration console to view the deployed application, datasources and servers in *test-domain*. we also open the pre-created *`base_project.wktproj`*, which already have pre-filled values for *Project Settings* section. Then we create the model file, by introspecting of an offline on-premise domain. At last, we validate the model and prepare the model to be deployed on Oracle Kubernetes Cluster (OKE).

### Objectives

In this lab, you will:

* Explore the on-premise WebLogic domain *test-domain* and view its deployed application, servers and datasources.
* Open the base WKT project, which contains some pre-filled values.
* Introspection of an offline on-premise domain using WebLogic Kubernetes Toolkit UI Application.
* Validate and prepare model to be deployed on Oracle Kubernetes Cluster (OKE). 

### Prerequisites

To run Lab 2, you must have:
* You should have a text editor, where you can paste the commands, URLs and modify them, as per your environment.
* Successfully created the Virtual machine using the custome image. As this virtual machine contains all the required software like JDK, Oracle WebLogic Server, Helm, Kubectl and Docker.


## Task 1: Start the Admin Server and verify the resources in existing on-premise domain

This Virtual Machine, contains WebLogic Domain *test-domain* with WebLogic Server version *12.2.1.3.0*. This *test-domain* have one application *opdemo* deployed, two datasources and one dynamic cluster. 

In this Task, we start the Admin Server in this *test-domain*, and navigate through the resources using WebLogic Administration console.

1. On left side, click *Arrow Icon* -> *Setting Icon* and then select *Remote Resizing* as shown below.
    ![Remote Resizing](images/RemoteResizing.png)
 > Again click on *Arrow Icon* to hide the *Settings* option. You can see the *Clipboard*, for copy and paste between the host machine and remote desktop, we use the *Clipboard*. For example, if you want copy from the host machine and want to paste it inside the remote desktop, you need to first paste in the clipboard first, then you can paste it in remote desktop.

2. To open the terminal, click *Activities* -> *Terminal icon*.
    ![Open Terminal](images/OpenTerminal.png)
 
3. To start the Admin Server in *test-domain*, copy the following commands and paste it in terminal.
    ````bash
    <copy>cd ~/Oracle/Middleware/Oracle_Home/user_projects/domains/test_domain/bin/
    ./startWebLogic.sh</copy>
    ````
    > This *~/Oracle/Middleware/Oracle_Home/user_projects/domains/test_domain/* is your domain home directory. 

    ![Start WebLogic](images/StartWebLogic.png)
    ![Running WebLogic](images/RunningWebLogic.png)

4. To open Chrome Browser, click *Activities* -> *Chrome Icon*.
    ![Open Chrome](images/OpenChrome.png)

5. During the whole workshop, whenever you see this window, enter *welcome1* as password and click *Unlock*.   
    ![Default Keyring](images/DefaultKeyring.png)

6. Click bookmark for *Oracle WebLogic Server Administrative Console*.
    ![Open Admin Console](images/OpenAdminConsole.png)
    
7. Enter *weblogic/Welcome1%* as `Username/Password`, then click *Login*. You can see, we have WebLogic Server version *12.2.1.3.0*.   
    ![Login Admin Console](images/LoginAdminConsole.png)

8. To view available servers, expand *Environment* and click *Servers*. You can see, we have one dynamic clusters with 5 managed servers. 
    ![View Servers](images/ViewServers.png)

9. To view the datasources, expand *Services* and click *Data Sources*.
    ![View Datasources](images/ViewDatasources.png)

10. To view the deployed application, click *Deployment*. You can see, we have *opdemo* as deployed application.
    ![View Deployments](images/ViewDeployments.png)

11. To shutdown the Admin Server, go back to terminal. Click *Activities* and select the *Terminal* window.
    ![Admin Terminal](images/AdminTerminal.png)

12. Press *`Ctrl + C`* to shutdown the Admin Server.
    ![Shutdown Admin](images/ShutdownAdmin.png)


## Task 2: Opening the base WKT UI Project

This Virtual Machine have *WebLogic Server*, *docker*, *helm*, *kubectl*, *JDK* installed. So we created a WKT Project *`base_project.wktproj`* for you, which already specified the installation directory for these softwares. You don't need to fill those values. 

In this task, we open a pre created  *`base_project.wktproj`* project. We see the different settings in *Project Settings* section.

1. Click *Activities* and then select the icon for *WebLogic Kubernetes Toolkit UI*.
    ![Open WKTUI](images/OpenWKTUI.png)

2. To open *base_project.wktproj* project, click *File* -> *Open Project*. 
    ![Open Project](images/OpenProject.png)

3. Click *Downloads* in left side, then choose *base_project.wktproj* and click *Open Project*.
    ![Project Location](images/ProjectLocation.png)

    > **For your information only:**<br>
    > As *Credential Story Policy*, we select **Store in Native OS Credentials Store**. It means the credentials (like for WebLogic Server and datasources) are only stored on the local machine.<br>
    > For *Where would you like the target Oracle Fusion Middleware domain to live?*, we select **Created in the container from the model in the image**. In this case, the set of model-related files are added to the image. So when the WebLogic Kubernetes Operator domain object is deployed, its inspector process runs and creates the WebLogic Server domain inside a running container on-the-fly.<br>
    ![Project Settings](images/ProjectSettings.png)
    > As *Kubernetes Environment Target Type*, we select **WebLogic Kubernetes Operator**. This means, you want this domain to be deployed in Kubernetes managed by the WebLogic Kubernetes Operator. This settings also determine what sections and their associated actions within the application, to display.<br>
    > we also specify the location for *JAVA HOME* and *ORACLE_HOME*. WebLogic Kubernetes Toolkit UI uses this directory when invoking the WebLogic Deployer Tooling and WebLogic Image Tool. <br>
    > To build new images, inspect images and interact with image repositories, the WKT UI application uses an image build tool, which defaults to docker.<br>
    ![Kubernetes Cluster Type](images/KubernetesClusterType.png)
    ![Software Locations](images/SoftwareLocations.png)


## Task 3: Introspection of an Offline on-premise domain 

In this task, we will use *File* -> *Add Model* menu to create a model of an existing *test-domain* using the `WebLogic Deploy Tooling's` [Discover Domain Tool](https://oracle.github.io/weblogic-deploy-tooling/userguide/tools/discover/). This *Model* section allows you to introspect a domain configuration.

For more information on *Model* section, see the *Introduction* section of this lab.

1. In WebLogic Kubernetes Toolkit UI, Click *Model*.
    ![Model](images/Model.png)

2. Click *File* -> *Add Model* -> *Discover Model(offline)*.
    ![Discover Model](images/DiscoverModel.png)

3. Click Open folder *icon* to open the *Domain Home*.
    ![Open Domain Hom](images/OpenDomainHome.png)

4. In the Home folder, navigate to *`/home/opc/Oracle/Middleware/Oracle_Home/user_projects/domains/`* directory and select *test-domain* folder then  click *Select*. Click *OK*.
    ![Navigate Location](images/NavigateLocation.png)
    ![Specify Location](images/SpecifyLocation.png)
    > If you look the console, you will see that this invokes WebLogic Deployer Tool to introspect the domain configuration in offline mode. 

5. You can see the window as shown below, at the end, you will have model ready for you.
    ![View Model](images/ViewModel.png)

    > The result of this WDT introspection are model(a metadata representation of your domain configuration), placeholder, where you can specify the values (like password for datasource) and application in the application archive.

## Task 4: Validate and Prepare Model to be deployed on Kubernetes Cluster

In this task, we validate the model and prepare the model to be deployed on Oracle Kubernetes Cluster (OKE).

1. To Validate the model, click *Validate Model*.
    ![Validate Model](images/ValidateModel.png)
    > **For your Information Only:**<br>
    > Validate model invokes the WDT [Validate Model Tool](https://oracle.github.io/weblogic-deploy-tooling/userguide/tools/validate/), which validates that the model and its related artifacts  are well-formed and provides help on the valid attributes and subfolder for a particular model location.

2. Once you see *Validate Model Complete* window, click *Ok*.
    ![Validate Complete](images/ValidateComplete.png)

3. To prepare the model, to be deployed on Kubernetes cluster, click *Prepare Model*
    ![Prepare Model](images/PrepareModel.png)
    > **For your Information Only:**<br>
    > Prepare model invokes the WDT [Prepare Model Tool](https://oracle.github.io/weblogic-deploy-tooling/userguide/tools/prepare/) to modify the model to work in a Kubernetes cluster with WebLogic Kubernetes Operator or Verrazzano installed.<br>
    > Prepare Model does the following:
    * Removes model sections and fields that are not compatible with the target environment.
    * Replaces endpoint values with model tokens that reference variables.
    * Replaces credential values with model tokens that reference either a field in a Kubernetes secret or a variable.
    * Provides default values for fields displayed in the application’s variable, variable overrides, and secret editors.
    * Extracts topology information to the application that it uses to generate the resource file used to deploy the domain.

4. Once you see *Prepare Model Complete* window,click *Ok*.
    ![Prepare Complete](images/PrepareComplete.png)


## Acknowledgements

* **Author** -  Ankit Pandey
* **Contributors** - Maciej Gruszka, Sid Joshi
* **Last Updated By/Date** - Kamryn Vinson, March 2022