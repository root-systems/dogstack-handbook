# Convention: File structure

The most important convention in `dogstack` is how we structure our projects into files across directories.

We want to provide [the hinges for developers to lay their medium-density fibreboard (MDF)](http://viewer.scuttlebot.io/%255U%2B7Fblfzf1iO%2BbE%2BanI%2Fwn%2FL9L0LkpM5A9%2BMlf0Wcc%3D.sha256).

In contrast to frameworks like Rails which split our project into directories for each type of file (models, views, controllers), our project is split into directories for each conceptual topic, where each topic contains the various types of files *within* that topic.

This leads to a directory structure of `${topic}/${type}/${name}`.

## What is a topic?

> What the module does

A topic is a grouping of modules that are related by concept.

Some examples of topics:

- accounts
- profiles
- navigation
- notifications
- payments
- database

Topics are sentimental and subjective, dependent mostly on the common vocabulary used across the team when communicating about the project.

The reasons for co-locating modules into topics:

- Keeps the project grounded in shared vocabulary and business logic
- Concepts are each cohesive inside and decoupled outside
- [Architecture of your files matches the architecture of your app](https://www.youtube.com/watch?v=WpkDN78P884&t=7m).

Known topics that are exceptional:

- app: a catch-all topic for your home page, layout, etc
- lib: what isn't part of any topic and should really be published as a reusable module, but too lazy

## What is a type?

> What a module is made of

A type is a grouping of modules that are related by the shape of export, as in how these modules interface with other modules.

Contrary to topics, types are more or less objective and predetermined by `dogstack`.

- sync (helper function that returns value or throws error)
- async (helper function that returns promise)
- type ([`tcomb` type](https://github.com/gcanti/tcomb))
- style ([`fela` rule](http://fela.js.org/docs/basics/Rules.html))
- action ([`redux` action creator](http://redux.js.org/docs/basics/Actions.html))
- reducer ([`redux` reducer](http://redux.js.org/docs/basics/Reducers.html))
- getter ([`reselect` selector](https://github.com/reactjs/reselect))
- component ([presentational](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0))
- container ([data](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0))
- hoc ([higher-order components](https://facebook.github.io/react/docs/higher-order-components.html))
- route ([`react-router`](https://github.com/ReactTraining/react-router) `<Route />`)
- service ([`feathers` service](https://docs.feathersjs.com/services/readme.html))
- migration ([`knex` migration](http://knexjs.org/#Migrations))
- seed ([`knex` seed](http://knexjs.org/#Seeds))

## What is a name?

The name of your export should be **exactly** the name of your default export.

## Common smells

- When a module _feels_ out of place, they probably need a better place.
- When your name contains the topic or type in it, you can leave out the topic or type from the name.
- When you feel the need to make a sub-directory anywhere, you probably need a new topic.
- When you keep using the same word to disambiguate files from those of the same type, it's probably a topic.
- When you talk to other developers on your project using different words than your topics and names, you need better topics and names.
- When you have a "core" topic, or something equally vague, it's probably multiple topics.
- When you have many topics each with a single file in them, you might be seperating too much.
  - Categories should tell us something about what they separate, so if they separate out only one thing it doesn't tell us much..
