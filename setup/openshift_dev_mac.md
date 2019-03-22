# Preparing a macOS machine for RedHat OPenShift

This document provides a list of software to install on a Mac for a RedHat OpenShift development environment. 
  
- [Prerequisites](#prerequisites)  
- [Command line utilities](#command-line-utilities)
- [MiniShift](#minishift)
- [Additional resources](#additional-resources)

## Prerequisites 

You should install [HomeBrew](https://brew.sh/) 
This was created on macOS 10.14.3 Mojave
Some of the items listed here are not available for Windows 

## Command line utilities

#### OpenShift client utilities -- oc 
```
brew install openshift-cli
```

xhyve virtualization


More information about xhyve here [https://docs.okd.io/latest/minishift/getting-started/setting-up-virtualization-environment.html#setting-up-xhyve-driver
](https://docs.okd.io/latest/minishift/getting-started/setting-up-virtualization-environment.html#setting-up-xhyve-driver
)

```
brew install docker-machine-driver-xhyve
sudo chown root:wheel $(brew --prefix)/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
sudo chmod u+s $(brew --prefix)/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
```
Stern -- Log tail for multiple kube clusters
```
brew install stern
```

## Minishift
Minishift is called RedHat Container Development Kit

### Red Hat Container Development Kit 3.8 -- Mar 2019
[https://developers.redhat.com/products/cdk/](https://developers.redhat.com/products/cdk/)


### Code Ready

Code Ready is a web based IDE (similar to Orion)

[https://developers.redhat.com/products/codeready-workspaces/getting-started](https://developers.redhat.com/products/codeready-workspaces/getting-started)

[https://developers.redhat.com/crw-hw/](https://developers.redhat.com/crw-hw/)

## Additional resources
    
### OpenShift 4 Blog Post Series:
[https://blog.openshift.com/the-modern-software-platform/](https://blog.openshift.com/the-modern-software-platform/)

[https://blog.openshift.com/openshift-4-a-noops-platform/](https://blog.openshift.com/openshift-4-a-noops-platform/)

[https://blog.openshift.com/openshift-4-install-experience/](https://blog.openshift.com/openshift-4-install-experience/)

[https://blog.openshift.com/how-and-why-were-changing-deployment-topology-in-openshift-4-0/](https://blog.openshift.com/how-and-why-were-changing-deployment-topology-in-openshift-4-0/)

### OpenShift Blog:
[https://blog.openshift.com]()https://blog.openshift.com

### Red Hat Containers Community of Practice
[http://uncontained.io](http://uncontained.io)

### OpenShift Documentation
[https://docs.openshift.com/container-platform/3.11/welcome/index.html](https://docs.openshift.com/container-platform/3.11/welcome/index.html)

### OpenShift Do -- Developer's Tool
[https://openshiftdo.org](https://openshiftdo.org)

Container Development Kit for OCP 3 -- Free Developer registration required
[https://developers.redhat.com/products/cdk/overview/](https://developers.redhat.com/products/cdk/overview/)

### Operator SDK
[https://github.com/operator-framework/operator-sdk](https://github.com/operator-framework/operator-sdk)

### Skopeo, Podman, Buildah -- Dockerless Container creation/management
[https://github.com/containers/skopeo](https://github.com/containers/skopeo)
[https://podman.io/](https://podman.io/)
[https://buildah.io/](https://buildah.io/)

### Awesome Operators -- list of operators
https://github.com/operator-framework/awesome-operators

### Community Operators -- for OCP 4 Marketplace
[https://github.com/operator-framework/community-operators](https://github.com/operator-framework/community-operators)

### Operator Developer Guide Book for Partners
[https://operators.gitbook.io/operator-developer-guide-for-red-hat-partners/operator-overview/what-is-an-operator](https://operators.gitbook.io/operator-developer-guide-for-red-hat-partners/operator-overview/what-is-an-operator)


