# Cluster Essentials Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

## <a id='1-7'></a> v1.7.0

**Release Date**: October 20, 2023

### <a id='1-7-new-features'></a> New features
* Unblock app deletion when namespace is terminating and resources are in the same namespace.
* Don't fallback to automatic noopDelete if cluster is set.
* Updating **kapp-controller to v0.46.1**. A full list of new features can be found in the open source [release notes](https://github.com/carvel-dev/kapp-controller/releases/tag/v0.46.0).
* Updating **secretgen-controller to v0.14.8**.
* Updating Carvel CLIs
  * imgpkg to v0.37.2 [release notes](https://github.com/carvel-dev/imgpkg/releases/tag/v0.37.1)
  * kapp to v0.57.1 [release notes](https://github.com/carvel-dev/kapp/releases/tag/v0.57.0)
  * kbld to v0.37.4
  * ytt to v0.45.3
