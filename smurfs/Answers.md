1. What problem does the context API help solve?

Enables us to share specific forms of data across all levels of the application. It's aimed at solving the problem of prop drilling.

2. In your own words, describe `actions`, `reducers` and the `store` and their role in Redux. What does each piece do? Why is the store known as a 'single source of truth' in a redux application?

The state of your whole application is stored in an object tree within a single store. A single state tree also makes it easier to debug or inspect an application; for a faster development cycle. 

The only way to change the state is to emit an action, an object describing what happened.This ensures that neither the views nor the network callbacks will ever write directly to the state. Instead, they express an intent to transform the state. Because all changes are centralized and happen one by one in a strict order. As actions are just plain objects, they can be logged, serialized, stored, and later replayed for debugging or testing purposes.

To specify how the state tree is transformed by actions, you write pure reducers. Reducers are just pure functions that take the previous state and an action, and return the next state. Remember to return new state objects, instead of mutating the previous state. You can start with a single reducer, and as your app grows, split it off into smaller reducers that manage specific parts of the state tree. Because reducers are just functions, you can control the order in which they are called, pass additional data, or even make reusable reducers for DRY tasks.

In React-Redux applications, when your Redux is a single source of truth, it means that the only way to change your data in UI is to dispatch redux action which will change state within redux reducer. And your React components will watch this reducer and if that reducer changes, then UI will change itself too. But never other way around, because Redux state is single source of truth.

3. What is the difference between Application state and Component state? When would be a good time to use one over the other?

The difference is that application state is global, and component state is local.  Redux, use what is called  "stores" to hold application state. That means any component, anywhere in the app can access it (kind of like a database) so long as they hook into it.

Component state however, lives within that specific component. As such, it can only be updated within that component and passed down to its children via props.

4. Describe `redux-thunk`, what does it allow us to do? How does it change our `action-creators`?

Redux Thunk is a middleware that lets you call action creators that return a function instead of an action object. That function receives the store's dispatch method, which is then used to dispatch regular synchronous actions inside the body of the function once the asynchronous operations have been completed.

5. What is your favorite state management system you've learned and this sprint? Please explain why!

Redux ! Because it makes easier to debug an application. By logging actions and state, it is easy to understand coding errors, network errors and other forms of bugs that might come up during production. It is easy to test Redux apps as functions used to change the state of pure functions.
