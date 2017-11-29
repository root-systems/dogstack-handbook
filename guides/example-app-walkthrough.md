# Creating your first `dogstack` app

🐕Welcome🐕 

This is a walkthrough of our example app. If you want to skip the doggy day care and get right into the code, we recommend you jump over to our [How to create a dogstack app](https://dogstack.js.org/guides/how-to-create-app.html) walkthrough. This walkthrough is for people that are familiar with `react` and `redux` but are new to functional Javascript or want a more in-depth knowledge of the modules and tooling `dogstack` uses.

## What we'll be creating
![An example of what we're creating](https://i.imgur.com/zQxPdoW.gif)

We'll be giving dogs a new leash on life(geddit?) with this 'adopt a dog' generator.
Users can adopt a dog(add a dog to our list) or give a dog to a friend(remove a dog from our list)

## Pre-requisites

This walkthough assumes you have a basic knowledge of `react`, `redux` and functional programming. If you don't, that's cool, but we reccoemnd learning the basics and coming back once you feel comfortable with them. Here's a list of resources we like.

- React
  - TODO: Need example that's not using classes
- Redux
  - https://egghead.io/courses/getting-started-with-redux
  - https://medium.com/@rajaraodv/step-by-step-guide-to-building-react-redux-apps-using-mocks-48ca0f47f9a
  - https://github.com/reactjs/redux/blob/master/docs/introduction/ThreePrinciples.md
- Functional Programming
  - https://medium.freecodecamp.org/functional-programming-in-js-with-practical-examples-part-1-87c2b0dbc276 (if you only read one thing from this article, make it the Currying section)

Before we start, please

- [install `node@8` and `npm@5`](https://dogstack.js.org/guides/how-to-install-js.html)

## Let's code

Let's start by cloning our example repo

`git clone git://github.com/root-systems/dogstack-example`

Installing the dependencies
```shell
cd dogstack-example
npm install

```

and setting up the database for the first time
```shell
npm run db migrate:latest
npm run db seed:run

```

Now that we've set up the scaffolding of our projects, let's dive in and see what we've got.

### File structure

The first thing you'll notice is how the directories are set up. 

![file structure](https://i.imgur.com/phigXbc.png)

Our project is split into directories for each conceptual topic, where each topic contains the various types of files within that topic.

This leads to a directory structure of `${topic}/${type}/${name}`.

You can read more about what topics, types and names are [here](https://dogstack.js.org/conventions/file-structure.html)

### There's so many files, what do they all do?!
Well, you're in for a treat. Although there is a lot of boilerplate, it's all there intentionally. You'll regularly find files less than 10 lines long this is because dogstack is heavily abstracted and focuses on everything being [obvious and readable.](https://github.com/reactjs/redux/issues/2295)

Hopefully everything is obvious and readable 😉, but lets walk you through some of the files anyway.

TODO: Where do I even start? Could start with `server.js` and briefly explain feathers, then deep dive when we actually use it. Should finish on `layout.js` so we can move onto creating features 🐶





## Show me the dogs 🐶
Now let's have a look at what we've got!

`npm run dev`

![step one](https://i.imgur.com/NkrJTPH.png)
That's not a dog...