# Rancher Turtles - Fleet Example

This repository can be used to import clusters into Rancher using Fleet. There are a number of different branches that you can use that demonstrate different aspects of this integration:

- **[main](https://github.com/rancher-sandbox/rancher-turtles-fleet-example/tree/main)** - used for for importing cluster definitions where all clusters within a namespace are automatically imported into Rancher.
- **[per-cluster-import](https://github.com/rancher-sandbox/rancher-turtles-fleet-example/tree/per-cluster-import)** - used for importing cluster definitions where individual clusters are marked for auto-importing into Rancher.
- **[templates](https://github.com/rancher-sandbox/rancher-turtles-fleet-example/tree/templates)** - contains Cluster API templates that are used by the Rancher Turtles documentation.
- **[cluster-class](https://github.com/rancher-sandbox/rancher-turtles-fleet-example/tree/clusterclass)** - contains a sample using ClusterClass
- **[aws](https://github.com/rancher-sandbox/rancher-turtles-fleet-example/tree/aws)** - contains a sample using AWS.
- **docker-rke2 (this branch)** - contains a sample using RKE2 docker provisioner.


Switch to the branch to read further information.

## Branch explanation

The [clusters](./clusters/) folder contains the definition for the clusters that you want to create and have imported into Rancher Manager. These definitions can be created using **clusterctl** or hand crafted. See the [Rancher Turtles documentation](https://rancher.github.io/turtles-docs/) for further details.

The [fleet.yaml](./clusters/fleet.yaml) file contains configuration used by Fleet when creating bundles. Specifically in this file we are declaring that the cluster definitions should be placed in a namespace called **default**. The file also contains `diff.comparePatches` block used by fleet to ignore resources modified by Cluster API.

You will need to add the **cluster-api.cattle.io/rancher-auto-import** label with a value of **true** to the **default** namespace to have the cluster auto-imported.
