# `<Alias>`

> [Node](./node.md) > [Internal]() > [Construct]() > Alias

This tag is used to defined custom special tags. See documentation on the 'alias' parser for information on supported attributes, as well as how this element is exported. Note that this tag should be defined before other elements that require aliased elements, otherwise WPML may not know that these are aliases and may treat them as generic nodes.

## Attributes

**parser** : 'alias'

**node** : null (required)

## Valueless Attributes

The first attribute without a modifier will be treated as the value of the 'node'. So writing `<alias post >` is the same as writing `<alias node='post' >`.

## Examples

### Create an Element extending the Post node for exporting posts with the post_type 'example'

```
<alias post >

    <example type='example' />

</alias>

<example>

    <title>Hello, Example!</title>

</example>
```