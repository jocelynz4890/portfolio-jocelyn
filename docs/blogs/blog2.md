---
title: Reactive Frameworks
layout: doc
---

# More Vue stuff
because I was ~~procrastinating on A4~~ inspired to read Vue documentation after lecture

## @ is short for v-on
The [Vue docs](https://vuejs.org/guide/introduction.html) use the `@` directive a lot. It turns out this is just shorthand for `v-on`, so the form input example from lecture would just be 
```ts
<input @input="event => message = event.target.value">
```

## Computed properties
Computed properties are useful for factoring logic, specifically logic that involves reactive data (data that should update the UI when it changes, aka refs), out into a separate function to DRY out your code and to be able to use that same logic elsewhere.

In order to use this, we create a ref and assign it to a computed value as we saw in lecture. Then, any bindings that depend on this ref will be automatically recomputed when any of the ref's dependencies (other refs that are used in the function we pass into `computed`) update.

`computed` takes a getter function that by default can't set any values (you'll get a runtime warning if you try to assign new values to a ref). To get around that, you can also give it a setter.

To access the previous state of a ref, we can use the `previous` argument of the getter.
```ts
const someRef = computed((previous) => return previous);
```

## Watchers are event listeners
Whenever a reactive state changes, we might want to execute a piece of code as a side-effect of the state change. We do this by using watchers, which take a ref (or an array of refs, reactive objects, and other things that involve a reactive state) and a callback. Whenever the state of the ref changes, the watcher triggers the callback.

```ts
watch(refName, async(newRefValue, oldRefValue) => { 
    // logic to update some other refs
})
```

## Lifecycle
![](/vue.png){:width='500'}
Source: [Vue docs: Lifecycle Hooks](https://vuejs.org/guide/essentials/lifecycle.html)

This chart shows the states that a component goes through, from initialization to dismount (when it is removed from the DOM). As an example, the reactive state changes that we looked at during lecture through changing the form inputs happened after the form components mounted (added to DOM and rendered). Then every time we change the form inputs, the form component would go through the update cycle to re-render and display that update to us. 

Vue provides **[hooks](https://vuejs.org/api/composition-api-lifecycle.html)** which allow us to basically intercept the state of the component at a certain stage in the lifecycle. For example, `onUpdated()` takes a callback that will be called when the component that it is in updates its DOM tree.