# `<select>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > Select

This is the default implementation of the [to_array](../parsers/to_array.md) parser.

This element will export an array containing the exported values of each embedded child.

## Attributes

**parser** : 'to_array'

## Examples

### Basic Usage:

This example exports an array of post ids and saves it as metadata of the parent `<page>` element.

```
<page>

    <title>Featured Posts</title>

    <select name="assigned_posts" >

        <post>

            <title>First Post</title>

        </post>

        <post>

            <title>Second Post</title>

        </post>

    </select>

</page>
```