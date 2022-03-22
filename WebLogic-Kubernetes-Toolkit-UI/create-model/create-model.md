# Creation of Model for the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI)
## Introduction



### About Product/Technology



### Objectives

In this lab, you will:

* 

### Prerequisites



## Task 1: View the Resources in existing on-premise domain

1. On left side, click *Arrow Icon* -> *Setting Icon* and then select *Remote Resizing* as shown below.
    ![Remote Resizing](images/RemoteResizing.png)

2. To open the terminal, click *Activities* -> *Terminal icon*.
    ![Open Terminal](images/OpenTerminal.png)

3. To run the Admin Server in *test-domain*, copy the following commands and paste it in terminal.
    ````bash
    <copy>cd ~/Oracle/Middleware/Oracle_Home/user_projects/domains/test_domain/bin/
    ./startWebLogic.sh</copy>
    ````
    ![Start WebLogic](images/StartWebLogic.png)
    ![Running WebLogic](images/RunningWebLogic.png)
4. To open Chrome Browser, click *Activities* -> *Chrome Icon*.
    ![Open Chrome](images/OpenChrome.png)

5. During the whole workshop, whenever you see this window, enter *welcome1* as password and click *Unlock*.   
    ![Default Keyring](images/DefaultKeyring.png)

6. Click bookmark for *Oracle WebLogic Server Administrative Console*.
    ![Open Admin Console](images/OpenAdminConsole.png)
    
7. Enter *weblogic/Welcome1%* as `Username/Password`, then click *Login*. You can see, we have WebLogic Server version 12.2.1.3.0.   
    ![Login Admin Console](images/LoginAdminConsole.png)

8. To view available servers, click *Environment* -> *Servers*. You can see, we have one dynamic clusters with 5 managed servers. 
    ![View Servers](images/ViewServers.png)

9. To view the datasources, click *Services* -> *Data Sources*.
    ![View Datasources](images/ViewDatasources.png)

10. To view the deployed application, click *Deployment*. You can see, we have *opdemo* as deployed application.
    ![View Deployments](images/ViewDeployments.png)

11. To shutdown the Admin Server, go back to terminal. Click *Activities* and select the *Terminal* window.
    ![Admin Terminal](images/AdminTerminal.png)

12. Press *`Ctrl + C`* to shutdown the Admin Server.
    ![Shutdown Admin](images/ShutdownAdmin.png)


## Task 2: Opening the base WKT UI Project

1. Click *Activities* and then select the icon for *WebLogic Kubernetes Toolkit UI*.
    ![Open WKTUI](images/OpenWKTUI.png)

2. We already created a project for you, which have common value pre-filled. To open that project, click *File* -> *Open Project*. 
    ![Open Project](images/OpenProject.png)

3. Click *Downloads* in left side, then choose *base_project.wktproj* and click *Open Project*.
    ![Project Location](images/ProjectLocation.png)

    > Theory
    
    ![Project Settings](images/ProjectSettings.png)

    > Theory
    
    ![Kubernetes Cluster Type](images/KubernetesClusterType.png)

    > Theory
    
    ![Software Locations](images/SoftwareLocations.png)


## Task 3: Introspection of an Offline on-premise domain 

Now in this section, we will introspect the on-premise domain. 

1. Click *Model* as shown.
    ![Model](images/Model.png)

2. Click *File* -> *Add Model* -> *Discover Model(offline)*.
    ![Discover Model](images/DiscoverModel.png)

3. Click Open folder *icon* to open the *Domain Home*.
    ![Open Domain Hom](images/OpenDomainHome.png)

4. In the Home folder, navigate to *~/Oracle/Middleware/Oracle_Home/user_projects/domains/* directory and select *test-domain* folder then  click *Select*. Click *OK*.
    ![Navigate Location](images/NavigateLocation.png)
    ![Specify Location](images/SpecifyLocation.png)

5. You can see the window as shown below, at the end, you will have model ready for you.
    ![View Model](images/ViewModel.png)

## Task 4: Validate and Prepare Model to be deployed on Kubernetes Cluster

1. To Validate the model, click *Validate Model*.
    ![Validate Model](images/ValidateModel.png)

2. Once model validation is successful and you see notification for the same, then click *Ok*.
    ![Validate Complete](images/ValidateComplete.png)

3. To prepare the model, to be deployed on Kubernetes cluster, click *Prepare Model*
    ![Prepare Model](images/PrepareModel.png)

4. Once model is successfully prepared, click *Ok*.
    ![Prepare Complete](images/PrepareComplete.png)


## Acknowledgements

* **Author** -  Ankit Pandey
* **Contributors** - Maciej Gruszka, Sid Joshi
* **Last Updated By/Date** - Kamryn Vinson, January 2022