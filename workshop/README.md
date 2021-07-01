
# Register to IBM Cloud 

[Register IBM Cloud](https://ibm.biz/Bdfv92 )

Please make sure to run all steps to get a valid IBM Lite Cloud account 
![](README_IMAGES/Register.png)

# The Lab is base on https://github.com/IBM/MAX-Object-Detector#deploy-on-red-hat-openshift and run from there 
1) Deploy from Quay - to run based on Docker on local- run as instructed in the base lab 
2) Deploy on Red Hat OpenShift - you will need to follow the steps below to get an Openshift cluster and a more updated screen shots 
3) Deploy on Code Engine - follow the steps below to get the option to deploy with Code Engine 

# 2) To Deploy on Openshift (updated)  - follow the updated instructions bellow 

# Get a preconfigured OpenShift environment available for four hours at no charge
1. [access to IBM Openshift  Cluster]( https://developer.ibm.com/openlabs/openshift)

2. Click on Bring Your Own Application    

![](README_IMAGES/BringYourOwn1.png)

A cluster will be allocated for you , this might take a few secounds.... 
<!-- ( optional not part of the workshop  : you may run Lab 1 ,2 ,3 to learn about Openshift ) -->
# Access the OpenShift web console to your cluster 
![](README_IMAGES/GoToOpenshift2.png)
# Choose to work with Developer View
![](README_IMAGES/DeveloperView3.png)
# Go to Create Project
![](README_IMAGES/GoCreateProject.png)
# Create Project by the name of 'max-deployments'
![](README_IMAGES/CreateProject.png)
# Choose from Docker image
![](README_IMAGES/FromDocker4.png)
# Enter codait/max-object-detector as Image name and click on tab so other fileds will be fields accordingly 
![](README_IMAGES/DeployImage.png)
# Click on the round image 
![](README_IMAGES/FindRoute.png)
# Click on the route to run the model 
![](README_IMAGES/ClickOnRoute.png)



# 3) Deploy on Code Engine - follow the steps below to get the option to deploy with Code Engine 

# Request to be authorized to create Code Engine projects under the IBM Lab Account  
1. [Please go to:](https://code-engine-workshop.mybluemix.net) with the password of `cerocks`
 
![](README_IMAGES/IBMCloudLab.png)


2. Click on the "Login in to this" to Login in to the IBM  Cloud (or via https://cloud.ibm.com/)

![](README_IMAGES/LogIn.png)

You will be able to use this option ( without a credit card ) to use Code Engine only for a short period of time. Please note that we will delete  any project that is older then 24-72 hours, so this is designed for short term learning.

# Go to Code Engine and start working 
 
1. From the IBM Cloud dashboard choose Code Engine from the left side bar , please make sure that you using the IBM Lab Account --> 1840867- Advowork 
![](README_IMAGES/GoToCE.png)
this is the Code Engine User Interface , you will be able to deploy apps from here, but we will start first deploying applications using the CE CLI.
2. Click on the  IBM Cloud Shell (at the right side of the screen), IBM CLoud Shell has all the needed CLI's installed .
![](README_IMAGES/gotocli.png)
3. Log in to the IBM Cloud CLI: `ibmcloud login -a cloud.ibm.com -r us-south`
4. Enter your IBM Cloud credentials when prompted.
  **Note:** If you have a federated ID, use `ibmcloud login --sso` to log in to the IBM Cloud CLI. Enter your user name, and use the provided URL in your CLI output to retrieve your one-time passcode. You know you have a federated ID when the login fails without the `--sso` and succeeds with the `--sso` option.
  
3. Select an account Enter a number : `2. Advowork (e2b54d0c3bbe4180b1ee63a0e2a7aba4) <-> 1840867  `  ( **not** not you  account )   
4. Target a resource group by running the following command `ibmcloud target -g advowork`
5. Create a project `ibmcloud ce project create --name xxxxxx` (**where xxxxxx*** is a uniqe name like your account name , use only small letters, this is due to the fact that we all share the same account for this lab)  
6. Run the container by pointing to the quay.io image and exposting port 5000.

$ ibmcloud ce application create --name max-object-detector --image quay.io/codait/max-object-detector --port 5000

7. Open the resulting URL in a browser, append /app to view the app instead of the API.






 

 

