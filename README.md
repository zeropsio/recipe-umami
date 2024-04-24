# Zerops x Umami

```yaml
project:
  name: umami
services:
  - hostname: db
    type: postgresql@16
    mode: NON_HA
  - hostname: umami
    type: nodejs@18
    ports:
      - port: 3000
        httpSupport: true
    enableSubdomainAccess: true
    minContainers: 1
```
