# openshift-workshop

This repo contains lab instructions, code, and other assets associated with learning the ways of OpenShift!

To get started follow these steps to get the OpenShift CDK installed

The CDK installation and configuration steps are as follows:

1) Install VirtualBox for Windows or Mac - The CDK makes use of Vagrant for neatly packaged/configured VM deployments and this requires VirtualBox as a result

2) Install Vagrant and docker for Windows or Mac - Vagrant drives VirtualBox which hosts OpenShift services all run within docker containers

3) Register with Developers program to receive developer entitlement (or use existing subscription) - This will provide developer subscription entitlements for us to use. It is a very useful (and free) program for any organization interested in developing with Red Hat technology
Register for Red Hat Developers Program

4) Download cdk zip file and vagrant box file - will need the developer account username
CDK Tools and Vagrant Files

5) Install cdk vagrant plugins - see the appropriate link below
6) Add rhel vagrant box - see the appropriate link below
2.3. Windows: Setting up CDK Software Components
3.3. Mac: Setting Up CDK Software Components

7) Start box (will ask to register against RH CDN, need account info)
2.4. Starting CDK Vagrant Box in Windows
3.4. Starting the CDK Vagrant Box on Mac OS X

8) Download and install OSE client tools:
OpenShift Clients
	- Download the zip file, create a directory, move the oc binary into the directory and add to PATH

9) Use service-manager plugin to view and set service environment variables (like docker)
	- Run following command to setup docker env: 
	- eval "$(vagrant service-manager env docker)"

10) Login with admin/admin or openshift-dev/devel to verify installation
	- Web console https://10.1.2.2:8443/console
	- oc login 10.1.2.2:8443 (from CLI)

The following can be used for installation and getting started references:
CDK Installation Guide
Getting Started with CDK
