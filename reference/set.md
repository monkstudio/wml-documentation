# `<set>`

> [Node](node.md) > [Internal](internal.md) > [Construct](construct.md) > [Splice](splice.md) > Set

This element is the default implementation of the [`Set`](../parsers/set.md) parser. All embedded children will be decorated with attributes set on this tag.

You can use this element to bulk assign attributes that would otherwise be duplicated across a set of elements, e.g. the 'type' attribute on a collection of `<post>` elements.

Note that this element extends [Splice](./splice.md), which mean child nodes will be exported as children of the `<set>`'s parent node.

## Attributes

**parser** : 'set'

**walk** : false

## Examples

### Basic Usage:

Assign the post_type 'example' to a group of `<post>` elements.

```
<set type='example' >

    <post>

        <title>Example One</title>

    </post>

    <post>

        <title 'Example Two' />

    </post>

    <post 'Example Three' />

</set>
```