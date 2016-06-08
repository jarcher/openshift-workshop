Introduction Lab
================
1) Login to the OpenShift WebUI as admin
----------------------------------------

	https://<vagrant VM IP>:8443/console/

2) Create a new project called _intro-lab_ and deploy first application
-----------------------------------------------------------------------
  - From the initial Projects list screen, click the 'New Project' button in top right
    - Name the project _intro-lab_
    - Set the Display Name and Description to _OpenShift Intro Lab_
    
  - Click the _Create_ button at the bottom left of the screen.
  
	- From the resulting _Add to Project_ screen, choose the _php:latest_ template
	  - Name the application _first-app_
	  - Set the Git Repository URL to _https://github.com/ptavares-rh/openshift-workshop.git_
	  - Click the _Show advanced routing, build, and deployment options_ link
	  - Set the Context Dir field to _/labs/code/intro_
	  - Scroll down to Labels section at the bottom of the content pane. Create a new label by setting the name field to _app_, the value field to _first-app_, and clicking the _Add_ button.
	  
  - Click the _Create_ button at the bottom left of the screen. Click the _Go to overview_ link from the resulting screen.

  - The application deployment process here is as follows:
  	- OpenShift will pull down the docker container image associated with the selected application template selected (_php:latest_) if it is not already cached locally. This will serve as the base container image.
  	- OpenShift will create a new image layer with the retrieved code from the referenced Git URL and context directory, layer it on top of the base container image, and deploy the resulting combined layers as a running container to an available OpenShift node.
  	
  - Once the deployment is complete you should see your _first-app_ service and deployment (showing a single deployed pod) components listed in the main project overview screen. If so, you've successfully deployed your first application.
