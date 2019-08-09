# `<mixin>`

> [Node](./node.md) > [Internal](./internal.md) > [Construct](./construct.md) > [Splice](./splice.md) > Mixin

This is the default implementation of the [mixin](../parsers/mixin.md) parser.

Similar to mixin functions found in CSS pre-processors like SASS, this element will interpolate the inner markup of another element that it is linked to into its parent's body where the `<mixin>` tag is located.

The 'link' attribute must be set with the ID of the element to mix-in, or alternatively a valueless attribute with the '&' modifier.

Note only the inner markup of a linked element will be imported.

## Attributes

**parser** : 'mixin'

## Examples

### Basic Usage:

```
<template id='terms-template' >

    <tag>Tag A</tag>
    <tag>Tag B</tag>

    <category>Example</category>

</template>

<post>

    <title>Post A</title>

    <mixin link='terms-template' />

</post>

<post>

    <title>Post B</title>

    <mixin &terms-template />

</post>
```