#Introduction to Component Designs

### What are Components?
> Components are predictable elements that produces an **expected output** when a set of **known inputs** are introduced into them. 

Components can be static (mainly responsible for presentations) or dynamic (users can interact with the component). They can be futher classified based on the patterns and usage they provide. Some common patterns includes: 

+ **Navigational**: Provides navigation and links to other pages.
+ **Selection**: Allow users to choose a predefined data.
+ **Getting inputs**: Often associated with forms, they require users to enter data.
+ **Presenting data**: Tables, charts, lists presents data to users.



### Native and Custom components

There are three major platforms - iOS, Android and Web. For every platform there are a list of predefined components. While they share different naming, their usage is similar (Textfield in iOS vs <input/> in HTML). Conform to the standard practice by using native components when possible and avoid creating new standards. 

Why design custom components? One word - experience. Component plays an important role in delivering the right experience on the web. Custom components are components tailored to deliver certain experience to the users. Visual branding is important. It's hard not to recognize Facebook from its famous `Like Button`, or Google's `Search Box`. Let's take a look at other examples:

**Airbnb, Foursquare, GoogleMap** - Location-based applications that relies heavily on a map to help users search/navigate through results in a particular area.

**Facebook, Twitter** - Social media components such as news feed, chat, etc to help users stay connected with one another.

**Medium, Quora** - Delivers the writing and reading experience on the web.

**Tumblr, Deviantart, Behance, Instagram** - Components that focuses on displaying images.

**Jira, Github** - Enterprise components.

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
