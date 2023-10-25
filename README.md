# Rancher Turtles - Fleet Example

This repository can be used to import clusters into Rancher using Fleet. There are a number of different branches that you can use that demonstrate different aspects of this integration:

- **[main](https://github.com/rancher-sandbox/rancher-turtles-fleet-example/tree/main)** - used for importing cluster definitions where all clusters within a namespace are automatically imported into Rancher.
- **[per-cluster-import](https://github.com/rancher-sandbox/rancher-turtles-fleet-example/tree/per-cluster-import)** - used for importing cluster definitions where individual clusters are marked for auto-importing into Rancher.
- **clusterclass (this branch)** - used for demonstrating using ClusterClass with Rancher Turtles.
- **[templates](https://github.com/rancher-sandbox/rancher-turtles-fleet-example/tree/templates)** - contains Cluster API templates that are used by the Rancher Turtles documentation.

Switch to the branch to read further information.

## Branch explanation

The [classes](./classes/) folder contains the definitions for the ClusterClasses. These will be used by the **cluster** definitions to create cluster instances.

The [clusters](./clusters/) folder contains the definition for the clusters that you want to create and have imported into Rancher Manager. These definitions use cluster classes.

> Its not required to split the clusterclass and cluster definitions like this.

Like the other branches, the [fleet.yaml](fleet.yaml) file contains configuration used by Fleet when creating bundles. Specifically in this examples we are declaring two bundles, one for the cluster classes and one for the that the cluster definitions.

The cluster definition in [cluster1.yaml](./clusters/cluster1.yaml) is labled so that it is auto-imported into Rancher when it is Ready. See the **Cluster** kind in the file.
