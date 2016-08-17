#List of Components

Also know as a collection of UI Patterns
Since there are different ways of categorizing the components, I will break them down based on two different aspects:
+ core functionality (getting input, navigation, presentation, layouts, informative)
+ hierachy (typically breaking down the components to the smallest elements and show how they are composed to build larger components)
+ domain specific language (DSL, since the components are designed based on the business rule/user story, they can vary. E.g. for Social Media, Finance, etc)


## Categorized by Core Functionality

1. **Navigational**. Responsible for user navigation thoughout the app/web. 
2. **Selection**. Allow users to make selection, such as when applying filters to a result, or selecting date from a datepicker.
3. **Presentational**. Responsible for displaying list or group of datas, charts and tables. 
4. **Layouts**. Responsible for the page layouts and determining how the children components will fit into the layouts.
5. **Getting inputs**. Responsible for acquiring data from users, in the form of form (pun intended) and inputs, and other means.
6. **Informative**. Responsible for displaying information to users such as errors and toasts.

### Navigation
+ Accordion
+ Alphanumeric Filter Links
+ Breadcrumbs
+ Navigation Bar
+ Pagination
+ Tabs
+ Search
+ Menu
+ Tag Cloud
+ Categories/Subcategories
+ Home Link


### Layouts
+ Grid layout
+ Header-footer
+ Main
+ Section
+ Aside
+ Card
+ List
+ Backdrop
+ Popup

### Informative
+ Cursor
+ Tooltip
+ Animation
+ Progress Bar
+ Charts
+ Info
+ Alert
+ Confirm
+ Placeholders/Empty states
+ Icons
+ Notifications
+ Onboarding
+ Table
+ Slideshow
+ Gallery
+ Lightbox
+ Dashboard
+ FAQ

### Getting Input
+ Drag and drop
+ Forms
+ Input
+ Label
+ Datepicker
+ Timepicker
+ Radio
+ Checkbox
+ Select
+ Dropdown
+ Combobox


## Categorized by Hierachy

This way of categorization is based on the Atomic Design Pattern. 

### Atoms
Atoms are the simplest building block that is required to make up large components. They can be composed from one or more elements. Aside from components, they can also be colour palette, utils or layouts and higher-order-components. 

+ Button
+ Break
+ Card
+ Checkbox
+ Close
+ Dropdown
+ Factory
+ Hint
+ Icon
+ Photo
+ Input
+ Jumbotron
+ Label
+ Menu
+ Modal
+ Paging
+ Radio
+ Rating
+ Select
+ Spinner
+ Tag
+ Thumbnail
+ Tooltip
+ Wrapper

### Molecules
Molecules are a group of atoms, usually meant to serve a specific purpose. They are made through recipes:

+ Card + DarkTheme = DarkCardTheme
+ Input + Label = InputWithLabel
+ Icon + Tooltip = IconWithTooltip
+ List + GridColumn = GridList
