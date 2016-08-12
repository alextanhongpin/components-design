#Introduction to Component Designs

### What are Components?
> Components are predictable elements that produces an **expected output** when a set of **known inputs** are introduced into them. 

E.g. A Twitter Tweetbox

**Known Inputs**: Are the initial states and user actions. In this case, a text with a maximum length of 140 characters, and a click action to submit the tweet.

**Expected Output**: A new tweet is created and added to the list.

### Custom tags

Custom tags are not part of the HTML tags that were proposed from the World Wide Web Consortium (W3C). For the full list (106 native tags), see [here](http://www.w3schools.com/tags/ref_byfunc.asp). With the rise of webcomponents, you can now create your own custom tags.

### Philosophy in Components Design

- Predictable
- Reusable
- Composable
- Accessible
- Usable
- Scalable
- Conventional

### Breakdown

There are three major considerations to be taken in components design:
- **Aesthetic** - Describes the visual of a component, which varies according to the state)
- **Structure & Composition** - Describes how the components are structure and composed from atoms to organism)
- **Behaviour & Actions** - Describes the interaction between users and the components, and the expected outcome from the interaction)


#### Aesthetic

> Design should be simple, and that is why it is so complicated.

Forget what people say about *form over functions*. The user interface and user experience are meant to work together harmoniously. We should not sacrife usability over design, and vice versa. It is possible to have both good user experience and stunning user interface. 

1. Components can be static or dynamic.
2. `Static components` are meant for display purpose only, or holds layouts information.
3. `Dynamic components` are components that users can interact with, and changes according to the state of the application.
4. Components are responsive by default - they fit whatever container width they are thrown into.
5. Layouts are part of `static components`, and are normally responsive grids. Can also be header-footer layout, main, aside, card deck, and list holder.
6. When designing, it is important to extract parts that are reusable early.
7. Standardization in design is important.
8. Color scheme, typography, sizing, layouts, positional properties and styles can be standardized.
9. 

CSS Tips
1. Use a standardized naming pattern like BEM (Block-Element-Modifier) or Atomic CSS to avoid conflicts in classnames.
2. Manage white spaces well.
3. Place positional css (top, left e.t.c) only in the wrapper elements. Placing it in the component will discourage usability, as the components might be rendered differently in different pages.
4. Do not hardcode the width and height - components should fit to parent width.

