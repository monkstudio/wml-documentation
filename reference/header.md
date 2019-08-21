# `<header>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > [File](./file.md) > [Img](./img.md) > Header

This element is the default implementation of the [`header_image`](../parsers/header_image.md) parser.

Use this tag to set the header image for the current theme.

Unlike other tags used as a theme_mod, `<header>` does not need to be embedded in the `<theme>` tag in order to work, but you can anyway if you want to keep all theme_mod settings grouped together.

## Attributes

**name** : 'header_image_id'

**parser** : 'header_image'

## Examples

### Basic Usage:

```
<header src=./images/penguin.jpg />
```