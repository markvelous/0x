# Instant DEX

PT7210027 Mark Tan, in fulfilment of SGBT4 Intermediate Blockchain module.

This is an OTB 0x Launch Kit that can set up a personal 0x-based cryptoasset exchange in minutes. It has an elegant UI making it easy to monitor and manage orders.

![](./03home.png)

The frontend is not uploaded on Netlify. A live demo is hosted on [Kovan Testnet Demo] (http://v3-kovan-demo.s3-website-us-east-1.amazonaws.com/#/erc20/)


## ⚠️ Warning ️

This is for class demo only. The Launch Kit is no longer maintained by 0x. Any serious attempt to create an offchain DEX should consider forking or running a [Standard Relayer API](https://0x.org/docs/api#sra) instance using the [0x API](https://github.com/0xProject/0x-api) instead to avoid deprecation issues.

|                              ERC-20                              |                              ERC-721                              |
| :--------------------------------------------------------------: | :---------------------------------------------------------------: |
| ![](https://s3.eu-west-2.amazonaws.com/0x-wiki-images/erc20.png) | ![](https://s3.eu-west-2.amazonaws.com/0x-wiki-images/erc721.png) |

The source codes are at https://github.com/0xProject/0x-launch-kit
## Quick Start

Install all dependencies below:
-   [Node.js](https://nodejs.org/en/download/) >v8.x
-   [Yarn](https://yarnpkg.com/en/) > v1.x
-   [Docker](https://docs.docker.com/compose/install/)
-   [npx](https://www.npmjs.com/package/npx)

```bash
npm install --global yarn
npm install -g npx
```

Install Docker
install node.js > 0.8x (node -v)

```
git clone https://github.com/0xProject/0x-launch-kit
```
`Run the wizard and load the Docker image`

```
npx @0x/launch-kit-wizard && docker-compose up
```

Once the image is built, open the browser to see the exchange instantly. It will be running at the port specified in the wizard. The default is http://localhost:3001/

There is further instructions for [using the Launch Kit with Ganache](https://github.com/0xProject/0x-launch-kit/wiki/FAQ#development-with-ganache) and for [deploying to AWS](https://github.com/0xProject/0x-launch-kit/wiki/FAQ#aws)

## About the Launch Kit

It is an open-source 0x relayer template that can be used as a starting point for a DEX project to ...
-   Quickly launch a market for your community token
-   Seemlessly create an in-game marketplace for digital items and collectibles
-   Enable trading of any ERC-20 or ERC-721 asset

The Launch Kit has two separate repos:
-   **[0x Launch Kit Frontend](https://github.com/0xProject/0x-launch-kit-frontend)**: ERC-20 and ERC-721 relayer UIs; it is a TypeScript codebase and uses React + Thunk to create and manage the UI.
-   **[0x API](https://github.com/0xProject/0x-api)**: An API that supports the [Standard Relayer API](https://0x.org/docs/api#sra) specification. It is a Typescript node codebase that uses Express to run an HTTP server.

This repo contains a Docker image that will run both codebases simultaneously for easy deployment. Both repos can be cloned or forked independently.

Note some installations of Docker on windows don't support forwarding `localhost` to the Docker VM. You may be required to update references of `localhost` to `192.168.99.100` or the `docker-machine ip` equivalent. These values should be replaced during the Wizard prompts and when navigating to the frontend website.
