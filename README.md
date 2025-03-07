# 🌈 Websites of DWH

## Setup

DWH is the independent LGBTI+ association of Delft and surroundings.
We're two things: a meeting place for LGBTI+ people and their friends and a group that actively
pushes for greater LGBTI+ rights and acceptance.

The website is a (statically generated) [Nuxt.js](https://nuxtjs.org) app hosted on [Cloudflare](https://cloudflare.com).
The app makes heavy use of [Vue.js](https://vuejs.org/) and [Tailwind CSS](https://tailwindcss.com/).


## Requirements

* [Node.js 22](https://nodejs.org/en)
* NPM

## Build Setup

```bash
npm install
```

## Development

```bash
npm run dev <domain>

# For example:
npm run dev dwhdelft.nl
npm run dev outsite.nl
```

_The domain argument is actually the subdirectory. We use [Nuxt layers](https://nuxt.com/docs/getting-started/layers) to generate multiple websites from the same codebase._

### Recommended development tools

* [Visual Studio Code](https://code.visualstudio.com)
  * [Vue - Official](https://marketplace.visualstudio.com/items?itemName=Vue.volar)
  * [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
  * [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
  * [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
* [Vue.js devtools](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)

## Production

Build the application for production:

```bash
npm run build <domain>
```

Locally preview production build:

```bash
npm run preview <domain>
```

Check out the [Nuxt deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.
