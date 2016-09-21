#### Structure and Compositions

When structuring the component, the following has to be considered:
+ should be able to integrate new features seamlessly
+ should be predictable
+ should not store specific business rules
+ should be KISS, DRY
+ should respect the components lifecycle - mount, unmount, render etc.
+ should be reactive
+ should have dumb views
+ should have an internal HMVC
+ should be isolated (stand by its own)
+ should not contain external dependencies

How should components be structured? It's best to structure them hierachically. I personally like the concept of __Atomic Design Pattern__. 

> Atomic design is methodology for creating design systems. - Brad Frost

The components, as well as the folder structure will have the following levels:

1. Atoms
2. Molecules
3. Organisms
4. Template
5. Pages

The components should have the following lifecycles:
- componentWillMount
- componentWillUnmount
- render
- componentDidMount
- componentShouldUpdate

