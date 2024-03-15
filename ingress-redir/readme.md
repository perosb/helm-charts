### Prereqs
 - [cert-manager](https://cert-manager.io/)
 - [ingress-nginx](https://github.com/kubernetes/ingress-nginx)

Add redirect sections to `values.yaml`

```
    - host:
        name: sweden
        names:
          - kermit.se
          - frog.se
        tls: true
        redir: /sv-se$request_uri
```


Redeploy helm chart to cluster:
`helm -n ingress-redir upgrade redir-rules helm/redir/ --values values.yaml`
