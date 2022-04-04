# Deploy Cluster Essentials

This document describes how to install, upgrade, and uninstall Cluster Essentials.

## <a id='supported-platforms'></a> Supported Platforms
Currently, Cluster Essentials only supports MacOS and Linux. 

## <a id='install'></a> Install
If you are using a VMware Tanzu Kubernetes Grid cluster, you do not need to install Cluster Essentials because the contents of Cluster Essentials are already installed on your cluster.

For all other clusters, install Cluster Essentials using the following steps.

### <a id='download'></a> Download artifacts from Tanzu Network
1. Sign in to [Tanzu Network](https://network.tanzu.vmware.com).

1. Go to [Cluster Essentials for VMware Tanzu](https://network.tanzu.vmware.com/products/tanzu-cluster-essentials/) on VMware Tanzu Network.

1. Accept or confirm that you have accepted the EULA for the product

1.  Select a download according to your Kubernetes provider and operating system:

    - For macOS, download `tanzu-cluster-essentials-darwin-amd64-1.1.0.tgz`.
    - For Linux, download `tanzu-cluster-essentials-linux-amd64-1.1.0.tgz`.

1. Unpack the TAR file into the `tanzu-cluster-essentials` directory:

    ```
    mkdir $HOME/tanzu-cluster-essentials
    tar -xvf DOWNLOADED-CLUSTER-ESSENTIALS-BUNDLE -C $HOME/tanzu-cluster-essentials
    ```

    Where `DOWNLOADED-CLUSTER-ESSENTIALS-BUNDLE` is the name of the bundle you downloaded.

### <a id='cluster-context'></a> Set Kubernetes cluster context

1. List the existing contexts by running:

    ```
    kubectl config get-contexts
    ```


1.  Set the context to the cluster that you want to use for the Cluster Essentials install.

    ```
    kubectl config use-context CONTEXT-NAME
    ```

### <a id='install'></a> Deploy onto cluster

1. (Optional) If your registry needs a custom certificate, you must [load that configuration](https://carvel.dev/kapp-controller/docs/v0.34.0/controller-config/) into the cluster before installing `kapp-controller`. If your registry uses a public certificate, this step is not required.

   Create the `kapp-controller` namespace:

    ```
    kubectl create namespace kapp-controller
    ```

   Create a configuration secret by using the registry's `ca.crt` stored on local disk:

    ```
    kubectl create secret generic kapp-controller-config \
       --namespace kapp-controller \
       --from-file caCerts=ca.crt
    ```

1. Configure and run `install.sh`, which will install `kapp-controller` and `secretgen-controller` on your cluster:

    ```
    export INSTALL_BUNDLE=registry.tanzu.vmware.com/tanzu-cluster-essentials/cluster-essentials-bundle@sha256:ab0a3539da241a6ea59c75c0743e9058511d7c56312ea3906178ec0f3491f51d
    export INSTALL_REGISTRY_HOSTNAME=registry.tanzu.vmware.com
    export INSTALL_REGISTRY_USERNAME=TANZU-NET-USER
    export INSTALL_REGISTRY_PASSWORD=TANZU-NET-PASSWORD
    cd $HOME/tanzu-cluster-essentials
    ./install.sh --yes
    ```

    Where `TANZU-NET-USER` and `TANZU-NET-PASSWORD` are your credentials for VMware Tanzu Network.

### <a id='cli-install'></a> Optionally install CLIs onto your `$PATH`
1. (Optional) Several Tanzu products, such as Tanzu Application Platform, use the `kapp` CLI to deploy. For convenience, you may install the `kapp` CLI onto your `$PATH`:

    ```
    sudo cp $HOME/tanzu-cluster-essentials/kapp /usr/local/bin/kapp
    ```

1. (Optional) Several Tanzu products, such as Tanzu Application Platform, use the `imgpkg` CLI to relocate packages. For convenience, you may install the `imgpkg` CLI onto your `$PATH`:

    ```
    sudo cp $HOME/tanzu-cluster-essentials/imgpkg /usr/local/bin/imgpkg
    ```

## <a id='upgrade'></a> Upgrade
Cluster Essentials components (such as `kapp-controller` and `secretgen-controller`) cannot be upgraded on clusters provisioned using VMware Tanzu Kubernetes Grid, Tanzu Community Edition, and VMware Tanzu Mission Control. 

For all other clusters, if you already have Cluster Essentials 1.0 installed on your target cluster, you can upgrade to Cluster Essentials 1.1 using the following steps. Running this upgrade will update the `kapp-controller` version on your cluster to `v0.34.0` and `secretgen-controller` version to `v0.8.0`.

1. Follow the steps above to [Download artifacts from Tanzu Network](#download) and [Set Kubernetes cluster context](#cluster-context)

1. Configure and run `install.sh`, which will install `kapp-controller` and `secretgen-controller` on your cluster:

    ```
    export INSTALL_BUNDLE=registry.tanzu.vmware.com/tanzu-cluster-essentials/cluster-essentials-bundle@sha256:ab0a3539da241a6ea59c75c0743e9058511d7c56312ea3906178ec0f3491f51d
    export INSTALL_REGISTRY_HOSTNAME=registry.tanzu.vmware.com
    export INSTALL_REGISTRY_USERNAME=TANZU-NET-USER
    export INSTALL_REGISTRY_PASSWORD=TANZU-NET-PASSWORD
    cd $HOME/tanzu-cluster-essentials
    ./install.sh --yes
    ```

    Where `TANZU-NET-USER` and `TANZU-NET-PASSWORD` are your credentials for VMware Tanzu Network.

1. Follow the [steps above](#cli-install) to optionally install newer versions of the `kapp` and `imgpkg` CLIs to your path 


## <a id='uninstall'></a> Uninstall
**Caution:** Please ensure that you have uninstalled all Custom Resources created by `kapp-controller` and `secretgen-controller` before running the uninstall script for Cluster Essentials.

1. Follow the steps above to [Set Kubernetes cluster context](#cluster-context)

1. Run `uninstall.sh`, which will uninstall `kapp-controller` and `secretgen-controller` on your cluster:

    ```
    cd $HOME/tanzu-cluster-essentials
    ./uninstall.sh --yes
    ```
