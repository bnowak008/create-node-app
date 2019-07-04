# Create Node App ![CircleCI](https://img.shields.io/circleci/build/github/kubesail/create-node-app.svg) [![npm version](https://img.shields.io/npm/v/create-node-app.svg)](https://www.npmjs.com/package/create-node-app)

Create modern Node.js apps with no build configuration. In a single command, this tool lets you create an app which closely follows [The Twelve Factors](https://12factor.net) of web application development. Inspired by and based on [create-react-app](https://github.com/facebook/create-react-app).

## Quick start

#### Creating an App

    npx create-node-app my-app
    cd my-app
    npm start

_Creates a new repository and starts a React frontend, an Express backend, and containers for Postgres and Redis locally_

#### Deploying to Production

    npm run deploy

_Containerizes your app and its dependencies (like Postgres and Redis) and deploys them to Kubernetes_

## What’s Included?

`create-node-app` automatically sets up and manages:

- A complete web app with React, Express, Postgres, and Redis
- A deploy script, `npm run deploy` that deploys your frontend, backend, and dependencies to Kubernetes via [deploy-node-app](https://github.com/kubesail/deploy-node-app)
- Creates a secure `Dockerfile` for containerized production deploys
- Developer tools: ESLint, editorconfig, prettier, automatic reload
- A [meta-module](https://github.com/metamodules/documentation) system for easy development with services like PostgreSQL, Redis, and MongoDB, all with no configuration

`create-node-app` has a simple core, with a small ecosystem of _meta-modules_.

## Meta-modules

Meta-modules are simple npm modules which include:

- A validated and secure Node.js library
- Metadata for configuring the library (Environment Variables)
- A Docker Container Image which is validated to work with the chosen library
- Metadata for configuring the service's container

For example, the [redis meta-module](https://github.com/metamodules/redis) bundles the [redis](https://github.com/NodeRedis/node_redis) library, a Redis 5 Docker image, and knows how to connect your app to Redis, _without any configuration!_ Meta-modules wrap some of the complexity of building microservices with Node.js, allowing you to rapidly iterate with the stack of your choice!

Explore modules [here](https://github.com/metamodules) or help create them if the one you want doesn't exist!

## Free App Hosting

This project is maintained by [KubeSail](kubesail.com), which provides free-tier hosting. After creating an app, try `npm run deploy` to easily launch your app on a Kubernetes cluster with built-in load-balancing, HTTPS, and high-availability! KubeSail also offers the best way to iterate on Kubernetes resources - check us out!

## Contributing

- If you feel that this tool can be improved, or you've created a meta-module you want us to include, feel free to open an issue or pull request!
- We also value contributions on [deploy-node-app](https://github.com/kubesail/deploy-node-app) which contains the bulk of the logic for creating and deploying dev and prod environments.
