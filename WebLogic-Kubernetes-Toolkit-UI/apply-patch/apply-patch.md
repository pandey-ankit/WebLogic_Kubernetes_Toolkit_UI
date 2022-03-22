# Applying the Patches to the WebLogic Server 

## Introduction



### About Product/Technology



### Objectives

In this lab, you will:

* Enter detail of new WebLogic Server Image (12.2.1.4) as Primary Image in WebLogic Kubernetes Toolkit UI Application.
* Update a deployed application by a rolling restart of the new  primary image.

### Prerequisites



## Task 1: Enter detail of new WebLogic Server Image as Primary Image

1. Go back to WebLogic Kubernetes Toolkit UI, click *Image*. Changed the WebLogic Server Tag to *12.2.1.4-slim-ol8*.
    ![Update Primary Image Tag](images/UpdateprimaryImageTag.png)

## Task 2: Update a deployed application by a rolling restart of the new  primary image

1. Click *WebLogic Domain* -> *Deploy Domain*. This will re-deploy the domain, it will use new primary image which contains WebLogic Server 12.2.1.4 version.
    ![Redeploy Domain](images/RedeployDomain.png)

2. Once you see *WebLogic Domain Deployment to Kubernetes Complete* window, Click *Ok*.
    ![Deployment Complete](images/DeploymentComplete.png)

3. Go back to *Terminal* and copy the below command and paste in terminal. You will notice rolling restart of servers one by one. First, Admin Server pods terminates and comes in *Running* state.
    ```bash
    <copy>kubectl get pods -n test-domain-ns -w</copy>
    ```
    ![View Pods](images/ViewPods.png)

4. To Verify that Admin Server and Managed Server pods are using updated WebLogic Server image, click *Monitoring Tree* icon and then select *Running Servers*. Use the *Scroll* bar below to view the *WebLogic Server Version*.
    ![WebLogic Version](images/WebLogicVersion.png)
## Acknowledgements

* **Author** -  Ankit Pandey
* **Contributors** - Maciej Gruszka, Sid Joshi
* **Last Updated By/Date** - Kamryn Vinson, January 2022