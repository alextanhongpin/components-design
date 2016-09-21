### Behaviours and Actions

_Actions_ are pure functions that are tied to views. They have the minimum information that the **Handlers** require in order to produce a **Behaviour**.

_Handlers_ receives information from the **Actions** and decides what to carry out. They do not have information for neither the view or the models but can produce the next state.

_Behaviours_ are the result of the actions that has been handled. It will usually be a change in the Model which will then be reflected on the View.

Actions and Handlers made up the Controllers in a typical MVC architecture. They contain business logics that will trigger a change in the models(states) and elicit behaviours.

+ Component exposes Actions
+ When user trigger an Action, it will be processed by the Handlers
+ When the Handler produces a successful output, component will elicit Behaviours
+ Example of Actions are `Click`, `Mousedown`, `Hover`, `Drag` etc.
+ Components should only dispatch the Actions, not triggering the Behaviours directly
+ Handlers are usually state machines that are responsible to produce the desired output.
+ Service calls are included in the Handlers.


