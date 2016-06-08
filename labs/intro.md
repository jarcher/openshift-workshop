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
  
	- From the resulting _Add to Project_ screen, choose the _php:latest_ build image
	  - Name the application _first-app_
	  - Set the Git Repository URL to _https://github/ptavares-rh/openshift-workshop/_
	  
  - Click the _Create_ button at the bottom left of the screen.
