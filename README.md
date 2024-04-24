# Zerops x Umami

https://umami.is on https://zerops.io

```yaml
#yamlPreprocessor=on
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
    buildFromGit: https://github.com/zeropsio/recipe-umami
    minContainers: 1
    envSecrets:
      APP_SECRET: <@generateRandomString(<64>)>
```
