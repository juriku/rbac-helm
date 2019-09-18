# Helm Kubernetes RBAC deployment
Simplified Kubernetes RBAC deployment with helm for user/groups

## Advantages
- an easy way to add users to one group and not repeat them in values
- can supply several groups to one role binding
- will not create individual role bindings per user, but group them instead
- use of default Kubernetes aggregated rules for admin/edit/view
- no need to specify users for only view - all authenticated users will have view access by default
- easy to add new custom (cluster)roles and role bindings

## Examples
Please refer to comments in "values.yaml"

## Google Cloud setup
The only permissions in IAM needed to get authenticated in Kubernetes for users:

```
container.apiServices.get
container.apiServices.list
container.clusters.get
container.clusters.getCredentials
```

This will get users to 'system:authenticated' group, which can be given (view) role, so no need to specify (view) users