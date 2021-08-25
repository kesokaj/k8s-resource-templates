````
apiVersion: traefik.containo.us/v1alpha1
kind: IngressRoute
metadata:
  name: <some name>
  namespace: default
spec:
  entryPoints:
    - websecure
  routes:
  - kind: Rule
    match: Host(`test.example.com`)
    services:
    - kind: Service
      name: <service name>
      port: 80
      strategy: RoundRobin
      weight: 10
  tls:
    certResolver: default

````
