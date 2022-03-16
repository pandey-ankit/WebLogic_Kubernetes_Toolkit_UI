# Deployment of WebLogic Kubernetes Operator to the Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI) From WebLogic Kubernetes Toolkit UI

## Introduction



### About Product/Technology



### Objectives

In this lab, you will:

* 

### Prerequisites



## Task 1: Configure kubectl (Kubernetes Cluster CLI) to connect to Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI)

1. In the Console, select the *Hamburger Menu* -> *Developer Services* -> *Kubernetes Clusters (OKE)* as shown.
    ![](images/3.png)

2. Click *Access Cluster*. 
    ![](images/4.png)


3. Select *Local Access* and then click on *Copy* as shown.
    ![](images/5.png)

4. Go back to terminal, Click on *Activities* and select the *Terminal*.
    ![](images/6.png)

5. Paste the copied command in the terminal. For *Do you want to create a new config file?*, Type *y* then press *Enter*. For *Do you want to create your config file by logging in through a browser?*, Type *y* then press *Enter*.
    ![](images/7.png)

6. In Chrome Browser, Click *Accept all*.
    ![](images/8.png)

7. Enter your tenancy name and click *Continue*.
    ![](images/9.png)

8. Enter your Cloud account Username and Password and then click *Sign In*.
    ![](images/10.png)
    > You will see *Authorization Completed* as shown.
    ![](images/11.png)

9. In *Enter a passphrase for your private key*, leave it empty and press *Enter*.
    ![](images/12.png)

10. Use the upper arrow key to run the *oce ce ...* command again and re-run it multiple time, until you see the *New config written to the Kubeconfig file /home/opc/.kube/config*.
    ![](images/13.png)



## Task 2: Verify Connectivity of WebLogic Kubernetes Toolkit UI to Oracle Container Engine for Kubernetes (OKE) on Oracle Cloud Infrastructure (OCI)

1. Go back to WebLogic Kubernetes Tool Kit UI, Click *Activities* and select the WebLogic Kubernetes Tool Kit UI window. Click *Client Configuration* under Kubernetes.
    ![](images/14.png)

2. Click *Verify Connectivity*.
    ![](images/15.png)

3. Once you see *Verify Kubernetes Client Connectivity Success* window, Click *Ok*.
    ![](images/16.png)

## Task 3: Install the WebLogic Kubernetes Operator

1. Click *WebLogic Operator*. You  see some pre-filled values. lets it remain the same and click *Install Operator*.
    ![](images/17.png) 
    
    > Theory
    ![](images/18.png)
    > Theory
    ![](images/19.png)
    > Theory
    ![](images/20.png)

2. Once you see *WebLogic Kubernetes Operator Installation Complete*, Click *Ok*.
    ![](images/21.png)

## Acknowledgements

* **Author** -  Ankit Pandey
* **Contributors** - Maciej Gruszka, Sid Joshi
* **Last Updated By/Date** - Kamryn Vinson, January 2022