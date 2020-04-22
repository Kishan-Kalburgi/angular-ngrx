# NgRx Introduction

## Actions
```
In the store object, you have a function to dispatch (trigger) actions. Actions are classes that implemenets the NGRX Action interface. These Action classes have two properties (let's take as an example an action class called GetUserName):

type: it’s a read only string describing what the action stand for. For example: ‘[User] Get User Name’

payload: the type of this property depends on what type of data this action needs to send to the reducer. In the case of the previous example, is going to be a string containing the user name. Not all actions needs a payload.
```

## Reducers
```
Reducers are pure functions accepting two arguments, the previous state and an Action. When an Action is dispatched ngrx goes through all the reducers passing as arguments the previous state and the Action, in the order that the reducers where created, until it finds a case for that action.
```

## Effects
```
Effects, on the ngrx libraries ecosystem, allow us to deal with side-effects caused from dispatching an action outside angular components or the ngrx store.

The Effects listen if any action is dispatched, then, similar to what reducers do, it checks if the action is one of the actions type it has a case for.

Then is going to perform a side-effect, usually getting or sending data to an API.

Finally is going to emit another action, usually, an action referring to the result-state of the side effect (success, error, etc), then a reducer is going to enter in the scene as we already mention in the ngrx flow.
```

## Selectors
```
As we mentioned before the state tree can become quite a big object, it doesn’t make sense to have all that object on places where we only need part of it.

NGRX store provides us the function “select” to obtain slices of our store. But what if we need to apply some logic to that slice before using the data in the components.

There is where selectors take action. They allow us to decouple any state slice data transformation from the components. The store “select” function accepts an an argument a pure function, this pure function is our selector.
```

## Store
```
A store is an object (an instance of the ngrx Store class) that brings the things we mentioned before (Actions, Reducers, Selectors) together. For example, when an action is dispatched (using the store object dispatch function), the store is the one finding and executing the appropriate reducer.
It is also the one holding the application state.
```# angular-ngrx

