WebUI Lab
=========

1) Login to WebUI as openshift-dev
----------------------------------

	https://<vagrant VM IP>:8443/console/

2) Deploy example Ruby application:
-----------------------------------
  
  - Select your _intro-lab_ project, create it first if necesary.
  
  - Click _Add to Project_ button in top right
	
  - Scroll down toward the bottom of the page, choose the _ruby:latest_ template
	
  - Create new application with the following values, click _Create_ button at the bottom of the page when finished:
    - Name: _ruby-example_
    - Git Repository URL: _https://github.com/openshift/ruby-hello-world.git_
    - Click _Show advanced routing, build, and deployment options_ link
    - Add following Label and click the _Add_ button when finished:
      - Name: _app_
      - Value: _ruby-example_

	- Click 'Continue to overview' on the resulting page.
	
	- If the application build is still taking place, you may view the status by clicking the 'View Log' link.
	
	- Once the application has finished deploying, you should see 1 successfully deployed pod.
	
	- The newly deployed _ruby-example_ app should now by accessible by clicking on the URL in the service box. Return to the Project Overview page in the WebUI when finished viewing the app.

3) Scaling and maintaining applications with the ReplicationController
----------------------------------------------------------------------
  
  - Click the up arrow next to the pod circle to scale up the application to two pods. Within a few moments, another pod should be running.
  
  - Click the pods circle itself and choose one of the pods from the resulting list by clicking the name link
  
  - Making note of the pod name, click the menu on the top right corner of the pod detail pane, and choose delete, and confirm
  
  - Notice that in the resulting pod list screen, a new pod (with a different name) has been (or is in the process of being) deployed to take the place of the deleted pod. The reason for this is that the ReplicationController component of the application has been set to maintain two running pods at all times (originally deployed with a configuration of one pod, you updated it to two when you scaled the pod count up).
  
  - Go back out to the Project Overview

4) Application Topology in OpenShift
------------------------------------

  - From the Project Overview page, click the topology button located on the same line as the project display name
  
  - Notice all the components associated with _ruby-example_ application (as well as any other apps) 
	  - By cliecking each connected component, you should see a DeploymentConfig, ReplicationController, Pod, Service, and Router
  
  - Each of these components has a purpose:
    - _DeploymentConfig_: sets any configuration settings for the application on the cluster and defines under what conditions the application should be re-created
    - _ReplicationController_: as seen earlier, is responsible for starting/stopping pods to scale up/down an application or to maintain overall health (ie will kill unresponsive pods and start new pods in their place to meet replica counts)
    - _Pod_: the actual group of running containers (minimal defined/required for a single application)
    - _Service_: abstraction layer above a set of one or more pods that serves as a load-balanced access point to the running pods 
    - _Router_: Publicly exposes a service to the outside world.
  
  - To delete an application from an OpenShift project, you must delete each one of these components. However, ReplicationControllers cannot yet be deleted via the UI. We will delete applications in the CLI lab.
	
Next Lab: [WebUI Lab](webui.md)
