## In which order the resources be installed by Helm
Helm collects all of the resources in a given Chart and it's dependencies, 
groups them by resource type, and then installs them in the following order

1. Namespace
2. ResourceQuota
3. LimitRange
4. PodSecurityPolicy
5. Secret
6. ConfigMap
7. StorageClass
8. PersistentVolume
9. PersistentVolumeClaim
10. ServiceAccount
11. CustomResourceDefinition
12. ClusterRole
13. ClusterRoleBinding
14. Role
15. RoleBinding
16. Service
17. DaemonSet
18. Pod
19. ReplicationController
20. ReplicaSet
21. Deployment
22. StatefulSet
23. Job
24. CronJob
25. Ingress
26. APIService
