# Zerops x Umami

![Umami](https://github.com/zeropsio/recipe-shared-assets/blob/main/covers/svg/recipe-umami.svg)

[Umami](https://umami.is/) makes it easy to collect, analyze, and understand your web data — while maintaining visitor privacy and data ownership. [Zerops](https://zerops.io) makes it easy to deploy Umami.

### Prerequisites
- Zerops account - [sign up here](https://app.zerops.io/registration) with up to $65 free credit


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
    type: nodejs@20
    enableSubdomainAccess: true
    buildFromGit: https://github.com/zeropsio/recipe-umami
    envSecrets:
      APP_SECRET: <@generateRandomString(<64>)>
```
