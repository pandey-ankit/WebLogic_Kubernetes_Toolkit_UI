# Deployment of Ingress Controller to the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI) From WebLogic Kubernetes Toolkit UI

## Introduction



### About Product/Technology



### Objectives

In this lab, you will:

* Install Ingress Controller to the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI)
* Update the Ingress Routes to Access the Application and Admin Console

### Prerequisites



## Task 1: Installtion of Ingress Controller to the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI)

1. Click *Ingress Controller*. You can see some pre-filled values, let it remain the same and click *Install Ingress Controller*.
    ![Install Ingress Controller](images/InstallIngressController.png)

2. Once you see *Ingress Controller Installation Complete*, click *Ok*.
    ![Ingress Controller Installed](images/IngressControllerInstalled.png)


## Task 2: Update the Ingress Routes to Access the Application and Admin Console

1. Scroll down and click on *+* icone to add the *Ingress Route Configuration*. 
    ![Add Ingress Routes](images/AddIngressRoutes.png)

2. Click on Edit icon as shown to modify the values.
    ![Edit Ingress](images/EditIngress.png)

3. Enter the following details and click on *OK*.<br>
        Name: console<br> 
        Path Expression: /console<br>
        Target Service Namespace: test-domain-ns<br>
        Target Service: test-domain-admin-server<br>
        Target Port: 7001<br>

    ![Console Ingress](images/ConsoleIngress.png)


4. In the similar way, add the following *opdemo* Ingress Routes as well:<br>
        Name: opdemo<br>
        Path Expression: /opdemo<br>
        Target Service Namespace: test-domain-ns<br>
        Target Service: test-domain-cluster-cluster-1 <br>
        Target Port: 8001<br>
    ![Opdemo Ingress](images/OpdemoIngress.png)

5. In the similar way, add the following *opdemo* Ingress Routes as well:<br>
        Name: remote-console<br>
        Path Expression: / <br>
        Target Service Namespace: test-domain-ns<br>
        Target Service: test-domain-admin-server<br>
        Target Port: 7001<br>
        ![Remote Console Ingress](images/RemoteConsoleIngress.png)

6. To update the Inress Routes, click *Update Ingress Routes*.
    ![Update Ingress Routes](images/UpdateIngressRoutes.png)

7. Once you see *Ingress Routes Update Complete* window, Click *Ok*.
    ![Update Ingress Complete](images/UpdateIngressComplete.png)

## Acknowledgements

* **Author** -  Ankit Pandey
* **Contributors** - Maciej Gruszka, Sid Joshi
* **Last Updated By/Date** - Kamryn Vinson, January 2022