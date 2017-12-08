# How to create a new `dogstack` app

## Pre-requisites

Before we begin, please ensure you have JavaScript ready to go:

- [How to Install Node.js](./how-to-install-js.md)

## Lay down the scaffold

Let's get started, woof woof! 🐕

First, [fork](https://guides.github.com/activities/forking/) the [`dogstack-example`](https://github.com/dogstack/dogstack-example) on GitHub.

Then, clone your fork onto your local machine:

```shell
mkdir -p ~/git/$USER
cd ~/git/$USER
git clone $USER/dogstack-example my-new-app
cd my-new-app
```

## See your app come to life!

With the code pulled down, let's fire it into action!

```shell
npm install
npm run start:dev
```

Browse to <http://localhost:3000> 🎉

## Explore our basic app code

Now that we have code ready, let's expore. 🔎

### Project

- `package.json`: project metadata
- `README.md`: project documentation

### Server

- `index.js`: entry point
- `server.js`: http server
- `service.js`: [feathers](https://docs.feathersjs.com) service

### Browser

- `browser.js`: entry point
- `client.js`: [feathers](https://docs.feathersjs.com) client
- `reducer.js`: [redux reducer](http://redux.js.org/docs/basics/Reducers.html)
- `router.js`: react router redux

### Cli

- `cli.js`: TODO cli entry point
