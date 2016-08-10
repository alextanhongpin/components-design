#List of Components

Also know as a collection of UI Patterns
Since there are different ways of categorizing the components, I will break them down based on two different aspects:
+ core functionality (getting input, navigation, presentation, layouts, informative)
+ hierachy (typically breaking down the components to the smallest elements and show how they are composed to build larger components)
+ domain specific language (DSL, since the components are designed based on the business rule/user story, they can vary. E.g. for Social Media, Finance, etc)


## Categorized by Core Functionality
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
+ Hint
+ Icon
+ Photo
+ Input
+ Jumbotron
+ Label
+ Menu
+ Modal
+ Paging
+ Rdio
+ Rating
+ Select
+ Spinner
+ Tag
+ Thumbnail
+ Tooltip
+ Wrapper

### Molecules
Molecules are a group of atoms, usually for a specific purpose. 

+ Input + Label = InputWithLabel
+ Icon + Tooltip = IconWithTooltip
