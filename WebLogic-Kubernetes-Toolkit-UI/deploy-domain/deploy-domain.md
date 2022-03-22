# Deployment of WebLogic Domain to the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI) From WebLogic Kubernetes Toolkit UI

## Introduction



### About Product/Technology



### Objectives

In this lab, you will:

* Deploy the WebLogic Domain to the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI).

### Prerequisites

## Task 1: Deploy the WebLogic Domain to the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI)

1. Click *WebLogic Domain*. we used weblogic/welcome1 as *WebLogic Admin Username*/*WebLogic Admin Password*. If you want, you can change these values.
    ![Admin Credentials](images/AdminCredentials.png)


2. Scroll down, enter the following in Primary Image section, Enter *domain-secret* as *Image Pull Secret Name*, and Use Oracle account username and password in *Image Registry Pull Username* and *Image Registry Pull Password*. Enter your Oracle email id in *Image Registry Pull Email Address*. These are the same credential which you used to accept license for *weblogic* images in Oracle Container Registry.
    ![Primary Image Details](images/PrimaryImageDetails.png)

3. Scroll down, enter the following in Auxiliary Image section, Enter *model-secret* as *Image Pull Secret Name*, and Use Cloud account username and password in *Image Registry Pull Username* and *Image Registry Pull Password*. Enter your Cloud email id in *Image Registry Pull Email Address*. These are the same credential which you used to push Auxiliary images in Oracle Cloud Container Image Registry.
    ![Auxiliary Image Details](images/AuxiliaryImageDetails.png)

4.  In *Clusters* section, click on *Edit* icon as shown.
    ![Cluster Resize](images/ClusterResize.png)

5. Enter *2* as *Replicas* and then Click *OK*.
    ![Cluster Replicas](images/ClusterReplicas.png)

6. In Datasources section, double click to edit *passwords* for two datasource. You can give *tiger* as password in both the datasources. Once done, click *Deploy Domain*.
    ![Datasoure Password](images/DatasourcePassword.png)

7. Once you see *WebLogic Domain Deployment to Kubernetes Complete* window, Click *OK*.
    ![Deployment Complete](images/DeploymentComplete.png)

8. Go back to terminal, Click *Activities* and select the *Terminal* window. Copy the following command and paste it terminal. You should see the similar output, where pod for introspector run first then for the Admin Server and later pods for managed server goes in the *Running* state.

    ````bash
    <copy>kubectl get pods -n test-domain-ns -w</copy>
    ````

    ![Pod Status](images/PodStatus.png)

9. You can also get the domain status through *WebLogic Kubernetes Toolkit UI*. Go back to *WebLogic Kubernetes Toolkit UI* and click *Get Domain Status*.
    ![Domain Status](images/DomainStatus.png)

10. In Domain Status window, Scroll down to see status of all server pods then click *OK*.
    ![Server Status](images/ServerStatus.png)


## Acknowledgements

* **Author** -  Ankit Pandey
* **Contributors** - Maciej Gruszka, Sid Joshi
* **Last Updated By/Date** - Kamryn Vinson, January 2022