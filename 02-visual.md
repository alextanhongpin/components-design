Component UI

> Design should be simple, and that is why it is complicated.


+ Components can be `static` or `dynamic`.
+ Static components are also know as `containers` or `layouts`.
+ Static components are meant for displaying purpose, or holds layout information.
+ Static components can be responsive layouts, wrappers, header-footer-layout, main, aside, split view, list with image, card deck and holders.
+ Styling should be placed in container.
+ Container can hold children component.
+ Children component should fit to the parent container.
+ Standardize the visual design for consistency.
+ Color palette, typography, sizing, grids, positional elements should be standardized.
+ Components should be as dumb as possible.
+ Dumb components holds no business logic.
+ Conditionals should be not have more than two levels of nesting.
+ Use `Factory Pattern` or `State Machine` for handling conditionals.
+ Parse data before passing to the component.
+ Conditionals can be authorization, permissions, empty data checking.
+ Build atomic components, large components are build through composition.
+ There are dynamic views - views that change based on the data that is passed in.
+ Dynamic views handles empty states, normal state, paginated state, loading state, etc.
+ Views have lifecycles - componentWillMount, componentDidMount, componentWillUnmount.
+ Views can be added, removed, or updated from the parent.

