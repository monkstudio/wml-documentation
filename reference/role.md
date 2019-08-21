# `<role>`

> [Node](./node.md) > Role

This is the default implementation of the [role](../parsers/role.md) parser.

Use this element to define user roles and their included capabilities.

## Attributes

**parser** : 'role'

**caps** : []

The array of capabilities associate with this role. See [add_role](https://codex.wordpress.org/Function_Reference/add_role) for documentation on how to format this attribute.

Note it is recommended to add capabilities as valueless attributes with the '+' modifier.

**display**

Set the title that this role will be displayed as.

## Valueless Attributes

By default, valueless attributes without a modifier will be set as the 'name' attribute.

### Supported modifiers

**+** : Valueless attributes set with the '+' modifier will be added the the role's capabilities array.

**-** : Valueless attributes set with the '-' modifier will be removed from the role's capabilities array.

## Attribute-less Values

If set, the value will assigned as the node's 'display' attribute.

## Examples

### Basic Usage:

This example defines the 'contributor' role with the display name 'Contributor' and assigns the capabilities: 'read', 'edit_posts', 'delete_posts'.

```
<role contributor "Contributor" +read +edit_posts +delete_posts />
```