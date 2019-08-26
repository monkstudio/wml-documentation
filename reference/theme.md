# `<theme>`

> [Node](./node.md) > Theme

This is the default implementation of the [theme_mod](../parsers/theme_mod.md) parser.

Creates or updates a modification setting for the current theme like the logo or header image.

## Attributes

**parser** : 'theme_mod'

## Examples

### Basic Usage:

```
<theme>

    <logo src=./images/logo.svg />

    <header src=./images/penguin.jpg />

    <another_mod>Another theme_mod example</another_mod>

</theme>
```