# Cluster Essentials Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

## <a id='1-8'></a> v1.8.0

**Release Date**: February 15, 2024

### <a id='1-8-new-features'></a> New features

- Avoid updating the kapp deploy status while performing a deletion.
- Adding an option to skip SSL verification when using Git.
- Updating **kapp-controller to v0.50.0**. A full list of new features can be found in the open source [release notes](https://github.com/carvel-dev/kapp-controller/releases/tag/v0.50.0).
- Updating **secretgen-controller to v0.16.1** [release notes](https://github.com/carvel-dev/secretgen-controller/releases/tag/v0.16.0).
- Updating Carvel CLIs.
    * imgpkg to v0.40.0 [release notes](https://github.com/carvel-dev/imgpkg/releases/tag/v0.40.0)
    * kapp to v0.60.0 [release notes](https://github.com/carvel-dev/kapp/releases/tag/v0.60.0)
    * kbld to v0.39.0
    * ytt to v0.47.0
