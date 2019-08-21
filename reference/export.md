# `<export>`

> [Node](./node.md) > [Meta](./meta.md) > [Field](./field.md) > Export

This element is the default interface for the [export](../parsers/export.md) parser.

The element will export the value of another node that it is linked to.

Note that the position of nodes being referenced generally does not matter; `<export>` tags can be placed before the node it is linked to.

## Attributes

**parser** : 'export'

## Examples

### Basic usage:

```
<!-- Exports: 'Hello, World' -->
<export link='export' />

<node id='export' >Hello, World!</node>
```

### Shorthand for converting a node to export the value of another node using the '=' modifier:

```
<node =example />

<node id='example' >{ 1 + 1 }</node>
```