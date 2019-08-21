# `<template>`

> [Node](./node.md) > Template

By default embedded markup will not be parsed and registered into the Node Tree and no value will be returned when this element is exported.

As the name implies, this element is intended to have its contents parsed by other elements.

For example, this element will typically be used in conjunction with [Mixin](./mixin.md) elements which insert the template's markup into it's current index within the Node Tree.

Note this element should always be assigned an ID so that it can be referenced by other elements.

## Attributes

**walk** : false

**parser** : 'noop'

## Examples

### Basic usage with `<mixin>`s:

Mixin the contents for multiple posts while using context properties to alter the content for each post.

```
<template id='example_template' >

    <title>{ $title }</title>

    <content md >

        This is my post content for { $title }

    </content>

    <tag>Tag A</tag>
    <tag>Tag B</tag>

    <category>Category A</category>
    <category>Category B</category>

</template>

<post context='title=Post A' >

    <mixin &example_template />

</post>

<post context='title=Post B' >

    <mixin &example_template />

</post>
```