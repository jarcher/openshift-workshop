Microservices Lab
=================

This lab will demonstrate the deployment of a microservices-based application to OpenShift. This lab makes use of the instructions, example code, and related architecture found at [debianmaster/microservices-on-openshift](https://github.com/debianmaster/microservices-on-openshift/blob/master/README.md).

One thing to note: Replace step 0 with our step 0 below.

0) Initial Setup
----------------
- Login to OSE as admin

        oc login -u admin

- Create a new project (microservices-lab)

        oc new-project microservices-lab

- Add admin role to openshift-dev user for microservices-lab project

        oc policy add-role-to-user admin openshift-dev -n microservices-lab

- Logout as admin, login as openshift-dev on CLI and web UI

        oc logout
        oc login -u openshift-dev 
        oc project microservices-lab

- Set some env vars

        export OSE_DOMAIN=rhel-cdk.<vagrant VM IP>.xip.io
        export OSE_PROJECT=microservices-lab

Back to [Lab Index](index.md)
