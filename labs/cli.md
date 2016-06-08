CLI Lab
=======

  All WebUI operations can also be done via the CLI (both the WebUI and CLI drive OpenShift and its various components via the same RESTful API calls that allow other tool integration)

1) Deploy application via CLI
-----------------------------

	- Login via CLI using the openshift-dev user account (password is _devel_) and switch to intro-lab project
		oc logout
		oc login -u openshift-dev
		oc project intro-lab
	
 - Deploy an example nodeJS app from GitHub, expose service route

	oc new-app https://github.com/openshift/nodejs-ex -l name=nodejs-example
	oc expose svc nodejs-ex

	Note: This initial deployment could take up to 5 mins. Automated build is taking place which involves downloading and deploying dependency packages and a base docker image that doesn't yet exist locally

3) From the WebUI, explore the newly deployed nodes-example app by clicking on the URL in the service box

4) Delete the application and all associated resources from the CLI
	
	oc delete all -l name=nodejs-example

	Notice the importance of the labels we've assigned to this application. It enables us to later select only the components of this application for delete (and other operations)

5) Re-deploy the same application, expose service route

	oc new-app https://github.com/openshift/nodejs-ex -l name=nodejs-example
	oc expose svc nodejs-ex

	Note: This deployment could still take up to a minute but notice that it should be a bit faster. Automated build is still running but now the required docker image is already cached locally

