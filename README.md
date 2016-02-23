# Guidelines for Builing Great JavaScript Components

1. **Reusable**. Components should not be designed to be too specific - you might end up creating similar components with different use cases. For example, an ordinary `Dropdown` component might end up rewritten as `DropdownSelect`, `DropdownMultiSelect`, `DropdownWithIcons`. Pass in `options` such as *allowMultipleSelection* or *showIcons* instead when initializing the components. The `Factory`, `Adapter` or `Decorator` pattern could be used to add enhancements to your component.
2. **Isolated**. Each component are standalone components and should have an unique identifier. Any changes in one component should not affect the other component on the same page. For example, toggling a dropdown will not affect the other dropdowns on similar page. Components can interact with one another (data transfer, triggering changes in another component) through the `Observer` pattern.
3. **Data Models** refers to the data input and output of the components. Allow options, usually a Plain Old JavaScript Object (POJO) to be passed in during the initialization of the components. Data that are immutables (private data) should be prefixed with an `_`, and mutable data should be accessible through getters and modified through getters. Methods like `.val()` might be more sensible for returning values that are mutables. In absence of the Data Models, always provide default values.
4. **Validations**. There should be a checking mechanism (possible a method) to validate the data models. Should an invalid data be passed in the components, throw an error with a reasonable error message.
5. **Naming Conventions**. Use clear and concise naming. `Block-Element-Modifier (BEM)` methodology has been proven to be helpful for naming components.
5. **Classes and Ids**. Use `classes` for components that shares the same styling. Use `id` for very specific components (input fields, forms). When binding events to the components, use `js-hooks` instead of `classes`. This will save you the hassle from searching through your JavaScript codes for the `className` that you are no longer using, should you change it in the markup.
6. **Component Lifecycles**. Is the component fetching resources from an API? Use JavaScript ES6 `Promises` to handle asynchrounous responses. The `Observer` patterns can also be used to handle components lifecycle. Some lifecycle includes onComponentMount, onComponentRender, onComponentDestroy, onClick, onStart, onComponentIsLoading, onDataIsLoading, onDataLoadingCompleted, onActionIsNotCompleted (when user clicks somewhere else without completing an action) etc.
7. **Events**. The events is the life of the components. Events such as `click`, `keyup`, `keydown` allow users to interact with the components and modify the data models. Always handle incomplete actions (user not completing a form) or lost focus (user navigates to another component, dropdowns should be closed upon blur).
8. **Graceful Error Handling**. In case of failed Ajax request, always return an error placeholder. For slow request, always set a timeout to prevent users from waiting. Abort the old request should a user sent a new one.
9. **Animation**. Users need a cue on what is happening. Using `fadeIn` for displaying new views and `fadeOut` when removing delete views. Add a disabled state to buttons once user clicks on it, and change the label appropriately. 
10. **Asynchronous Components**. If your components are fetching/modifying data constantly with your API, always ensure that one request is completed before fetching another. Prevent users from firing multiple request at the same time by either using a *dirty flag*, disabling the button or aborting the previous requests.
11. **Events Binding**. When rerendering and binding new events, remember to unbind the previously binded events. The may prevent multiple same events firing. 
12. **Events Delegation**. In JavaScript, it is possible to target a parent container and delegate the events to the children through bubbling. Binding the events every time after rerendering a view can be painful. Event delegation is a graceful way to bind events to new components.
13. **Pure functions**. Components should be designed as pure functions - they should return the results without modifying the input.




Different ways of initializing a component.

1. render the html with the components markup first, then bind the events using js. options can be passed in through html5 data attributes
2. render the html, then upon completion initialize the components using javascript and append the component to the view
