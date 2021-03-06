# Guidelines for Building Great JavaScript Components


### Reusable 
+ Breakdown components into smaller parts to increase reusability.
+ Each component should do one thing, and do it well
+ Which parts of the components are reusable - behaviours and style
+ Behaviours can be extracted by building higher-order-components
+ Styles can be shared by sharing similar CSS className
+ Components can have different styling but share the same logic
+ Standardize the models that components accepts to promote reusability
+ Serving a `specific` purpose and serving a `general` purpose are two different thing. Specific purpose: A dropdown that display a list of countries. General purpose: A dropdown displaying a list of items (variable), with keyboard navigation. 
+ In components, there are `variables` and `constants`. Your models should be the variable, and the component behaviours should be constant (See example above) 
+ Components should not be designed to be too specific - you might end up creating similar components with different use cases. E.g, an ordinary `Dropdown` component might end up rewritten as `DropdownSelect`, `DropdownMultiSelect`, `DropdownWithIcons`. 
+ Pass in `options` such as *allowMultipleSelection* or *showIcons* instead when initializing the components. The `Factory`, `Adapter` or `Decorator` pattern could be used to add enhancements to your component.


### Atomic Design pattern
+ Break components into smaller parts - atoms, molecules, organisms, template and pages.
+ Split components by roles.
+ Build larger components by composition rather than inheritance.

### Isolated
+ Components are unique
+ Components can share the same styling, but have different logic implemented within (different states due to permissions)
+ Each component are standalone components and should have an unique identifier. 
+ Any changes in one component should not affect the other component on the same page. E.g, toggling a dropdown will not affect the other dropdowns on similar page. 
+ Components can interact with one another (data transfer, triggering changes in another component) through the `Observer` pattern.

### Data Models
+ Data Models refers to the data input and output of the components. 
+ Allow options, usually a Plain Old JavaScript Object (POJO) to be passed in during the initialization of the components.
+ Data that are immutables (private data) should be prefixed with an `_`, and mutable data should be accessible through getters and modified through getters. 
+ Methods like `.val()` might be more sensible for returning values that are mutables. 
+ In absence of the Data Models, always provide default values.
+ Components should not hold states
+ Components should only receive states from the parent
+ Build dumb components for a smarter system
+ Data models should be standardize so that the components are reusable
+ Data models should be validated
+ Components should be able to handle whatever data that is passed in to them (paginated data, normal state, empty state)
+ Components will receive a set of known inputs.
+ If you need to parse the model that will be passed in to the components, do it externally - do not let the components parse the model. This will increase specificity and reduce the reusability of the components.

### Validations
+ There should be a checking mechanism (possible a method) to validate the data models. 
+ Should an invalid data be passed in the components, throw an error with a reasonable error message.

### Naming Conventions 
+ Use clear and concise naming. 
+ `Block-Element-Modifier (BEM)` methodology has been proven to be helpful for naming components.
+ Atomic CSS can also be implemented.
+ Separate naming for fonts, layouts, positioning css, and js-hooks.

### Classes and Ids
+ Use `classes` for components that shares the same styling. Use `id` for very specific components (input fields, forms). 
+ When binding events to the components, use `js-hooks` instead of `classes`. 
+ This will save you the hassle from searching through your JavaScript codes for the `className` that you are no longer using, should you change it in the markup.

### Component Lifecycles
+ Is the component fetching resources from an API? Use JavaScript ES6 `Promises` to handle asynchrounous responses. 
+ The `Observer` patterns can also be used to handle components lifecycle. 
+ Some lifecycle includes onComponentMount, onComponentRender, onComponentDestroy, onClick, onStart, onComponentIsLoading, onDataIsLoading, onDataLoadingCompleted, onActionIsNotCompleted (when user clicks somewhere else without completing an action) etc.

### Events
+ The events is the life of the components. 
+ Events such as `click`, `keyup`, `keydown` allow users to interact with the components and modify the data models. 
+ Always handle incomplete actions (user not completing a form) or lost focus (user navigates to another component, dropdowns should be closed upon blur).

### Graceful Error Handling
+ In case of failed Ajax request, always return an error placeholder. 
+ For slow request, always set a timeout to prevent users from waiting. 
+ Abort the old request should a user sent a new one.

### Animation
+ Users need a cue on what is happening. 
+ Using `fadeIn` for displaying new views and `fadeOut` when removing delete views. 
+ Add a disabled state to buttons once user clicks on it, and change the label appropriately.
+ Animation when displaying data.
+ Animation when data is deleted.
+ Animation when new data is added.
+ Animation when data is updated.

### Asynchronous Components
+ If your components are fetching/modifying data constantly with your API, always ensure that one request is completed before fetching another. 
+ Prevent users from firing multiple request at the same time by either using a *dirty flag*, disabling the button or aborting the previous requests.
+ When submitting a form, remember to disable all fields and buttons when sending to the server.

### Events Binding
+ When rerendering and binding new events, remember to unbind the previously binded events. 
+ Events that are binded repeatedly will execute multiple times.
+ Events should be easily mounted/unmounted

### Events Delegation
+ In JavaScript, it is possible to target a parent container and delegate the events to the children through bubbling. 
+ Binding the events every time after rerendering a view can be painful. 
+ Event delegation is a graceful way to bind events to new components.

### Pure functions
+ Components should be designed as pure functions - they should return the results without modifying the input.

### Freeze/Unfreeze Components
+ Each component functionalities can be enabled/disabled through a private method. 
+ This enables a greater control over the component or two interacting components (For example, two datepickers for picking a startDate and endDate. 
+ The endDateDatepicker should be disabled first, as the user have not selected the start date. 
+ It should be reenabled with the start date as the min date that can be selected).

### Debouncing/Throttling
+ Limit the amount of JavaScript you are executing based on DOM events for performance reasons using debouncing and throttling.

### Responsive UI
+ The UI should adapt to different screen sizes. 
+ The display on mobile should be touch intuitive, in contrast to the click intuitive and keyboard navigable components on the desktop.

### WAI-ARIA for Desktop Components
+ Improve the accessibilities of your components (keyboard navigable, screen reader) for users with disabilities).


### Documentation
+ Last but not least, a well documented component will help users understand how to use your component better. 
+ Provide use cases and examples using `.help()` method, or prepare a link to an online documentation.

### Living Components

A concept that bridges UI and UX together. Living components are components that ...

### Remove Unused Views

Do not use CSS to hide views - always remove them. Views such as `alert box`, `modal popups`, and `tab panels` should be destroyed, even if they have contents that required ajax calls to populate the view. For views such as `tab panels`, you can use a client side `router` to determine what subviews to display. 

### Displaying Data
+ Components are meant to display data - if there are no data returned, use a placeholder
+ Placeholders can be a simple text, or a call-to-action leading to another view
+ When fetching a data through Ajax, display a loading placeholder
+ When the Ajax call returns an error, display a retry placeholder
+ There are limited items that can be displayed - so limit the results and show a load more button or infinite scrolling

#### Bonus
There are two ways to initialze a component.

1. Render the html with the component's markup first, then bind the events using JavaScript. Options can be passed in the markup through html5 data-attributes.
2. Render the html, then upon completion initialize the components using JavaScript and append the component to the current view.
