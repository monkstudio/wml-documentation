# `<tag>`

> [Node](./node.md) > [Term](./term.md) > Tag

Alias of [Tag](./term.md) for inserting Tag terms into the target WordPress context.

For example, writing:

```
<tag>Example</tag>
```

Is the same as writing:

```
<term taxonomy='post_tag' >Example</term>
```

## Attributes

**taxonomy** : 'post_tag'

## Examples

### Basic Usage:

```
<post>

    <title>Hello, World</title>

    <tag>Tag A</tag>
    <tag>Tag B</tag>

</post>
```