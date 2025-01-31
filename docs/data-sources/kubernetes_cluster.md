---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "civo_kubernetes_cluster Data Source - terraform-provider-civo"
subcategory: ""
description: |-
  Provides a Civo Kubernetes cluster data source.
  Note: This data source returns a single Kubernetes cluster. When specifying a name, an error will be raised if more than one Kubernetes cluster found.
---

# civo_kubernetes_cluster (Data Source)

Provides a Civo Kubernetes cluster data source.

Note: This data source returns a single Kubernetes cluster. When specifying a name, an error will be raised if more than one Kubernetes cluster found.

## Example Usage

```terraform
data "civo_kubernetes_cluster" "my-cluster" {
    name = "my-super-cluster"
}

output "kubernetes_cluster_output" {
  value = data.civo_kubernetes_cluster.my-cluster.master_ip
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Optional

- **id** (String) The ID of this resource.
- **name** (String) The name of the Kubernetes Cluster
- **region** (String) The region where cluster is running

### Read-Only

- **api_endpoint** (String) The base URL of the API server on the Kubernetes master node
- **applications** (String) A list of application installed
- **created_at** (String) The date where the Kubernetes cluster was create
- **dns_entry** (String) The unique dns entry for the cluster in this case point to the master
- **installed_applications** (List of Object) (see [below for nested schema](#nestedatt--installed_applications))
- **instances** (List of Object) (see [below for nested schema](#nestedatt--instances))
- **kubeconfig** (String) A representation of the Kubernetes cluster's kubeconfig in yaml format
- **kubernetes_version** (String) The version of Kubernetes
- **master_ip** (String) The IP of the Kubernetes master node
- **num_target_nodes** (Number) The size of the Kubernetes cluster
- **pools** (List of Object) (see [below for nested schema](#nestedatt--pools))
- **ready** (Boolean) If the Kubernetes cluster is ready
- **status** (String) The status of Kubernetes cluster
- **tags** (String) A list of tags
- **target_nodes_size** (String) The size of each node

<a id="nestedatt--installed_applications"></a>
### Nested Schema for `installed_applications`

Read-Only:

- **application** (String)
- **category** (String)
- **installed** (Boolean)
- **version** (String)


<a id="nestedatt--instances"></a>
### Nested Schema for `instances`

Read-Only:

- **cpu_cores** (Number)
- **disk_gb** (Number)
- **hostname** (String)
- **ram_mb** (Number)
- **size** (String)
- **status** (String)
- **tags** (Set of String)


<a id="nestedatt--pools"></a>
### Nested Schema for `pools`

Read-Only:

- **count** (Number)
- **id** (String)
- **instance_names** (Set of String)
- **instances** (List of Object) (see [below for nested schema](#nestedobjatt--pools--instances))
- **size** (String)

<a id="nestedobjatt--pools--instances"></a>
### Nested Schema for `pools.instances`

Read-Only:

- **cpu_cores** (Number)
- **disk_gb** (Number)
- **hostname** (String)
- **ram_mb** (Number)
- **size** (String)
- **status** (String)
- **tags** (Set of String)


