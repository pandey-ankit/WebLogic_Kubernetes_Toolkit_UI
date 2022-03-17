# Scale the WebLogic Cluster 

## Introduction



### About Product/Technology



### Objectives

In this lab, you will:

* 

### Prerequisites



## Task 1: Scaling a WebLogic Cluster using WebLogic Kubernetes Toolkit UI

1. Go back to WebLogic Kubernetes Toolkit UI,  Click *WebLogic Domain*. Go to *Clusters* section and click on *Edit* icon.  
    ![](images/1.png)

2. Change the Replicas from *2* to *3*, and click *OK*. 
    ![](images/2.png)

3. To Re-deploy the domain, click *Deploy Domain*.
    ![](images/3.png)

4. Once you see *WebLogic Domain Deployment to Kubernetes Complete* window, click *Ok*.
    ![](images/4.png)

5. Go back to *Terminal* window, Click *Activities* and select the *Terminal* window. Copy the following command and paste in terminal.
    ```bash
    <copy>kubectl get pods -n test-domain-ns -w</copy>
    ```
    ![](images/5.png)


## Acknowledgements

* **Author** -  Ankit Pandey
* **Contributors** - Maciej Gruszka, Sid Joshi
* **Last Updated By/Date** - Kamryn Vinson, January 2022