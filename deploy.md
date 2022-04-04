## <a id='tanzu-cluster-essentials'></a> Deploying Cluster Essentials

If you are using a VMware Tanzu Kubernetes Grid cluster, you do not need to install Cluster Essentials because the contents of Cluster Essentials are already installed on your cluster.

For all other clusters, install Cluster Essentials using the following steps:

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

    Where:

    - `DOWNLOADED-CLUSTER-ESSENTIALS-BUNDLE` is the name of the cluster essentials package you downloaded.

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
    export INSTALL_BUNDLE=registry.tanzu.vmware.com/tanzu-cluster-essentials/cluster-essentials-bundle@sha256:82dfaf70656b54dcba0d4def85ccae1578ff27054e7533d08320244af7fb0343
    export INSTALL_REGISTRY_HOSTNAME=registry.tanzu.vmware.com
    export INSTALL_REGISTRY_USERNAME=TANZU-NET-USER
    export INSTALL_REGISTRY_PASSWORD=TANZU-NET-PASSWORD
    cd $HOME/tanzu-cluster-essentials
    ./install.sh
    ```

    Where:

    - `TANZU-NET-USER` and `TANZU-NET-PASSWORD` are your credentials for VMware Tanzu Network.

1. (Optional) Several Tanzu products, such as Tanzu Application Platform, use the `kapp` CLI to deploy. For convenience, install the `kapp` CLI onto your `$PATH`:

    ```
    sudo cp $HOME/tanzu-cluster-essentials/kapp /usr/local/bin/kapp
    ```

1. (Optional) Several Tanzu products, such as Tanzu Application Platform, use the `imgpkg` CLI to relocate packages. For convenience, install the `imgpkg` CLI onto your `$PATH`:

    ```
    sudo cp $HOME/tanzu-cluster-essentials/imgpkg /usr/local/bin/imgpkg
    ```
