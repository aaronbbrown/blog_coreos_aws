# Overview

This is a respository of code to bring up CoreOS in AWS with
AutoScaling and and ELB listening on port 80.  It expects an HTTP service
running on port 8080.

It runs a Docker image of the 9minutesnooze blog.

1. Create a stack with coreos-alpha-pv.json using ${TOOLS} or Console,
   supplying all parameters
2. Check that the blog service is running on all cluster nodes
```
$ ssh core@ec2-XX-XXX-XX-XXX.compute-1.amazonaws.com
$ fleetctl list-units
UNIT		MACHINE				ACTIVE	SUB
blog.service	04b78c6d.../10.170.80.136	active	running
blog.service	13ae35c7.../10.144.85.189	active	running
blog.service	e48b04c0.../10.228.32.103	active	running
```
