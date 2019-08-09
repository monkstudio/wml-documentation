# `<frontpage>`

> [Node](./node.md) > [Post](./post.md) > [Page](./page.md) > Frontpage

This element is a shorthand way of setting the home page for the current WordPress site.

Note that this element is assigned the ID of 'frontpage' by default for easier referencing by other elements.

## Attributes

**option** : 'page_on_front'

**id** : 'frontpage'

## Examples

### Creating the front page and a menu item linking to it:

```
<frontpage>

    <title>Welcome to my site</title>

</frontpage>

<show_on_front option 'page' />

<menu location='primary' >

    <menuitem &frontpage >Home</menuitem>

</menu>
```