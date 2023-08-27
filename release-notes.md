# Cluster Essentials Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

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

## <a id='1-5-2'></a> v1.5.2

**Release Date**: June 30, 2023

### <a id='1-5-2-resolved-issues'></a> Resolved Issues
* Updating **kapp-controller to v0.45.2**. This patch release addresses CVEs identified in v1.5. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.45.2).
* Updating **secretgen-controller to v0.14.8**
* Updating Carvel CLIs
  * imgpkg to v0.36.4
  * kapp to v0.55.2
  * kbld to v0.37.4
  * ytt to v0.45.3

## <a id='1-5-1'></a> v1.5.1

**Release Date**: June 6, 2023

### <a id='1-5-1-resolved-issues'></a> Resolved Issues
* Updating **kapp-controller to v0.45.1**. This patch release addresses CVEs identified in v1.5. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.45.1).
* Updating **secretgen-controller to v0.14.3**
* Updating Carvel CLIs
  * imgpkg to v0.36.2
  * kapp to v0.55.1
  * kbld to v0.37.1
  * ytt to v0.45.1

## <a id='1-5'></a> v1.5.0

**Release Date**: March 31, 2023

### <a id='1-5-new-features'></a> New features
* Enrich error message for kapp-controller custom resources.
* Performance enhancement by not listing labeled resources for newly created app.
* Updating **kapp-controller to v0.45.0**. A full list of new features can be found in the open source [release notes](https://github.com/carvel-dev/kapp-controller/releases/tag/v0.45.0).
* Updating **secretgen-controller to v0.14.2**.
* Updating Carvel CLIs
  * imgpkg to v0.36.0
  * kapp to v0.55.0
  * kbld to v0.37.0
  * ytt to v0.45.0

## <a id='1-4-2'></a> v1.4.2

**Release Date**: June 30, 2023

### <a id='1-4-2-resolved-issues'></a> Resolved issues
* Updating **kapp-controller to v0.44.8**. This patch release addresses CVEs identified in v1.4.1. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.44.8).
* Updating **secretgen-controller to v0.13.3**
* Updating Carvel CLIs
  * imgpkg to v0.33.5
  * kapp to v0.54.5
  * kbld to v0.36.8
  * ytt to v0.44.8

## <a id='1-4-1'></a> v1.4.1

**Release Date**: February 14, 2023

### <a id='1-4-1-resolved-issues'></a> Resolved issues
* Support added automatic IaaS authentication for fetching images from IaaS provided registry, for example, ECR from EKS. 
* Adding support for OpenShift 4.10.
* Updating **kapp-controller to v0.44.6**. This patch release addresses CVE known issues identified in 1.4. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).
* Updating **secretgen-controller to v0.13.0**
* Updating Carvel CLIs
  * imgpkg to v0.31.1
  * kapp to v0.54.3
  * kbld to v0.36.4
  * ytt to v0.44.3

## <a id='1-4'></a> v1.4.0

**Release Date**: January 9, 2023

### <a id='1-4-issues'></a> Known Issues
* Automatic IaaS authentication for fetching images from IaaS provided registry, for example, ECR from EKS, does not succeed. 
VMware recommends continued use of Cluster Essentials v1.3.0 if this feature is required.
* Due to a stricter seccomp profile, installation on OpenShift 4.10 will fail.
VMware recommends continued use of Cluster Essentials v1.3.0 if your environment is OpenShift 4.10.

### <a id='1-4-new-features'></a> New features
* Adding support for Kubernetes 1.25 and OpenShift 4.11
* Updating **kapp-controller to v0.44.1**. Some highlights from this release are listed below. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).
  * Caching of images and bundles to improve resiliency when the image registry is not available
  * Improved experience deploying on OpenShift 4.11 by resolving warnings
  * Improved pausing and waiting behaviors for PackageInstall
* Updating **secretgen-controller to v0.13.0**
* Updating Carvel CLIs
  * imgpkg to v0.31.1
  * kapp to v0.54.1
  * kbld to v0.36.1
  * ytt to v0.44.1

## <a id='1-3-1'></a> v1.3.1

**Release Date**: June 30, 2023

### <a id='1-3-1-resolved-issues'></a> Resolved issues

* Updating **kapp-controller to v0.41.8**. This patch release addresses issues identified in v1.3.0. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.41.8).
* Updating **secretgen-controller to v0.11.6**
* Updating Carvel CLIs
  * imgpkg to v0.31.5
  * kbld to v0.35.4
  * ytt to v0.43.4
  * kapp to v0.53.8

## <a id='1-3'></a> v1.3.0

**Release Date**: October 7, 2022

### <a id='1-3-new-features'></a> New features

* Adding support for Red Hat OpenShift Container Platform 4.10 running on vSphere and baremetal
* Adding a Windows installer for Cluster Essentials

* Updating **kapp-controller to v0.41.2**. Some highlights from this release are listed below. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).
  * Surface namespace and group-kind of App CR associated resources in App CR status
  * Package authors can now specify that their package can be installed on a certain versions of kapp-controller or Kubernetes
  * Allow configuring minimum app sync period
  * Adjust default TLS cipher suites to be restrictive
  * [Bug fix] Clean up sidecarexec socket file in case of previous unclean process termination

* Updating **secretgen-controller to v0.11.0**

* Updating Carvel CLIs
  * imgpkg to v0.31.0
  * kbld to v0.35.0 
  * ytt to v0.43.0 
  * kapp to v0.53.0
  
## <a id='1-2'></a> v1.2.0

**Release Date**: July 11, 2022

### <a id='1-2-new-features'></a> New features

* Updating **kapp-controller to v0.38.4**. Some highlights from this release are listed below. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).
  * Add support for Kubernetes 1.24
  * PackageRepositories support having identical packages from multiple different repositories
  * Remove support for Helm v2
  * kapp-controller will now wait indefinitely for APIService resource to succeed
  * kapp-controller will now keep a maximum of 5 app changes by default

* Updating **secretgen-controller to v0.9.1**
  * SecretTemplate API: SecretTemplate resources introduce a highly flexible way of telling secretgen-controller to populate a single secret from fields in any other resource on the cluster selected via JSONpath.
  
* Updating Carvel CLIs
  * imgpkg to v0.29.0
  * kbld to v0.34.0 
  * ytt to v0.41.1 
  * kapp to v0.49.0


## <a id='1-1'></a> v1.1.0

**Release Date**: April 5, 2022

### <a id='1-1-new-features'></a> New features

* Updating **kapp-controller to v0.34.0**. This update brings in significant performance improvements when running large Package Repositories. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).

* Updating **secretgen-controller to v0.8.0**
