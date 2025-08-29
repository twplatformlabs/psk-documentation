## Control Plane Application Deployment Engineering Standards and Practices

- [x] Disable auto-mounting of service account tokens
```yaml
kind: ServiceAccount
automountServiceAccountToken: true
```

- [x] Use dedicated service accounts for each application

Do no use the namespace default service account.  

- [x] Run the application as a non-root user
- [x] Restrict the containers that can run as privileged
- [x] Do not allow privileged escalation
- [x] Configure your images with read-only root file system
- [x] Runtime Linux capabilities and Seccomp
Use secure context:  
```yaml
  allowPrivilegeEscalation: false
  readOnlyRootFilesystem: true

  runAsNonRoot: true
  runAsUser: 65532
  runAsGroup: 65532
  fsGroup: 65532

  seccompProfile:
    type: RuntimeDefault

  capabilities:
    drop: ["ALL"]
```

- [x] Grant least privileged access to applications

Set EKS Pod Identity or IRSA permission boundaries to only required permissions.  

- [x] Disable service discovery

For pods that do not need to lookup or call in-cluster services, you can reduce the amount of information given to a pod. You can set the Pod’s DNS policy to not use CoreDNS, and not expose services in the pod’s namespace as environment variables.
```yaml
spec:
    dnsPolicy: Default # Literal default is "ClusterFirst"
    enableServiceLinks: false
```