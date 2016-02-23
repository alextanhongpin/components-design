# Guidelines for Builing Great JavaScript Components

1. **Reusability**. Components should not be designed to be too specific for a particular use case - you will end up creating similar components with different use cases. For example, an ordinary `Dropdown` component might end up rewritten as `DropdownSelect`, `DropdownMultiSelect`, `DropdownWithIcons`. Pass in `options` such as *allowMultipleSelection* or *showIcons* instead when initializing the components.
