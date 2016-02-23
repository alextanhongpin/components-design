# Guidelines for Builing Great JavaScript Components

1. **Reusable**. Components should not be designed to be too specific - you might end up creating similar components with different use cases. For example, an ordinary `Dropdown` component might end up rewritten as `DropdownSelect`, `DropdownMultiSelect`, `DropdownWithIcons`. Pass in `options` such as *allowMultipleSelection* or *showIcons* instead when initializing the components. The `Factory`, `Adapter` or `Decorator` pattern could be used to add enhancements to your component.
2. **Isolated**. Each component are standalone components and should have an unique identifier. Any changes in one component should not affect the other component on the same page. For example, toggling a dropdown will not affect the other dropdowns on similar page. Components can interact with one another (data transfer, triggering changes in another component) through the `Observer` pattern.
3. **Data Models** refers to the data input and output of the components. Allow options, usually a Plain Old JavaScript Object (POJO) to be passed in during the initialization of the components. Data that are immutables (private data) should be prefixed with an `_`, and mutable data should be accessible through getters and modified through getters. Methods like `.val()` might be more sensible for returning values that are mutables. In absence of the Data Models, always provide default values.
4. **Validations*. There should be a checking mechanism (possible a method) to validate the data models. Should an invalid data be passed in the components, throw an error with a reasonable error message.
5. **Naming Conventions**. Use clear and concise naming. `Block-Element-Modifier (BEM)` methodology has been proven to be helpful for naming components.
5. **Classes and Ids**. Use `classes` for components that shares the same styling. Use `id` for very specific components (input fields, forms). When binding events to the components, use `js-hooks` instead of `classes`. This will save you the hassle from searching through your JavaScript codes for the `className` that you are no longer using, should you change it in the markup.




Different ways of initializing a component.

1. render the html with the components markup first, then bind the events using js. options can be passed in through html5 data attributes
2. render the html, then upon completion initialize the components using javascript and append the component to the view
