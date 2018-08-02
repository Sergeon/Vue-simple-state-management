# Vue-simple-state-management

Simple state management in Vue with provide/inject plus a Vue instance as event emitter 

## Installation

`npm install`

Then:

`npm serve`

To open a local dev server in the 8080 port. This project is built with `vue-cli` 3 so all the vue cli standard commands are available.

## Why this

Sometimes, a vuex store to manage the state of a small application or a related group of components is some sort of an overkill ([or so they say](https://blog.kentcdodds.com/application-state-management-66de608ccb24)).

If you're not using a store, you will need to re-emit a lot of events and pass a lot of props down to long chains of components, which feels awkward and usually forces you to not split your application in components enough.

A way to handle this situation in React is the [context api](https://reactjs.org/docs/context.html). Vue has a similar feature, [provide/inject](https://vuejs.org/v2/api/#provide-inject). Just providing a state object with `provide` solves the prop drilling problem, but provide/inject itself doesn't help to avoid the events re-emitting.

A way to avoid constant event re-emitting is to `provide` a Vue instance that serves as an event emitter (and, in fact, an `EventEmitter` instance will work the same). Instead of emitting and listening to events using `$emit` and `$on` on the components, we emit and listen events from and to a provided Vue instance.
