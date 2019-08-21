# `<page>`

> [Node](./node.md) > [Post](./post.md) > Page

This element is an alias of [Post](./post.md) as a shorthand for inserting 'page' post-types.

## Attributes

**type** : 'page'

## Examples

### Basic Usage:

```
<page>

    <title>Example Page</title>

    This is a simple page example.

</page>
```

### Create child pages:

```
<page>
    <title>Parent Page</title>

    <page>

        <title 'Child Page 1' />

    </page>

    <page 'Child Page 2' />

</page>
```

### Assigning a page template:

```
<page template=templates/contact.php >

    <title 'Contact Me' />

</page>
```