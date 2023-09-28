# Cluster Essentials Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

## <a id='1-6-2'></a> v1.6.2

**Release Date**: September 29, 2023

### <a id='1-6-2-resolved-issues'></a> Resolved Issues
* Updating **kapp-controller to v0.46.2** with photon patch. This patch release addresses CVEs identified in v1.6.1 .

## <a id='1-6-1'></a> v1.6.1

**Release Date**: August 31, 2023

### <a id='1-6-1-resolved-issues'></a> Resolved Issues
* Updating **kapp-controller to v0.46.2**. This patch release addresses CVEs identified in v1.6. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.46.2).
* Updating **secretgen-controller to v0.14.10**.
* Updating Carvel CLIs
  * imgpkg to v0.37.3 [release notes](https://github.com/carvel-dev/imgpkg/releases/tag/v0.37.1)
  * kapp to v0.57.2 [release notes](https://github.com/carvel-dev/kapp/releases/tag/v0.57.0)
  * kbld to v0.37.5
  * ytt to v0.45.4

## <a id='1-6'></a> v1.6.0

**Release Date**: July 6, 2023

### <a id='1-6-new-features'></a> New features
* Unblock app deletion when namespace is terminating and resources are in the same namespace.
* Don't fallback to automatic noopDelete if cluster is set.
* Updating **kapp-controller to v0.46.1**. A full list of new features can be found in the open source [release notes](https://github.com/carvel-dev/kapp-controller/releases/tag/v0.46.0).
* Updating **secretgen-controller to v0.14.8**.
* Updating Carvel CLIs
  * imgpkg to v0.37.2 [release notes](https://github.com/carvel-dev/imgpkg/releases/tag/v0.37.1)
  * kapp to v0.57.1 [release notes](https://github.com/carvel-dev/kapp/releases/tag/v0.57.0)
  * kbld to v0.37.4
  * ytt to v0.45.3
