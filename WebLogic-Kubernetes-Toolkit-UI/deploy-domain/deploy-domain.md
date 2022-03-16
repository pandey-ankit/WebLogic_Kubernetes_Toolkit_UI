# Deployment of WebLogic Domain to the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI) From WebLogic Kubernetes Toolkit UI

## Introduction



### About Product/Technology



### Objectives

In this lab, you will:

* 

### Prerequisites

## Task 1: Deploy the WebLogic Domain to the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI)

1. Click *WebLogic Domain*. we used weblogic/welcome1 as *WebLogic Admin Username*/*WebLogic Admin Password*. If you want, you can change these values.
    ![](images/22.png)


2. Scroll down, enter the following in Primary Image section, Enter *domain-secret* as *Image Pull Secret Name*, and Use Oracle account username and password in *Image Registry Pull Username* and *Image Registry Pull Password*. Enter your Oracle email id in *Image Registry Pull Email Address*. These are the same credential which you used to accept license for *weblogic* images in Oracle Container Registry.
    ![](images/23.png)

3. Scroll down, enter the following in Auxiliary Image section, Enter *model-secret* as *Image Pull Secret Name*, and Use Cloud account username and password in *Image Registry Pull Username* and *Image Registry Pull Password*. Enter your Cloud email id in *Image Registry Pull Email Address*. These are the same credential which you used to push Auxiliary images in Oracle Cloud Container Image Registry.
    ![](images/24.png)

4.  In *Clusters* section, click on *Edit* icon as shown.
    ![](images/25.png)

5. Enter *2* as *Replicas* and then Click *OK*.
    ![](images/26.png)

6. In Datasources section, double click to edit *passwords* for two datasource. You can give *tiger* as password in both the datasources. Once done, click *Deploy Domain*.
    ![](images/27.png)

7. Once you see *WebLogic Domain Deployment to Kubernetes Complete* window, Click *OK*.
    ![](images/28.png)

8. Go back to terminal, Click *Activities* and select the *Terminal* window. Copy the following command and paste it terminal. You should see the similar output, where pod for introspector run first then for the Admin Server and later pods for managed server goes in the *Running* state.

    ````bash
    <copy>kubectl get pods -n test-domain-ns -w</copy>
    ````

    ![](images/29.png)

9. You can also get the domain status through *WebLogic Kubernetes Toolkit UI*. Go back to *WebLogic Kubernetes Toolkit UI* and click *Get Domain Status*.
    ![](images/30.png)

10. In Domain Status window, Scroll down to see status of all server pods then click *OK*.
    ![](images/31.png)


## Acknowledgements

* **Author** -  Ankit Pandey
* **Contributors** - Maciej Gruszka, Sid Joshi
* **Last Updated By/Date** - Kamryn Vinson, January 2022