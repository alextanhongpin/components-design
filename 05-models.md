### Models

+ Models, (a.k.a. states/options/defaults) are the inputs that your component consumes.
+ Since there are many different names, we are defining the purpose for each here.
+ Models stored by the root component are called states.
+ Models that are obtained from the parent component are called props.
+ Components can have default models.
+ Children components should not have states.
+ Components can have nested components.
+ The parent component will contain the children component.
+ Components will initialize a default model (good defaults pattern) if no inputs are passed to them.
+ Example of good defaults are placeholder image, empty arrays, zero values or plain null object.
+ Components should throw error when the models are invalid.
+ Models should have standardized schema.
+ Model keys should not be too specific.
+ Components accepts inputs and produces outputs.
+ Output will equal input in unmodified state.
+ Output are input models that has undergone transformation/mapping through user's Actions
+ Different Actions will cause the output to be different.
+ If the actions are incomplete (user clicks outside dropdown before selecting etc), the output will be equal to the last modified output
(InputFallback).
+ In some cases, the output can be reverted to the previous output (Undo)
+ Models should carry out validations for input/output.
+ Components can have restrictions to certain data fields too.
+ Restriction includes acceptsArrayOnly, acceptsIntOnly, minLength, maxLength, etc.
+ Components should obey the show, don't tell policy.
+ Tooltips, Hint are a good way of telling users what inputs are required.
+ Components should be descriptive - usage and example required inputs/produced outputs.
+ The flow of data from parent to children components are called data-flow.
+ There are several data flow patterns including two-way data-binding, unidirectional data-flow, redux and flux.
+ Models should be consistent so that logics can be shared. (e.g. for Pagination)
+ HMVC (Hierachical-Model-View-Controller) is a good way of controlling dependencies between components.
+ HMVC encourages composition over inheritance.
+ Components handles errors gracefully.
+ Components are dumb - they display data based on the models they received.
+ Models should be parsed before entering the components, not within. (Sharing components with different inputs will cause an issue)
+ Presentation components should handle empty inputs (by displaying placeholder)
+ Within a component, there is a state machine which handles conditionals (can also be extracted outside)
+ Components decides what to render based on the models.
+ Components can throw confirmation under certain circumstances.
+ E.g. User did not complete a required action,
+ User navigates to another page
+ User changes focus to another section or component
+ User wants to delete something
+ User aborts an incomplete action(editing, posting)
+ E.g. Models = isValidated, isEmpty, isLoaded
+ E.g. Actions = isInitialized, isInProgress, isCompleted


#### Handling empty states
+ Components are just a state machine - they render the views based on the models that are present.
+ Different states will affect the views that will be rendered. 
+ Treat component states like behaviours - when you are angry, your face will be red and you'll frown. When you are sad, you will cry and tears will flow.

### Factory Pattern
+ Suitable for handling different instances of a component (E.g. Button100, Button200, Button300, H1, H2, H3).
+ Decides what instances of a component to render dynamically. 
+ ButtonFactory produces Button100, Button200, Button300.

### State Machine
+ Decides what view to render based on the current model.
+ EmptyState -> Display placeholder
+ WithData -> Display content
+ WithALotOfData -> Show paginated content
