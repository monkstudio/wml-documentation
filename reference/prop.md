# `<prop>`

> [Node](./node.md) > [Internal](./internal.md) > [Construct](./construct.md) > Prop

This element is the default implementation of the [prop](../parsers/prop.md) parser.

Populates the current context of the element that this tag is embedded in.

Note that exported properties only affect the parent element and subsequently all of its child elements. Proceeding sibling elements of the parent will not be affected.

Also be aware that because this is a Construct, properties are only exported once the parser reaches that element and therefore will only affect the context for proceeding child elements.

Finally note that Prop elements are immediately removed from the node tree after they are exported. This means that they cannot be referenced by other node, but it also means that `<prop>` tags can safely be embedded in elements like `<select>` or `<loop>` amd they will not be included in their exported values.

## Attributes

**parser** : 'prop'

**walk** : false

## Examples

### Basic Usage

Because the `<prop>` tags in this example are defined in the root, their properties will be defined in the context for all subsequent children in the Node Tree.

```
<prop name=gretting >Hello</prop>
<prop name=user 'Jakki' />

<content>

    { $gretting }, { $user }!

</content>
<!-- Exports: <0/0/content> 'Hello, Jakki!' -->
```

### Embedding Prop elements:

```
<prop name='title' >Parent Page</prop>

<page>

    <title>{ $title }</title> <!-- Exports: 'Parent Page' -->

    <prop name='title' 'Child Page' />

    <page '{ $title }' /> <!-- Exports: 'Child Page' -->

</page>


<node dump >{ $title }</node>
<!-- Exports: <0/1/node> 'Parent Page' -->
```