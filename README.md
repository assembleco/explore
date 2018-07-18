# Building Nimbus from scratch

This document outlines a standard process for building apps.

You can view it as a tutorial of sorts;
if you follow it from start to finish,
you'll have a working Nimbus Point of Sale app.

There are several `TODO`'s sprinkled throughout the document.
They represent things that I'd personally like to follow up on at some point.

## Initialization (Commit 0)

Okay, I'm starting to write the Nimbus app from scratch,
using the best practices I've discovered in the past couple months.

First things first, let's get an app going:

```bash
npx create-react-app nimbus
cd nimbus
yarn
yarn start
```

## Commit 1

Next up, we'll add a few libraries that will make our lives 10000% easier.

```bash
yarn add \
  mobx \
  mobx-react \
  mobx-react-devtools \
  mobx-utils \
  react-app-rewire-mobx \
  styled-components

yarn add -D react-app-rewired
```

And [rewire] our app to support MobX.

[rewire]: https://github.com/timarney/react-app-rewired/tree/master/packages/react-app-rewire-mobx

## Commit 2

We don't need the boilerplate page
that `create-react-app` gives us out of the box,
so let's remove it.

> Note: We're removing `src/registerServiceWorker.js`,
> mostly because we don't really know what it does,
> and this app is an exercise in simplicity.
> It seems like something we should study up on at some point, though.
> TODO: Study up on Service Workers. https://goo.gl/KwvDNy