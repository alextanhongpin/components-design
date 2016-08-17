#Introduction to Component Designs

### What are Components?
> Components are predictable elements that produces an **expected output** when a set of **known inputs** are introduced into them. 

The three major platform - iOS, Android and Web has their own list of predefined components. Given that such components already exists, why do we still need to create custom components?

> Custom components are components tailored to deliver certain experience to the users.

Visual branding is important. It's hard not to recognize Facebook from its famous `Like Button`, or Google's `Search Box`. Let's take a look at other examples:

**Airbnb, Foursquare, GoogleMap** - Location-based applications that relies heavily on a map to help users search/navigate through results in a particular area.

**Facebook, Twitter** - Mostly social media components that encourages users to share, connect and communicate with others.

**Medium, Quora** - Delivers the writing experience on the web through their editor.

**Tumblr, Deviantart, Behance, Instagram** - Focuses on images (display, edit) 

### Philosophy in Components Design

- Predictable
- Reusable
- Composable
- Accessible
- Usable
- Scalable
- Conventional
- Consistent
- Productive

### Breakdown

There are three major considerations to be taken in components design:
- **Visual Aesthetic** - Describes the visual of a component, which varies according to the state)
- **Structure & Composition** - Describes how the components are structure and composed from atoms to organism)
- **Behaviour & Actions** - Describes the interaction between users and the components, and the expected outcome from the interaction)

#### Visual Aesthetic

> Design should be simple, and that is why it is so complicated.

While it is important to have a design that impresses users, it's more important to have a usable interface. This fact remains:

> People ignore design that ignores people. 

Let's apply Pareto's principle (80/20 rule) here. 80 percent of user experience are made up of 20 percent of the component's usability. The remaining 20 percent comes from the presentation. We should not sacrifice usability over design, and vice versa. It is possible to have both good user experience and stunning user interface.

1. Components can be static or dynamic.
2. `Static components` are meant for display purpose only, or holds layouts information.
3. `Dynamic components` are components that users can interact with, and changes according to the state of the application.
4. Components are responsive by default - they fit whatever container width they are thrown into.
5. Layouts (a.k.a `Containers`) are part of `static components`, and are normally responsive grids. Can also be header-footer layout, main, aside, split view, list with image, card deck, and list holder.
6. If the layout contains a card for example, throw all the styling information in the layout. Try to reduce the styling on the children component, as they are less reusable. 
6. When designing, it is important to extract parts that are reusable early.
7. Standardization in design is important.
8. Color scheme, typography, sizing, layouts, positional properties and styles should be standardized. Together they make up the visual brand of a company/product.
9. Dumb views - views should be as dumb as possible. They should not be handling any business logic. Views can however dispatch user actions. 
10. Do you need to deal with a lot of conditionals (if else, with multiple conditions)? Throw the conditionals in the parent and let them decide which view to render. But avoid coupling it with the view that is responsible for displaying the data.
11. Need to parse the data before rendering? Do that in the parent, but do not couple it with the component.
12. Some conditionals present are authorization, empty data, new state, permissions to view etc. The views that will be rendered depends on the conditions present. The `State Machine` design pattern can be implemented here.
13. Breaks views down to the smallest possible elements, and compose them to build larger components. 

CSS Tips

1. Use a standardized naming pattern like BEM (Block-Element-Modifier) or Atomic CSS to avoid conflicts in classnames.
2. Manage white spaces well.
3. Place positional css (top, left e.t.c) only in the wrapper elements. Placing it in the component will discourage usability, as the components might be rendered differently in different pages.
4. Do not hardcode the width and height - components should fit to parent width. This makes the component reusable and responsive, since it does not hold a fixed width or height. They will only adapt to the parent layout.
5. Do not mix vertical and horizontal spacing together. Instead of applying padding (20px 10px), set a custom `<BR/>` with height 20px, and then set a layout with padding left and right to equal 10px. This will eliminate a lot of issues for the layout. Use classes such as `.break` or `.p-10px` (refers to padding left and right 10px, since the vertical spacing is separated). 
6. When toggling, do not just show or hide. Instead, unmount the component directly. The same applies for switching tabs (or basically swapping views).
7. Store only presentational information in classes. Avoid using ids for styling unless it is a layout. When binding actions to classes, use js-hooks instead. Do not share the presentational and actionable class names. 



