# Zerops x Umami
[Umami](https://umami.is/) makes it easy to collect, analyze, and understand your web data — while maintaining visitor privacy and data ownership. [Zerops](https://zerops.io) makes it easy to deploy Umami.

![unami](https://github.com/zeropsio/recipe-shared-assets/blob/main/covers/svg/recipe-umami.svg)

<br />

## Deploy on Zerops
You can either click the deploy button to deploy directly on Zerops, or manually copy the [import yaml](https://github.com/zeropsio/recipe-unami/blob/main/zerops-project-import.yml) to the import dialog in the Zerops app.

[![Deploy on Zerops](https://github.com/zeropsio/recipe-shared-assets/blob/main/deploy-button/green/deploy-button.svg)](https://app.zerops.io/recipe/unami)

<br/>

## Recipe features
- **Unami** app running on a load balanced **Zerops Node.js** service
- Zerops **PostgreSQL 16** service as database
- Utilization of Zerops' built-in **environment variables** system

<br/>

## Production vs. development

Base of the recipe is ready for production, the difference comes down to:

- Use highly available version of the PostgreSQL database (change `mode` from `NON_HA` to `HA` in recipe YAML, `db` service section)
- Set up database backups in the `db` service details.

<br/>
<br/>

Need help setting your project up? Join [Zerops Discord community](https://discord.com/invite/WDvCZ54).


