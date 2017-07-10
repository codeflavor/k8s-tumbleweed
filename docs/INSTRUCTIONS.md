In order to get started, you need to specify how your cluster should be
structured in the [invetory](../inventory.yaml) file.   
There are 3 roles in this repository that will bootstrap your cluster.

* `[cluster]` -  All nodes that you want to add go here (master/node).
This role performs basic configuration of the underlying OS.

* `[master]` - Only one single node should be here, that you want as master. This role will install the master binaries together with other optional tools
(such as helm).

* `[node]` - The rest of the nodes that you need to add to your cluster go here.
