# Zerops x Umami

![Header Image](/umami-zerops.png)

[Umami](https://umami.is/) makes it easy to collect, analyze, and understand your web data — while maintaining visitor privacy and data ownership. [Zerops](https://zerops.io) makes it easy to deploy Umami.

### Prerequisities
- Zerops account - [sign up here](https://app.zerops.io/registration) with up to $100 free credit


### Deploy your Umami to Zerops
Locate "Import project" in the menu in the top left corner and paste in following yaml:

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
