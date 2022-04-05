# Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

## <a id='1-1'></a> v1.1.0

**Release Date**: April 5, 2022

### <a id='1-1-new-features'></a> New features

* Updating **kapp-controller to v0.34.0**. This update brings in significant performance improvements when running large Package Repositories. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).

* Updating **secretgen-controller to v0.8.0**

* Adding an **uninstall.sh** script for uninstalling all in-cluster components. Please ensure that you have uninstalled all CRs created by kapp-controller and secretgen-controller before running the uninstall script for Cluster Essentials.
