---
layout: default
title: "Getting Started"
permalink: /getting-started/
---

# Getting Started - [Client apps](#client-apps) <!-- omit in toc -->
  - [Browser Support](#browser-support)
- [Client apps](#client-apps)
  - [Browser Support](#browser-support)
- [Getting started](#getting-started)
  - [VueJS](#vuejs)
  - [Javascript](#javascript)
  - [Styles](#styles)
  - [Firebase](#firebase)
    - [Realtime database and Cloud Firestore](#realtime-database-and-cloud-firestore)
    - [Firebase auth](#firebase-auth)
    - [Firebase cloud functions](#firebase-cloud-functions)
  - [Sentry](#sentry)
  - [Algolia](#algolia)
  - [Slack](#slack)
  - [Daily standup](#daily-standup)
  - [IDE/Code editor](#idecode-editor)

View live: https://dascosales.github.io/dascosales-development-guide/

## Client apps
The client apps are Single-Page Applications built with Vue.js and Vuetify and interacting with the firebase backend over Firebase SDK.

[Vue.js](https://vuejs.org) is a Javascript framework which provides data binding and component-based approach to building SPA apps.  

[Vuetify](https://vuetifyjs.com) itself works on top of Vue.js. It has a rich collection of UI Components.  

Other libraries used: 
* [Vue CLI](https://cli.vuejs.org/) - the official cli for Vue.js
* [Vuex](https://vuex.vuejs.org) - the official state management library for Vue.js
* [Vue router](https://router.vuejs.org) - the official router for Vue.js
* [Firebase SDK](https://firebase.google.com/docs/reference/js) - the official direbase sdk library for Javascript

### Browser Support
Any customer-facing app has to support IE 11 and Edge. All apps for Daughtridge Sales team members can be developed to be used on a modern desktop, tablet , or mobile browser (i.e. Chrome, FF, etc)

## Getting started
### VueJS
First of all, make sure you read the official Vue.js [style guide](https://vuejs.org/v2/style-guide).
It’s a great reference to avoid common errors and anti-patterns.

It is also important to understand how Vue.js Single File Components work. Please see [single file components documentation](https://vuejs.org/v2/guide/single-file-components) for more information.

### Javascript
[StandardJS](https://standardjs.com) is our Javascript code style of choice for this project.
Note: Most of the latest ES6 / ES7 features are available within the project and can be used safely thanks to Babel, which takes the Javascript code and transpiles it into ES5 supported by all major browsers.

### Styles
SCSS is supported for better flexibility.    
To prevent naming collisions, styles are usually scoped to a component.  
To add global styles use `assets/styles` folder.  
*Note: By default, Vuetify offers a great collection of CSS helper classes, which means that there is no need to add custom styles in most cases.*

### Firebase
We use the following firebase products:
- [Realtime database](https://firebase.google.com/docs/database)
- [Cloud Firestore](https://firebase.google.com/docs/firestore)
- [Firebase auth](https://firebase.google.com/docs/auth)
- [Firebase cloud functions](https://firebase.google.com/docs/functions)

#### Realtime database and Cloud Firestore
`Realtime Database` is the first version of Firebase NoSQL cloud database. We use it for old data.  
`Cloud Firestore` is the new version of Firebase NoSQL cloud database. It is preferable to use Cloud Firestore for new collections.
#### Firebase auth
We use the email/password authentication mechanism.

#### Firebase cloud functions
We use cloud functions to do the action we can't perform on frontend side (like sending emails, calculate prices, update some models from backend, etc). We use `javascript` as a functions language.  
There are 3 main types of functions:
- triggers - called from firebase side after some action
- callable functions - called using firebase sdk
- HTTP functions - can be called via http request. Callable functions are preferable but in some situation, it is impossible to implement logic using callable functions

### Sentry
Sentry is used for monitoring of errors on production applications. Integrated with `slack`. More details about `Vue.js` + `Sentry` integration can be found in [official sentry.io documentation](https://docs.sentry.io/platforms/javascript/vue/).

It is a bad practice to log any issues to the console on deployment. If there is a specific error that you would like to have additional info or messages for you can send it to Sentry in the callback instead of a `console.log`.

### Algolia
Aloglia is a search indexing tool that allows for us to create customized searches, handle types and deliver a specifc set of filterable props to large lists of data and items.

It is primarily used in the product search portion of DascoSales.com.

[Daughtridge Sales Algolia Docs](Algolia)

### Slack
We use `slack` as the main messenger. Our main channels are: 
* `dev` - used for general team conversations
* `dev-daily` - used for daily digital standup
* `dev-github` - used for github integration
* `dev-sentry` - used for sentry integration

### Daily standup
We use `slack` for daily standups. Just chat message into `dev-daily` channel in the format:
```
[YYYY-MM_DD] (0800-1700) // [Date] (Local Time)
1. What have you completed since the last meeting?
2. What do you plan to complete by the next meeting?
3. What is getting in your way?
```

### IDE/Code editor
`Visual Studio Code` is a primary code editor for our team. Though most linting is handled in configs, we have some `VS Code` specific settings in some projects. Also by using `VS Code` as the primary editor we can Live Share code easier.  
You can use any preferable ide/editor.